---
title: Avaliar o modelo de previsão de pagamento inicial do cliente (versão prévia)
description: Este tópico descreve as etapas que podem ser executadas para compreender o modelo de previsão de pagamento do cliente e avaliar sua eficácia.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f45392d540b6696d23261a6b2197c3185f5ede2b7c646f6b751480145dcacfdc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768858"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model-preview"></a>Avaliar o modelo de previsão de pagamento inicial do cliente (versão prévia)

[!include [banner](../includes/banner.md)]

Este tópico explica como avaliar um modelo de previsão depois de ter ativado o Finance Insights e gerado e treinado seu primeiro modelo. Este tópico aborda modelos para prever pagamentos de cliente. Ele descreve as etapas que podem ser executadas para compreender o modelo de previsão de pagamento do cliente e avaliar sua eficácia.

## <a name="getting-details-about-the-model"></a>Obter detalhes sobre o modelo

Na página **Parâmetros do Finance Insights** no Microsoft Dynamics 365 Finance, o link **Melhorar a precisão do modelo** aparece ao lado da pontuação de precisão.

[![Link Melhorar a precisão do modelo.](./media/prediction-model.png)](./media/prediction-model.png)

Este link leva você para o AI Builder, no qual você pode saber mais sobre o modelo atual e também executar etapas para aprimorá-lo. A ilustração a seguir mostra a página que é aberta.

[![AI Builder.](./media/what-to-predict.png)](./media/what-to-predict.png)

A página que é aberta mostra as seguintes informações:

- Na seção **Desempenho**, a taxa de desempenho do modelo fornece a perspectiva sobre a qualidade do modelo. Para obter mais informações sobre essa classificação, consulte [Desempenho do modelo de previsão](/ai-builder/prediction-performance) na documentação do AI Builder.
- A seção **Dados mais influentes** mostra como os diferentes tipos de dados de entrada são importantes para o seu modelo. É possível avaliar essa lista e as porcentagens correspondentes para determinar se as informações são consistentes com o que você sabe sobre a sua empresa e o mercado.

    [![Seções Desempenho e Dados mais influentes para o modelo de previsão.](./media/models.png)](./media/models.png)

- Na seção **Desempenho**, selecione **Ver detalhes** para saber mais sobre a classificação e outras considerações. Na ilustração a seguir, os detalhes mostram que o modelo usa menos informações do que o recomendado. Portanto, o sistema gerou uma mensagem de aviso.

    [![Avisos sobre o desempenho do modelo.](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Aprofundando-se

Embora a precisão seja um bom ponto de partida para avaliar um modelo, e a taxa de desempenho ofereça perspectiva, o AI Builder fornece métricas mais detalhadas que você pode usar para sua avaliação. Para baixar os detalhes, na seção **Desempenho**, selecione o botão de reticências (**...**) ao lado do botão **Usar modelo** e, em seguida, selecione **Baixar métricas detalhadas**.

[![Comando baixar métricas detalhadas.](./media/performance.png)](./media/performance.png)

A ilustração a seguir mostra o formato no qual você pode baixar os dados.

[![Formato dos dados baixados.](./media/data-format.png)](./media/data-format.png)

Para uma análise mais profunda dos resultados, um bom ponto de partida é revisar a métrica "Matriz de confusão". Por exemplo, estes são os dados mostrados para essa métrica na ilustração anterior.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Você pode expandir esses dados da maneira a seguir.

| &nbsp;                   | Previsto dentro do prazo | Previsto para atraso | Previsto para muito atraso |
|--------------------------|-------------------|----------------|---------------------|
| Pagamento dentro do prazo   | **71**            | 0              | 21                  |
| Pagamento atrasado real      | 5                 | **0**          | 27                  |
| Pagamento muito atrasado real | 2                 | 0              | **45**              |

A matriz de confusão mostra os resultados de um conjunto de teste aleatoriamente selecionado do processo de treinamento. Como essas faturas fechadas não foram usadas para treinar o modelo, elas são casos de teste bons para o modelo. Além disso, como o estado real da fatura é conhecido, o desempenho do modelo também pode ser visto.

A primeira coisa a ser procurada é o valor real mais comum. Embora esse valor não possa ser perfeitamente alinhado com o conjunto de uma geral, é uma aproximação razoável. Nesse caso, o **Pagamento real dentro do prazo** ocorre para 92 das 171 faturas totais é o valor real mais comum. Portanto, é uma boa linha de base para seu modelo. Se você acabou de chutar que todas as faturas estarão dentro do prazo, você estará corrigindo 92 de 171 vezes (ou seja, 54% do tempo).

É importante que você entenda quão balanceado o seu conjunto de informações está. Nesse caso, 92 de 171 faturas foram pagas dentro do prazo, 32 foram pagas atrasadas e 47 foram pagas muito atrasadas. Esses valores indicam um conjunto de dados razoavelmente balanceado, pois há resultados não triviais em cada classificação. Uma situação em que um dos estados tem poucos resultados pode ser desafiador para um modelo de aprendizado de máquina.

A precisão do modelo indica o número de previsões corretas para o conjunto de dados de teste. Essas previsões corretas são os valores que são mostrados em negrito no exemplo anterior. Nesse caso, os valores produzem uma precisão calculada de 67,8% (= \[71 + 0 + 45\] ÷ 171). Esse valor representa uma melhoria de 14% sobre a estimativa da linha de base de 54% e é um indicador da qualidade do modelo.

Se você olhar mais atentamente na matriz de confusão, perceberá que o modelo faz um bom trabalho de previsão de pagamentos de faturas dentro do prazo e muito atrasadas. No entanto, há algum problema sobre todas as 32 faturas que foram realmente pagas atrasadas (mas não muito atrasadas). Esse resultado sugere que são necessárias explorações e melhorias adicionais do modelo.

Um número que representa o desempenho do modelo melhor que a precisão é a pontuação da macro F1. Essa pontuação considera os resultados de cada estado de classificação (dentro do prazo, atrasado e muito atrasado). Por exemplo, estes são os dados mostrados para a métrica "F1 Macro" na ilustração anterior.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

Nesse caso, a pontuação de macro F1 de aproximadamente 49,3% indica que o modelo não oferece previsões eficazes em cada estado, apesar de uma pontuação de precisão geral que parece razoavelmente alta.

## <a name="improving-the-model"></a>Melhorando o modelo

Depois de compreender melhor os resultados do seu primeiro modelo, talvez você queira melhorar o modelo adicionando ou removendo colunas de recursos ou filtrando quaisquer partes do conjunto de informações que não dão suporte a previsões precisas. Feche o AI Builder e use o link **Melhorar modelo** no Dynamics 365 Finance para reiniciar o processo do AI Builder. Você pode testar características diferentes sem afetar o modelo publicado. O modelo publicado é afetado somente quando você seleciona **Publicar**. Lembre-se de que um único modelo é usado para sua instância do Dynamics 365 Finance. Portanto, você deve revisar cuidadosamente qualquer novo modelo antes de publicá-lo.

## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre como avaliar modelos de previsão, [Resultados de modelos de aprendizado de máquina](/confusion-matrix.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
