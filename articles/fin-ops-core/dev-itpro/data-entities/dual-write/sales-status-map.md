---
title: Configurar o mapeamento dos campos de status da ordem de venda
description: Este tópico explica como configurar os campos de status da ordem de venda para a gravação dupla.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997665"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="3236e-103">Configurar o mapeamento dos campos de status da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="3236e-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3236e-104">Os campos que indicam o status da ordem de venda têm diferentes valores de enumeração no Microsoft Dynamics 365 Supply Chain Management e no Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3236e-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="3236e-105">Uma configuração adicional é necessária para mapear esses campos em gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="3236e-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="3236e-106">Campos no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3236e-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="3236e-107">No Supply Chain Management, dois campos refletem o status da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3236e-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="3236e-108">Os campos que você deve mapear são **Status** e **Status do Documento**.</span><span class="sxs-lookup"><span data-stu-id="3236e-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="3236e-109">A enumeração **Status** especifica o status geral da ordem.</span><span class="sxs-lookup"><span data-stu-id="3236e-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3236e-110">Esse status é mostrado no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="3236e-110">This status is shown on the order header.</span></span>

<span data-ttu-id="3236e-111">A enumeração **Status** tem os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3236e-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3236e-112">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-112">Open Order</span></span>
- <span data-ttu-id="3236e-113">Entregues</span><span class="sxs-lookup"><span data-stu-id="3236e-113">Delivered</span></span>
- <span data-ttu-id="3236e-114">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-114">Invoiced</span></span>
- <span data-ttu-id="3236e-115">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-115">Cancelled</span></span>

<span data-ttu-id="3236e-116">A enumeração **Status do Documento** especifica o documento mais recente que foi gerado para a ordem.</span><span class="sxs-lookup"><span data-stu-id="3236e-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="3236e-117">Por exemplo, se a ordem for confirmada, este documento será uma confirmação de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3236e-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="3236e-118">Se uma ordem de venda for parcialmente faturada e a linha restante for confirmada, o status do documento permanecerá como **Fatura** , pois a fatura será gerada posteriormente no processo.</span><span class="sxs-lookup"><span data-stu-id="3236e-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice** , because the invoice is generated later in the process.</span></span>

<span data-ttu-id="3236e-119">A enumeração **Status do Documento** tem os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3236e-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3236e-120">Confirmação</span><span class="sxs-lookup"><span data-stu-id="3236e-120">Confirmation</span></span>
- <span data-ttu-id="3236e-121">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="3236e-121">Picking List</span></span>
- <span data-ttu-id="3236e-122">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="3236e-122">Packing Slip</span></span>
- <span data-ttu-id="3236e-123">Fatura</span><span class="sxs-lookup"><span data-stu-id="3236e-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="3236e-124">Campos em Vendas</span><span class="sxs-lookup"><span data-stu-id="3236e-124">Fields in Sales</span></span>

<span data-ttu-id="3236e-125">Em Vendas, dois campos indicam o status da ordem.</span><span class="sxs-lookup"><span data-stu-id="3236e-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="3236e-126">Os campos que você deve mapear são **Status** e **Status de Processamento**.</span><span class="sxs-lookup"><span data-stu-id="3236e-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="3236e-127">A enumeração **Status** especifica o status geral da ordem.</span><span class="sxs-lookup"><span data-stu-id="3236e-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3236e-128">Tem os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3236e-128">It has the following values:</span></span>

- <span data-ttu-id="3236e-129">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-129">Active</span></span>
- <span data-ttu-id="3236e-130">Envio feito</span><span class="sxs-lookup"><span data-stu-id="3236e-130">Submitted</span></span>
- <span data-ttu-id="3236e-131">Atendidos</span><span class="sxs-lookup"><span data-stu-id="3236e-131">Fulfilled</span></span>
- <span data-ttu-id="3236e-132">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-132">Invoiced</span></span>
- <span data-ttu-id="3236e-133">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-133">Cancelled</span></span>

