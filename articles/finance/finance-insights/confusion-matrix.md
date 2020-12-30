---
title: Resultados de modelos de aprendizado de máquina (versão prévia)
description: Este tópico discute as matrizes de confusão, os problemas de classificação e a acurácia nos modelos ML (aprendizado de máquina). O objetivo é aprimorar sua compreensão da acurácia em resultados de previsão de ML.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-14
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6a1620c33ee1e23a79ef5413afebdee332aa82b6
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645008"
---
# <a name="results-of-machine-learning-models-preview"></a>Resultados de modelos de aprendizado de máquina (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico discute as matrizes de confusão, os problemas de classificação e a acurácia nos modelos ML (aprendizado de máquina). O objetivo é aprimorar sua compreensão da acurácia em resultados de previsão de ML. O público-alvo inclui engenheiros, analistas e gerentes que desejam criar conhecimentos e habilidades em ciência de dados.

## <a name="confusion-matrix"></a>Matriz de confusão
Depois que um problema de ML é treinado em um conjunto de dados históricos, ele é testado usando dados que são retidos a partir do processo de treinamento. Dessa forma, você pode comparar as previsões do modelo treinado com os valores reais. A matriz de confusão fornece um meio de avaliar o êxito de um problema de classificação e onde ele comete erros (ou seja, onde ele se torna "confuso").

Por exemplo, seu objetivo é prever se um animal de estimação é um cachorro ou um gato, com base em alguns atributos físicos e comportamentais. Se você tiver um conjunto de dados de teste que contém 30 cachorros e 20 gatos, a matriz de confusão pode ser semelhante à ilustração a seguir.

[![Exemplo de previsão de espécies](./media/species-prediction-matrix.png)](./media/species-prediction-matrix.png)

Os números nas células verdes representam previsões corretas. Como você pode ver, o modelo previu corretamente uma porcentagem maior dos gatos reais. A acurácia geral do modelo é fácil de calcular. Nesse caso, é 42 ÷ 50 ou 0,84.

### <a name="multi-class-classifiers-in-a-confusion-matrix"></a>Classificadores de várias classes em uma matriz de confusão

A maioria das discussões sobre a matriz de confusão concentra-se em classificadores binários, como no exemplo anterior. Esse é um caso especial em que outras métricas podem ser consideradas, como sensibilidade e revocação.

Em seguida, consideraremos um problema de classificação para um cenário de finanças que tem três estados. O modelo prevê se uma nota fiscal de cliente será paga dentro do prazo, atrasada ou muito atrasada. Por exemplo, de 100 faturas teste, 50 são pagas dentro do prazo, 35 são pagas atrasadas e 15 são pagas muito atrasadas. Nesse caso, um modelo pode produzir uma matriz de confusão que se assemelha à ilustração a seguir.

[![Modelo 1](./media/payment-prediction-matrix.png)](payment-prediction-matrix.png) Modelo 1

Uma matriz de confusão fornece mais informações do que uma métrica de acurácia simples. No entanto, ela ainda é relativamente fácil entender. Uma matriz de confusão informa se você tem um conjunto de dados equilibrado no qual as classes de saída têm contagens semelhantes. Para o cenário de várias classes, ela informa o quanto uma previsão pode estar errada quando as classes de saída são ordinais, como no exemplo anterior sobre pagamentos de cliente.

## <a name="model-accuracy"></a>Acurácia do modelo 
Diferentes métricas de acurácia têm a vantagem de quantificar a qualidade do modelo. 

Como a acurácia é uma métrica fácil de compreender, é um bom ponto de partida para explicar um modelo a outras pessoas, especialmente para os usuários do modelo que não são cientistas de dados. Não é necessário compreender estatísticas para compreender a acurácia do modelo. Quando houver uma matriz de confusão disponível, ela fornecerá mais informações sobre o desempenho do modelo.

