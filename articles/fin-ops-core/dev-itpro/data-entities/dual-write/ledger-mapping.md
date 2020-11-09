---
title: Razão integrado
description: Este tópico descreve a integração de dados do razão entre o Finance and Operations e outros aplicativos do Dynamics 365 usando o Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7f5435a97776b817a4b99887cbab8283de25b692
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4014849"
---
# <a name="integrated-ledger"></a><span data-ttu-id="69b85-103">Razão integrado</span><span class="sxs-lookup"><span data-stu-id="69b85-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="69b85-104">Em um aplicativo de negócios, os dados do razão definem a configuração principal relacionada ao modo como a empresa faz negócios.</span><span class="sxs-lookup"><span data-stu-id="69b85-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="69b85-105">Por exemplo, os dados do razão descrevem o ano fiscal seguido pela empresa, as moedas usadas nas transações e as contas que ela utiliza.</span><span class="sxs-lookup"><span data-stu-id="69b85-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="69b85-106">Este tópico descreve a integração desses dados financeiros principais.</span><span class="sxs-lookup"><span data-stu-id="69b85-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="69b85-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="69b85-107">Templates</span></span>

<span data-ttu-id="69b85-108">Os dados do razão incluem um conjunto de mapas de entidades financeiras centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="69b85-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="69b85-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="69b85-109">Finance and Operations apps</span></span>      | <span data-ttu-id="69b85-110">Aplicativo controlado por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="69b85-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="69b85-111">descrição</span><span class="sxs-lookup"><span data-stu-id="69b85-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="69b85-112">Moedas</span><span class="sxs-lookup"><span data-stu-id="69b85-112">Currencies</span></span>                       | <span data-ttu-id="69b85-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="69b85-113">transactioncurrencies</span></span>            |
<span data-ttu-id="69b85-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="69b85-114">FiscalCalendar</span></span>                   | <span data-ttu-id="69b85-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="69b85-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="69b85-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="69b85-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="69b85-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="69b85-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="69b85-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="69b85-118">ExchRateType</span></span>                     | <span data-ttu-id="69b85-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="69b85-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="69b85-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="69b85-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="69b85-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="69b85-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="69b85-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="69b85-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="69b85-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="69b85-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="69b85-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="69b85-124">MainAccountCategory</span></span>              | <span data-ttu-id="69b85-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="69b85-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="69b85-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="69b85-126">MainAccount</span></span>                      | <span data-ttu-id="69b85-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="69b85-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="69b85-128">Razão</span><span class="sxs-lookup"><span data-stu-id="69b85-128">Ledger</span></span>                           | <span data-ttu-id="69b85-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="69b85-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="69b85-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="69b85-130">ExchangeRates</span></span>                    | <span data-ttu-id="69b85-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="69b85-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="69b85-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="69b85-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="69b85-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="69b85-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="69b85-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="69b85-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="69b85-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="69b85-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="69b85-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="69b85-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="69b85-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="69b85-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="69b85-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="69b85-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="69b85-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="69b85-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




