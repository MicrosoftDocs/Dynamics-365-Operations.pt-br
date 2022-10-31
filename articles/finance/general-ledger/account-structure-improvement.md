---
title: Aprimoramento do desempenho da ativação da estrutura de conta
description: Este artigo explica o novo aprimoramento do desempenho para o processo de ativação da estrutura de conta.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713989"
---
# <a name="account-structure-activation-performance-enhancement"></a>Aprimoramento do desempenho da ativação da estrutura de conta

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Esse aprimoramento do desempenho permite que você ative estruturas de conta mais rapidamente executando várias atualizações de transações ao mesmo tempo. Além disso, a estrutura em si é marcada como ativa depois de ser validada, e o processamento da transação pode continuar enquanto as transações não lançadas existentes são atualizadas para a nova estrutura. Como as atualizações das transações podem levar algum tempo, você pode acompanhar o status da ativação selecionando **Exibir status da ativação** acima da grade na página **Estruturas de conta**. Você também pode exibir o status da ativação selecionando **Exibir** no Painel de Ações e depois **Status da ativação** no menu suspenso.

[![Página Estruturas de conta.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Depois que você selecionar **Exibir status da ativação**, será exibida uma caixa de diálogo mostrando as tarefas individuais que estão em execução como parte do processo de ativação. Para cada tarefa, você pode exibir o status e, depois que a tarefa for concluída, a data e a hora de conclusão.

[![Linha do tempo da ativação da estrutura de conta.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Dicas para a ativação da estrutura de conta

A caixa de diálogo da ativação da estrutura de conta que aparece quando você seleciona **Ativar** para uma estrutura de conta de rascunho tem uma seção de guia chamada **Atualizar transações não lançadas**. Essa seção inclui uma opção chamada **Forçar atualização**. Você pode selecionar essa opção para atualizar todas as transações não lançadas na estrutura atual. No entanto, você deverá usar essa opção somente quando ocorrer um erro ou receber instruções do suporte da Microsoft para usá-la.

Veja alguns dos fatores que podem afetar o desempenho do processo de ativação:

- Um grande número de registros de diário não lançados
- Um grande número de registros de documento de código aberto, como faturas de texto livre, faturas de fornecedor e documentos relacionados que usam a estrutura do documento de origem e têm distribuições contábeis abertas
- A quantidade de dados em TaxUncommitted
- A quantidade de dados de orçamentos abertos
- Importação de dados de diário enquanto as tarefas de ativação ainda estão em execução

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
