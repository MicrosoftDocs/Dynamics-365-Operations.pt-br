---
title: Fluxo de trabalho de despesas
description: Este tópico explica como você pode usar o sistema de fluxo de trabalho do Microsoft Dynamics 365 Finance para configurar um processo de revisão de relatórios de despesas no Gerenciamento de despesas.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52915860709e38013ec06204c52bb06de417eb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187581"
---
# <a name="expense-workflow"></a>Fluxo de trabalho de despesas

[!include [banner](../includes/banner.md)]

Você pode usar o sistema de fluxo de trabalho para configurar um processo de revisão de relatórios de despesas no Gerenciamento de despesas. É possível configurar um fluxo de trabalho que usa os seguintes critérios para determinar quem aprova os relatórios de despesas:

- A hierarquia de relatórios de funcionários e os limites de aprovação predefinidos
- Aprovação de vários níveis que suporta aprovadores provisórios e um aprovador final
- Dimensões financeiras e responsabilidade do projeto
- Atribuição a usuários ou grupos de usuários específicos

As aprovações do fluxo de trabalho podem ser criadas para relatórios de despesas, requisições de viagem, adiantamentos em dinheiro e recuperação do imposto sobre valor agregado (IVA).

**Exemplo**

O processo a seguir é um exemplo do fluxo de trabalho de gerenciamento de despesas para um relatório de despesas.

1. Um funcionário cria e salva um relatório de despesas.
2. O funcionário envia o relatório para aprovação. O aprovador é identificado com base nas regras definidas quando o fluxo de trabalho foi configurado.
3. O aprovador recebe uma notificação de que um relatório de despesas está pronto para aprovação. O aprovador examina o relatório de despesas e verifica se as seguintes condições são atendidas:

    - As despesas não violam nenhuma política de despesas. Se uma despesa violar uma política, o aprovador verificará se o relatório de despesas tem uma justificativa de negócios válida.
    - Recibos de equipamentos eletrônicos estão anexados ao relatório de despesas.

4. O aprovador aprova o relatório de despesas.
5. O relatório de despesas é atribuído ao coordenador de contas a pagar para lançamento.
6. Uma das seguintes etapas ocorre, se o lançamento automático for configurado.

    - Se o lançamento automático for configurado, o relatório de despesas será processado para pagamento e o status do relatório será atualizado.
    - Se o lançamento automático não for configurado, o coordenador de contas a pagar verificará se todos os recibos originais foram enviados e se eles correspondem às despesas contidas no relatório de despesas. Todos os códigos de imposto inseridos no relatório de despesas também devem ser confirmados como corretos.

Após a verificação desses requisitos, o relatório de despesas será lançado.

Após o lançamento do relatório de despesas, o pagamento do relatório é autorizado e o funcionário é reembolsado.
