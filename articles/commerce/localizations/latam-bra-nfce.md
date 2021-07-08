---
title: Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de documento fiscal NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
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
ms.search.validFrom: 2019-06-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8ebc23bdd8eba9b1420c0005275bab5217c26066
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303525"
---
# <a name="nfc-e-fiscal-document-functionality-in-commerce-pos-for-brazil"></a><span data-ttu-id="afae2-103">Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="afae2-103">NFC-e fiscal document functionality in Commerce POS for Brazil</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="afae2-104">Este tópico dá uma visão geral da funcionalidade de documento fiscal NFCe (Nota Fiscal do Consumidor eletrônica) no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="afae2-104">This topic gives an overview of NFC-e (Nota Fiscal do Consumidor eletrônica) fiscal document functionality in Microsoft Dynamics 365 Commerce point of sale (POS) for Brazil.</span></span> <span data-ttu-id="afae2-105">Ele também explica como emitir documentos NFC-e e imprimir recibos fiscais DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) quando as vendas de mercadorias no varejo são concluídas no PDV do Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="afae2-105">It also explains how to issue NFC-e documents and print DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) fiscal receipts when retail sales of goods are completed in Commerce POS for Brazil.</span></span>

<span data-ttu-id="afae2-106">Uma NFC-e é um documento fiscal eletrônico gerado para registrar a venda de mercadorias para um cliente.</span><span class="sxs-lookup"><span data-stu-id="afae2-106">An NFC-e is an electronic fiscal document that is generated to register the sale of goods to a customer.</span></span> <span data-ttu-id="afae2-107">Ela permite o controle fiscal e fiscal por parte das autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="afae2-107">It enables tax and fiscal control by tax authorities.</span></span> <span data-ttu-id="afae2-108">Ela também permite que os clientes verifiquem a validade e autenticidade dos documentos fiscais que recebem.</span><span class="sxs-lookup"><span data-stu-id="afae2-108">It also lets customers verify the validity and authenticity of fiscal documents that they receive.</span></span> <span data-ttu-id="afae2-109">As vendas de serviços não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="afae2-109">Sales of services aren't supported.</span></span>

<span data-ttu-id="afae2-110">A funcionalidade do Commerce para o Brasil permite o formato NFC-e modelo 65 para varejistas brasileiros.</span><span class="sxs-lookup"><span data-stu-id="afae2-110">Commerce functionality for Brazil supports the NFC-e model 65 format for Brazilian retailers.</span></span> <span data-ttu-id="afae2-111">O formato de NFC-e modelo 65 é um padrão nacional para documentos fiscais eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="afae2-111">The NFC-e model 65 format is a national standard for electronic fiscal documents.</span></span> <span data-ttu-id="afae2-112">Ele foi projetado para o varejo e é baseado nas mesmas normas técnicas do formato do modelo 55 da NF-e (Nota Fiscal eletrônica).</span><span class="sxs-lookup"><span data-stu-id="afae2-112">It's designed for retail and is based on the same technical standards as the NF-e (Nota Fiscal eletrônica) model 55 format.</span></span> <span data-ttu-id="afae2-113">Para obter mais informações sobre o formato e o processo da NF-e, consulte [Visão geral do processo de NF-e do Brasil](../../finance/localizations/latam-bra-nf-e-process.md).</span><span class="sxs-lookup"><span data-stu-id="afae2-113">For more information about the NF-e format and process, see [Brazil NF-e process overview](../../finance/localizations/latam-bra-nf-e-process.md).</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="afae2-114">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="afae2-114">Supported scenarios</span></span>

<span data-ttu-id="afae2-115">Os cenários de exemplo a seguir mostram as ações do Commerce frequentemente realizadas que estão associadas a documentos NFC-e.</span><span class="sxs-lookup"><span data-stu-id="afae2-115">The following example scenarios show frequently performed Commerce actions that are associated with NFC-e documents.</span></span>