<span data-ttu-id="3236e-134">A enumeração **Status de Processamento** foi introduzida para que o status possa ser mapeado mais precisamente com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3236e-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="3236e-135">A tabela a seguir mostra o mapeamento do **Status de Processamento** no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3236e-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="3236e-136">Status do processamento</span><span class="sxs-lookup"><span data-stu-id="3236e-136">Processing Status</span></span>   | <span data-ttu-id="3236e-137">Status no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3236e-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="3236e-138">Status do Documento no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3236e-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="3236e-139">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-139">Active</span></span>              | <span data-ttu-id="3236e-140">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-140">Open Order</span></span>                        | <span data-ttu-id="3236e-141">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="3236e-141">None</span></span>                                       |
| <span data-ttu-id="3236e-142">Confirmada</span><span class="sxs-lookup"><span data-stu-id="3236e-142">Confirmed</span></span>           | <span data-ttu-id="3236e-143">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-143">Open Order</span></span>                        | <span data-ttu-id="3236e-144">Confirmação</span><span class="sxs-lookup"><span data-stu-id="3236e-144">Confirmation</span></span>                               |
| <span data-ttu-id="3236e-145">Separada</span><span class="sxs-lookup"><span data-stu-id="3236e-145">Picked</span></span>              | <span data-ttu-id="3236e-146">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-146">Open Order</span></span>                        | <span data-ttu-id="3236e-147">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="3236e-147">Picking List</span></span>                               |
| <span data-ttu-id="3236e-148">Parcialmente entregue</span><span class="sxs-lookup"><span data-stu-id="3236e-148">Partially Delivered</span></span> | <span data-ttu-id="3236e-149">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-149">Open Order</span></span>                        | <span data-ttu-id="3236e-150">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="3236e-150">Packing Slip</span></span>                               |
| <span data-ttu-id="3236e-151">Entregues</span><span class="sxs-lookup"><span data-stu-id="3236e-151">Delivered</span></span>           | <span data-ttu-id="3236e-152">Entregues</span><span class="sxs-lookup"><span data-stu-id="3236e-152">Delivered</span></span>                         | <span data-ttu-id="3236e-153">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="3236e-153">Packing Slip</span></span>                               |
| <span data-ttu-id="3236e-154">Parcialmente faturada</span><span class="sxs-lookup"><span data-stu-id="3236e-154">Partially Invoiced</span></span>  | <span data-ttu-id="3236e-155">Entregues</span><span class="sxs-lookup"><span data-stu-id="3236e-155">Delivered</span></span>                         | <span data-ttu-id="3236e-156">Fatura</span><span class="sxs-lookup"><span data-stu-id="3236e-156">Invoice</span></span>                                    |
| <span data-ttu-id="3236e-157">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-157">Invoiced</span></span>            | <span data-ttu-id="3236e-158">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-158">Invoiced</span></span>                          | <span data-ttu-id="3236e-159">Fatura</span><span class="sxs-lookup"><span data-stu-id="3236e-159">Invoice</span></span>                                    |
| <span data-ttu-id="3236e-160">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-160">Cancelled</span></span>           | <span data-ttu-id="3236e-161">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-161">Cancelled</span></span>                         | <span data-ttu-id="3236e-162">Não Aplicável</span><span class="sxs-lookup"><span data-stu-id="3236e-162">Not applicable</span></span>                             |

<span data-ttu-id="3236e-163">A tabela a seguir mostra o mapeamento do **Status de Processamento** entre Vendas e o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3236e-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="3236e-164">Status do processamento</span><span class="sxs-lookup"><span data-stu-id="3236e-164">Processing Status</span></span>   | <span data-ttu-id="3236e-165">Status em Vendas</span><span class="sxs-lookup"><span data-stu-id="3236e-165">Status in Sales</span></span> | <span data-ttu-id="3236e-166">Status no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3236e-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="3236e-167">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-167">Active</span></span>              | <span data-ttu-id="3236e-168">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-168">Active</span></span>          | <span data-ttu-id="3236e-169">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-169">Open Order</span></span>                        |
| <span data-ttu-id="3236e-170">Confirmada</span><span class="sxs-lookup"><span data-stu-id="3236e-170">Confirmed</span></span>           | <span data-ttu-id="3236e-171">Envio feito</span><span class="sxs-lookup"><span data-stu-id="3236e-171">Submitted</span></span>       | <span data-ttu-id="3236e-172">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-172">Open Order</span></span>                        |
| <span data-ttu-id="3236e-173">Separada</span><span class="sxs-lookup"><span data-stu-id="3236e-173">Picked</span></span>              | <span data-ttu-id="3236e-174">Envio feito</span><span class="sxs-lookup"><span data-stu-id="3236e-174">Submitted</span></span>       | <span data-ttu-id="3236e-175">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-175">Open Order</span></span>                        |
| <span data-ttu-id="3236e-176">Parcialmente entregue</span><span class="sxs-lookup"><span data-stu-id="3236e-176">Partially Delivered</span></span> | <span data-ttu-id="3236e-177">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-177">Active</span></span>          | <span data-ttu-id="3236e-178">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-178">Open Order</span></span>                        |
| <span data-ttu-id="3236e-179">Parcialmente faturada</span><span class="sxs-lookup"><span data-stu-id="3236e-179">Partially Invoiced</span></span>  | <span data-ttu-id="3236e-180">Ativos</span><span class="sxs-lookup"><span data-stu-id="3236e-180">Active</span></span>          | <span data-ttu-id="3236e-181">Ordem em Aberto</span><span class="sxs-lookup"><span data-stu-id="3236e-181">Open Order</span></span>                        |
| <span data-ttu-id="3236e-182">Parcialmente faturada</span><span class="sxs-lookup"><span data-stu-id="3236e-182">Partially Invoiced</span></span>  | <span data-ttu-id="3236e-183">Atendidos</span><span class="sxs-lookup"><span data-stu-id="3236e-183">Fulfilled</span></span>       | <span data-ttu-id="3236e-184">Entregues</span><span class="sxs-lookup"><span data-stu-id="3236e-184">Delivered</span></span>                         |
| <span data-ttu-id="3236e-185">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-185">Invoiced</span></span>            | <span data-ttu-id="3236e-186">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-186">Invoiced</span></span>        | <span data-ttu-id="3236e-187">Faturadas</span><span class="sxs-lookup"><span data-stu-id="3236e-187">Invoiced</span></span>                          |
| <span data-ttu-id="3236e-188">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-188">Cancelled</span></span>           | <span data-ttu-id="3236e-189">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-189">Cancelled</span></span>       | <span data-ttu-id="3236e-190">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3236e-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="3236e-191">Configurar</span><span class="sxs-lookup"><span data-stu-id="3236e-191">Setup</span></span>