No entanto, para ter uma compreensão mais abrangente, vários desafios associados a acurácia devem ser observados. A utilidade da métrica depende do contexto do problema. Uma pergunta que geralmente surge em relação ao desempenho do modelo é "Qual é a eficácia do modelo?" No entanto, a resposta para essa pergunta não é exatamente simples. Considere a seguinte matriz de confusão (modelo 2).

[![Exemplo de previsão de pagamento com uma amostra maior](./media/payment-prediction-matrix-2.png)](payment-prediction-matrix-2.png)

Um cálculo rápido mostra que a acurácia deste modelo é (70 + 10 + 3) ÷ 100 ou 0,83. Na superfície, esse resultado parece ser melhor do que o resultado do modelo de várias classes anterior (modelo 1), que tem uma acurácia de 0,73. Mas é realmente melhor?

Para começar a discutir essa pergunta, considere a acurácia de uma suposição ingênua. Para um problema de classificação, uma estimativa simples sempre prevê a classe mais comum. Para o modelo 1, essa estimativa será "dentro do prazo" e produzirá uma acurácia de 0,50. A estimativa do modelo 2 também será "dentro do prazo" e produzirá uma acurácia de 0,80. Como o modelo 1 melhora a suposição ingênua de 0,73 - 0,50 = 0,23, enquanto que o modelo 2 melhora a suposição ingênua de 0,83 – 0,80 = 0,03, o modelo 1 é melhor, mesmo que tenha uma acurácia menor. O cálculo revela que a avaliação real da qualidade de um modelo requer mais contexto do que o valor de acurácia.

É importante observar outro aspecto. Considere um cenário no qual um teste médico é usado para detectar uma doença em uma paciente. Esse é um problema de classificação binária em que um resultado positivo indica que a paciente tem a doença. Neste cenário, você deve pensar no impacto dos seguintes erros:

- Falsos positivos, em que o teste diz que uma paciente tem a doença, mas ela não tem realmente
- Falsos negativos, em que o teste diz que uma paciente não tem a doença, mas ela tem

Obviamente, os dois tipos de erro são indesejados, mas qual é pior? Mais uma vez, depende. No caso de uma doença que ameaça a vida e exige tratamento rápido, a minimização de falsos negativos (seguidos de testes adicionais, espera-se) é algo prioritário. Em outras situações menos críticas, os criadores de modelo podem minimizar falsos positivos. De qualquer forma, uma conclusão razoável é que para determinar efetivamente a qualidade de um modelo, você deve ter mais informações do que as fornecidas por uma métrica de acurácia.

### <a name="recommendations"></a>Recomendações

A acurácia é uma ferramenta importante para a comunicação com especialistas em domínio que não estão familiarizados com as estatísticas. No entanto, para que as informações sejam úteis, é fundamental que o contexto adicional seja fornecido juntamente com o valor de acurácia.

Para o cenário de previsão de pagamento, você pode definir uma meta para o modelo ML que inclui fatores em diferentes comportamentos de pagamento. A meta é que o modelo deve melhorar em uma suposição ingênua reduzindo o número de respostas incorretas em pelo menos 50%. Em outras palavras, você quer uma acurácia alvo que divide o diferente entre a acurácia de uma suposição ingênua e 100%.

A tabela a seguir resume esse princípio para as matrizes de confusão neste tópico.

| Modelo   | Suposição ingênua | Alvo | Acurácia do modelo | A meta foi cumprida?                                          |
|---------|-------------|--------|----------------|-----------------------------------------------------------|
| Modelo 1 | 0,50        | 0,75   | 0,73           | Quase. Esse modelo melhora consideravelmente a estimativa. |
| Modelo 2 | 0,80        | 0,90   | 0,83           | Nº É necessário melhorar.                              |

## <a name="classification-f1-accuracy"></a>Acurácia f da classificação

A consideração final neste tópico é uma medida mais avançada da classificação de desempenho de ML, conhecida como acurácia f.

