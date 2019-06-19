---
title: Gerar documentos fiscais para uma carga
description: Este tópico explica como gerar gerar documentos fiscais para uma carga do Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 06/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: dd7343a08196b45ec0ebb455f779642b7ca26cca
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555182"
---
# <a name="generate-fiscal-documents-for-a-load"></a><span data-ttu-id="94c1a-103">Gerar documentos fiscais para uma carga</span><span class="sxs-lookup"><span data-stu-id="94c1a-103">Generate fiscal documents for a load</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94c1a-104">Você pode criar uma carga que contém várias linhas de carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-104">You can create a load that has multiple load lines.</span></span> <span data-ttu-id="94c1a-105">Cada linha de carga é criada para uma quantidade específica de itens de uma linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="94c1a-105">Each load line is created for a specific quantity of items from a sales order line.</span></span> <span data-ttu-id="94c1a-106">Você pode criar uma ou mais linhas de carga ou cargas para uma ou mais linhas da ordem de venda ou para ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="94c1a-106">You can create one or more load lines or loads for one or more sales order lines or sales orders.</span></span>

> [!NOTE]
> <span data-ttu-id="94c1a-107">Este tópico se aplica aos recursos do módulo **Gerenciamento de transporte**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-107">This topic applies to features in the **Transportation management** module.</span></span> <span data-ttu-id="94c1a-108">Não se aplica aos recursos do módulo de Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="94c1a-108">It doesn't apply to features in the Inventory management  module.</span></span>

<span data-ttu-id="94c1a-109">Você pode gerar um ou mais documentos fiscais para uma carga, dependendo das ordens de venda na qual a carga foi criada.</span><span class="sxs-lookup"><span data-stu-id="94c1a-109">You can generate one or more fiscal documents for a load, depending on the sales orders that the load is created for.</span></span> <span data-ttu-id="94c1a-110">A quantidade em uma linha de documento fiscal é a quantidade de retirada da linha de carga, não a quantidade da linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="94c1a-110">The quantity on a fiscal document line is the pick-up quantity for the load line, not the quantity from the sales order line.</span></span>

<span data-ttu-id="94c1a-111">O exemplo a seguir mostra como você pode criar linhas de cargas e cargas para linhas da ordem de venda e ordens de venda e como os documentos fiscais são gerados para cada carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-111">The following example shows how you can create load lines and loads for sales order lines and sales orders, and how fiscal documents are generated for each load.</span></span>

### <a name="sales-orders-and-sales-order-lines"></a><span data-ttu-id="94c1a-112">Ordens de venda e linhas de ordens de venda</span><span class="sxs-lookup"><span data-stu-id="94c1a-112">Sales orders and sales order lines</span></span>

1. <span data-ttu-id="94c1a-113">Ordem de venda 1 para o cliente C1 que contém as seguintes linhas da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="94c1a-113">Sales order 1 for customer C1 has the following sales order lines:</span></span>

    1. <span data-ttu-id="94c1a-114">Linha da ordem de venda 1.1 que contém 50 unidades do item. A.</span><span class="sxs-lookup"><span data-stu-id="94c1a-114">Sales order line 1.1, which has 50 units of item A</span></span>
    2. <span data-ttu-id="94c1a-115">Linha da ordem de venda 1.2 que contém 20 unidades do item B</span><span class="sxs-lookup"><span data-stu-id="94c1a-115">Sales order line 1.2, which has 20 units of item B</span></span>

2. <span data-ttu-id="94c1a-116">Ordem de venda 2 para o cliente C2 que contém as seguintes linhas da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="94c1a-116">Sales order 2 for customer C2 has the following sales order lines:</span></span>

    1. <span data-ttu-id="94c1a-117">Linha da ordem de venda 2.1 que contém 200 unidades do item C</span><span class="sxs-lookup"><span data-stu-id="94c1a-117">Sales order line 2.1, which has 200 units of item C</span></span>
    2. <span data-ttu-id="94c1a-118">Linha da ordem de venda 2.2 que contém 100 unidades do item D</span><span class="sxs-lookup"><span data-stu-id="94c1a-118">Sales order line 2.2, which has 100 units of item D</span></span>