### <a name="scenario-1-make-a-cash-and-carry-sale-of-goods-and-print-a-danfe-receipt"></a><span data-ttu-id="afae2-116">Cenário 1: fazer uma venda de mercadorias cash-and-carry e imprimir um recibo DANFE</span><span class="sxs-lookup"><span data-stu-id="afae2-116">Scenario 1: Make a cash-and-carry sale of goods and print a DANFE receipt</span></span>

1. <span data-ttu-id="afae2-117">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="afae2-117">Sign in to POS.</span></span>
1. <span data-ttu-id="afae2-118">Adicione produtos ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="afae2-118">Add products to the cart.</span></span>
1. <span data-ttu-id="afae2-119">Registre os pagamentos da transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-119">Register payments for the transaction.</span></span>
1. <span data-ttu-id="afae2-120">Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-120">Select the DANFE format (**Simplified** or **Detailed**), and then finalize the transaction.</span></span>
1. <span data-ttu-id="afae2-121">Verifique se as informações (incluindo o código QR) no recibo DANFE impresso correspondem à venda.</span><span class="sxs-lookup"><span data-stu-id="afae2-121">Verify that the information (including the QR code) on the printed DANFE receipt corresponds to the sale.</span></span>

### <a name="scenario-2-make-a-cash-and-carry-sale-of-goods-to-an-identified-customer"></a><span data-ttu-id="afae2-122">Cenário 2: fazer uma venda de mercadorias cash-and-carry para um cliente identificado</span><span class="sxs-lookup"><span data-stu-id="afae2-122">Scenario 2: Make a cash-and-carry sale of goods to an identified customer</span></span>

1. <span data-ttu-id="afae2-123">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="afae2-123">Sign in to POS.</span></span>
1. <span data-ttu-id="afae2-124">Adicione produtos ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="afae2-124">Add products to the cart.</span></span>
1. <span data-ttu-id="afae2-125">Adicione um cliente nomeado ou insira manualmente informações do cliente.</span><span class="sxs-lookup"><span data-stu-id="afae2-125">Add a named customer, or manually enter customer information.</span></span> <span data-ttu-id="afae2-126">Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).</span><span class="sxs-lookup"><span data-stu-id="afae2-126">For more information, see [Manage customer information in POS for Brazil](latam-bra-customer-information.md).</span></span>
1. <span data-ttu-id="afae2-127">Registre os pagamentos da transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-127">Register payments for the transaction.</span></span>
1. <span data-ttu-id="afae2-128">Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-128">Select the DANFE format (**Simplified** or **Detailed**), and then finalize the transaction.</span></span>
1. <span data-ttu-id="afae2-129">Verifique se as informações (incluindo o código QR) no recibo DANFE impresso correspondem à venda.</span><span class="sxs-lookup"><span data-stu-id="afae2-129">Verify that the information (including the QR code) on the printed DANFE receipt corresponds to the sale.</span></span>

### <a name="scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode"></a><span data-ttu-id="afae2-130">Cenário 3: fazer uma venda de mercadorias por cash-and-carry no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="afae2-130">Scenario 3: Make a cash-and-carry sale of goods in offline contingency mode</span></span>

<span data-ttu-id="afae2-131">O modo de contingência offline NFC-e deve ser usado quando a conexão à Internet de uma loja não estiver disponível, ou quando o serviço de autorização da SEFAZ (Secretaria de Estado de Fazenda) estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="afae2-131">The NFC-e offline contingency mode must be used when a store's internet connection isn't available, or when the SEFAZ (Secretaria de Estado de Fazenda) authorization service is down.</span></span> <span data-ttu-id="afae2-132">No modo de contingência offline, o PDV gera documentos NFC-e localmente.</span><span class="sxs-lookup"><span data-stu-id="afae2-132">In offline contingency mode, POS locally generates NFC-e documents.</span></span> <span data-ttu-id="afae2-133">Esses documentos são encaminhados à SEFAZ posteriormente.</span><span class="sxs-lookup"><span data-stu-id="afae2-133">Those documents are then transmitted to SEFAZ later.</span></span>

