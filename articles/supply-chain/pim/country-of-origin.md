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
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0471785991a307de11147e9773d9abe1e02941d6
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895539"
---
# <a name="country-of-origin"></a><span data-ttu-id="f8f96-105">País de origem</span><span class="sxs-lookup"><span data-stu-id="f8f96-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f8f96-106">Muitas organizações emitem certificados para seus fornecedores a fim de garantir que os produtos atendam a padrões de certificação específicos.</span><span class="sxs-lookup"><span data-stu-id="f8f96-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="f8f96-107">Esses certificados geralmente dependem do país de origem.</span><span class="sxs-lookup"><span data-stu-id="f8f96-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="f8f96-108">O recurso de país de origem permite vincular um produto ao país de origem e monitorar as certificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="f8f96-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="f8f96-109">Ativar o recurso de país de origem</span><span class="sxs-lookup"><span data-stu-id="f8f96-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="f8f96-110">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="f8f96-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="f8f96-111">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="f8f96-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="f8f96-112">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f8f96-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f8f96-113">**Módulo:** *Gerenciamento de informações sobre produtos*</span><span class="sxs-lookup"><span data-stu-id="f8f96-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="f8f96-114">**Nome do recurso:** *Recurso de gerenciamento do país de origem*</span><span class="sxs-lookup"><span data-stu-id="f8f96-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="f8f96-115">Configurar países de origem e de destino</span><span class="sxs-lookup"><span data-stu-id="f8f96-115">Configure source and destination countries</span></span>