### <a name="loads-and-load-lines"></a><span data-ttu-id="94c1a-119">Cargas e linhas de carga</span><span class="sxs-lookup"><span data-stu-id="94c1a-119">Loads and load lines</span></span>

1. <span data-ttu-id="94c1a-120">Você cria uma carga 1 que contém as linhas de carga a seguir:</span><span class="sxs-lookup"><span data-stu-id="94c1a-120">You create load 1 that has the following load lines:</span></span>

    1. <span data-ttu-id="94c1a-121">Linha de carga 1.1 para linha de ordem de vendas 1.1.</span><span class="sxs-lookup"><span data-stu-id="94c1a-121">Load line 1.1 for sales order line 1.1.</span></span> <span data-ttu-id="94c1a-122">Esta linha de carga tem 30 unidades do item A.</span><span class="sxs-lookup"><span data-stu-id="94c1a-122">This load line has 30 units of item A.</span></span>
    2. <span data-ttu-id="94c1a-123">Linha de carga 1.2 para linha de ordem de vendas 1.2.</span><span class="sxs-lookup"><span data-stu-id="94c1a-123">Load line 1.2 for sales order line 1.2.</span></span> <span data-ttu-id="94c1a-124">Esta linha de carga tem 10 unidades do item B.</span><span class="sxs-lookup"><span data-stu-id="94c1a-124">This load line has 10 units of item B.</span></span>
    3. <span data-ttu-id="94c1a-125">Linha de carga 1.3 para linha de ordem de vendas 2.1.</span><span class="sxs-lookup"><span data-stu-id="94c1a-125">Load line 1.3 for sales order line 2.1.</span></span> <span data-ttu-id="94c1a-126">Esta linha de carga tem 100 unidades do item C.</span><span class="sxs-lookup"><span data-stu-id="94c1a-126">This load line has 100 units of item C.</span></span>

2. <span data-ttu-id="94c1a-127">Você cria uma carga 2 que contém as linhas de carga a seguir:</span><span class="sxs-lookup"><span data-stu-id="94c1a-127">You create load 2 that has the following load lines:</span></span>

    1. <span data-ttu-id="94c1a-128">Linha de carga 2.1 para linha de ordem de vendas 1.1.</span><span class="sxs-lookup"><span data-stu-id="94c1a-128">Load line 2.1 for sales order line 1.1.</span></span> <span data-ttu-id="94c1a-129">Esta linha de carga tem as 20 unidades restantes do item A.</span><span class="sxs-lookup"><span data-stu-id="94c1a-129">This load line has the remaining 20 units of item A.</span></span>
    2. <span data-ttu-id="94c1a-130">Linha de carga 2.2 para linha de ordem de vendas 2.1.</span><span class="sxs-lookup"><span data-stu-id="94c1a-130">Load line 2.2 for sales order line 2.1.</span></span> <span data-ttu-id="94c1a-131">Esta linha de carga tem 50 unidades do item C.</span><span class="sxs-lookup"><span data-stu-id="94c1a-131">This load line has 50 units of item C.</span></span>

### <a name="fiscal-documents"></a><span data-ttu-id="94c1a-132">Notas fiscais</span><span class="sxs-lookup"><span data-stu-id="94c1a-132">Fiscal documents</span></span>

1. <span data-ttu-id="94c1a-133">Estes documentos fiscais são gerados para a carga 1:</span><span class="sxs-lookup"><span data-stu-id="94c1a-133">The following fiscal documents are generated for load 1:</span></span>

    1. <span data-ttu-id="94c1a-134">Um documento fiscal é gerado para o cliente C1 que contém uma linha de documento fiscal para 30 unidades do item A e outra para 10 unidades do item B.</span><span class="sxs-lookup"><span data-stu-id="94c1a-134">A fiscal document for customer C1 that has one fiscal document line for 30 units of item A and another line for 10 units of item B</span></span>
    2. <span data-ttu-id="94c1a-135">Um documento fiscal é gerado para o cliente C2 que contém uma linha de documento fiscal para 100 unidades do item C.</span><span class="sxs-lookup"><span data-stu-id="94c1a-135">A fiscal document for customer C2 that has a fiscal document line for 100 units of item C</span></span>

