---
title: Razão integrado
description: Este tópico descreve a integração de dados do razão entre o Finance and Operations e o Customer Engagement usando o Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 43819e23b167663a51095546cab307e7d7c79a38
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771039"
---
## <a name="integrated-ledger"></a><span data-ttu-id="11ac5-103">Razão integrado</span><span class="sxs-lookup"><span data-stu-id="11ac5-103">Integrated ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11ac5-104">Em um aplicativo de negócios, os dados do razão definem a configuração principal relacionada ao modo como a empresa faz negócios.</span><span class="sxs-lookup"><span data-stu-id="11ac5-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="11ac5-105">Por exemplo, os dados do razão descrevem o ano fiscal seguido pela empresa, as moedas usadas nas transações e as contas que ela utiliza.</span><span class="sxs-lookup"><span data-stu-id="11ac5-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="11ac5-106">Este tópico descreve a integração desses dados financeiros principais.</span><span class="sxs-lookup"><span data-stu-id="11ac5-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="11ac5-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="11ac5-107">Templates</span></span>

<span data-ttu-id="11ac5-108">Os dados do razão incluem um conjunto de mapas de entidades financeiras centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="11ac5-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="11ac5-109">Aplicativos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11ac5-109">Finance and Operations apps</span></span>      | <span data-ttu-id="11ac5-110">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="11ac5-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="11ac5-111">Moedas</span><span class="sxs-lookup"><span data-stu-id="11ac5-111">Currencies</span></span>                       | <span data-ttu-id="11ac5-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="11ac5-112">transactioncurrencies</span></span>
<span data-ttu-id="11ac5-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="11ac5-113">FiscalCalendar</span></span>                   | <span data-ttu-id="11ac5-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="11ac5-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="11ac5-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="11ac5-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="11ac5-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="11ac5-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="11ac5-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="11ac5-117">ExchRateType</span></span>                     | <span data-ttu-id="11ac5-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="11ac5-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="11ac5-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="11ac5-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="11ac5-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="11ac5-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="11ac5-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="11ac5-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="11ac5-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="11ac5-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="11ac5-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="11ac5-123">MainAccountCategory</span></span>              | <span data-ttu-id="11ac5-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="11ac5-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="11ac5-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="11ac5-125">MainAccount</span></span>                      | <span data-ttu-id="11ac5-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="11ac5-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="11ac5-127">Razão</span><span class="sxs-lookup"><span data-stu-id="11ac5-127">Ledger</span></span>                           | <span data-ttu-id="11ac5-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="11ac5-128">msdyn\_ledgers</span></span>
<span data-ttu-id="11ac5-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="11ac5-129">ExchangeRates</span></span>                    | <span data-ttu-id="11ac5-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="11ac5-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="11ac5-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="11ac5-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="11ac5-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="11ac5-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="11ac5-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="11ac5-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="11ac5-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="11ac5-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="11ac5-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="11ac5-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="11ac5-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="11ac5-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="11ac5-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="11ac5-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="11ac5-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="11ac5-138">msdyn\_chartofaccounts.md</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Currency](dual-write/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](dual-write/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](dual-write/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](dual-write/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](dual-write/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](dual-write/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](dual-write/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](dual-write/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](dual-write/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](dual-write/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](dual-write/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](dual-write/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




