---
title: Integração de ativos fixos
description: Ativos fixos podem ser integrados à Contabilidade, ao Gerenciamento de estoque, a Contas a receber e a Contas a pagar. Você também pode configurar os Ativos fixos para que sejam integrados às ordens de compra.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fb1348a3a3c47e5fd7df46d9ce4af3725d8896b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176398"
---
# <a name="fixed-assets-integration"></a><span data-ttu-id="e6ae1-104">Integração de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="e6ae1-104">Fixed assets integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6ae1-105">Ativos fixos podem ser integrados à Contabilidade, ao Gerenciamento de estoque, a Contas a receber e a Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-105">Fixed assets can be integrated with General ledger, Inventory management, Accounts receivable, and Accounts payable.</span></span> <span data-ttu-id="e6ae1-106">Você também pode configurar os Ativos fixos para que sejam integrados às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-106">You can also set up Fixed assets so that it is integrated with purchase orders.</span></span>

<a name="general-ledger"></a><span data-ttu-id="e6ae1-107">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="e6ae1-107">General ledger</span></span>
--------------

<span data-ttu-id="e6ae1-108">Na Contabilidade, o valor de todos os ativos fixos geralmente é resumido em várias contas principais que são exigidas para relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-108">In General ledger, the value of all fixed assets is typically summarized in multiple main accounts that are required for financial reporting.</span></span> <span data-ttu-id="e6ae1-109">No entanto, na página **Ativos fixos**, você pode criar muitos registros de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-109">However, on the **Fixed assets** page, you can create many fixed asset records.</span></span> <span data-ttu-id="e6ae1-110">Esses registros podem incluir informações como preço de aquisição, depreciação e avaliação.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-110">These records can include information such as the acquisition price, depreciation, and valuation.</span></span> <span data-ttu-id="e6ae1-111">Toda vez que você lançar uma transação para um ativo fixo, as contas principais adequadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-111">Each time that you post a transaction for a fixed asset, the appropriate main accounts are updated.</span></span> <span data-ttu-id="e6ae1-112">As contas principais dos ativos fixos sempre mostram o valor atualizado dos ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-112">The main accounts for fixed assets always show the updated value of the fixed assets.</span></span>

<span data-ttu-id="e6ae1-113">Na página **Perfis de lançamentos de ativo fixo**, você define as contas principais nas quais as transações do registro de ativo fixo são lançadas.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-113">On the **Fixed asset posting profiles** page, you define the main accounts that fixed asset book transactions are posted to.</span></span> <span data-ttu-id="e6ae1-114">Você também pode especificar os tipos de transações de ativo fixo que serão lançados em cada conta principal.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-114">You also specify the types of fixed asset transactions that are posted to each main account.</span></span> <span data-ttu-id="e6ae1-115">É possível criar várias combinações de contas principais de ativos fixos, dependendo do nível de detalhes que você deseja para os ativos fixos na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-115">You can create various combinations of main accounts for fixed assets, depending on the level of detail that you want for fixed assets in the general ledger.</span></span> <span data-ttu-id="e6ae1-116">As contas principais podem ser baseadas nos tipos de transação, nos registros e em outras contas principais.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-116">Main accounts can be based on transaction types, books, and other main accounts.</span></span>

## <a name="inventory-management"></a><span data-ttu-id="e6ae1-117">Gerenciamento de estoque</span><span class="sxs-lookup"><span data-stu-id="e6ae1-117">Inventory management</span></span>
<span data-ttu-id="e6ae1-118">No diário de estoque para ativos fixos, você pode inserir a aquisição de ativos fixos que a entidade legal gerou ou construiu para si própria.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-118">In the inventory journal for fixed assets, you can enter the acquisition of fixed assets that the legal entity has produced or constructed for itself.</span></span> <span data-ttu-id="e6ae1-119">Você pode então transferir itens de estoque para ativos fixos como uma aquisição ou como parte de uma aquisição.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-119">You can then transfer inventory items to fixed assets either as an acquisition or as part of an acquisition.</span></span> 

