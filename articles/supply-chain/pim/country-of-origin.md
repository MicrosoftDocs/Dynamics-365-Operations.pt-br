---
title: País de origem
description: Muitas organizações emitem certificados para seus fornecedores a fim de garantir que os produtos atendam a padrões de certificação específicos. Esses certificados geralmente dependem do país de origem. Este tópico fornece informações sobre o recurso de país de origem, que permite vincular um produto ao país de origem e monitorar as certificações de produtos.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fd234c57bf9893e9b8bcfa5ada7439a642f7a288
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596202"
---
# <a name="country-of-origin"></a><span data-ttu-id="b000b-105">País de origem</span><span class="sxs-lookup"><span data-stu-id="b000b-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b000b-106">Muitas organizações emitem certificados para seus fornecedores a fim de garantir que os produtos atendam a padrões de certificação específicos.</span><span class="sxs-lookup"><span data-stu-id="b000b-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="b000b-107">Esses certificados geralmente dependem do país de origem.</span><span class="sxs-lookup"><span data-stu-id="b000b-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="b000b-108">O recurso de país de origem permite vincular um produto ao país de origem e monitorar as certificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="b000b-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="b000b-109">Configurar países de origem e de destino</span><span class="sxs-lookup"><span data-stu-id="b000b-109">Configure source and destination countries</span></span>

<span data-ttu-id="b000b-110">Antes de emitir um certificado para um produto, você deve vincular o produto ao país de destino e ao país de origem.</span><span class="sxs-lookup"><span data-stu-id="b000b-110">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="b000b-111">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Regras do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="b000b-111">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="b000b-112">Selecione uma configuração de país existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de país.</span><span class="sxs-lookup"><span data-stu-id="b000b-112">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="b000b-113">Defina os valores a seguir para o país novo ou selecionado.</span><span class="sxs-lookup"><span data-stu-id="b000b-113">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="b000b-114">Campo</span><span class="sxs-lookup"><span data-stu-id="b000b-114">Field</span></span> | <span data-ttu-id="b000b-115">descrição</span><span class="sxs-lookup"><span data-stu-id="b000b-115">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b000b-116">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="b000b-116">Item number</span></span> | <span data-ttu-id="b000b-117">Selecione o número de itens do produto.</span><span class="sxs-lookup"><span data-stu-id="b000b-117">Select the item number of the product.</span></span> |
    | <span data-ttu-id="b000b-118">País/região de destino</span><span class="sxs-lookup"><span data-stu-id="b000b-118">Destination country</span></span> | <span data-ttu-id="b000b-119">Selecione o país para o qual você está enviando o produto.</span><span class="sxs-lookup"><span data-stu-id="b000b-119">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="b000b-120">País de origem</span><span class="sxs-lookup"><span data-stu-id="b000b-120">Origin country</span></span> | <span data-ttu-id="b000b-121">Selecione o país do qual você está enviando o produto.</span><span class="sxs-lookup"><span data-stu-id="b000b-121">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="b000b-122">A finalidade desta configuração é ajudá-lo a gerar um relatório de lista de materiais (BOM), no qual é possível incluir o país de origem de cada peça para a qual os países de origem e de destino foram especificados.</span><span class="sxs-lookup"><span data-stu-id="b000b-122">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="b000b-123">Esse relatório vai ajudá-lo a obter uma visão holística de onde as peças vêm e aonde estão indo.</span><span class="sxs-lookup"><span data-stu-id="b000b-123">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="b000b-124">Monitorar certificados de fornecedores</span><span class="sxs-lookup"><span data-stu-id="b000b-124">Keep track of vendor certificates</span></span>

