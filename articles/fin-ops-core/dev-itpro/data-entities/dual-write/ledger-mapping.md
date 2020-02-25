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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 6bf1c554f56c1424da9fde98f67f80a6b7c95461
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019639"
---
# <a name="integrated-ledger"></a><span data-ttu-id="fa3be-103">Razão integrado</span><span class="sxs-lookup"><span data-stu-id="fa3be-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="fa3be-104">Em um aplicativo de negócios, os dados do razão definem a configuração principal relacionada ao modo como a empresa faz negócios.</span><span class="sxs-lookup"><span data-stu-id="fa3be-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="fa3be-105">Por exemplo, os dados do razão descrevem o ano fiscal seguido pela empresa, as moedas usadas nas transações e as contas que ela utiliza.</span><span class="sxs-lookup"><span data-stu-id="fa3be-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="fa3be-106">Este tópico descreve a integração desses dados financeiros principais.</span><span class="sxs-lookup"><span data-stu-id="fa3be-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="fa3be-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="fa3be-107">Templates</span></span>

<span data-ttu-id="fa3be-108">Os dados do razão incluem um conjunto de mapas de entidades financeiras centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa3be-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="fa3be-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fa3be-109">Finance and Operations apps</span></span>      | <span data-ttu-id="fa3be-110">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fa3be-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="fa3be-111">Moedas</span><span class="sxs-lookup"><span data-stu-id="fa3be-111">Currencies</span></span>                       | <span data-ttu-id="fa3be-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="fa3be-112">transactioncurrencies</span></span>
<span data-ttu-id="fa3be-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="fa3be-113">FiscalCalendar</span></span>                   | <span data-ttu-id="fa3be-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="fa3be-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="fa3be-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="fa3be-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="fa3be-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="fa3be-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="fa3be-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="fa3be-117">ExchRateType</span></span>                     | <span data-ttu-id="fa3be-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="fa3be-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="fa3be-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="fa3be-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="fa3be-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="fa3be-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="fa3be-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="fa3be-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="fa3be-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="fa3be-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="fa3be-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="fa3be-123">MainAccountCategory</span></span>              | <span data-ttu-id="fa3be-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="fa3be-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="fa3be-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="fa3be-125">MainAccount</span></span>                      | <span data-ttu-id="fa3be-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="fa3be-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="fa3be-127">Razão</span><span class="sxs-lookup"><span data-stu-id="fa3be-127">Ledger</span></span>                           | <span data-ttu-id="fa3be-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="fa3be-128">msdyn\_ledgers</span></span>
<span data-ttu-id="fa3be-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="fa3be-129">ExchangeRates</span></span>                    | <span data-ttu-id="fa3be-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="fa3be-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="fa3be-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="fa3be-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="fa3be-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="fa3be-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="fa3be-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="fa3be-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="fa3be-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="fa3be-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="fa3be-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="fa3be-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="fa3be-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="fa3be-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="fa3be-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="fa3be-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="fa3be-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="fa3be-138">msdyn\_chartofaccounts.md</span></span>


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