<span data-ttu-id="e6ae1-120">Também é possível adquirir ativos usando ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-120">You can also acquire assets by using purchase orders.</span></span> <span data-ttu-id="e6ae1-121">Quando as ordens de compra contêm itens de estoque designados como ativos fixos, a configuração da opção **Permitir a aquisição de ativos de Compras** na página **Parâmetros de ativos fixos** determina se uma aquisição é lançada para o ativo fixo quando a fatura é lançada.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-121">When purchase orders contain inventory items that are designated as fixed assets, the setting of the **Allow asset acquisition from Purchasing** option on the **Fixed assets parameters** page determines whether an acquisition is posted for the fixed asset when the invoice is posted.</span></span> <span data-ttu-id="e6ae1-122">Uma linha de compras criará um ativo fixo, independentemente da quantidade.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-122">One purchasing line will create one fixed asset, regardless of the quantity.</span></span> <span data-ttu-id="e6ae1-123">O impacto que a aquisição de ativos fixos tem no estoque depende da configuração da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-123">The effect that the acquisition of fixed assets has on inventory depends on the setup of the legal entity.</span></span> 

<span data-ttu-id="e6ae1-124">Quando um item de estoque se torna uma aquisição de ativo fixo, por meio do diário de estoque, uma ordem de compra ou uma proposta de aquisição, é criada uma transação de aquisição de registros de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-124">When an inventory item becomes a fixed asset acquisition through the inventory journal, a purchase order, or an acquisition proposal, a fixed asset book acquisition transaction is created.</span></span> <span data-ttu-id="e6ae1-125">Se uma aquisição de registros incluir um registro de depreciações derivado, também será criada uma transação de aquisição de registro de depreciações.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-125">If a book acquisition includes a derived book, the derived book acquisition transaction is also created.</span></span> 

<span data-ttu-id="e6ae1-126">Postar regras que são definidas na página **Postagem** em controle de gerenciamento de estoque diminui em estoque quando uma aquisição é postada.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-126">Posting rules that are set up on the **Posting** page in Inventory management control the decrease in inventory when an acquisition is posted.</span></span> <span data-ttu-id="e6ae1-127">No entanto, nem sempre é necessário diminuir o estoque ao lançar faturas relacionadas a ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-127">However, you don’t always decrease inventory when you post invoices that are related to fixed assets.</span></span> <span data-ttu-id="e6ae1-128">Em alguns casos, os ativos fixos podem ser comprados para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-128">In some cases, the fixed assets might be purchased for internal use.</span></span> <span data-ttu-id="e6ae1-129">Um exemplo é gerado um laptop comprado para o departamento de vendas.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-129">An example is a laptop that is purchased for the sales department.</span></span> <span data-ttu-id="e6ae1-130">Ao trabalhar com ordens de compra, é possível usar itens configurados tanto para a revenda com para o uso interno.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-130">When you work with purchase orders, you can use items that are set up for both resale and internal use.</span></span> 

<span data-ttu-id="e6ae1-131">Se você usar contas específicas de recebimento e saída em grupos de itens para ativos fixos, é possível usar o mesmo item de estoque para compras internas e como estoque para revenda.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-131">If you use specific receipt and issue accounts on item groups for fixed assets, you can use the same inventory item both for internal purchases and as stock for resale.</span></span> 

<span data-ttu-id="e6ae1-132">Os ativos fixos para uso interno são configurados de forma que tenham um tipo de conta **Recebimento de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-132">Fixed assets that are for internal use are set up so that they have an account type of **Fixed asset receipt**.</span></span> <span data-ttu-id="e6ae1-133">Esse tipo de conta é usado para rastrear o recebimento do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-133">This account type is used to track the receipt of the fixed asset.</span></span> <span data-ttu-id="e6ae1-134">Ao lançar uma fatura de fornecedor, use a conta de recebimento de ativo fixo se qualquer uma das seguintes condições se aplicar:</span><span class="sxs-lookup"><span data-stu-id="e6ae1-134">When you post a vendor invoice, use the fixed asset receipt account if any of the following conditions is true:</span></span>

-   <span data-ttu-id="e6ae1-135">A linha da fatura contém um ativo fixo existente para fins internos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-135">The invoice line contains an existing fixed asset for internal purposes.</span></span>
-   <span data-ttu-id="e6ae1-136">A caixa de seleção **Novo ativo fixo?** está marcada para a linha de recebimento de produtos que foi lançada.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-136">The **New fixed asset?** check box is selected for the product receipt line that is posted.</span></span>
-   <span data-ttu-id="e6ae1-137">A caixa de seleção **Criar um novo ativo fixo** é selecionada para a linha de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-137">The **Create a new fixed** asset check box is selected for the vendor invoice line.</span></span>

