---
title: Importar taxas de câmbio de moeda
description: Se uma entidade legal recebeu faturas em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local. Isso significa que as taxas de câmbio atualizadas para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas na Internet pelos provedores de taxa de câmbio, como o Banco Central Europeu e o Banco Central da Rússia.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cdc9373ab22092e1f28bd087519f7476a7f2139a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186500"
---
# <a name="import-currency-exchange-rates"></a><span data-ttu-id="4733d-105">Importar taxas de câmbio de moeda</span><span class="sxs-lookup"><span data-stu-id="4733d-105">Import currency exchange rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4733d-106">Se uma entidade legal recebeu faturas em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local.</span><span class="sxs-lookup"><span data-stu-id="4733d-106">If a legal entity has received invoices in foreign currencies, it’s necessary to convert the foreign currency into the local currency.</span></span> <span data-ttu-id="4733d-107">Isso significa que as taxas de câmbio atualizadas para diferentes moedas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="4733d-107">This means that up-to-date exchange rates for different currencies are required.</span></span> <span data-ttu-id="4733d-108">Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas na Internet pelos provedores de taxa de câmbio, como o Banco Central Europeu e o Banco Central da Rússia.</span><span class="sxs-lookup"><span data-stu-id="4733d-108">This topic provides an overview of the required settings and processing for importing foreign exchange reference rates published over the Internet by the exchange rate providers, such as the European Central Bank and the Central Bank of Russia.</span></span>

<span data-ttu-id="4733d-109">As seções a seguir descrevem o fluxo de informações usadas para configurar e processar a importação de taxas de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-109">The following sections describe the flow of information that is used for setting up and processing the import of foreign exchange rates.</span></span>

## <a name="configure-an-exchange-rate-provider"></a><span data-ttu-id="4733d-110">Configurar um provedor de taxa de câmbio</span><span class="sxs-lookup"><span data-stu-id="4733d-110">Configure an exchange rate provider</span></span>
<span data-ttu-id="4733d-111">Antes de importar taxas de câmbio, você deve configurar as informações necessárias para configurar os provedores que fornecem as taxas de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-111">Before you can import exchange rates, you must set up the information that is required by the providers who offer the exchange rates.</span></span> <span data-ttu-id="4733d-112">Use a página **Configurar provedores de taxa de câmbio** para selecionar os provedores de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-112">Use the **Configure exchange rate providers** page to select the exchange rate providers.</span></span> <span data-ttu-id="4733d-113">Alguns provedores de taxa de câmbio são incluídos com dados de demonstração no Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="4733d-113">Some exchange rate providers are included with the demo data in Dynamics 365 Finance.</span></span> <span data-ttu-id="4733d-114">A tabela a seguir fornece descrições dos controles desta página.</span><span class="sxs-lookup"><span data-stu-id="4733d-114">The following table provides descriptions for the controls on this page.</span></span>

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4733d-115">**Campo**</span><span class="sxs-lookup"><span data-stu-id="4733d-115">**Field**</span></span> | <span data-ttu-id="4733d-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4733d-116">**Description**</span></span>                                                                                                                                                                                                             |
| <span data-ttu-id="4733d-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4733d-117">**Name**</span></span>  | <span data-ttu-id="4733d-118">O nome do provedor de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-118">The name of the exchange rate provider.</span></span>                                                                                                                                                                                     |
| <span data-ttu-id="4733d-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4733d-119">**Key**</span></span>   | <span data-ttu-id="4733d-120">O identificador exclusivo das informações de configuração necessárias ao provedor.</span><span class="sxs-lookup"><span data-stu-id="4733d-120">The unique identifier for each piece of configuration information that is required by the provider.</span></span> <span data-ttu-id="4733d-121">Essas informações são adicionadas automaticamente para cada fornecedor da taxa de câmbio que você adiciona quando clica no botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4733d-121">This information is automatically added for each exchange rate provider that you add when you click the **Add** button.</span></span> |
| <span data-ttu-id="4733d-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4733d-122">**Value**</span></span> | <span data-ttu-id="4733d-123">As informações sobre cada chave.</span><span class="sxs-lookup"><span data-stu-id="4733d-123">Information for each key.</span></span> <span data-ttu-id="4733d-124">Essas informações são adicionadas a cada provedor da taxa de câmbio que você adiciona quando clica no botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4733d-124">This information is added for each exchange rate provider that you add when you click the **Add** button.</span></span>                                                                                         |

