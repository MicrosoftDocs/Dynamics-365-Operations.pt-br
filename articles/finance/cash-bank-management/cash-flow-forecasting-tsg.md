---
title: Solucionar problemas de configuração de previsão de fluxo de caixa
description: Este tópico oferece respostas para dúvidas que você possa ter ao configurar a previsão de fluxo de caixa. Ele aborda perguntas frequentes sobre a configuração de fluxo de caixa, atualizações para fluxo de caixa e fluxo de caixa do Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1cde9321259753bd0cacab3706c7f8455598ff3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232480"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="2afab-104">Solucionar problemas de configuração de previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="2afab-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2afab-105">Este tópico oferece respostas para dúvidas que você possa ter ao configurar a previsão de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="2afab-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="2afab-106">Ele aborda perguntas frequentes sobre a configuração de fluxo de caixa, atualizações para fluxo de caixa e fluxo de caixa do Power BI.</span><span class="sxs-lookup"><span data-stu-id="2afab-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="2afab-107">Por que o fluxo de caixa é mostrado para uma única entidade legal?</span><span class="sxs-lookup"><span data-stu-id="2afab-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="2afab-108">A previsão de fluxo de caixa é configurada e calculada por entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2afab-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="2afab-109">Os relatórios do Power BI e o recurso de previsões de fluxo de caixa no Finance Insights mostram os resultados.</span><span class="sxs-lookup"><span data-stu-id="2afab-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="2afab-110">A previsão de fluxo de caixa deve ser configurada para cada entidade legal para a qual você deseja ver uma previsão.</span><span class="sxs-lookup"><span data-stu-id="2afab-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="2afab-111">Revise a configuração de previsão de fluxo de caixa em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2afab-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="2afab-112">Como alternativa, revise a configuração de todas as entidades legais para a previsão de fluxo de caixa e verifique se elas estão definidas da maneira desejada.</span><span class="sxs-lookup"><span data-stu-id="2afab-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="2afab-113">Por que o Power BI não mostra todos os dados do fluxo de caixa?</span><span class="sxs-lookup"><span data-stu-id="2afab-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="2afab-114">Várias etapas devem ser concluídas para que previsões de fluxo de caixa apareçam em exibições do Power BI.</span><span class="sxs-lookup"><span data-stu-id="2afab-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="2afab-115">Revise a seguinte lista de verificação e verifique se todas as etapas foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="2afab-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="2afab-116">Configure o fluxo de caixa para cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2afab-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="2afab-117">Nos parâmetros da contabilidade, defina a moeda do sistema e o tipo de taxa de câmbio do sistema.</span><span class="sxs-lookup"><span data-stu-id="2afab-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="2afab-118">Defina a moeda contábil do razão e o tipo de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="2afab-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="2afab-119">Insira as taxas de câmbio entre a moeda da transação e a moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="2afab-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="2afab-120">Insira as taxas de câmbio entre a moeda contábil e a moeda do sistema.</span><span class="sxs-lookup"><span data-stu-id="2afab-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="2afab-121">Insira as taxas de câmbio entre a moeda contábil e a moeda de cada banco.</span><span class="sxs-lookup"><span data-stu-id="2afab-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="2afab-122">Por que o fluxo de caixa do Power BI funcionou em versões anteriores, mas agora está em branco?</span><span class="sxs-lookup"><span data-stu-id="2afab-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="2afab-123">Verifique se as medidas "Medida de fluxo de caixa V2" e "LedgerCovLiquidityMeasurement" do Repositório de entidades foram configuradas.</span><span class="sxs-lookup"><span data-stu-id="2afab-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="2afab-124">Para obter mais informações sobre como trabalhar com dados no Repositório de entidades, consulte [Integração do Power BI com o Repositório de entidades](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verifique se todas as etapas necessárias para exibir conteúdo do Power BI foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="2afab-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="2afab-125">Para obter mais informações, consulte [Conteúdo de visão geral do caixa do Power BI](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="2afab-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="2afab-126">As entidades do Repositório de entidades foram atualizadas?</span><span class="sxs-lookup"><span data-stu-id="2afab-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="2afab-127">Você deve atualizar as entidades periodicamente para garantir que os dados sejam atuais e precisos.</span><span class="sxs-lookup"><span data-stu-id="2afab-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="2afab-128">Para atualizar manualmente uma entidade específica, acesse **Administração do sistema \> Configuração \> Repositório de entidades**, selecione a entidade e, depois, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="2afab-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="2afab-129">Os dados também podem ser atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2afab-129">The data can also be updated automatically.</span></span> <span data-ttu-id="2afab-130">Na página **Repositório de entidades**, defina a opção **Atualização automática habilitada** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2afab-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]