<span data-ttu-id="e6ae1-138">Essa conta é tipicamente uma conta de despesa.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-138">Typically, this account is an expense account.</span></span> <span data-ttu-id="e6ae1-139">É possível configurar o tipo de conta **Recebimento de ativo fixo** para um grupo de itens ou para um item individual usando a guia **Ordem de compra** nas páginas **Grupo de itens** ou **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-139">You can set up the **Fixed asset receipt** account type for either an item group or an individual item by using the **Purchase order** tab on the **Item group** or **Posting** page.</span></span>

<span data-ttu-id="e6ae1-140">Da mesma forma, os ativos fixos para uso interno podem ser configurados de forma que tenham um tipo de conta **Emissão de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-140">Similarly, fixed assets that are for internal use can be set up so that they have an account type of **Fixed asset issue**.</span></span> <span data-ttu-id="e6ae1-141">Esse tipo de conta é usado para rastrear a emissão do ativo fixo ao destinatário.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-141">This account type is used to track the issuing of the fixed asset to the recipient.</span></span> <span data-ttu-id="e6ae1-142">Quando um ativo é adquirido usando uma ordem de compra, a conta de saída do ativo fixo compensa a conta de débito do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-142">When an asset is acquired by using a purchase order, the fixed asset issue account offsets the fixed asset debit account.</span></span> <span data-ttu-id="e6ae1-143">A aquisição de ativo pode ser lançada ao lançar uma fatura de fornecedor ou ao lançar a aquisição do ativo no diário Ativos fixos, provavelmente usando uma proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-143">The asset acquisition can be posted either when you post a vendor invoice or when you post the asset acquisition in the Fixed assets journal, possibly by using an acquisition proposal.</span></span> <span data-ttu-id="e6ae1-144">É possível configurar o tipo de conta **Emissão de ativo fixo** para um grupo de itens ou para um item individual usando a guia **Estoque** nas páginas **Grupo de itens** ou **Lançamento de item**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-144">You can set up the **Fixed asset issue** account type for either an item group or an individual item by using the **Inventory** tab on the **Item group** or **Item posting** page.</span></span> 

<span data-ttu-id="e6ae1-145">Por fim, as contas principais que são usadas para lançamento são determinadas pelas opções para integração do razão que são especificadas para o grupo de modelos de item.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-145">Ultimately, the main accounts that are used for posting are determined by the options for ledger integration that are specified for the item model group.</span></span> <span data-ttu-id="e6ae1-146">Além disso, as contas principais que são usadas variam, dependendo de um ativo ter sido atribuído à linha de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-146">Additionally, the main accounts that are used vary, depending on whether an asset is assigned to the purchase order line.</span></span> <span data-ttu-id="e6ae1-147">As contas são derivadas do perfil de lançamento para cada grupo de itens.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-147">The accounts are derived from the posting profile for each item group.</span></span> 
<span data-ttu-id="e6ae1-148">**Observação:** Se uma reserva de estoque existir quando recebimentos de produtos forem lançados, você não poderá atribuir um ativo fixo nem criar um ativo fixo a partir da linha.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-148">**Note:** If an inventory reservation exists when product receipts are posted, you can’t assign a fixed asset or create a fixed asset from the line.</span></span> 

<span data-ttu-id="e6ae1-149">As contas em que as transações de ativo fixo serão lançadas dependerão de dois fatores: da origem dos ativos, se eles serão comprados ou construídos pela entidade legal, e do tipo de transação do ativo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-149">The accounts that fixed asset transactions are posted to depend on two factors: whether the assets are purchased or constructed by the legal entity, and the transaction type of the asset.</span></span> 