1. <span data-ttu-id="afae2-134">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="afae2-134">Sign in to POS.</span></span>
1. <span data-ttu-id="afae2-135">Adicione produtos ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="afae2-135">Add products to the cart.</span></span>
1. <span data-ttu-id="afae2-136">Registre os pagamentos da transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-136">Register payments for the transaction.</span></span> <span data-ttu-id="afae2-137">Você receberá um erro quando o PDV tentar se comunicar com a SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="afae2-137">You will receive an error when POS tries to communicate with SEFAZ.</span></span>
1. <span data-ttu-id="afae2-138">Selecione **Adiar**, digite uma justificativa para o adiamento e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-138">Select **Postpone**, enter a justification for the postponement, and then finalize the transaction.</span></span>
1. <span data-ttu-id="afae2-139">Verifique se são impressas duas cópias do DANFE detalhado: uma para o consumidor (via consumidor) e outra para o estabelecimento (via estabelecimento).</span><span class="sxs-lookup"><span data-stu-id="afae2-139">Verify that two copies of the detailed DANFE are printed: one for the consumer (via consumidor) and one for the establishment (via estabelecimento).</span></span>
1. <span data-ttu-id="afae2-140">Verifique se as informações (incluindo o código QR) nos recibos DANFE impressos correspondem à venda.</span><span class="sxs-lookup"><span data-stu-id="afae2-140">Verify that the information (including the QR code) on the printed DANFE receipts corresponds to the sale.</span></span>
1. <span data-ttu-id="afae2-141">Verifique se os recibos DANFE contêm o seguinte texto: "EMITIDA EM CONTINGÊNCIA Pendente de autorização".</span><span class="sxs-lookup"><span data-stu-id="afae2-141">Verify that the DANFE receipts contain the following text: "EMITIDA EM CONTINGÊNCIA Pendente de autorização" ("ISSUED IN CONTINGENCY Authorization Pending").</span></span>

### <a name="scenario-4-make-a-mixed-sale-that-contains-gift-cards-and-other-goods-in-the-same-transaction"></a><span data-ttu-id="afae2-142">Cenário 4: fazer uma venda mista que contenha vales-presente e outras mercadorias na mesma transação</span><span class="sxs-lookup"><span data-stu-id="afae2-142">Scenario 4: Make a mixed sale that contains gift cards and other goods in the same transaction</span></span>

<span data-ttu-id="afae2-143">As operações de emissão de vales-presente e agregação de valor aos vales-presente não estão sujeitas a tributações no Brasil.</span><span class="sxs-lookup"><span data-stu-id="afae2-143">The operations for issuing gift cards and adding value to gift cards aren't subject to taxations in Brazil.</span></span> <span data-ttu-id="afae2-144">Portanto, elas não são inseridas no recibo fiscal.</span><span class="sxs-lookup"><span data-stu-id="afae2-144">Therefore, they aren't written to the fiscal receipt.</span></span>

1. <span data-ttu-id="afae2-145">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="afae2-145">Sign in to POS.</span></span>
1. <span data-ttu-id="afae2-146">Adicione produtos ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="afae2-146">Add products to the cart.</span></span>
1. <span data-ttu-id="afae2-147">Emita vales-presente na mesma transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-147">Issue gift cards in the same transaction.</span></span>
1. <span data-ttu-id="afae2-148">Registre os pagamentos da transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-148">Register payments for the transaction.</span></span>
1. <span data-ttu-id="afae2-149">Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="afae2-149">Select the DANFE format (**Simplified** or **Detailed**), and then finalize the transaction.</span></span>
1. <span data-ttu-id="afae2-150">Verifique se o recibo DANFE impresso não inclui os vales-presente junto com os outras mercadorias que foram vendidas.</span><span class="sxs-lookup"><span data-stu-id="afae2-150">Verify that the printed DANFE receipt doesn't include the gift cards together with the other goods that were sold.</span></span>
1. <span data-ttu-id="afae2-151">Verifique se os recibos separados são impressos para cada vale-presente que foi vendido.</span><span class="sxs-lookup"><span data-stu-id="afae2-151">Verify that separate receipts are printed for each gift card that was sold.</span></span>