## <a name="import-currency-exchange-rates"></a><span data-ttu-id="4733d-125">Importar taxas de câmbio de moeda</span><span class="sxs-lookup"><span data-stu-id="4733d-125">Import currency exchange rates</span></span>
<span data-ttu-id="4733d-126">Você pode importar taxas de câmbio de origem de provedores da taxa de câmbio, e configurá-las na página **Taxas de câmbio de moedas**.</span><span class="sxs-lookup"><span data-stu-id="4733d-126">You can import exchange rates from the exchange rate providers source, and set them up in the **Currency exchange rates** page.</span></span> <span data-ttu-id="4733d-127">Use a página **Importar taxas de câmbio de moeda** para importar as taxas de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-127">Use the **Import currency exchange rates** page to import the exchange rates.</span></span> <span data-ttu-id="4733d-128">A tabela a seguir fornece descrições dos campos necessários para concluir com êxito o processo de importação.</span><span class="sxs-lookup"><span data-stu-id="4733d-128">The following table provides descriptions the fields that are required to successfully complete the import process.</span></span>

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4733d-129">**Campo**</span><span class="sxs-lookup"><span data-stu-id="4733d-129">**Field**</span></span>                              | <span data-ttu-id="4733d-130">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4733d-130">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="4733d-131">**Tipo de taxa de câmbio**</span><span class="sxs-lookup"><span data-stu-id="4733d-131">**Exchange rate type**</span></span>                 | <span data-ttu-id="4733d-132">Um tipo de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-132">An exchange rate type.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="4733d-133">**Provedor de taxa de câmbio**</span><span class="sxs-lookup"><span data-stu-id="4733d-133">**Exchange rate provider**</span></span>             | <span data-ttu-id="4733d-134">Um do provedor de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-134">An exchange rate provider.</span></span>                                                                                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="4733d-135">**Importar a partir de**</span><span class="sxs-lookup"><span data-stu-id="4733d-135">**Import as of**</span></span>                       | <span data-ttu-id="4733d-136">Este parâmetro gerencia se a importação deve ser feita na data de hoje ou para um intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="4733d-136">This parameter manages whether to import as of today’s date or for a date range.</span></span> <span data-ttu-id="4733d-137">Se quiser usar um intervalo de datas, insira ou selecione as datas de início e de término.</span><span class="sxs-lookup"><span data-stu-id="4733d-137">If you want to use a date range, enter or select starting and ending dates.</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="4733d-138">**Criar os pares de moedas necessários**</span><span class="sxs-lookup"><span data-stu-id="4733d-138">**Create necessary currency pairs**</span></span>    | <span data-ttu-id="4733d-139">Esta caixa de seleção gerencia a criação automática dos pares de moeda, se os pares de moeda que são importados não existirem.</span><span class="sxs-lookup"><span data-stu-id="4733d-139">This check box manages the automatic creation of currency pairs, if the currency pairs that are imported do not exist.</span></span> <span data-ttu-id="4733d-140">Esta opção talvez não esteja disponível para alguns provedores.</span><span class="sxs-lookup"><span data-stu-id="4733d-140">This option might not be available for some providers.</span></span>                                                                                                                                                                                               |
| <span data-ttu-id="4733d-141">**Substituir taxas de câmbio existentes**</span><span class="sxs-lookup"><span data-stu-id="4733d-141">**Override existing exchange rates**</span></span>   | <span data-ttu-id="4733d-142">Esta caixa de seleção gerencia a atualização da taxa de câmbio existente para um par de moedas quando já existir a taxa de câmbio para uma data específica.</span><span class="sxs-lookup"><span data-stu-id="4733d-142">This check box manages the update of the existing exchange rate for a currency pair when the exchange rate for a specific date already exists.</span></span> <span data-ttu-id="4733d-143">Se você não marcar esta caixa de seleção, a taxa de câmbio para as datas específicas não será importada, se já existir outra taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="4733d-143">If you do not select this check box, the exchange rate for the specific dates is not imported if another exchange rate already exists.</span></span>                                                                                       |
| <span data-ttu-id="4733d-144">**Evitar importação em feriado nacional**</span><span class="sxs-lookup"><span data-stu-id="4733d-144">**Prevent import on national holiday**</span></span> | <span data-ttu-id="4733d-145">Esta caixa de seleção gerencia a importação da taxa de câmbio para uma data que seja um feriado.</span><span class="sxs-lookup"><span data-stu-id="4733d-145">This check box manages the import of the exchange rate for a date that is a public holiday.</span></span> <span data-ttu-id="4733d-146">Por exemplo, se você marcar esta caixa de seleção e usar o Banco Central Europeu como o provedor da taxa de câmbio, o sistema não atualizará a taxa de câmbio em um feriado que é relacionado à entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="4733d-146">For example, if you select this check box and use the European Central Bank as the exchange rate provider, the system will not update the exchange rate on a public holiday that is related to the current legal entity.</span></span> <span data-ttu-id="4733d-147">Esta opção talvez não esteja disponível para alguns provedores.</span><span class="sxs-lookup"><span data-stu-id="4733d-147">This option might not be available for some providers.</span></span> |