<span data-ttu-id="e6ae1-150">O tipo de transação conecta a transação de estoque ao perfil de lançamentos nos Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-150">The transaction type connects the inventory transaction to the posting profile in Fixed assets.</span></span> <span data-ttu-id="e6ae1-151">Como o perfil de lançamentos nos Ativos fixos define quais contas serão atualizadas, a seleção de um tipo de transação para um ativo fixo também será, indiretamente, uma seleção das contas principais em que a transação será lançada.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-151">Because the posting profile in Fixed assets defines which accounts are updated, the selection of a transaction type for a fixed asset is also, indirectly, the selection of the main accounts that the transaction is posted to.</span></span> <span data-ttu-id="e6ae1-152">Para os ativos fixos construídos e comprados, o tipo de transação geralmente será **Aquisição** ou **Ajuste de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-152">For both constructed and purchased fixed assets, the transaction type is typically **Acquisition** or **Acquisition adjustment**.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="e6ae1-153">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="e6ae1-153">Accounts receivable</span></span>
<span data-ttu-id="e6ae1-154">A integração de Ativos fixos com Contas a receber usa perfis de lançamento que são configurados nos Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-154">The integration of Fixed assets with Accounts receivable uses posting profiles that are set up in Fixed assets.</span></span> <span data-ttu-id="e6ae1-155">Esses perfis de lançamento são ativados quando um ativo fixo, registro e tipo de transação de ativo fixo são selecionados para uma fatura de cliente antes de seu lançamento.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-155">These posting profiles are activated when a fixed asset, book, and fixed asset transaction type are selected for a customer invoice before the customer invoice is posted.</span></span> <span data-ttu-id="e6ae1-156">Como os ativos fixos não fazem parte do gerenciamento de estoque, você deverá usar a página **Fatura de texto livre** quando vender um ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-156">Because fixed assets aren’t part of Inventory management, you must use the **Free text invoice** page when you sell a fixed asset.</span></span> 

<span data-ttu-id="e6ae1-157">Se o registro incluir um registro de depreciações derivadas, uma transação de registro de depreciações será criada no lançamento da fatura do cliente.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-157">If the book includes a derived book, the derived book transaction is created when you post the customer invoice.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="e6ae1-158">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="e6ae1-158">Accounts payable</span></span>
<span data-ttu-id="e6ae1-159">Os ativos fixos são normalmente adquiridos de fornecedores externos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-159">Typically, fixed assets are acquired from external vendors.</span></span> <span data-ttu-id="e6ae1-160">Você pode usar a página **Parâmetros de ativos fixos** para especificar se as aquisições de ativo são sempre lançadas quando as faturas de fornecedor são lançadas, ou se as aquisições de ativo podem ser lançadas somente de Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-160">You can use the **Fixed assets parameters** page to specify whether asset acquisitions are always posted when you post vendor invoices, or whether asset acquisitions can be posted only from Fixed assets.</span></span> <span data-ttu-id="e6ae1-161">Se você permitir que aquisições de ativos sejam lançadas de Contas a pagar, as contas de ativo fixo serão atualizadas sempre que uma fatura de fornecedor para uma aquisição de ativo fixo for lançada.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-161">If you enable asset acquisitions to be posted from Accounts payable, fixed asset accounts are updated whenever a vendor invoice for a fixed asset acquisition is posted.</span></span> 

<span data-ttu-id="e6ae1-162">Se o sistema estiver configurado para lançar uma aquisição de ativo quando uma fatura for lançada, a transação será lançada de acordo com os perfis de lançamentos configurados nos Ativos fixos para os diversos tipos de transação de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-162">If the system is set up to post an asset acquisition when an invoice is posted, the transaction is posted according to the posting profiles that are set up in Fixed assets for the various fixed asset transaction types.</span></span> <span data-ttu-id="e6ae1-163">O lançamento é controlado pelo ativo fixo, registro e tipo de transação de ativo fixo que são selecionados na página **Ordem de compra** antes do lançamento da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-163">The posting is controlled by the fixed asset, book, and fixed asset transaction type that are selected on the **Purchase order** page before the vendor invoice is posted.</span></span> 

<span data-ttu-id="e6ae1-164">Se o registro incluir um registro de depreciações derivadas, uma transação de registro de depreciações será criada no lançamento da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-164">If the book includes a derived book, the derived book transaction is created when you post the vendor invoice.</span></span>

