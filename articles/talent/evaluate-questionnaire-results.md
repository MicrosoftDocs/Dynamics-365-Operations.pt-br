---
title: "Exibir e avaliar os resultados de um questionário"
description: "Este tópico explica como você pode exibir e avaliar os resultados dos questionários que os entrevistados concluem."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 68dde5f6d67b48dad753e9f4c4123fb9e9e6b53a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a>Exibir e avaliar os resultados de um questionário

Este tópico explica como você pode exibir e avaliar os resultados dos questionários que os entrevistados concluem. 

Depois que os entrevistados preencherem um questionário, você poderá exibir e avaliar os resultados do questionário das seguintes maneiras:

-   **Sessões de respostas concluídas** – Exiba detalhes sobre os questionários preenchidos pelos participantes e gere relatórios para resumir as respostas, e também quaisquer que sejam os pontos ganhos.
-   **Grupos de resultados** – Exiba detalhes e estatísticas do grupo de resultados de questionários. As estatísticas do grupo de resultados podem ser geradas para uma única sessão de respostas de um questionário ou para todas as sessões de respostas.
-   **Estatísticas do questionário** – Especifique os critérios para calcular estatísticas para um determinado grupo de entrevistados.

Você também pode gerar diversos relatórios para exibir os resultados classificados por pessoa, por sessão de resposta ou por grupo de resultados. Os seguintes relatórios referentes aos questionários preenchidos estão disponíveis:

-   Respostas
-   Respostas por questionário
-   Respostas por pessoa
-   Análise de comentários

## <a name="answer-session-results"></a>Resultados da sessão de respostas
Depois que os entrevistados preenchem o questionário, você pode exibir os resultados das sessões de respostas preenchidas. Uma sessão de resposta é a uma resposta do usuário a um questionário. Você pode exibir detalhes sobre as sessões de respostas preenchidas na página **Respostas**. As sessões de respostas que estão inclusas na página **Respostas** serão filtradas de várias maneiras, dependendo de como você abrir a página:

-   Todos os questionários
-   Um questionário específico
-   Uma pessoa específica

Na página **Respostas**, você pode exibir detalhes sobre respostas, pontos ganhos, respostas de um participante em cada grupo de resultados e a hierarquia de perguntas usadas no questionário selecionado, se uma hierarquia de perguntas tiver sido utilizada. Você também pode gerar e imprimir os seguintes relatórios:

-   **Relatório de resultados** – Este relatório mostra uma representação gráfica dos pontos obtidos por grupo de resultados para a sessão de respostas selecionada.
-   **Relatório de respostas** – Este relatório mostra as respostas que o participante selecionou para cada pergunta do questionário.
-   **Respostas incorretas** – Este relatório mostra informações relacionadas às respostas incorretas que o participante selecionou.

**Observação:** O relatório de **Resultados** está disponível somente se você usar grupos de resultados do questionário, e se você selecionou **Página de resultados** na página **Questionários**. O relatório de **Respostas** e o relatório de **Respostas incorretas** só estarão disponíveis se você selecionou **Relatório de respostas** na página **Questionários**.

## <a name="questionnaire-statistics"></a>Estatísticas do questionário
Você pode usar as estatísticas do questionário para analisar os resultados de um questionário preenchido, com base nos cálculos definidos por você. Para definir os cálculos, você deve concluir as seguintes tarefas:

-   Selecione critérios para calcular e exibir as estatísticas.
    -   Você pode exibir as estatísticas do questionário, pelas perguntas, pelas linhas de pergunta, ou os grupos de resultados.
    -   Selecione o tipo de gráfico que será usado ao exibir os resultados.
    -   Selecione os tipos de pessoas na rede como, por exemplo, funcionários, pessoas de contato, ou candidatos, para os quais você incluirá respostas. Você também pode incluir as respostas de questionários que foram preenchidos anônima.
    -   Configurar os intervalos com base na idade ou em tempo para analisar os resultados.
-   Selecione ou marque as configurações que refinam o assunto das estatísticas. Por exemplo, ao selecionar um CEP ou código postal, você poderá analisar os resultados de todos os pesquisados dessa área geográfica específica.
-   Selecione ou marque os critérios para analisar os resultados por ou características do participante do questionário. Por exemplo, selecionando o **CEP/código postal**, você poderá analisar a correção entre o local de um respondente e respostas corretas.

As configurações que você define são salvas e podem ser usadas para recalcular resultados periodicamente.

<a name="see-also"></a>Consulte também
--------

[Projetar questionários](design-questionnaires.md)

[Usando questionários](questionnaires.md)

[Distribuindo e preenchendo questionários](distribute-questionnaires.md)


