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
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="cf6fd-103">Metodologia de convenção de depreciação semestral</span><span class="sxs-lookup"><span data-stu-id="cf6fd-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cf6fd-104">Este tópico descreve o método usado em ativos fixos para calcular a depreciação usando a convenção semestral.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="cf6fd-105">A convenção semestral calcula seis meses de depreciação durante o primeiro e o último anos de serviço de um ativo.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="cf6fd-106">Para obter mais informações sobre convenções de depreciação, consulte [Métodos e convenções de depreciação](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="cf6fd-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="cf6fd-107">Quando você usa a convenção de depreciação semestral, o sistema usa o ano de aquisição ou o ano em que o ativo foi colocado em serviço, calcula cinco anos de depreciação a partir desse ano e adiciona seis meses.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="cf6fd-108">Para ilustrar esse processo, considere um ativo adquirido pelo preço de 50.000 e colocado em serviço em abril de 2020.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="cf6fd-109">Suponha também que o ativo tenha uma vida útil de cinco anos.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="cf6fd-110">O primeiro ano de serviço terminará em dezembro de 2020, o que significa que o final da vida útil do serviço de cinco anos do ativo será dezembro de 2024.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="cf6fd-111">A convenção de depreciação semestral adiciona seis meses à vida do ativo, o que significa que a vida útil terminará em junho de 2025.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="cf6fd-112">Depreciação anual 50.000/5 = 10.000 depreciação mensal 10.000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="cf6fd-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="cf6fd-113">A depreciação do primeiro ano 10.000/2 = 5.000 e a depreciação mensal subsequente 5.000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="cf6fd-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="cf6fd-114">[![Agenda de depreciação para convenção de depreciação semestral](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="cf6fd-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="cf6fd-115">Os períodos de depreciação estendidos adicionados pela convenção semestral fornecem uma alocação mais precisa da depreciação.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="cf6fd-116">A convenção semestral representa as despesas de depreciação de forma mais uniforme, o que é útil para relatórios no demonstrativo de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="cf6fd-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]