2. <span data-ttu-id="94c1a-136">Estes documentos fiscais são gerados para a carga 2:</span><span class="sxs-lookup"><span data-stu-id="94c1a-136">The following fiscal documents are generated for load 2:</span></span>

    1. <span data-ttu-id="94c1a-137">Um documento fiscal é gerado para o cliente C1 que contém uma linha de documento fiscal para 20 unidades do item A.</span><span class="sxs-lookup"><span data-stu-id="94c1a-137">A fiscal document for customer C1 that has a fiscal document line for 20 units of item A</span></span>
    2. <span data-ttu-id="94c1a-138">Um documento fiscal é gerado para o cliente C2 que contém uma linha de documento fiscal para 50 unidades do item C.</span><span class="sxs-lookup"><span data-stu-id="94c1a-138">A fiscal document for customer C2 that has a fiscal document line for 50 units of item C</span></span>

<span data-ttu-id="94c1a-139">Siga as etapas deste tópico para gerar documentos fiscais para uma carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-139">Follow the steps in this topic to generate fiscal documents for a load.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94c1a-140">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="94c1a-140">Prerequisites</span></span>

<span data-ttu-id="94c1a-141">A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.</span><span class="sxs-lookup"><span data-stu-id="94c1a-141">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="94c1a-142">Categoria</span><span class="sxs-lookup"><span data-stu-id="94c1a-142">Category</span></span></th>
<th><span data-ttu-id="94c1a-143">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="94c1a-143">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="94c1a-144">País/região</span><span class="sxs-lookup"><span data-stu-id="94c1a-144">Country/region</span></span></td>
<td><span data-ttu-id="94c1a-145">O público-alvo principal da entidade legal deve estar no Brasil.</span><span class="sxs-lookup"><span data-stu-id="94c1a-145">The primary address for the legal entity must be in Brazil.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="94c1a-146">Tarefas de configuração relacionadas</span><span class="sxs-lookup"><span data-stu-id="94c1a-146">Related setup tasks</span></span></td>
<td>
<ul>
<li><span data-ttu-id="94c1a-147">Criar um grupo de estabelecimentos fiscais e um estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="94c1a-147">Create a fiscal establishment group and a fiscal establishment.</span></span> </li>
<li><span data-ttu-id="94c1a-148">Configurar um tipo de documento fiscal e, em seguida, atribuí-lo a clientes, fornecedores ou itens de estoque.</span><span class="sxs-lookup"><span data-stu-id="94c1a-148">Set up a fiscal document type, and then assign it to customers, vendors, or inventory items.</span></span></li>
<li><span data-ttu-id="94c1a-149">Configurar uma transportadora de gerenciamento de transporte que contém o mesmo fornecedor que o especificado no campo de <strong>Conta do fornecedor</strong> no formulário de <strong>Transportadora</strong> no módulo <strong>Vendas e marketing</strong>.</span><span class="sxs-lookup"><span data-stu-id="94c1a-149">Set up a transportation management shipping carrier that has the same vendor that you specified in the <strong>Vendor account</strong> field in the <strong>Carrier</strong> form in the <strong>Sales and Marketing</strong> module.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="94c1a-150">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="94c1a-150">Related task</span></span></td>
<td><span data-ttu-id="94c1a-151">Criar uma carga de saída para uma remessa.</span><span class="sxs-lookup"><span data-stu-id="94c1a-151">Create an outbound load for a shipment.</span></span></td>
</tr>
</tbody>
</table>

## <a name="generate-fiscal-documents-for-a-load"></a><span data-ttu-id="94c1a-152">Gerar documentos fiscais para uma carga</span><span class="sxs-lookup"><span data-stu-id="94c1a-152">Generate fiscal documents for a load</span></span>

