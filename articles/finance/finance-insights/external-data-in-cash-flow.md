---
title: Usar dados externos em previsões de fluxo de caixa (versão prévia)
description: Este tópico descreve as etapas de configuração que devem ser concluídas para que os dados externos possam ser inseridos ou importados para previsões de fluxo de caixa.
author: rcarlson
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 66bdb8bd638859bb4fc5565e3f12a8f671addcff
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186681"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="d638d-103">Usar dados externos em previsões de fluxo de caixa (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="d638d-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d638d-104">Os dados externos podem ser inseridos ou importados para previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="d638d-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="d638d-105">Este tópico descreve as etapas de configuração específicas ao uso de dados externos e que permitem que os dados externos sejam incluídos em uma previsão de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="d638d-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="d638d-106">Dados mestres externos</span><span class="sxs-lookup"><span data-stu-id="d638d-106">External data setup</span></span>

<span data-ttu-id="d638d-107">Use a guia **Fonte externa** na página **Configuração de previsão de fluxo de caixa** (**Gerenciamento de caixa e de banco \> Previsão de fluxo de caixa**) para inserir configurações que suportam o uso de dados externos em previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="d638d-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="d638d-108">Para obter mais informações sobre a configuração, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).</span><span class="sxs-lookup"><span data-stu-id="d638d-108">For more information about the setup, see [Cash flow forecasting](../cash-bank-management/cash-flow-forecasting.md).</span></span>

<span data-ttu-id="d638d-109">Para inserir dados externos para previsões de fluxo de caixa, você pode usar a experiência Abrir no Excel para inserir e modificar dados externos.</span><span class="sxs-lookup"><span data-stu-id="d638d-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="d638d-110">Selecione o botão **Dados externos** e selecione **Adicionar dados externos** ou **Editar dados externos existentes**.</span><span class="sxs-lookup"><span data-stu-id="d638d-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="d638d-111">Quando o arquivo do Microsoft Excel é aberto, você pode inserir informações nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="d638d-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="d638d-112">**ID da Entrada**</span><span class="sxs-lookup"><span data-stu-id="d638d-112">**Entry ID**</span></span>
- <span data-ttu-id="d638d-113">**Descrição** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d638d-113">**Description** (optional)</span></span>
- <span data-ttu-id="d638d-114">**Nome de origem externo** – Selecione um dos valores na lista que você definiu ao configurar o Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="d638d-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="d638d-115">**Entidade legal**</span><span class="sxs-lookup"><span data-stu-id="d638d-115">**Legal Entity**</span></span>
- <span data-ttu-id="d638d-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="d638d-116">**Date**</span></span>
- <span data-ttu-id="d638d-117">**Valor na moeda de transação**</span><span class="sxs-lookup"><span data-stu-id="d638d-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="d638d-118">**Código de Moeda**</span><span class="sxs-lookup"><span data-stu-id="d638d-118">**Currency Code**</span></span>
- <span data-ttu-id="d638d-119">**Dimensão padrão** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d638d-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="d638d-120">**Número do documento** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d638d-120">**Document number** (optional)</span></span>
- <span data-ttu-id="d638d-121">**Número da conta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d638d-121">**Account number** (optional)</span></span>
- <span data-ttu-id="d638d-122">**Nome da conta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="d638d-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="d638d-123">Importar dados externos usando a estrutura de gerenciamento de dados</span><span class="sxs-lookup"><span data-stu-id="d638d-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="d638d-124">Você pode importar dados externos para previsões de fluxo de caixa usando o espaço de trabalho **Gerenciamento de dados** e a entidade chamada **Entrada de origem externa de previsão de fluxo de caixa**.</span><span class="sxs-lookup"><span data-stu-id="d638d-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="d638d-125">Além disso, se você precisar mover os dados de configuração de um ambiente para outro, as seguintes entidades estão disponíveis para as tabelas de configuração necessárias:</span><span class="sxs-lookup"><span data-stu-id="d638d-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="d638d-126">Configuração da fonte externa de previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="d638d-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="d638d-127">Configuração da entidade legal de fonte externa de previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="d638d-127">Cash flow forecast external source legal entity setup</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
