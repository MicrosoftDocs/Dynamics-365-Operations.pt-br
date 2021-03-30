---
title: Usar dados externos em previsões de fluxo de caixa (versão prévia)
description: Este tópico descreve as etapas de configuração que devem ser concluídas para que os dados externos possam ser inseridos ou importados para previsões de fluxo de caixa.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 03318eaae0b3329dc758c48202f8f47ca2c4ab08
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245559"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="0022f-103">Usar dados externos em previsões de fluxo de caixa (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="0022f-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0022f-104">Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="0022f-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="0022f-105">Este tópico descreve as etapas de configuração específicas ao uso de dados externos e que permitem que os dados externos sejam incluídos em uma previsão de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="0022f-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="0022f-106">Dados mestres externos</span><span class="sxs-lookup"><span data-stu-id="0022f-106">External data setup</span></span>

<span data-ttu-id="0022f-107">Use a guia **Fonte externa** na página **Configuração de previsão de fluxo de caixa** (**Gerenciamento de caixa e de banco \> Previsão de fluxo de caixa**) para inserir configurações que suportam o uso de dados externos em previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="0022f-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="0022f-108">Para obter mais informações sobre a configuração, consulte [Previsão de fluxo de caixa](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="0022f-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="0022f-109">Para inserir dados externos para previsões de fluxo de caixa, você pode usar a experiência Abrir no Excel para inserir e modificar dados externos.</span><span class="sxs-lookup"><span data-stu-id="0022f-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="0022f-110">Selecione o botão **Dados externos** e selecione **Adicionar dados externos** ou **Editar dados externos existentes**.</span><span class="sxs-lookup"><span data-stu-id="0022f-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="0022f-111">Quando o arquivo do Microsoft Excel é aberto, você pode inserir informações nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0022f-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="0022f-112">**ID da Entrada**</span><span class="sxs-lookup"><span data-stu-id="0022f-112">**Entry ID**</span></span>
- <span data-ttu-id="0022f-113">**Descrição** (opcional)</span><span class="sxs-lookup"><span data-stu-id="0022f-113">**Description** (optional)</span></span>
- <span data-ttu-id="0022f-114">**Nome de origem externo** – Selecione um dos valores na lista que você definiu ao configurar o Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="0022f-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="0022f-115">**Entidade legal**</span><span class="sxs-lookup"><span data-stu-id="0022f-115">**Legal Entity**</span></span>
- <span data-ttu-id="0022f-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="0022f-116">**Date**</span></span>
- <span data-ttu-id="0022f-117">**Valor na moeda de transação**</span><span class="sxs-lookup"><span data-stu-id="0022f-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="0022f-118">**Código de Moeda**</span><span class="sxs-lookup"><span data-stu-id="0022f-118">**Currency Code**</span></span>
- <span data-ttu-id="0022f-119">**Dimensão padrão** (opcional)</span><span class="sxs-lookup"><span data-stu-id="0022f-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="0022f-120">**Número do documento** (opcional)</span><span class="sxs-lookup"><span data-stu-id="0022f-120">**Document number** (optional)</span></span>
- <span data-ttu-id="0022f-121">**Número da conta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="0022f-121">**Account number** (optional)</span></span>
- <span data-ttu-id="0022f-122">**Nome da conta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="0022f-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="0022f-123">Importar dados externos usando a estrutura de gerenciamento de dados</span><span class="sxs-lookup"><span data-stu-id="0022f-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="0022f-124">Você pode importar dados externos para previsões de fluxo de caixa usando o espaço de trabalho **Gerenciamento de dados** e a entidade chamada **Entrada de origem externa de previsão de fluxo de caixa**.</span><span class="sxs-lookup"><span data-stu-id="0022f-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="0022f-125">Além disso, se você precisar mover os dados de configuração de um ambiente para outro, as seguintes entidades estão disponíveis para as tabelas de configuração necessárias:</span><span class="sxs-lookup"><span data-stu-id="0022f-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="0022f-126">Configuração da fonte externa de previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="0022f-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="0022f-127">Configuração da entidade legal de fonte externa de previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="0022f-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="0022f-128">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="0022f-128">Privacy notice</span></span>
<span data-ttu-id="0022f-129">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="0022f-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]