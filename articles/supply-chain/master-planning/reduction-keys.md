---
title: Chaves de redução
description: Estes artigos oferecem exemplos que mostram como configurar uma chave de redução. Eles incluem informações sobre as diversas configurações da chave de redução e os resultados de cada uma delas. Você pode usar uma chave de redução para definir como reduzir os requisitos de previsão.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7457aca4ca4d5188bafb497d3052276cfc154ad1
ms.sourcegitcommit: 704d273485dcdc25c97a222bc0ef0695aad334d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2019
ms.locfileid: "770907"
---
# <a name="reduction-keys"></a>Chaves de redução

[!include [banner](../includes/banner.md)]

Estes artigos oferecem exemplos que mostram como configurar uma chave de redução. Eles incluem informações sobre as diversas configurações da chave de redução e os resultados de cada uma delas. Você pode usar uma chave de redução para definir como reduzir os requisitos de previsão.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Exemplo 1: Porcentagem - princípio de redução de previsão da chave de redução
---------------------------------------------------------------

Este exemplo mostra como uma chave de redução reduz requisitos de previsão de demanda de acordo com as porcentagens e os períodos que são definidos pela chave de redução.

1. Na página **Chaves de redução**, configure as seguintes linhas.

   | Troco | Unidade  | Percentual |
   |--------|-------|---------|
   |   1    | Mês |   100   |
   |   2    | Mês |   75    |
   |   3    | Mês |   50    |
   |   4    | Mês |   25    |


2. Vincule a chave de redução ao grupo de cobertura do item.
3. Na página **Planos mestres**, no campo **Princípio de redução**, selecione **Percentual - chave de redução**.
4. Crie uma previsão de demanda de 1.000 peças por mês.

Se você executar o plano de previsão em 1º de janeiro, os requisitos de previsão de demanda serão consumidos de acordo com as porcentagens configuradas na página **Chaves de redução**. As quantidades da requisição a seguir são transferidas para o plano mestre.

| Mês                | Número de peças necessárias |
|----------------------|---------------------------|
| Janeiro              | 0                         |
| Fevereiro             | 250                       |
| Março                | 500                       |
| Abril                | 750                       |
| Maio até dezembro | 1.000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Exemplo 2: Transações - princípio de redução de previsão da chave de redução
Este exemplo mostra como as ordens reais que ocorrem durante os períodos definidos pela chave de redução reduzem requisitos de previsão de demanda.

-   Na página **Planos mestres**, no campo **Princípio de redução**, selecione **Transações - chave de redução**.

As ordens de venda a seguir existem em 1º de janeiro.

| Mês    | Número de peças pedidas |
|----------|--------------------------|
| Janeiro  | 956                      |
| Fevereiro | 1.176                    |
| Março    | 451                      |
| Abril    | 119                      |

Se você usar a mesma previsão de demanda de 1.000 peças por mês, as quantidades da requisição a seguir serão transferidas para o plano mestre.

| Mês                | Número de peças necessárias |
|----------------------|---------------------------|
| Janeiro              | 44                        |
| Fevereiro             | 0                         |
| Março                | 549                       |
| Abril                | 881                       |
| Maio até dezembro | 1.000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Exemplo 3: Transações - princípio de redução de previsão do período dinâmico
Na maioria dos casos, os sistemas são configurados de forma que as transações reduzam a previsão de demanda nos períodos de previsão específicos: semanas, meses, e assim por diante. Os períodos são definidos na chave de redução. No entanto, o tempo entre duas linhas de previsão de demanda também pode *implicar* em um período.

1. Crie uma previsão de demanda para as seguintes datas e quantidades.

   | Data       | Previsão de demanda |
   |------------|-----------------|
   | 1º de janeiro  | 1.000           |
   | 5 de janeiro  | 500             |
   | 12 de janeiro | 1.000           |

   Nesta previsão, não há um período desmarcado entre as datas da previsão: entre as primeiras e segundas datas há um período de quatro dias e, entre a segunda e terceira datas há um período de sete dias. Esses vários períodos são os períodos dinâmicos.
2. Crie linhas de ordem de venda como segue.

   | Data                             | Quantidade da ordem de venda |
   |----------------------------------|----------------------|
   | 15 de dezembro do ano anterior | 500                  |
   | 3 de janeiro                        | 100                  |
   | 10 de janeiro                       | 200                  |

A previsão será reduzida da seguinte maneira:

-   A primeira ordem de venda não está dentro de um período, dessa forma ela não reduzirá nenhuma previsão.
-   A segunda ordem de venda está entre 1º e 5 de janeiro, então isso reduzirá a previsão de 1º de janeiro por 100.
-   A terceira ordem de venda está entre o 5 e 12 de janeiro, então isso reduzirá a previsão de 5 de janeiro por 200.

A seguinte ordem planejada será criada para atender à previsão.

| Data da previsão de demanda | Quantidade reduzida |
|----------------------|------------------|
| 1º de janeiro            | 900              |
| 5 de janeiro            | 300              |
| 12 de janeiro           | 1.000            |

Aqui está um resumo de **Transações - redução de período** dinâmico:

-   Os requisitos de previsão são reduzidos por transações de ordens reais que ocorrem durante o período dinâmico. O período dinâmico cobre as datas de previsão atuais e termina no início da próxima previsão.
-   Este método não usa ou não requer uma chave de redução.
-   Quando esta opção é usada, o seguinte comportamento ocorre:
    -   Se a previsão for completamente reduzida, os requisitos da previsão atual se tornam 0 (zero).
    -   Se não houver previsão futura, os requisitos de previsão da última previsão que foi inserida serão reduzidos.
    -   Os limites de tempo são incluídos no cálculo de redução de previsão.
    -   Os dias positivos são incluídos no cálculo de redução de previsão.
    -   Se as transações de ordens reais excederam os requisitos de previsão, as outras transações não serão encaminhadas para o próximo período de previsão.


<a name="additional-resources"></a>Recursos adicionais
--------

[Planos mestres](master-plans.md)



