---
title: Extensibilidade da Otimização de Planejamento
description: Este artigo descreve os cenários de extensão na Otimização de Planejamento.
author: t-benebo
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d649110959e6bcfdaeb32dd53c55dbc446ed1be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857534"
---
# <a name="planning-optimization-extensibility"></a>Extensibilidade da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Este artigo descreve os cenários de extensão que estão relacionados a um planejamento mestre e permitidos na Otimização de Planejamento. Esses recursos estão disponíveis a partir da versão 10.0.13 do Microsoft Dynamics 365 Supply Chain Management.

## <a name="custom-processing-when-master-planning-is-completed"></a>Processamento personalizado quando o planejamento master é concluído

No cenário de extensão mais comum na Otimização de planejamento, o processamento personalizado é feito após a atualização do plano. Por exemplo, você pode adicionar uma coluna à tabela de pedidos planejados (`ReqPO`) ou derivar algumas informações estatísticas do plano gerado. O principal ponto de extensão que possibilita esses cenários é o método `jobCompletedSuccessfully` na classe `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Este é um exemplo de uma extensão que define um campo `CstmOrderPriority` personalizado na ordem planejada.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Ao adicionar uma lógica personalizada, considere as seguintes restrições e práticas recomendadas:

- O método `jobCompletedSuccessfully` é acionado fora do escopo de transação. Portanto, o plano já está visível para o usuário quando a lógica personalizada começa a ser executada. Se a personalização definir outros campos em pedidos planejados, é importante que você permita que os usuários saibam que os valores desses campos eventualmente estarão consistentes (em outras palavras, eles podem estar desatualizados imediatamente após um trabalho de planejamento ser concluído).
- Outro trabalho de planejamento master pode ser iniciado quando o método `jobCompletedSuccessfully` é chamado. O novo trabalho pode afetar o plano completo ou parte do plano. O novo trabalho pode atualizar ou excluir os mesmos pedidos planejados ou transações de requisitos que foram criadas ou atualizadas como parte do trabalho de planejamento que foi usado no `jobCompletedSuccessfully`. As exceções de conflito de atualização devem ser usadas quando este evento é estendido.
- Evite usar escopo de transação única ao estender esse método. Uma única execução do planejamento master pode produzir milhões de transações de necessidades e centenas de milhares de pedidos planejados. Se todas essas transações e pedidos planejados forem processados no escopo de uma única transação, vários bloqueios de SQL ocorrerão e bloquearão outros processos de planejamento. Além disso, se a transação for mantida por muito tempo, os "registros fantasmas" serão criados no banco de dados SQL. Os registros fantasmas afetarão de forma negativa todos os processos no sistema.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]