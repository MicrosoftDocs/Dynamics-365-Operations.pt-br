---
title: Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de cancelamento e devolução para documentos NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: v-ankvik
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: v-ankvik
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5b2ea57de34c22b1cc95318d2e73a376744a82b1
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303527"
---
# <a name="cancellation-and-return-of-nfc-e-documents-in-commerce-pos-for-brazil"></a><span data-ttu-id="c2dcf-103">Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="c2dcf-103">Cancellation and return of NFC-e documents in Commerce POS for Brazil</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c2dcf-104">Este tópico dá uma visão geral da funcionalidade de cancelamento e devolução para documentos NFC-e (Nota Fiscal do Consumidor eletrônica) no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-104">This topic gives an overview of the cancellation and return functionality for NFC-e (Nota Fiscal do Consumidor eletrônica) documents in Microsoft Dynamics 365 Commerce point of sale (POS) for Brazil.</span></span>

<span data-ttu-id="c2dcf-105">A funcionalidade do Commerce para o Brasil permite o cancelamento e a devolução das vendas que foram emitidas por meio de documentos NFC-e.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-105">Commerce functionality for Brazil supports the cancellation and return of sales that were issued by using NFC-e documents.</span></span> <span data-ttu-id="c2dcf-106">Os formatos de documentos NFC-e baseiam-se nas normas técnicas nacionais para documentos fiscais eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-106">NFC-e document formats are based on the national technical standards for electronic fiscal documents.</span></span> <span data-ttu-id="c2dcf-107">Essas normas também incluem um formato para eventos de cancelamento e NF-e (Nota Fiscal eletrônica) modelo 55 para devoluções.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-107">These standards also include a format for cancellation events and NF-e (Nota Fiscal eletrônica) model 55 for returns.</span></span>

<span data-ttu-id="c2dcf-108">Uma NF-e é um documento fiscal eletrônico gerado e impressa para registrar a devolução de mercadorias que foram vendidas para um cliente.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-108">An NF-e is an electronic fiscal document that is generated and printed to register the return of goods that were sold to a customer.</span></span> <span data-ttu-id="c2dcf-109">Ela permite o controle fiscal e fiscal por parte das autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-109">It enables tax and fiscal control by tax authorities.</span></span> <span data-ttu-id="c2dcf-110">Ela também permite que os clientes verifiquem a validade e autenticidade dos documentos fiscais que recebem.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-110">It also lets customers verify the validity and authenticity of the fiscal documents that they receive.</span></span> <span data-ttu-id="c2dcf-111">Para obter mais informações sobre o processo de NF-e, consulte [Visão geral do processo de NF-e do Brasil](../../finance/localizations/latam-bra-nf-e-process.md).</span><span class="sxs-lookup"><span data-stu-id="c2dcf-111">For more information about the NF-e process, see [Brazil NF-e process overview](../../finance/localizations/latam-bra-nf-e-process.md).</span></span>

<span data-ttu-id="c2dcf-112">Um documento NFC-e só pode ser cancelado se já tiver sido autorizado pela autoridade fiscal, e se a mercadoria e o cliente ainda estiverem no estabelecimento.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-112">An NFC-e document can be canceled only if it has already been authorized by the tax authority, and if the goods and the customer are still in the establishment.</span></span> <span data-ttu-id="c2dcf-113">O prazo para o cancelamento de um documento NFC-e é de 30 minutos após a autorização de uso ser concedida.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-113">The deadline for canceling an NFC-e document is 30 minutes after the authorization for use was granted.</span></span> <span data-ttu-id="c2dcf-114">Após o término deste prazo de cancelamento, um documento de devolução da NF-e deve ser emitido para cancelar uma venda.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-114">After this cancellation deadline expires, a return NF-e document must be issued to cancel a sale.</span></span>

## <a name="limitations"></a><span data-ttu-id="c2dcf-115">Limitações</span><span class="sxs-lookup"><span data-stu-id="c2dcf-115">Limitations</span></span>

<span data-ttu-id="c2dcf-116">As seguintes limitações aplicam-se à funcionalidade de cancelamento e devolução para documentos NFC-e:</span><span class="sxs-lookup"><span data-stu-id="c2dcf-116">The following limitations apply to the cancellation and return functionality for NFC-e documents:</span></span>

