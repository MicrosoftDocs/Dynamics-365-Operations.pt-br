---
title: Metodologia de convenção de depreciação semestral
description: Este tópico descreve o método usado pelos ativos fixos para calcular a depreciação usando a convenção semestral, que calcula seis meses de depreciação durante o primeiro e o último anos de um ativo em serviço.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: cb027513da086d882942c4677892b15cf8e7b338
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260796"
---
# <a name="half-year-depreciation-convention-methodology"></a>Metodologia de convenção de depreciação semestral

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve o método usado em ativos fixos para calcular a depreciação usando a convenção semestral. A convenção semestral calcula seis meses de depreciação durante o primeiro e o último anos de serviço de um ativo. Para obter mais informações sobre convenções de depreciação, consulte [Métodos e convenções de depreciação](Fixed-asset-depreciation-conventions.md). 

Quando você usa a convenção de depreciação semestral, o sistema usa o ano de aquisição ou o ano em que o ativo foi colocado em serviço, calcula cinco anos de depreciação a partir desse ano e adiciona seis meses. Para ilustrar esse processo, considere um ativo adquirido pelo preço de 50.000 e colocado em serviço em abril de 2020. Suponha também que o ativo tenha uma vida útil de cinco anos.

O primeiro ano de serviço terminará em dezembro de 2020, o que significa que o final da vida útil do serviço de cinco anos do ativo será dezembro de 2024. A convenção de depreciação semestral adiciona seis meses à vida do ativo, o que significa que a vida útil terminará em junho de 2025. 

> Depreciação anual 50.000/5 = 10.000 depreciação mensal 10.000/12 = 833,33 <br>
> A depreciação do primeiro ano 10.000/2 = 5.000 e a depreciação mensal subsequente 5.000/9 = 555,56

   [![Agenda de depreciação para convenção de depreciação semestral](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

Os períodos de depreciação estendidos adicionados pela convenção semestral fornecem uma alocação mais precisa da depreciação. A convenção semestral representa as despesas de depreciação de forma mais uniforme, o que é útil para relatórios no demonstrativo de lucros e perdas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]