<span data-ttu-id="94c1a-153">Use o formulário **Cargas** para exibir as cargas, selecione uma carga com uma remessa confirmada.</span><span class="sxs-lookup"><span data-stu-id="94c1a-153">Use the **Loads** form to view the loads, and then select a load that has a confirmed shipment.</span></span> <span data-ttu-id="94c1a-154">Em seguida, você pode usar o formulário **Lançando fatura** para lançar ordens de venda e gerar documentos fiscais para uma carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-154">You can then use the **Posting invoice** form to post sales orders and generate fiscal documents for that load.</span></span>

<span data-ttu-id="94c1a-155">Siga essas etapas para concluir essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="94c1a-155">Follow these steps to complete this task.</span></span>

1. <span data-ttu-id="94c1a-156">Clique em **Contas a receber** \> **Periódico** \> **Atualização de vendas** \> **Cargas**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-156">Click **Accounts receivable** \> **Periodic** \> **Sales update** \> **Loads**.</span></span>
2. <span data-ttu-id="94c1a-157">No formulário **Cargas**, selecione uma carga que contenha uma remessa confirmada, e verifique o código de identificação, o status, a direção, o local, depósito e a remessa de carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-157">In the **Loads** form, select a load that has a confirmed shipment, and verify the identification code, status, direction, site, warehouse, and shipment of the load.</span></span>

    | <span data-ttu-id="94c1a-158">Campo</span><span class="sxs-lookup"><span data-stu-id="94c1a-158">Field</span></span>                                 | <span data-ttu-id="94c1a-159">descrição</span><span class="sxs-lookup"><span data-stu-id="94c1a-159">Description</span></span> |
    |---------------------------------------|-------------|
    | <span data-ttu-id="94c1a-160">ID da Carga</span><span class="sxs-lookup"><span data-stu-id="94c1a-160">Load ID</span></span>                               | <span data-ttu-id="94c1a-161">O código de identificação da remessa.</span><span class="sxs-lookup"><span data-stu-id="94c1a-161">The identification code of the shipment.</span></span> |
    | <span data-ttu-id="94c1a-162">Status da carga</span><span class="sxs-lookup"><span data-stu-id="94c1a-162">Load status</span></span>                           | <span data-ttu-id="94c1a-163">O status da carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-163">The status of the load.</span></span> <span data-ttu-id="94c1a-164">O status pode ser **Enviado**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-164">The status can be **Shipped**.</span></span> |
    | <span data-ttu-id="94c1a-165">Direção</span><span class="sxs-lookup"><span data-stu-id="94c1a-165">Direction</span></span>                             | <span data-ttu-id="94c1a-166">A direção da carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-166">The direction of the load.</span></span> <span data-ttu-id="94c1a-167">A direção pode ser **Saída**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-167">The direction can be **Outbound**.</span></span> |
    | <span data-ttu-id="94c1a-168">Site</span><span class="sxs-lookup"><span data-stu-id="94c1a-168">Site</span></span>                                  | <span data-ttu-id="94c1a-169">O local no qual a carga é separada.</span><span class="sxs-lookup"><span data-stu-id="94c1a-169">The site that the load is picked up from.</span></span> |
    | <span data-ttu-id="94c1a-170">Depósito</span><span class="sxs-lookup"><span data-stu-id="94c1a-170">Warehouse</span></span>                             | <span data-ttu-id="94c1a-171">O depósito no qual a carga é separada.</span><span class="sxs-lookup"><span data-stu-id="94c1a-171">The warehouse that the load is picked up from.</span></span> |
    | <span data-ttu-id="94c1a-172">ID da Remessa</span><span class="sxs-lookup"><span data-stu-id="94c1a-172">Shipment ID</span></span>                           | <span data-ttu-id="94c1a-173">O código de identificação da remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-173">The identification code of the load shipment.</span></span> |
    | <span data-ttu-id="94c1a-174">Data e a hora da remessa de carga agendada</span><span class="sxs-lookup"><span data-stu-id="94c1a-174">Scheduled load shipping date and time</span></span> | <span data-ttu-id="94c1a-175">A data e a hora agendadas para remessa de carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-175">The scheduled date and time of the load shipment.</span></span> |

