---
title: Confirmação automática com a Otimização de Planejamento
description: Este tópico explica como usar a confirmação automática com a Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 61e9e6aa660bc0828645c6bf1f2655539804831a
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594517"
---
# <a name="autofirming-with-planning-optimization"></a>Confirmação automática com a Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

A confirmação automática permite que você confirme (ou seja, libere) as ordens planejadas como parte do processo de planejamento mestre. Quando as ordens planejadas forem confirmadas, serão transformadas em ordens de compra, ordens de transferência ou ordens de produção reais. Quando a Otimização de Planejamento for usada, as ordens planejadas serão confirmadas durante a execução de um planejamento mestre quando a data da ordem (ou seja, a data inicial) estiver dentro do limite de tempo para a confirmação.

> [!NOTE]
> A confirmação automática de uma ordem de compra planejada só poderá ocorrer se o item estiver associado a um fornecedor.

## <a name="turn-on-autofirming"></a>Ativar a confirmação automática

Para ativar a confirmação automática, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione **Confirmação automática para Otimização de Planejamento** na lista. Se o recurso não aparecer na guia **Novo** , examine as guias **Não habilitado** e **Tudo**.
1. Selecione **Habilitar agora**. Como alternativa, selecione **Agenda** e selecione a hora em que você deseja que o recurso seja ativado.

## <a name="set-up-the-firming-time-fence"></a>Configure o limite de tempo de confirmação

O limite de tempo de confirmação é calculado a partir da data de execução do planejamento mestre. Ele é definido pelo número de dias inserido. Você pode controlar o limite de tempo de confirmação das seguintes maneiras:

- Para definir o limite de tempo de confirmação padrão para um grupo de cobertura, vá para **Planejamento mestre** \> **Configuração** \> **Cobertura** \> **Grupos de cobertura** e selecione um grupo de cobertura. Em seguida, na Guia Rápida **Outro**, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.
- Para substituir o limite de tempo de confirmação definido para o grupo de cobertura para um item específico, vá para **Gerenciamento de informações do produto** \> **Produtos liberados** e, no Painel de Ações, selecione **Plano** e **Cobertura de item**. Em seguida, na guia **Geral**, selecione **Limite de tempo de substituição** e, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.
- Para substituir o limite de tempo de confirmação definido para o grupo de cobertura e a cobertura de item para um plano mestre específico, acesse **Planejamento mestre** \> **Configuração** \> **Planos mestres** e selecione um Plano mestre. Em seguida, na FastTab **Limite de tempo em dias**, defina **Confirmação** como **Sim** e insira o número de dias.

Se a confirmação automática estiver ativada para uma execução de planejamento mestre que use a Otimização de Planejamento, o processo de confirmação automática será concluído de acordo com sua configuração. Se a confirmação automática não estiver ativada ou se o planejamento tiver sido iniciado na página **Requisitos líquidos**, o processo de confirmação automática será ignorado.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Otimização de Planejamento versus o mecanismo de planejamento interno do Supply Chain Management

A Otimização de Planejamento e o mecanismo de planejamento interno do Microsoft Dynamics 365 Supply Chain Management podem ser usados para confirmar ordens planejadas de forma automática. No entanto, há alguns diferenças importantes. Por exemplo, embora a Otimização de Planejamento use a data da ordem (ou seja, a data inicial) para determinar quais ordens planejadas deverá confirmar, o mecanismo de planejamento interno do Supply Chain Management usa a data de requisição (ou seja, a data de conclusão). Aqui está um resumo das diferenças.

**Otimização do Planejamento**

- A confirmação automática se baseia na data da ordem (data de início).
- Como a data da ordem (data inicial) dispara a confirmação, você não precisa considerar o prazo de entrega como parte do limite de tempo de confirmação.
- Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser de uma semana.

**Mecanismo de planejamento interno do Supply Chain Management**

- A confirmação automática se baseia na data de requisição (data de término).
- Para ajudar a garantir que as ordens sejam confirmadas no prazo, o tempo limite de confirmação deverá ser superior ao prazo de entrega.
- Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser o prazo de entrega mais uma semana.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]