<span data-ttu-id="f8f96-116">Antes de emitir um certificado para um produto, você deve vincular o produto ao país de destino e ao país de origem.</span><span class="sxs-lookup"><span data-stu-id="f8f96-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="f8f96-117">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Regras do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="f8f96-118">Selecione uma configuração de país existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de país.</span><span class="sxs-lookup"><span data-stu-id="f8f96-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="f8f96-119">Defina os valores a seguir para o país novo ou selecionado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="f8f96-120">Campo</span><span class="sxs-lookup"><span data-stu-id="f8f96-120">Field</span></span> | <span data-ttu-id="f8f96-121">descrição</span><span class="sxs-lookup"><span data-stu-id="f8f96-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="f8f96-122">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="f8f96-122">Item number</span></span> | <span data-ttu-id="f8f96-123">Selecione o número de itens do produto.</span><span class="sxs-lookup"><span data-stu-id="f8f96-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="f8f96-124">País/região de destino</span><span class="sxs-lookup"><span data-stu-id="f8f96-124">Destination country</span></span> | <span data-ttu-id="f8f96-125">Selecione o país para o qual você está enviando o produto.</span><span class="sxs-lookup"><span data-stu-id="f8f96-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="f8f96-126">País de origem</span><span class="sxs-lookup"><span data-stu-id="f8f96-126">Origin country</span></span> | <span data-ttu-id="f8f96-127">Selecione o país do qual você está enviando o produto.</span><span class="sxs-lookup"><span data-stu-id="f8f96-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="f8f96-128">A finalidade desta configuração é ajudá-lo a gerar um relatório de lista de materiais (BOM), no qual é possível incluir o país de origem de cada peça para a qual os países de origem e de destino foram especificados.</span><span class="sxs-lookup"><span data-stu-id="f8f96-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="f8f96-129">Esse relatório vai ajudá-lo a obter uma visão holística de onde as peças vêm e aonde estão indo.</span><span class="sxs-lookup"><span data-stu-id="f8f96-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="f8f96-130">Monitorar certificados de fornecedores</span><span class="sxs-lookup"><span data-stu-id="f8f96-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="f8f96-131">Você pode usar a página **Certificados de fornecedores do país de origem** para monitorar os certificados emitidos para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="f8f96-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="f8f96-132">Você deve decidir quais documentos de certificado está emitindo e como vai relatá-los aos clientes.</span><span class="sxs-lookup"><span data-stu-id="f8f96-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="f8f96-133">Este recurso ajuda a monitorar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="f8f96-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="f8f96-134">Ele também permite escolher se os números de certificados relevantes aparecerão em faturas, guias de remessa e/ou confirmações de ordens.</span><span class="sxs-lookup"><span data-stu-id="f8f96-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="f8f96-135">Para configurar as informações sobre o certificado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f8f96-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="f8f96-136">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Certificados de fornecedores do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="f8f96-137">Selecione uma configuração de certificado existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de certificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="f8f96-138">Defina as configurações a seguir para o certificado novo ou selecionado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="f8f96-139">Campo</span><span class="sxs-lookup"><span data-stu-id="f8f96-139">Field</span></span> | <span data-ttu-id="f8f96-140">descrição</span><span class="sxs-lookup"><span data-stu-id="f8f96-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="f8f96-141">Conta de Fornecedor</span><span class="sxs-lookup"><span data-stu-id="f8f96-141">Vendor account</span></span> | <span data-ttu-id="f8f96-142">Selecione o fornecedor para o qual você emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="f8f96-143">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="f8f96-143">Item number</span></span> | <span data-ttu-id="f8f96-144">Selecione o item para o qual você emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="f8f96-145">País/região</span><span class="sxs-lookup"><span data-stu-id="f8f96-145">Country/region</span></span> | <span data-ttu-id="f8f96-146">O país ou a região de destino em que você deve usar este certificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="f8f96-147">Número do certificado</span><span class="sxs-lookup"><span data-stu-id="f8f96-147">Certificate number</span></span> | <span data-ttu-id="f8f96-148">Insira o número de identificação do certificado emitido.</span><span class="sxs-lookup"><span data-stu-id="f8f96-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="f8f96-149">Em vigor</span><span class="sxs-lookup"><span data-stu-id="f8f96-149">Effective</span></span> | <span data-ttu-id="f8f96-150">Selecione a primeira data em que o certificado atual é válido.</span><span class="sxs-lookup"><span data-stu-id="f8f96-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="f8f96-151">Vencimento</span><span class="sxs-lookup"><span data-stu-id="f8f96-151">Expiration</span></span> | <span data-ttu-id="f8f96-152">Selecione a última data em que o certificado atual é válido.</span><span class="sxs-lookup"><span data-stu-id="f8f96-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="f8f96-153">Imprimir na fatura</span><span class="sxs-lookup"><span data-stu-id="f8f96-153">Print on invoice</span></span> | <span data-ttu-id="f8f96-154">Marque esta caixa de seleção para imprimir o número do certificado nas faturas endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="f8f96-155">Imprimir na guia de remessa</span><span class="sxs-lookup"><span data-stu-id="f8f96-155">Print on packing slip</span></span> | <span data-ttu-id="f8f96-156">Marque esta caixa de seleção para imprimir o número do certificado nas guias de remessa endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="f8f96-157">Imprimir na ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f8f96-157">Print on sales order</span></span> | <span data-ttu-id="f8f96-158">Marque esta caixa de seleção para imprimir o número do certificado nas ordens de venda endereçadas ao país especificado durante o intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="f8f96-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="f8f96-159">Incluir o país de origem nos relatórios de BOM</span><span class="sxs-lookup"><span data-stu-id="f8f96-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="f8f96-160">Ao gerar um relatório de BOM, você pode incluir o país de origem de cada peça para a qual especificou países de origem e de destino na página **Regras do país de origem**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="f8f96-161">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="f8f96-162">Selecione ou crie um produto para abrir sua página **Detalhes do produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="f8f96-163">No Painel de Ação, na guia **Engenharia**, no grupo **BOM**, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="f8f96-164">Na página exibida, no Painel de Ação, selecione **BOM \> Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="f8f96-165">Na caixa de diálogo **Linhas da lista de materiais**, defina o campo **País de destino** como o país de destino que você deseja exibir no relatório.</span><span class="sxs-lookup"><span data-stu-id="f8f96-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="f8f96-166">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f96-166">Select **OK**.</span></span>

<span data-ttu-id="f8f96-167">Um relatório que mostra informações sobre o país de origem de cada peça é gerado e exibido.</span><span class="sxs-lookup"><span data-stu-id="f8f96-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="f8f96-168">Veja aqui um exemplo do relatório.</span><span class="sxs-lookup"><span data-stu-id="f8f96-168">Here is an example of the report.</span></span>

<span data-ttu-id="f8f96-169">![Relatório sobre o país de origem](media/country-of-origin-report.png "Relatório sobre o país de origem")</span><span class="sxs-lookup"><span data-stu-id="f8f96-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