3. <span data-ttu-id="94c1a-176">Clique em **Fatura** para abrir o formulário **Lançamento de fatura**, no qual você pode exibir as linhas da ordem de venda para as quais a carga foi criada.</span><span class="sxs-lookup"><span data-stu-id="94c1a-176">Click **Invoice** to open the **Posting invoice** form, where you can view the sales order lines that the load is created for.</span></span> <span data-ttu-id="94c1a-177">As linhas contêm somente as quantidades de linha da carga.</span><span class="sxs-lookup"><span data-stu-id="94c1a-177">The lines have only the load line quantities.</span></span>
4. <span data-ttu-id="94c1a-178">Marque a caixa de seleção **Lançamento** para lançar as ordens de venda para a carga para gerar documentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="94c1a-178">Select the **Posting** check box to post the sales orders for the load to generate fiscal documents.</span></span>
5. <span data-ttu-id="94c1a-179">Especifica qualquer linha adicional de detalhes necessária.</span><span class="sxs-lookup"><span data-stu-id="94c1a-179">Specify any additional details that are required.</span></span> 
6. <span data-ttu-id="94c1a-180">Clique em **OK** para lançar ordens de venda para a carga e gerar os documentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="94c1a-180">Click **OK** to post the sales orders for the load and generate the fiscal documents.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="94c1a-181">Informações técnicas para administradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="94c1a-181">Technical information for system administrators</span></span>

<span data-ttu-id="94c1a-182">Se você não tiver acesso às páginas que são usadas para concluir essa tarefa, entre em contato com o administrador do sistema e forneça as informações que são mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="94c1a-182">If you don't have access to the pages that are used to complete this task, contact your system admin, and provide the information in the following table.</span></span>

| <span data-ttu-id="94c1a-183">Categoria</span><span class="sxs-lookup"><span data-stu-id="94c1a-183">Category</span></span>                      | <span data-ttu-id="94c1a-184">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="94c1a-184">Prerequisite</span></span> |
|-------------------------------|--------------|
| <span data-ttu-id="94c1a-185">Chaves de configuração</span><span class="sxs-lookup"><span data-stu-id="94c1a-185">Configuration keys</span></span>            | <span data-ttu-id="94c1a-186">Clique em **Administração do sistema** &gt; **Configuração** &gt; **Licença** &gt; **Configuração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-186">Click **System administration** &gt; **Setup** &gt; **Licensing** &gt; **License configuration**.</span></span> <span data-ttu-id="94c1a-187">Expanda a chave de licença de **Comércio** e selecione a chave de configuração **gerenciamento de Depósito e Transporte**.</span><span class="sxs-lookup"><span data-stu-id="94c1a-187">Expand the **Trade** license key, and then select the **Warehouse and Transportation management** configuration key.</span></span> |
| <span data-ttu-id="94c1a-188">Funções de segurança e direitos</span><span class="sxs-lookup"><span data-stu-id="94c1a-188">Security roles and duties</span></span>     | <span data-ttu-id="94c1a-189">Para executar essa tarefa, você deve ser membro da função de segurança que inclui o direito **Manter transações da fatura de cliente** (CustInvoiceCustomerInvoiceTransMaintain).</span><span class="sxs-lookup"><span data-stu-id="94c1a-189">To perform this task, you must be a member of a security role that includes the **Maintain customer invoice transactions** (CustInvoiceCustomerInvoiceTransMaintain) duty.</span></span> |
| <span data-ttu-id="94c1a-190">Funções de segurança e privilégios</span><span class="sxs-lookup"><span data-stu-id="94c1a-190">Security roles and privileges</span></span> | <span data-ttu-id="94c1a-191">Para executar essa tarefa, você deve ser membro de uma função de segurança que inclua o privilégio **Cargas** (WHSLoadTableInvoicePost\_BR).</span><span class="sxs-lookup"><span data-stu-id="94c1a-191">To perform this task, you must be a member of a security role that includes the **Loads** (WHSLoadTableInvoicePost\_BR) privilege.</span></span> |