- <span data-ttu-id="c2dcf-117">Cancelamentos e devoluções são permitidos apenas para vendas que são feitas dentro do mesmo estado.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-117">Cancellations and returns are allowed only for sales that are made within the same state.</span></span> <span data-ttu-id="c2dcf-118">As operações interestaduais são proibidas.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-118">Interstate operations are prohibited.</span></span>
- <span data-ttu-id="c2dcf-119">O cancelamento de documentos NFC-e autorizados por terminais de PDV em outras lojas não é compatível.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-119">Cancellation of NFC-e documents that are authorized by POS terminals in other stores isn't supported.</span></span> <span data-ttu-id="c2dcf-120">Somente documentos NFC-e autorizados que são emitidos por terminais do PDV na mesma loja podem ser cancelados.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-120">Only authorized NFC-e documents that are issued by POS terminals in the same store can be canceled.</span></span>
- <span data-ttu-id="c2dcf-121">Os cancelamentos e devoluções que são emitidos no modo de contingência offline não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-121">Cancellations and returns that are issued in offline contingency mode aren't supported.</span></span> <span data-ttu-id="c2dcf-122">Em outras palavras, os cancelamentos e devoluções não podem ser emitidos por terminais de PDV que não tenham acesso à internet, ou quando o serviço de autorização da autoridade fiscal está disponível.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-122">In other words, cancellations and returns can't be issued by POS terminals that don't have internet access, or when the tax authority's authorization service is down.</span></span>
- <span data-ttu-id="c2dcf-123">O DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) simplificado para o formato modelo 55 é o único layout compatível para devoluções.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-123">The simplified DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) for model 55 format is the only layout that is supported for returns.</span></span>
- <span data-ttu-id="c2dcf-124">As vendas e devoluções de serviços não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-124">Sales and returns of services aren't supported.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="c2dcf-125">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="c2dcf-125">Supported scenarios</span></span>

<span data-ttu-id="c2dcf-126">Os cenários de exemplo a seguir mostram como iniciar cancelamentos e devoluções no PDV do Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-126">The following example scenarios show how to initiate cancellations and returns in Commerce POS for Brazil.</span></span>

### <a name="scenario-1-initiate-a-cancellation-of-sold-goods"></a><span data-ttu-id="c2dcf-127">Cenário 1: iniciar o cancelamento de mercadorias vendidas</span><span class="sxs-lookup"><span data-stu-id="c2dcf-127">Scenario 1: Initiate a cancellation of sold goods</span></span>

<span data-ttu-id="c2dcf-128">Para iniciar o cancelamento de mercadorias vendidas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-128">To initiate a cancellation of sold goods, follow these steps.</span></span>

1. <span data-ttu-id="c2dcf-129">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-129">Sign in to POS.</span></span>
1. <span data-ttu-id="c2dcf-130">Abra a página **Exibir diário**.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-130">Open **Show journal** page.</span></span>
1. <span data-ttu-id="c2dcf-131">Encontre a venda que deve ser cancelada.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-131">Find the sale that must be canceled.</span></span>
1. <span data-ttu-id="c2dcf-132">Selecione **Cancelar transação**.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-132">Select **Cancel transaction**.</span></span>
1. <span data-ttu-id="c2dcf-133">Digite uma justificativa para o cancelamento e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-133">Enter a justification for the cancellation, and then select **OK**.</span></span>
1. <span data-ttu-id="c2dcf-134">Adicione um cliente nomeado ou insira manualmente informações do cliente.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-134">Add a named customer, or manually enter customer information.</span></span> <span data-ttu-id="c2dcf-135">Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).</span><span class="sxs-lookup"><span data-stu-id="c2dcf-135">For more information, see [Manage customer information in POS for Brazil](latam-bra-customer-information.md).</span></span>
1. <span data-ttu-id="c2dcf-136">Registre os reembolsos de pagamento da transação e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-136">Register payment refunds for the transaction, and then finalize the transaction.</span></span>

### <a name="scenario-2-initiate-a-return-of-sold-goods"></a><span data-ttu-id="c2dcf-137">Cenário 2: iniciar a devolução de mercadorias vendidas</span><span class="sxs-lookup"><span data-stu-id="c2dcf-137">Scenario 2: Initiate a return of sold goods</span></span>

