--- 
title: "Analisar resultados de questionário"
description: "As estatísticas do questionário podem ser usadas para calcular média, totais e porcentagens, com base em um conjunto de dados demográficos."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7d0bece11b4f78d2e7abc701b8b5b9aa0d76a6a6
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="analyze-questionnaire-results"></a>Analisar resultados de questionário

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

As estatísticas do questionário podem ser usadas para calcular média, totais e porcentagens, com base em um conjunto de dados demográficos. Para iniciar este procedimento, vá para Questionário > Exibir e analisar resultados > Estatísticas de questionário. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Criar um registro de estatísticas de questionário
1. Vá para Estatísticas do questionário.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Estatísticas, digite um valor.
5. No campo Descrição, digite um valor.
6. No campo Questionário, clique no botão suspenso para abrir a pesquisa.
7. Na lista, clique no link na linha selecionada.
8. Clique na guia Geral.
    * Selecione se deseja incluir resultados anônimos ou resultados de trabalhadores, contatos e candidatos.  
9. Marque ou desmarque a caixa de seleção Trabalhador.
    * Se você deseja exibir os resultados por tempo de serviço ou por idade, especifique os intervalos que você gostaria de usar para agrupar os resultados.  
    * Inserindo um 5 para o intervalo de idade o agrupará com base nos resultados em intervalos de cinco anos de idade.  
10. No campo Idade, insira um número.
    * Selecione se você deseja executar o cálculo inteiro, em relação ao questionário para cada grupo de resultados, para cada pergunta ou para cada linha de pergunta.  
    * Selecione como gostaria de agrupas os resultados.  
    * Por exemplo, se você calcular os pontos médios por pergunta, você pode desejar ver as perguntas agrupadas por grupo de resultados.  
    * Selecione os dados no qual basear o cálculo.  
    * Por exemplo, se você desejar ver a porcentagem média recebida no questionário por meio dos funcionários em relação ao número médio de pontos obtido por meio dos funcionários.  
11. Clique na guia Variação.
    * Use intervalos para limitar o conjunto de resultados somente se essas atendem aos critérios do intervalo.  
12. Clique no Agrupamento por guia.
    * Use grupos para determinar como os resultados serão exibidos.  
    * Por exemplo, agrupar os resultados primeiro por gênero, então por idade.  
13. Na lista, localize e selecione o PDV desejado.
    * Mova os agrupamentos no lado Selecionado e posicione-os na ordem desejada.  

## <a name="execute-the-statistics-calculation"></a>Executa o cálculo das estatísticas
1. Clique em Executar.
    * Selecione a função de cálculo que você gostaria de executar nos resultados.  
    * Por exemplo, calcule as porcentagens médio por meio do questionário para os agrupamentos selecionados ou o total de pontos por meio de grupos de resultados dos agrupamentos selecionados.  
2. Selecione ou limpe as caixas de seleção Excluir buscas anteriores.
3. Clique em OK.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Exiba os resultados da execução de estatísticas do questionário.
1. Clique em Resultado.
2. Clique em Resultado.
3. Feche a página.


