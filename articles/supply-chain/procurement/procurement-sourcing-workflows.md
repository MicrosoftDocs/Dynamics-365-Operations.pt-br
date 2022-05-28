---
title: Fluxos de trabalho de Compras
description: Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.
author: GalynaFedorova
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ebfd96690eea762d0797db1b485544d957d17ce0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671916"
---
# <a name="procurement-and-sourcing-workflows"></a>Fluxos de trabalho de compras

[!include [banner](../includes/banner.md)]

Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento. O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:

- **Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas. O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.
- **Visibilidade do processo** — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.
- **Lista de trabalho centralizada** — os usuários podem exibir uma lista de trabalho centralizada para exibir as tarefas do fluxo de trabalho e as aprovações atribuídas a eles em todos os fluxos de trabalho de que participam. Isso está disponível na página Itens de trabalho.

## <a name="the-types-of-workflows-that-you-can-create"></a>Os tipos de fluxo de trabalho que você pode criar

Os tipos de fluxo de trabalho a seguir estão disponíveis para Compras.

| Tipo | Use este tipo para |
|---|---|
| Revisão da requisição de compra | Criar fluxos de trabalho de aprovação e revisão para requisições de compra. |
| Revisão de linha de requisição de compra | Criar fluxos de trabalho de revisão e aprovação para linhas de requisição de compra. |
| Fluxo de trabalho da ordem de compra | Criar fluxos de trabalho de revisão e aprovação para ordens de compra. |
| Fluxo de trabalho da linha da ordem de compra | Criar fluxos de trabalho de revisão e aprovação para linhas de ordens de compra. |
| Fluxo de trabalho da solicitação de emprego adicionada pelo fornecedor | Criar fluxos de trabalho da revisão e de aprovação para adicionar novos fornecedores por meio de solicitações de fornecedor. |

> [!IMPORTANT]
> Ao adicionar um novo fluxo de trabalho, talvez você também veja os seguintes fluxos de trabalho obsoletos listados na caixa de diálogo **Criar fluxo de trabalho**. Eles estão relacionados à funcionalidade *confirmação de recebimento* que estava disponível no [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), mas que agora foi preterida. Não há suporte para esses fluxos de trabalho no momento.
> 
> - Fluxo de trabalho da notificação de data de vencimento da entrega
> - Fatura recebeu fluxo de trabalho da notificação
> - Falha de recebimento de produtos no fluxo de trabalho de notificação
> - Fluxo de trabalho da notificação de rejeição do recebimento de produtos não confirmados

## <a name="creating-a-workflow"></a>Criação de um fluxo de trabalho

Para criar um fluxo de trabalho, Acesse Compras &gt; Configuração &gt; Fluxos de trabalho de compras e crie um novo fluxo de trabalho ao selecionar o tipo de fluxo de trabalho que deseja criar. 

Na tela do fluxo de trabalho, você pode arrastar elementos de fluxo de trabalho para o designer e vincular os elementos a um fluxo. Os elementos de fluxo de trabalho devem ser configurados. Para os elementos do fluxo de trabalho de aprovação e de tarefa, você pode configurar qual participante deverá executar a ação.

## <a name="types-of-participants"></a>Tipos de participantes

Você pode atribuir uma etapa de aprovação aos grupos de participantes a seguir.

| Grupo de usuários | Descrição |
|---|---|
| Participante | Atribuir a etapa de aprovação aos membros de um grupo ou de uma função. |
| Hierarquia | Atribuir a etapa de aprovação aos usuários em uma hierarquia organizacional específica. |
| Usuário de fluxo de trabalho | Atribuir a etapa de aprovação aos usuários desse fluxo de trabalho. |
| Fila | Atribua a etapa de aprovação em uma fila de itens de trabalho. |
| Usuário | Atribua a etapa de aprovação a usuários específicos. |

## <a name="additional-resources"></a>Recursos adicionais

- [Definir fluxos de trabalho de processos de negócios para requisições de compra](https://www.microsoft.com/download/details.aspx?id=101821)
- [Fluxo de trabalho de requisição de compra](purchase-requisitions-workflow.md)
- [Integração de fornecedores](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]