<span data-ttu-id="3236e-192">Para configurar o mapeamento dos campos de status da ordem de venda, você deve habilitar os atributos **IsSOPIntegrationEnabled** e **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="3236e-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="3236e-193">Para habilitar o atributo **IsSOPIntegrationEnabled** , siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3236e-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3236e-194">Em um navegador, vá para `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="3236e-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="3236e-195">Substitua **\<test-name\>** pelo link da sua empresa para Vendas.</span><span class="sxs-lookup"><span data-stu-id="3236e-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="3236e-196">Na página que está aberta, localize **organizationid** e anote o valor.</span><span class="sxs-lookup"><span data-stu-id="3236e-196">On the page that is opened, find **organizationid** , and make a note of the value.</span></span>

    ![Localizando organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="3236e-198">Em Vendas, abra o console do navegador e execute o seguinte script.</span><span class="sxs-lookup"><span data-stu-id="3236e-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="3236e-199">Use o valor **organizationid** da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3236e-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Código JavaScript no console do navegador](media/sales-map-script.png)

4. <span data-ttu-id="3236e-201">Verifique se **IsSOPIntegrationEnabled** está definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="3236e-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="3236e-202">Use a URL da etapa 1 para verificar o valor.</span><span class="sxs-lookup"><span data-stu-id="3236e-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled está definido como true](media/sales-map-integration-enabled.png)

<span data-ttu-id="3236e-204">Para habilitar o atributo **isIntegrationUser** , siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3236e-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3236e-205">Em Vendas, vá para **Configuração \> Personalização \> Personalizar o Sistema** , selecione **Entidade do usuário** e abra **Formulário \> Usuário**.</span><span class="sxs-lookup"><span data-stu-id="3236e-205">In Sales, go to **Setting \> Customization \> Customize the System** , select **User entity** , and then open **Form \> User**.</span></span>

    ![Abrindo o formulário do usuário](media/sales-map-user.png)

2. <span data-ttu-id="3236e-207">No Explorador do Campo, localize o **modo de usuário integração** e clique duas vezes nele para adicioná-lo ao formulário.</span><span class="sxs-lookup"><span data-stu-id="3236e-207">In Field Explorer, find **Integration user mode** , and double-click it to add it to the form.</span></span> <span data-ttu-id="3236e-208">Salve sua alteração.</span><span class="sxs-lookup"><span data-stu-id="3236e-208">Save your change.</span></span>

    ![Adicionando o campo modo de usuário de integração ao formulário](media/sales-map-field-explorer.png)

3. <span data-ttu-id="3236e-210">Em Vendas, vá para **Configuração \> Segurança \> Usuários** e altere a exibição de **Usuários Habilitados** para **Usuários do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3236e-210">In Sales, go to **Setting \> Security \> Users** , and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Alterando a exibição de Usuários Habilitados para Usuários de Aplicativos](media/sales-map-enabled-users.png)

4. <span data-ttu-id="3236e-212">Selecione as duas entradas para **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="3236e-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Lista de usuários do aplicativo](media/sales-map-user-mode.png)

5. <span data-ttu-id="3236e-214">Altere o valor do campo **Modo de usuário de integração** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3236e-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Alterar o valor do campo Modo de usuário de integração](media/sales-map-user-mode-yes.png)

<span data-ttu-id="3236e-216">Suas ordens de venda agora estão mapeadas.</span><span class="sxs-lookup"><span data-stu-id="3236e-216">Your sales orders are now mapped.</span></span>
