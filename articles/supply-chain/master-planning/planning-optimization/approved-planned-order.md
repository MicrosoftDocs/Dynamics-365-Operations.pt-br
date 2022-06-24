---
title: Exibir, gerenciar e aprovar ordens planejadas
description: Este artigo fornece informações sobre como exibir, gerenciar e aprovar ordens planejadas na Otimização de Planejamento.
author: t-benebo
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 22c690222cdb72e2113ea137a05da21f315e5a33
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887418"
---
# <a name="view-manage-and-approve-planned-orders"></a>Exibir, gerenciar e aprovar ordens planejadas

[!include [banner](../../includes/banner.md)]

Este artigo fornece informações sobre como exibir, gerenciar e aprovar ordens planejadas na Otimização de Planejamento.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Exibir e gerenciar ordens planejadas

Você pode exibir e gerenciar ordens planejadas em qualquer página de lista de ordens planejadas. Acesse um dos seguintes locais, dependendo do tipo de ordens planejadas com as quais você deseja trabalhar:

- Planejamento mestre \> Espaços de trabalho \> Planejamento mestre
- Planejamento mestre \> Planejamento mestre \> Ordens planejadas
- Controle de produção \> Ordens de produção \> Ordens de produção planejadas
- Compras e fornecimento \> Ordens de compra \> Ordens de compra planejadas
- Gerenciamento de estoque \> Ordens de entrada \> Transferências planejadas
- Gerenciamento de estoque \> Ordens de saída \> Transferências planejadas

## <a name="view-and-edit-the-status-of-planned-orders"></a>Exiba e edite o status das ordens planejadas

Você pode usar o campo **Status** de cada ordem planejada para ajudar a rastrear seu progresso ou alterar a forma como uma ordem planejada será processada. Os seguintes valores de **Status** estão disponíveis:

- **Não processado** – Quando o planejamento mestre gera ordens planejadas, elas recebem este status. As ordens planejadas com esse status serão excluídas durante a próxima execução de planejamento.
- **Concluído** – este status indica que a ordem planejada foi concluída. Se você optar por não confirmar uma ordem planejada, poderá atribuir manualmente seu status para *Concluído*. Observe que o sistema trata os status *Não processado* e *Concluído* da mesma forma.
- **Aprovado** – este status indica que a ordem planejada foi aprovada para confirmação. Se você desejar confirmar uma ordem planejada, poderá alterar seu status para *Aprovado*. Se desejar manter as edições que foram feitas em uma ordem planejada ou se estiver planejando confirmar uma ordem planejada, altere seu status para *Aprovado*. As ordens planejadas com o status *Aprovado* são consideradas de fornecimento fixo e esperado pelo planejamento mestre. Portanto, elas não serão modificadas ou excluídas durante a execução do planejamento mestre posterior. Para atingir este procedimento, a lógica de planejamento copia as ordens planejadas com status *Aprovado* da versão anterior do plano para a nova versão do plano durante o planejamento mestre. Observe que as ordens planejadas com o status *Aprovado* só são consideradas fornecimento no plano mestre específico.

Para alterar o status de uma ordem planejada única, [abra qualquer página de lista de ordens planejadas](#view-planned-orders)abra a ordem e siga uma destas etapas:

- Na FastTab **Geral**, altere o valor do campo **Status**.
- No Painel de Ações, na guia **Ordem de alteração**, no grupo **Processo**, selecione **Alterar status**.
- No Painel de Ações, selecione **Aprovar** para marcar a ordem como aprovada.

Para alterar o status de várias ordens planejadas ao mesmo tempo, [abra qualquer página de lista de ordens planejadas](#view-planned-orders), marque a caixa de seleção para cada ordem que deseja alterar e siga uma destas etapas:

- No Painel de Ações, na guia **Ordem de alteração**, no grupo **Processo**, selecione **Alterar status**.
- No Painel de Ações, selecione **Aprovar** para marcar as ordens como aprovadas.

## <a name="approve-planned-orders"></a>Aprovar ordens planejadas

A aprovação de ordens planejadas é uma etapa opcional no processo de criação de uma ordem confirmada com base em uma ordem planejada.

A ilustração a seguir mostra como você pode usar o valor **Status** que é atribuído a cada ordem planejada para implementar um fluxo de trabalho de aprovação. Para implementar um processo de aprovação, ajuste manualmente o valor do **Status** de cada ordem planejada, conforme descrito na seção anterior.

![Fluxo de ordem planejada.](media/approved-planned-orders-1.png)

> [!TIP]
> Recomendamos que você aprove quaisquer ordens planejadas modificadas. Caso contrário, as edições serão ignoradas e sobrescritas pela próxima execução de planejamento.

## <a name="additional-resources"></a>Recursos adicionais

- [Confirmar ordens planejadas](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