<span data-ttu-id="e6ae1-165">A integração de cada linha da ordem é ativada na guia **Ativos fixos** da **Guia Rápida Detalhes** da linha na página **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-165">The integration for each order line is activated on the **Fixed assets** tab on the **Line details** FastTab on the **Purchase order** page.</span></span> <span data-ttu-id="e6ae1-166">Você pode enviar uma ordem de compra para um ativo fixo ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-166">You can send a purchase order for a fixed asset to the vendor.</span></span> <span data-ttu-id="e6ae1-167">No entanto, os ativos fixos e as contas principais são atualizados somente quando você lança a fatura de fornecedor depois que o ativo fixo é recebido.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-167">However, the fixed assets and main accounts are updated only when you post the vendor invoice after the fixed asset is received.</span></span> <span data-ttu-id="e6ae1-168">Como as ordens de compra podem conter somente itens de estoque, o impacto que a aquisição de ativos fixos tem no estoque dependerá da configuração da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-168">Because purchase orders can contain only inventory items, the effect that the acquisition of fixed assets has on inventory depends on the setup of the legal entity.</span></span>

## <a name="project-management-and-accounting"></a><span data-ttu-id="e6ae1-169">Gerenciamento de projetos e de contabilidade</span><span class="sxs-lookup"><span data-stu-id="e6ae1-169">Project management and accounting</span></span>
<span data-ttu-id="e6ae1-170">É possível associar um projeto com um ativo que é afetado pelo projeto.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-170">You can associate a project with an asset that is affected by the project.</span></span> <span data-ttu-id="e6ae1-171">Também é possível associar cada fase, tarefa ou subprojeto a um ativo diferente.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-171">You can also associate each phase, task, or subproject to a different asset.</span></span> <span data-ttu-id="e6ae1-172">Um ativo pode ser associado a cada registro do projeto.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-172">One asset can be associated with each project record.</span></span> <span data-ttu-id="e6ae1-173">Você criar a associação ao inserir um número de ativo fixo no campo Número de **ativo fixo** na página **Projetos**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-173">You create the association when you enter a fixed asset number in the **Fixed asset** number field on the **Projects** page.</span></span> <span data-ttu-id="e6ae1-174">O tipo de projeto deve ser **Interno** ou de **Custo**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-174">The project type must be either **Internal** or **Cost project**.</span></span> 

<span data-ttu-id="e6ae1-175">Também é possível usar a página **Projetos** para exibir os detalhes sobre os ativos associados aos projetos.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-175">You can also use the **Projects** page to view details about assets that are associated with projects.</span></span> <span data-ttu-id="e6ae1-176">Para exibir o registro de ativo fixo, clique no link do ativo na Guia Rápida **Configuração** para abrir a página **Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-176">To view the fixed asset record, on the **Setup** FastTab, click the asset link to open the **Fixed assets** page.</span></span> <span data-ttu-id="e6ae1-177">Em seguida, clique em **Projetos** &gt; **Todos os projetos** para exibir os projetos que estão associados ao ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-177">Then click **Projects** &gt; **All projects** to view the projects that are associated with the fixed asset.</span></span> 

<span data-ttu-id="e6ae1-178">É possível associar tipicamente ativos fixos a projetos quando os projetos estão relacionados com trabalho, manutenção ou melhorias para o ativo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-178">Typically, you associate fixed assets with projects when the projects are related to work, maintenance, or improvements for the asset.</span></span> <span data-ttu-id="e6ae1-179">Quando o projeto é concluído, um ajuste de valorização para o ativo não será criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-179">When the project is completed, a write-up adjustment for the asset isn’t created automatically.</span></span> <span data-ttu-id="e6ae1-180">Portanto, você deverá criar o ajuste de valorização manualmente, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-180">Therefore, if a write-up adjustment is required, you must create it manually.</span></span> 

<span data-ttu-id="e6ae1-181">Para excluir a associação entre um projeto e um ativo, desmarque o campo **Número do ativo fixo** na página **Projetos**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-181">To delete the association between a project and an asset, clear the **Fixed asset number** field on the **Projects** page.</span></span> 

<span data-ttu-id="e6ae1-182">Também é possível designar um ativo fixo que você está criando ou fabricando como parte de um projeto estimado.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-182">You can also designate a fixed asset that you’re creating or manufacturing as part of an estimate project.</span></span> <span data-ttu-id="e6ae1-183">No fim de um projeto previsto, você pode lançar automaticamente uma transação de aquisição de ativo.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-183">At the end of an estimate project, you can automatically post an asset acquisition transaction.</span></span>

<span data-ttu-id="e6ae1-184">Para obter mais informações, consulte [Adquirir ativos por meio de compras](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae1-184">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md)</span></span>