## <a name="custom-fields-for-danfe-fiscal-receipts"></a><span data-ttu-id="afae2-152">Campos personalizados para recibos fiscais DANFE</span><span class="sxs-lookup"><span data-stu-id="afae2-152">Custom fields for DANFE fiscal receipts</span></span>

<span data-ttu-id="afae2-153">Os recibos fiscais DANFE podem implementar e usar os seguintes campos personalizados para incluir informações adicionais:</span><span class="sxs-lookup"><span data-stu-id="afae2-153">DANFE fiscal receipts can implement and use the following custom fields to include additional information:</span></span>

- <span data-ttu-id="afae2-154">**Chave de acesso** – A chave de acesso que consiste em 11 blocos, cada um com quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="afae2-154">**Access key (Chave de acesso)** – The access key that consists of 11 blocks, each of which has four digits.</span></span>
- <span data-ttu-id="afae2-155">**Protocolo de Autorização** – Número que é obtido da SEFAZ quando são emitidos documentos fiscais NFC-e ou NF-e.</span><span class="sxs-lookup"><span data-stu-id="afae2-155">**Authorization protocol (Protocolo de Autorização)** – The number that is obtained from SEFAZ when NFC-e or NF-e fiscal documents are issued.</span></span>
- <span data-ttu-id="afae2-156">**Dados fiscais do emissor (Emitente)**:</span><span class="sxs-lookup"><span data-stu-id="afae2-156">**Fiscal data of the issuer (Emitente)**:</span></span>

    - <span data-ttu-id="afae2-157">**Nome** – O nome corporativo do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="afae2-157">**Name** – The corporate name of the fiscal establishment.</span></span>
    - <span data-ttu-id="afae2-158">**CNPJ** – O número CNPJ do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="afae2-158">**CNPJ** – The CNPJ number of the fiscal establishment.</span></span>
    - <span data-ttu-id="afae2-159">**IE** – O ID de registro do estado do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="afae2-159">**IE** – The state registration ID of the fiscal establishment.</span></span>
    - <span data-ttu-id="afae2-160">**Endereço** – O endereço do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="afae2-160">**Address** – The address of the fiscal establishment.</span></span>

- <span data-ttu-id="afae2-161">**Data de emissão (Emissão / Dados de recebimento)** – A data e hora em que o recibo é emitido.</span><span class="sxs-lookup"><span data-stu-id="afae2-161">**Date of issue (Emissão / Data de recebimento)** – The date and time when the receipt is issued.</span></span>
- <span data-ttu-id="afae2-162">**Número NFC-e / NF-e (Número)** – O número do documento fiscal eletrônico.</span><span class="sxs-lookup"><span data-stu-id="afae2-162">**NFC-e / NF-e number (Número)** – The number of the electronic fiscal document.</span></span>
- <span data-ttu-id="afae2-163">**Série** – A série do documento fiscal eletrônico.</span><span class="sxs-lookup"><span data-stu-id="afae2-163">**Series (Série)** – The series of the electronic fiscal document.</span></span>
- <span data-ttu-id="afae2-164">**Tipo de operação (Saída / Entrada )** – O tipo de entrada ou saída da operação.</span><span class="sxs-lookup"><span data-stu-id="afae2-164">**Type of operation (Saída / Entrada )** – The input or output type of the operation.</span></span>
- <span data-ttu-id="afae2-165">**Dados fiscais do cliente (Destinatário)**:</span><span class="sxs-lookup"><span data-stu-id="afae2-165">**Fiscal data of the customer (Destinatário)**:</span></span>

    - <span data-ttu-id="afae2-166">**Nome** – O nome do destinatário ou da corporação.</span><span class="sxs-lookup"><span data-stu-id="afae2-166">**Name** – The name of the recipient or corporation.</span></span>
    - <span data-ttu-id="afae2-167">**CPF/CNPJ/ID de estrangeiro** – O número do CPF/CNPJ ou ID de estrangeiro do destinatário.</span><span class="sxs-lookup"><span data-stu-id="afae2-167">**CPF/CNPJ/Foreigner ID** – The CPF/CNPJ number or foreigner ID of the recipient.</span></span>
    - <span data-ttu-id="afae2-168">**Endereço** - O endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="afae2-168">**Address** – The address of the recipient.</span></span>