<span data-ttu-id="c2dcf-138">Para iniciar a devolução de mercadorias vendidas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-138">To initiate a return of sold goods, follow these steps.</span></span>

1. <span data-ttu-id="c2dcf-139">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-139">Sign in to POS.</span></span>
1. <span data-ttu-id="c2dcf-140">Abra a página **Exibir diário**.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-140">Open the **Show journal** page.</span></span>
1. <span data-ttu-id="c2dcf-141">Encontre a venda que deve ser devolvida total ou parcialmente.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-141">Find the sale that must be fully or partially returned.</span></span>
1. <span data-ttu-id="c2dcf-142">Selecione **Devolução**, selecione os produtos que podem ser devolvidos conforme necessário e selecione **Devolver**.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-142">Select **Return**, select the returnable products as required, and then select **Return**.</span></span>
1. <span data-ttu-id="c2dcf-143">Adicione um cliente nomeado ou insira manualmente informações do cliente.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-143">Add a named customer, or manually enter customer information.</span></span> <span data-ttu-id="c2dcf-144">Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).</span><span class="sxs-lookup"><span data-stu-id="c2dcf-144">For more information, see [Manage customer information in POS for Brazil](latam-bra-customer-information.md).</span></span>
1. <span data-ttu-id="c2dcf-145">Registre os pagamentos da transação.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-145">Register payments for the transaction.</span></span>
1. <span data-ttu-id="c2dcf-146">Verifique se as informações (incluindo o código de barras) no recibo DANFE simplificado impresso para o documento fiscal modelo 55 correspondem à venda.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-146">Verify that the information (including the barcode) on the printed simplified DANFE for model 55 fiscal receipt corresponds to the sale.</span></span>

## <a name="simplified-danfe-for-model-55-fiscal-receipt"></a><span data-ttu-id="c2dcf-147">DANFE simplificado para o recibo fiscal modelo 55</span><span class="sxs-lookup"><span data-stu-id="c2dcf-147">Simplified DANFE for model 55 fiscal receipt</span></span>

<span data-ttu-id="c2dcf-148">Além da [lista comum de campos personalizados para DANFE](latam-bra-nfce.md), um DANFE simplificado para o recibo fiscal modelo 55 pode incluir o seguinte campo personalizado:</span><span class="sxs-lookup"><span data-stu-id="c2dcf-148">In addition to the [common list of custom fields for DANFE](latam-bra-nfce.md), a simplified DANFE for model 55 fiscal receipt can include the following custom field:</span></span>

- <span data-ttu-id="c2dcf-149">**Código de barras** – Você pode adicionar um campo de código de barras ao DANFE simplificado para recibos fiscais do modelo 55 para devoluções.</span><span class="sxs-lookup"><span data-stu-id="c2dcf-149">**Barcode (Código de barras)** – You can add a bar code field to simplified DANFE for model 55 fiscal receipts for returns.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2dcf-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c2dcf-150">Additional resources</span></span>

[<span data-ttu-id="c2dcf-151">Configurar e implantar a localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="c2dcf-151">Set up and deploy Commerce localization for Brazil</span></span>](latam-bra-deployment.md)

[<span data-ttu-id="c2dcf-152">Localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="c2dcf-152">Commerce localization for Brazil</span></span>](latam-bra-commerce-localization.md)

[<span data-ttu-id="c2dcf-153">Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="c2dcf-153">NFC-e fiscal document functionality in Commerce POS for Brazil</span></span>](latam-bra-nfce.md)

[<span data-ttu-id="c2dcf-154">Gerenciar informações do cliente no PDV para o Brasil</span><span class="sxs-lookup"><span data-stu-id="c2dcf-154">Manage customer information in POS for Brazil</span></span>](latam-bra-customer-information.md)

[<span data-ttu-id="c2dcf-155">Registro adiado de documentos NFC-e emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="c2dcf-155">Postponed registration of NFC-e documents issued in offline contingency mode</span></span>](latam-bra-nfce-contingency-mode.md)

[<span data-ttu-id="c2dcf-156">Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="c2dcf-156">Post Brazilian fiscal documents via retail statements in Commerce headquarters</span></span>](latam-bra-retail-statements.md)
