---
title: "Convenções de depreciação de ativos fixos"
description: "Este tópico oferece uma visão geral das convenções de depreciação de ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 03/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c69fd798c2e978935a63b079fb11c68d8555594c
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="fixed-asset-depreciation-conventions"></a>Convenções de depreciação de ativos fixos

[!INCLUDE [banner](../includes/banner.md)]

As convenções de depreciação são usadas para determinar quando e como a depreciação é calculada para o ano em que o ativo é adquirido e o ano em que o ativo fixo é descartado.

As convenções de depreciação podem ser atribuídas à configuração de um registro de grupo de ativos fixos. Nesse caso, as convenções de depreciação atribuídas são usadas como valores padrão quando os registros de ativos fixos são criados. As convenções de depreciação também podem ser definidas em registro de ativo fixo individual.


|  Convenção de depreciação  |                                                                                                                                                                                                                                                                                                                                                                                                     descrição                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nenhum(a)            |                                                                                                                                                                                                                                                                                                                                                                     Os ativos começam a ser depreciados na data <strong>Colocado em serviço</strong>.                                                                                                                                                                                                                                                                                                                                                                      |
|         Semestre         |                                                                                                                                                                                                                                                                                                     Você deduz meio ano de depreciação para o primeiro ano e o último ano em que você deprecia a propriedade. Você deduz um ano inteiro de depreciação para cada outro ano durante o período de recuperação.                                                                                                                                                                                                                                                                                                      |
|        Mês inteiro         |                                                                                                                                                                                                                                                        Os ativos com uma data <strong>Colocado em serviço</strong> que ocorra a qualquer momento durante o mês começam a ser depreciados no primeiro dia daquele mês. Os ativos desativados a qualquer momento durante o mês são considerados desativados para fins de depreciação no último dia do mês anterior.                                                                                                                                                                                                                                                         |
|        Meio do trimestre        |                                                                                                           Para calcular a dedução de depreciação para o ano em que você coloca a propriedade em serviço, multiplique a depreciação de um ano inteiro pelo percentual para o trimestre quando a propriedade é colocada em serviço, como mostra a tabela a seguir.<table><thead><tr><th>Trimestre</th><th>Porcentagem</th></tr></thead><tbody><tr><td>Primeira</td><td>87,5</td></tr><tr><td>Segunda</td><td>62,5</td></tr><tr><td>Terceira</td><td>37,5</td></tr><tr><td>Quarto</td><td>12,5</td></tr></tbody></table>Um trimestre de depreciação é retirado no trimestre de descarte (ou no trimestre da depreciação total).                                                                                                            |
| Meio do mês (Primeiro Dia do Mês)  | Os ativos com a data <strong>Colocado em serviço</strong> na primeira metade do mês (do primeiro ao décimo-quinto dia) começam a ser depreciados no primeiro dia do mês da data <strong>Colocado em serviço</strong>. Os ativos com a data <strong>Colocado em serviço</strong> na segunda metade do mês (do décimo-sexto dia até o final do mês) começam a ser depreciados no primeiro dia do mês após a data <strong>Colocado em serviço</strong>. Os ativos desativados na primeira metade do mês (do primeiro ao décimo-quinto dia) são considerados desativados para fins de depreciação no último dia do mês anterior. Os ativos desativados na segunda metade do mês (do décimo-sexto dia até o final do mês) são considerados desativados para fins de depreciação no último dia do mês da desativação. |
| Meio do mês (Décimo quinto dia do Mês) |                                                                                                                                                        Para calcular a dedução de depreciação para o ano quando você coloca a propriedade em serviço, multiplique a depreciação de um ano inteiro por uma fração. O numerador (número superior) dessa fração é o número de meses completos no ano em que a propriedade esteve em serviço, mais 1/2 ou (0,5). O denominador (número inferior) é 12. Se você descartar a propriedade antes do final do período de recuperação, use o mesmo método para calcular a dedução de depreciação para o ano de descarte.                                                                                                                                                        |
| Semestre (início do ano) |                                                                                                                                                                                                                                                          Os ativos com uma data <strong>Colocado em serviço</strong> na primeira metade do ano começam a ser depreciados no primeiro dia do ano (ano inteiro). Os ativos com uma data <strong>Colocado em serviço</strong> na segunda metade do ano começam a ser depreciados na metade do ano.                                                                                                                                                                                                                                                          |
|   Semestre (próximo ano)   |                                                            Os ativos com uma data <strong>Colocado em serviço</strong> na primeira metade do ano começam a ser depreciados no primeiro dia do ano (ano inteiro). Os ativos com uma data <strong>Colocado em serviço</strong> na segunda metade do ano começam a ser depreciados no primeiro dia do próximo ano. Os ativos desativados na primeira metade do ano são considerados desativados para fins de depreciação no último dia do ano anterior. Qualquer depreciação lançada no ano atual deve ser revertida ou ajustada. Os ativos desativados na segunda metade do ano são considerados desativados para fins de depreciação no último dia do ano de desativação.                                                            |