- <span data-ttu-id="afae2-169">**Quantidade (Qtd.)** – A quantidade de itens.</span><span class="sxs-lookup"><span data-stu-id="afae2-169">**Quantity (Qtd.)** – The quantity of items.</span></span>
- <span data-ttu-id="afae2-170">**Valor total do item (Valor total)** – O valor por item.</span><span class="sxs-lookup"><span data-stu-id="afae2-170">**Total value of the item (Valor total)** – The amount per item.</span></span>
- <span data-ttu-id="afae2-171">**Quantidade total (Qtd. total de itens)** – A quantidade total de itens no recibo.</span><span class="sxs-lookup"><span data-stu-id="afae2-171">**Total quantity (Qtd. total de itens)** – The total quantity of items on the receipt.</span></span>
- <span data-ttu-id="afae2-172">**Valor total** – O valor total do recibo.</span><span class="sxs-lookup"><span data-stu-id="afae2-172">**Total value (Valor total)** – The total amount of the receipt.</span></span>
- <span data-ttu-id="afae2-173">**Código QR** – Um recibo pode incluir um código QR para DANFE modelo 65 para vendas.</span><span class="sxs-lookup"><span data-stu-id="afae2-173">**QR-code** – A receipt can include a QR code for DANFE model 65 for sales.</span></span>
- <span data-ttu-id="afae2-174">**Mensagem de Interesse do Contribuinte** – Um detalhamento aproximado da carga tributária nos documentos fiscais da NFC-e.</span><span class="sxs-lookup"><span data-stu-id="afae2-174">**Taxpayer Interest Message (Mensagem de Interesse do Contribuinte)** – An approximate breakdown of the tax burden in NFC-e fiscal documents.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="afae2-175">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="afae2-175">Additional resources</span></span>

[<span data-ttu-id="afae2-176">Configurar e implantar a localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="afae2-176">Set up and deploy Commerce localization for Brazil</span></span>](latam-bra-deployment.md)

[<span data-ttu-id="afae2-177">Localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="afae2-177">Commerce localization for Brazil</span></span>](latam-bra-commerce-localization.md)

[<span data-ttu-id="afae2-178">Gerenciar informações do cliente no PDV para o Brasil</span><span class="sxs-lookup"><span data-stu-id="afae2-178">Manage customer information in POS for Brazil</span></span>](latam-bra-customer-information.md)

[<span data-ttu-id="afae2-179">Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="afae2-179">Cancellation and return of NFC-e documents in Commerce POS for Brazil</span></span>](latam-bra-nfce-cancel-return.md)

[<span data-ttu-id="afae2-180">Registro adiado de documentos NFC-e emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="afae2-180">Postponed registration of NFC-e documents issued in offline contingency mode</span></span>](latam-bra-nfce-contingency-mode.md)

[<span data-ttu-id="afae2-181">Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="afae2-181">Post Brazilian fiscal documents via retail statements in Commerce headquarters</span></span>](latam-bra-retail-statements.md)
