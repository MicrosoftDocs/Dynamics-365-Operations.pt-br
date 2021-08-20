---
title: Exibir e avaliar os resultados de questionários
description: Este artigo explica como você pode exibir e avaliar os resultados dos questionários que os participantes concluem.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e2241c2ade361631228cf721b18adabcb1fbc091c8949d47727bb89f0f67bdb6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755482"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>Exibir e avaliar os resultados de questionários

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo explica como você pode exibir e avaliar os resultados dos questionários que os participantes concluem. 

Depois que os entrevistados preencherem um questionário, você poderá exibir e avaliar os resultados do questionário das seguintes maneiras:

-   **Sessões de respostas concluídas** – Exiba detalhes sobre os questionários preenchidos pelos entrevistados e gere relatórios para resumir respostas e os pontos ganhos.
-   **Grupos de resultados** – Exiba detalhes e estatísticas do grupo de resultados de questionários. As estatísticas do grupo de resultados podem ser geradas para uma única sessão de respostas de um questionário ou para todas as sessões de respostas.
-   **Estatísticas do questionário** – Especifique os critérios para calcular estatísticas para um determinado grupo de entrevistados.

Você também pode gerar diversos relatórios para exibir os resultados classificados por pessoa, por sessão de resposta ou por grupo de resultados. Os seguintes relatórios referentes aos questionários preenchidos estão disponíveis:

-   Respostas
-   Respostas por questionário
-   Respostas por pessoa
-   Análise de comentários

## <a name="answer-session-results"></a>Resultados da sessão de respostas

Depois que os entrevistados preenchem o questionário, você pode exibir os resultados das sessões de respostas preenchidas. Uma sessão de resposta é a uma resposta do usuário a um questionário. Você pode exibir detalhes sobre as sessões de respostas preenchidas na página **Respostas**. As sessões de respostas incluídas na página **Respostas** serão filtradas de várias maneiras, dependendo de como você abrir a página:

-   Todos os questionários
-   Um questionário específico
-   Uma pessoa específica

Na página **Respostas**, você pode exibir detalhes sobre respostas, pontos ganhos, respostas de um participante em cada grupo de resultados e a hierarquia de perguntas usadas no questionário selecionado, se uma hierarquia de perguntas tiver sido utilizada. Você também pode gerar e imprimir os seguintes relatórios:

-   **Relatório de resultados** – Este relatório mostra uma representação gráfica dos pontos obtidos por grupo de resultados para a sessão de respostas selecionada.
-   **Relatório de respostas** – Este relatório mostra as respostas que o participante selecionou para cada pergunta do questionário.
-   **Respostas incorretas** – Este relatório mostra informações relativas às respostas incorretas que o entrevistado selecionou.

> [!NOTE]
> O relatório **Resultados** só estará disponível se você usar grupos de resultados do questionário e se tiver selecionado **Página de resultados** na página **Questionários**. O relatório de **Respostas** e o relatório de **Respostas incorretas** só estarão disponíveis se você selecionou **Relatório de respostas** na página **Questionários**.

## <a name="questionnaire-statistics"></a>Estatísticas do questionário

Você pode usar as estatísticas do questionário para analisar os resultados de um questionário preenchido, com base nos cálculos definidos por você. Para definir os cálculos, você deve concluir as seguintes tarefas:

-   Selecione critérios para calcular e exibir as estatísticas.
    -   Você pode exibir as estatísticas do questionário, pelas perguntas, pelas linhas de pergunta, ou os grupos de resultados.
    -   Selecione o tipo de gráfico que será usado ao exibir os resultados.
    -   Selecione os tipos de pessoas na rede como, por exemplo, funcionários, pessoas de contato, ou candidatos, para os quais você incluirá respostas. Você também pode incluir as respostas de questionários que foram preenchidos anônima.
    -   Configurar os intervalos com base na idade ou em tempo para analisar os resultados.
-   Selecione ou marque as configurações que refinam o assunto das estatísticas. Por exemplo, ao selecionar um CEP ou código postal, você pode analisar os resultados de todos os entrevistados dessa área geográfica específica.
-   Selecione ou marque os critérios para analisar os resultados por ou características do participante do questionário. Por exemplo, selecionando o **CEP/código postal**, você poderá analisar a correção entre o local de um respondente e respostas corretas.

As configurações que você define são salvas e podem ser usadas para recalcular resultados periodicamente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]