<span data-ttu-id="b000b-125">Você pode usar a página **Certificados de fornecedores do país de origem** para monitorar os certificados emitidos para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="b000b-125">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="b000b-126">Você deve decidir quais documentos de certificado está emitindo e como vai relatá-los aos clientes.</span><span class="sxs-lookup"><span data-stu-id="b000b-126">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="b000b-127">Este recurso ajuda a monitorar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="b000b-127">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="b000b-128">Ele também permite escolher se os números de certificados relevantes aparecerão em faturas, guias de remessa e/ou confirmações de ordens.</span><span class="sxs-lookup"><span data-stu-id="b000b-128">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="b000b-129">Para configurar as informações sobre o certificado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b000b-129">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="b000b-130">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Certificados de fornecedores do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="b000b-130">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="b000b-131">Selecione uma configuração de certificado existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de certificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-131">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="b000b-132">Defina as configurações a seguir para o certificado novo ou selecionado.</span><span class="sxs-lookup"><span data-stu-id="b000b-132">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="b000b-133">Campo</span><span class="sxs-lookup"><span data-stu-id="b000b-133">Field</span></span> | <span data-ttu-id="b000b-134">descrição</span><span class="sxs-lookup"><span data-stu-id="b000b-134">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b000b-135">Conta de Fornecedor</span><span class="sxs-lookup"><span data-stu-id="b000b-135">Vendor account</span></span> | <span data-ttu-id="b000b-136">Selecione o fornecedor para o qual você emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-136">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="b000b-137">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="b000b-137">Item number</span></span> | <span data-ttu-id="b000b-138">Selecione o item para o qual você emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-138">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="b000b-139">País/região</span><span class="sxs-lookup"><span data-stu-id="b000b-139">Country/region</span></span> | <span data-ttu-id="b000b-140">O país ou a região de destino em que você deve usar este certificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-140">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="b000b-141">Número do certificado</span><span class="sxs-lookup"><span data-stu-id="b000b-141">Certificate number</span></span> | <span data-ttu-id="b000b-142">Insira o número de identificação do certificado emitido.</span><span class="sxs-lookup"><span data-stu-id="b000b-142">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="b000b-143">Em vigor</span><span class="sxs-lookup"><span data-stu-id="b000b-143">Effective</span></span> | <span data-ttu-id="b000b-144">Selecione a primeira data em que o certificado atual é válido.</span><span class="sxs-lookup"><span data-stu-id="b000b-144">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="b000b-145">Vencimento</span><span class="sxs-lookup"><span data-stu-id="b000b-145">Expiration</span></span> | <span data-ttu-id="b000b-146">Selecione a última data em que o certificado atual é válido.</span><span class="sxs-lookup"><span data-stu-id="b000b-146">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="b000b-147">Imprimir na fatura</span><span class="sxs-lookup"><span data-stu-id="b000b-147">Print on invoice</span></span> | <span data-ttu-id="b000b-148">Marque esta caixa de seleção para imprimir o número do certificado nas faturas endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-148">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b000b-149">Imprimir na guia de remessa</span><span class="sxs-lookup"><span data-stu-id="b000b-149">Print on packing slip</span></span> | <span data-ttu-id="b000b-150">Marque esta caixa de seleção para imprimir o número do certificado nas guias de remessa endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-150">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b000b-151">Imprimir na ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b000b-151">Print on sales order</span></span> | <span data-ttu-id="b000b-152">Marque esta caixa de seleção para imprimir o número do certificado nas ordens de venda endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="b000b-152">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="b000b-153">Incluir o país de origem nos relatórios de BOM</span><span class="sxs-lookup"><span data-stu-id="b000b-153">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="b000b-154">Ao gerar um relatório de BOM, você pode incluir o país de origem de cada peça para a qual especificou países de origem e de destino na página **Regras do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="b000b-154">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="b000b-155">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="b000b-155">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b000b-156">Selecione ou crie um produto para abrir sua página **Detalhes do produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="b000b-156">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="b000b-157">No Painel de Ação, na guia **Engenharia**, no grupo **BOM**, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b000b-157">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="b000b-158">Na página exibida, no Painel de Ação, selecione **BOM \> Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="b000b-158">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="b000b-159">Na caixa de diálogo **Linhas da lista de materiais**, defina o campo **País de destino** como o país de destino que você deseja exibir no relatório.</span><span class="sxs-lookup"><span data-stu-id="b000b-159">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="b000b-160">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000b-160">Select **OK**.</span></span>

<span data-ttu-id="b000b-161">Um relatório que mostra informações sobre o país de origem de cada peça é gerado e exibido.</span><span class="sxs-lookup"><span data-stu-id="b000b-161">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="b000b-162">Veja aqui um exemplo do relatório.</span><span class="sxs-lookup"><span data-stu-id="b000b-162">Here is an example of the report.</span></span>

<span data-ttu-id="b000b-163">![Relatório sobre o país de origem](media/country-of-origin-report.png "Relatório sobre o país de origem")</span><span class="sxs-lookup"><span data-stu-id="b000b-163">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