Para que a acurácia f possa ser definida, duas métricas adicionais devem ser introduzidas: precisão e revocação. A precisão indica o número total de previsões especificadas como positivas que são atribuídas corretamente. Essa métrica também é conhecida como valor de previsão positivo. Revocação é o número total de casos positivos reais que foram previstos corretamente. Essa métrica também é conhecida como sensibilidade.

[![Resultados verdadeiros vs. falsos.](./media/tn-fn.png)](./media/tn-fn.png)

Na matriz de confusão da ilustração anterior, essas métricas são calculadas da seguinte maneira:

- Precisão = VP ÷ (VP + FP)
- Revocação = VP ÷ (VP + FN)

A medida f combina precisão e revocação. O resultado é a média harmônica dos dois valores. Ele é calculado da seguinte maneira:

- F = 2 × (precisão × revocação) ÷ (precisão + revocação)

Vejamos um exemplo concreto. Anteriormente neste tópico, havia um exemplo de um modelo que previa se um animal era um cachorro ou um gato. A ilustração é repetida aqui.

[![Exemplo de previsão de espécies](./media/species-prediction-matrix.png)](./media/species-prediction-matrix.png)

Estes serão os resultados se "cachorro" for usado como a resposta positiva.

- Precisão = 24 ÷ (24 + 2) = 0,9231
- Revocação = 24 ÷ (24 + 6) = 0,8
- F = 2 × (0,9231 × 0,8) ÷ (0,9231 + 0,8) = 0,8572

Como você pode ver, o valor F encontra-se entre os valores de precisão e revocação.

Embora a acurácia f não seja tão fácil de entender, ela adiciona nuances ao número de acurácia básica. Ele também pode ajudar com conjuntos de dados não equilibrados, conforme mostra a seguinte discussão.

A seção [Acurácia do modelo](#classify-machine-learning-accuracy) deste tópico comparou as duas matrizes de confusão a seguir. Embora o primeiro modelo tenha a acurácia menor, ele foi considerado um modelo mais útil, pois mostrou mais melhorias do que a estimativa padrão de um pagamento dentro do prazo.

[![Exemplo de previsão de pagamento versus dados reais](./media/payment-prediction-matrix.png)](payment-prediction-matrix.png)

[![Exemplo de previsão de pagamento com uma amostra maior](./media/payment-prediction-matrix-2.png)](payment-prediction-matrix-2.png)

Vamos ver como esses dois modelos se comparam quando a medida f é usada. A medida f considera a precisão e revocação de cada estado, e então o cálculo de macro f calcula a média da medida f em todos os estados para determinar uma medida f geral. Há outras variantes f, mas o mais interessante é considerar a versão do macro, dada a mesma consideração que é dada a todos os três estados.

Para simplificar os cálculos, os conjuntos de amostras foram criados para coincidir com os valores reais e previstos. Essas matrizes usaram a biblioteca de métricas do sklearn no Python para calcular os valores. Este é o resultado.

| Modelo   | Estimativa ingênua | Acurácia | Macro f |
|---------|-------------|----------|----------|
| Modelo 1 | 0,5         | 0,73     | 0,67     |
| Modelo 2 | 0,80        | 0,83     | 0,66     |

Para obter mais detalhes sobre como esse cálculo funciona, aqui está o relatório de classificação sklearn. para o modelo 1. Os três estados, "Dentro do prazo", "Atrasado" e "Muito atrasado", são representados pelas linhas rotuladas 1, 2 e 3, respectivamente. A média da macro é apenas a média da coluna "medida f".

|           | precisão | revocação   | medida f |
|-----------|-----------|----------|----------|
| **1**     | 0,83      | 0,80     | 0,82     |
| **2**     | 0,68      | 0,71     | 0,69     |
| **3**     | 0,50      | 0,50     | 0,50     |

Conforme mostram os resultados, os dois modelos têm uma pontuação de acurácia de macro f quase idêntica. Neste e em muitos outros casos, a acurácia f fornece um indicador melhor do recurso de um modelo. Quanto à acurácia, a interpretação dos resultados requer que você compreenda o que é mais importante considerar no modelo.

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
