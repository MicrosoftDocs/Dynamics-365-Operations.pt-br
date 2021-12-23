---
title: Convenções de depreciação de ativos fixos
description: Este tópico descreve as convenções de depreciação de ativos fixos.
author: moaamer
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 823f8826e297a01c3658ceb8e82e6f9902d7a359
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883403"
---
# <a name="fixed-asset-depreciation-conventions"></a>Convenções de depreciação de ativos fixos

[!include [banner](../includes/banner.md)]

Este tópico descreve as convenções de depreciação de ativos fixos. As convenções de depreciação são usadas para determinar quando e como a depreciação é calculada para o ano em que o ativo é adquirido e o ano em que o ativo fixo é descartado.

As convenções de depreciação podem ser atribuídas à configuração de um registro de grupo de ativos fixos. Para exibir ou atribuir a convenção de depreciação, na área de instalação de ativos fixos, selecione os grupos de **Ativos fixos**. Selecione o botão **Registros**. Nesse caso, as convenções de depreciação atribuídas são usadas como valores padrão quando os registros de ativos fixos são criados. As convenções de depreciação também podem ser definidas em registro de ativo fixo individual. Para fazer isso, selecione **Registros** na área de instalação de ativos fixos e selecione o botão **Grupos de ativos fixos**.

| Convenção de depreciação   | Descrição |
|---------------------------|-------------|
| Nenhuma                      | Os ativos começam a ser depreciados na data <strong>Colocado em serviço</strong>. |
| Semestre                 | Meio ano de depreciação é deduzido para o primeiro ano e o último ano em que você deprecia a propriedade. Um ano inteiro de depreciação é deduzido para cada outro ano durante o período de recuperação. |
| Mês inteiro                | Os ativos com uma data <strong>Colocado em serviço</strong> que ocorra a qualquer momento durante o mês começam a ser depreciados no primeiro dia daquele mês. Para fins de depreciação, os ativos são considerados desativados no último dia do mês anterior. O dia específico do mês em que eles foram desativados não é considerado. |
| Meio do trimestre               | Para calcular a dedução de depreciação para o ano em que você coloca a propriedade em serviço, multiplique a depreciação de um ano inteiro pelo percentual para o trimestre quando a propriedade é colocada em serviço, como mostra a tabela a seguir.<table><thead><tr><th>Trimestre</th><th>Percentual</th></tr></thead><tbody><tr><td>Primeira</td><td>87,5</td></tr><tr><td>Segunda</td><td>62,5</td></tr><tr><td>Terceira</td><td>37,5</td></tr><tr><td>Quarto</td><td>12.5</td></tr></tbody></table>Um trimestre de depreciação é desativado no trimestre quando o ativo foi descartado (ou no trimestre em que foi totalmente depreciado). |
| Meio do mês (Primeiro Dia do Mês)  | Os ativos com a data <strong>Colocado em serviço</strong> na primeira metade do mês (do primeiro ao décimo-quinto dia) começam a ser depreciados no primeiro dia do mês da data <strong>Colocado em serviço</strong>. Os ativos com a data <strong>Colocado em serviço</strong> na segunda metade do mês (do décimo-sexto dia até o final do mês) começam a ser depreciados no primeiro dia do mês após a data <strong>Colocado em serviço</strong>. Os ativos desativados na primeira metade do mês (do primeiro ao décimo-quinto dia) são considerados desativados no último dia do mês anterior para fins de depreciação. Os ativos desativados na segunda metade do mês (do décimo-sexto dia até o final do mês) são considerados desativados no último dia do mês da desativação para fins de depreciação. |
| Meio do mês (Décimo quinto dia do Mês) | Para calcular a dedução de depreciação para o ano quando você coloca a propriedade em serviço, multiplique a depreciação de um ano inteiro por uma fração. O numerador (número superior) dessa fração é o número de meses completos no ano em que a propriedade esteve em serviço, mais 1/2 ou (0,5). O denominador (número inferior) é 12. Se você descartar a propriedade antes do final do período de recuperação, use o mesmo método para calcular a dedução de depreciação para o ano de descarte. |
| Semestre (início do ano) | Os ativos com uma data <strong>Colocado em serviço</strong> na primeira metade do ano começam a ser depreciados no primeiro dia do ano (ano inteiro). Os ativos com uma data <strong>Colocado em serviço</strong> na segunda metade do ano começam a ser depreciados na metade do ano. |
| Semestre (próximo ano)     | Os ativos com uma data <strong>Colocado em serviço</strong> na primeira metade do ano começam a ser depreciados no primeiro dia do ano (ano inteiro). Os ativos com uma data <strong>Colocado em serviço</strong> na segunda metade do ano começam a ser depreciados no primeiro dia do próximo ano. Os ativos desativados na primeira metade do ano são considerados desativados no último dia do ano anterior para fins de depreciação. Qualquer depreciação lançada no ano atual deve ser revertida ou ajustada. Os ativos desativados na segunda metade do ano são considerados desativados no último dia do ano de desativação para fins de depreciação. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
