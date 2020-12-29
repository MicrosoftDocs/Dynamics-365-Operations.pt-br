---
title: Solucionar problemas de informações do produto
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com informações do produto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 87b04998889b86a79fd8dabde422147c5494b003
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516729"
---
# <a name="troubleshoot-product-information"></a><span data-ttu-id="a3e69-103">Solucionar problemas de informações do produto</span><span class="sxs-lookup"><span data-stu-id="a3e69-103">Troubleshoot product information</span></span>

<span data-ttu-id="a3e69-104">Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com informações do produto.</span><span class="sxs-lookup"><span data-stu-id="a3e69-104">This topic describes how to fix issues that you might encounter while you work with product information.</span></span>

## <a name="i-cant-delete-a-released-product"></a><span data-ttu-id="a3e69-105">Não consigo excluir um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-105">I can't delete a released product.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-106">Issue description</span></span>

<span data-ttu-id="a3e69-107">É possível excluir um produto liberado e todas as suas variantes somente se o produto liberado não tiver nenhuma transação relacionada.</span><span class="sxs-lookup"><span data-stu-id="a3e69-107">You can delete a released product and all its variants only if the released product doesn't have any related transactions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-108">Issue resolution</span></span>

<span data-ttu-id="a3e69-109">Siga as etapas a seguir para excluir um produto liberado ou produto mestre.</span><span class="sxs-lookup"><span data-stu-id="a3e69-109">Follow these steps to delete a released product or product master.</span></span>

1. <span data-ttu-id="a3e69-110">Feche todas as transações em aberto para os itens.</span><span class="sxs-lookup"><span data-stu-id="a3e69-110">Close all open transactions for the items.</span></span>
1. <span data-ttu-id="a3e69-111">Reduza o estoque a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a3e69-111">Reduce the inventory to 0 (zero).</span></span>
1. <span data-ttu-id="a3e69-112">Realize o fechamento do estoque.</span><span class="sxs-lookup"><span data-stu-id="a3e69-112">Perform inventory closing.</span></span>
1. <span data-ttu-id="a3e69-113">Exclua todas as variantes do produto para o produto mestre que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="a3e69-113">Delete all product variants for the product master that you want to delete.</span></span>

## <a name="can-i-change-the-item-number-of-a-released-product"></a><span data-ttu-id="a3e69-114">Posso alterar o número do item de um produto liberado?</span><span class="sxs-lookup"><span data-stu-id="a3e69-114">Can I change the item number of a released product?</span></span>

<span data-ttu-id="a3e69-115">Na maioria dos casos, não é possível editar os números dos itens para produtos liberados, porque essa alteração fará com que os dados sejam corrompidos.</span><span class="sxs-lookup"><span data-stu-id="a3e69-115">In most cases, you can't edit item numbers for released products, because that change will cause data to become corrupted.</span></span> <span data-ttu-id="a3e69-116">Você pode editar o número do item apenas se precisar reparar dados corrompidos por uma renomeação anterior da chave primária desse produto liberado, conforme mencionado na lista de [recursos removidos ou preteridos do Finance and Operations 10.0.0 com atualização da plataforma 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="a3e69-116">You can edit the item number only if you must repair data corruption that was caused by a previous rename of the primary key of that released product, as mentioned in the list of [removed or deprecated features for Finance and Operations 10.0.0 with Platform update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).</span></span>

<span data-ttu-id="a3e69-117">Se você quiser editar os números dos itens de produtos liberados, [vote nessa ideia no portal de ideias](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span><span class="sxs-lookup"><span data-stu-id="a3e69-117">If you want to be able to edit item numbers for released products, [vote for this idea in Ideas portal](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).</span></span>

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a><span data-ttu-id="a3e69-118">O princípio de liberação padrão do produto não está sendo inserido na linha da lista de materiais.</span><span class="sxs-lookup"><span data-stu-id="a3e69-118">The default flushing principle from the product isn't being entered on the bill of materials line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-119">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-119">Issue description</span></span>

<span data-ttu-id="a3e69-120">Quando você adiciona um item a uma linha de lista de materiais (BOM), o sistema não usa as informações do princípio de liberação padrão configuradas para o item.</span><span class="sxs-lookup"><span data-stu-id="a3e69-120">When you add an item to a bill of materials (BOM) line, the system doesn't use the default flushing principle information that is set up for the item.</span></span> <span data-ttu-id="a3e69-121">Em outras palavras, o princípio de liberação do item não aparece na página **Linha BOM**.</span><span class="sxs-lookup"><span data-stu-id="a3e69-121">In other words, the flushing principle from the item doesn't appear on the **BOM line** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-122">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-122">Issue resolution</span></span>

<span data-ttu-id="a3e69-123">Se você especificar um princípio de liberação em uma linha BOM, ele se aplicará a essa linha BOM.</span><span class="sxs-lookup"><span data-stu-id="a3e69-123">If you specify a flushing principle on a BOM line, it will apply to that BOM line.</span></span> <span data-ttu-id="a3e69-124">Contudo, se o princípio de liberação estiver em branco ou se não for definido em uma linha BOM, o princípio de liberação definido no item ainda se aplicará a essa linha BOM, embora não seja mostrado nela.</span><span class="sxs-lookup"><span data-stu-id="a3e69-124">However, if the flushing principle is blank, or if it isn't set on a BOM line, the flushing principle that is set on the item will still apply to that BOM line, even though it isn't shown on the BOM line.</span></span>

<span data-ttu-id="a3e69-125">A lógica padrão para outros recursos no Microsoft Dynamics 365 Supply Chain Management geralmente não funciona dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="a3e69-125">The defaulting logic for other features in Microsoft Dynamics 365 Supply Chain Management doesn't usually work in this way.</span></span> <span data-ttu-id="a3e69-126">No entanto, o comportamento atual não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-126">However, the current behavior can't be changed.</span></span> <span data-ttu-id="a3e69-127">Caso contrário, algumas personalizações existentes que dependem dele podem ser interrompidas.</span><span class="sxs-lookup"><span data-stu-id="a3e69-127">Otherwise, some existing customizations that rely on it might be broken.</span></span>

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a><span data-ttu-id="a3e69-128">O sistema me permite salvar códigos de barras duplicados para itens diferentes ou para o mesmo item que possui dimensões diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3e69-128">The system lets me save duplicate bar codes for different items or for the same item that has different dimensions.</span></span>

<span data-ttu-id="a3e69-129">Atualmente, o sistema não impõe códigos de barras exclusivos e a adição dessa restrição seria uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="a3e69-129">The system doesn't currently enforce unique bar codes, and the addition of this restriction would be a breaking change.</span></span> <span data-ttu-id="a3e69-130">Na verdade, a Microsoft tem evidências de que algumas instalações existentes do cliente seriam interrompidas por essa mudança.</span><span class="sxs-lookup"><span data-stu-id="a3e69-130">In fact, Microsoft has evidence that some existing customer installations would be broken by this change.</span></span> <span data-ttu-id="a3e69-131">Entretanto, consideraremos uma mudança de design mais ampla para habilitar esse recurso no futuro.</span><span class="sxs-lookup"><span data-stu-id="a3e69-131">However, we will consider a broader design change to enable this feature in the future.</span></span>

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a><span data-ttu-id="a3e69-132">Recebo a seguinte mensagem de erro quando edito modelos de registro de item: "O local do depósito não pode ser criado porque o item não está em estoque.</span><span class="sxs-lookup"><span data-stu-id="a3e69-132">I receive the following error message when I edit item record templates: "The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="a3e69-133">Para itens de estoque, a opção de produto em estoque no grupo de modelo de item associado deve ser selecionada."</span><span class="sxs-lookup"><span data-stu-id="a3e69-133">To stock items, the Stocked product option on the associated item model group must be selected."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-134">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-134">Issue description</span></span>

<span data-ttu-id="a3e69-135">Esse problema ocorre se você seguir essas etapas para tentar criar um modelo para um item que não está em estoque.</span><span class="sxs-lookup"><span data-stu-id="a3e69-135">This issue occurs if you follow these steps to try to create a template for an item that isn't stocked.</span></span>

1. <span data-ttu-id="a3e69-136">Abra um produto liberado que não está em estoque.</span><span class="sxs-lookup"><span data-stu-id="a3e69-136">Open a released product that isn't stocked.</span></span>
1. <span data-ttu-id="a3e69-137">No Painel de ações, na guia **Opções**, selecione **Informações sobre registro**.</span><span class="sxs-lookup"><span data-stu-id="a3e69-137">On the Action Pane, on the **Options** tab, select **Record info**.</span></span>
1. <span data-ttu-id="a3e69-138">Na caixa de diálogo **Informações sobre registro**, selecione **Modelo de contas da empresa**.</span><span class="sxs-lookup"><span data-stu-id="a3e69-138">In the **Record information** dialog box, select **Company accounts template**.</span></span>

<span data-ttu-id="a3e69-139">Nesse caso, você receberá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="a3e69-139">In this case, you receive the following error message:</span></span>

> <span data-ttu-id="a3e69-140">O local do depósito não pode ser criado porque o item não está em estoque.</span><span class="sxs-lookup"><span data-stu-id="a3e69-140">The warehouse location cannot be created because the item is not stocked.</span></span> <span data-ttu-id="a3e69-141">Para itens de estoque, a opção de produto em estoque no grupo de modelo de item associado deve ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3e69-141">To stock items, the Stocked product option on the associated item model group must be selected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-142">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-142">Issue resolution</span></span>

<span data-ttu-id="a3e69-143">O processo de criação de modelos de produto requer lógica extra específica do produto.</span><span class="sxs-lookup"><span data-stu-id="a3e69-143">The process of creating product templates requires extra product-specific logic.</span></span> <span data-ttu-id="a3e69-144">Portanto, você não pode usar o botão **Modelo de contas da empresa** genérico para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="a3e69-144">Therefore, you can't use the generic **Company accounts template** button for this purpose.</span></span> <span data-ttu-id="a3e69-145">Em vez disso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a3e69-145">Instead, follow these steps.</span></span>

1. <span data-ttu-id="a3e69-146">Abra um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-146">Open a released product.</span></span>
1. <span data-ttu-id="a3e69-147">No Painel de ações, na guia **Produto**, no grupo **Novo**, selecione **Modelo \> Criar modelo compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="a3e69-147">On the Action Pane, on the **Product** tab, in the **New** group, select **Template \> Create shared template**.</span></span>

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a><span data-ttu-id="a3e69-148">O texto de ajuda padrão adicionado aos atributos do produto não é inserido em um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-148">Default Help text that is added in product attributes isn't entered in a released product.</span></span>

<span data-ttu-id="a3e69-149">Uma descrição e um texto de ajuda adicionados aos atributos do produto não são visíveis ou inseridos por padrão nos produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="a3e69-149">A description and Help text that are added in the product attributes aren't visible or entered by default in the released products.</span></span> <span data-ttu-id="a3e69-150">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="a3e69-150">This behavior is by design.</span></span>

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a><span data-ttu-id="a3e69-151">A quantidade padrão inserida difere quando é registrada de uma BOM e quando é registrada de uma versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="a3e69-151">The default quantity that is entered differs when it's registered from a BOM and when it's registered from a BOM version.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-152">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-152">Issue description</span></span>

<span data-ttu-id="a3e69-153">Por padrão, quando você adiciona um item a uma BOM, a quantidade é definida como 1 em vez da quantidade definida no campo **Quantidade mínima para ordem** na página **Configurações de ordem padrão** para um produto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-153">By default, when you add an item to a BOM, the quantity is set to 1 instead of the quantity that is defined in the **Min. order quantity** field on the **Default order settings** page for a selected product.</span></span> <span data-ttu-id="a3e69-154">No entanto, quando você adiciona um item de uma versão da BOM e o item e a variante são selecionados, a quantidade inserida por padrão leva em consideração a quantidade mínima definida nas configurações padrão da ordem para as dimensões específicas.</span><span class="sxs-lookup"><span data-stu-id="a3e69-154">However, when you add an item from a BOM version, and the item and variant are selected, the quantity that is entered by default takes into account the minimum quantity that is set in the default order settings for the specific dimensions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-155">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-155">Issue resolution</span></span>

<span data-ttu-id="a3e69-156">Esse comportamento é esperado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-156">This behavior is expected.</span></span> <span data-ttu-id="a3e69-157">Contudo, o fato de que a lógica difere na BOM e na versão da BOM é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="a3e69-157">However, the fact that the logic differs in the BOM and the BOM version is a known issue.</span></span> <span data-ttu-id="a3e69-158">Esse comportamento, porém, não será alterado, porque uma mudança pode afetar muitos cenários de clientes diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3e69-158">Nevertheless, this behavior won't be changed, because a change could affect many different customer scenarios.</span></span>

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a><span data-ttu-id="a3e69-159">Nos detalhes do produto liberado, não posso alterar as imagens anexadas que foram carregadas da entidade de dados de anexos do documento do produto.</span><span class="sxs-lookup"><span data-stu-id="a3e69-159">In the released product details, I can't change the attached images that were uploaded from the Product document attachments data entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-160">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-160">Issue description</span></span>

<span data-ttu-id="a3e69-161">Esse problema pode ocorrer quando você anexa uma imagem a um item usando a entidade de dados *Anexos do documento do produto*.</span><span class="sxs-lookup"><span data-stu-id="a3e69-161">This issue can occur when you attach an image to an item by using the *Product document attachments* data entity.</span></span> <span data-ttu-id="a3e69-162">Nesse caso, a imagem de item é mostrada para o item.</span><span class="sxs-lookup"><span data-stu-id="a3e69-162">In this case, the item image is shown for the item.</span></span> <span data-ttu-id="a3e69-163">Contudo, se você selecionar **Alterar imagem**, nada será mostrado na lista de imagens carregadas.</span><span class="sxs-lookup"><span data-stu-id="a3e69-163">However, if you select **Change image**, nothing is shown in the list of uploaded images.</span></span> <span data-ttu-id="a3e69-164">Além disso, nenhum anexo é mostrado para o item.</span><span class="sxs-lookup"><span data-stu-id="a3e69-164">Additionally, no attachments are shown for the item.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-165">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-165">Issue resolution</span></span>

<span data-ttu-id="a3e69-166">A entidade *EcoResProductDocumentAttachmentEntity* (*Anexos do documento do produto*) importa anexos do documento para *produtos*, mas não para *produtos liberados*.</span><span class="sxs-lookup"><span data-stu-id="a3e69-166">The *EcoResProductDocumentAttachmentEntity* entity (*Product document attachments*) imports document attachments for *products* but not for *released products*.</span></span> <span data-ttu-id="a3e69-167">(Os produtos liberados também são conhecidos como *items*.) Para exibir os anexos de um item na página **Detalhes do produto liberado**, você deve usar a entidade *EcoResReleasedProductDocumentAttachmentEntity* (*Anexos de documentos de produtos liberados*) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="a3e69-167">(Released products are also known as *items*.) To view the attachments for an item on the **Released product details** page, you must use the *EcoResReleasedProductDocumentAttachmentEntity* entity (*Released product document attachments*) instead.</span></span>

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a><span data-ttu-id="a3e69-168">O conector do Microsoft Flow mostra a seguinte mensagem de erro: "Atualização não permitida para o campo 'ProductNumber'."</span><span class="sxs-lookup"><span data-stu-id="a3e69-168">The Microsoft Flow connector shows the following error message: "Update not allowed for field 'ProductNumber'."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-169">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-169">Issue description</span></span>

<span data-ttu-id="a3e69-170">Esse problema ocorre se você tentar atualizar o campo **Número do produto** usando a entidade V2 *Produtos liberados* e o Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="a3e69-170">This issue occurs if you try to update the **Product number** field by using the *Released products* entity V2 and Microsoft Flow.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-171">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-171">Issue resolution</span></span>

<span data-ttu-id="a3e69-172">Esse comportamento é esperado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-172">This behavior is expected.</span></span> <span data-ttu-id="a3e69-173">A capacidade de editar o número do produto para um produto liberado foi removida no Dynamics 365 Finance and Operations 10.0.0 com a atualização de plataforma 24 para ajudar a evitar a corrupção de dados.</span><span class="sxs-lookup"><span data-stu-id="a3e69-173">The ability to edit the product number for a released product was removed in Dynamics 365 Finance and Operations 10.0.0 with platform update 24 to help prevent data corruption.</span></span> <span data-ttu-id="a3e69-174">Em casos excepcionais, quando você deve reparar dados corrompidos causados por uma renomeação anterior da chave primária de um produto liberado, você pode pedir ao Suporte da Microsoft para remover temporariamente essa restrição.</span><span class="sxs-lookup"><span data-stu-id="a3e69-174">In exceptional cases, where you must repair data corruption that was caused by a previous rename of the primary key of a released product, you can ask Microsoft Support to temporarily remove this restriction.</span></span>

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a><span data-ttu-id="a3e69-175">Não consigo criar uma variante de produto liberado em outra entidade legal.</span><span class="sxs-lookup"><span data-stu-id="a3e69-175">I can't create a released product variant in another legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-176">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-176">Issue description</span></span>

<span data-ttu-id="a3e69-177">Se você tentar liberar um produto mestre sem variantes e depois criar as variantes em cada entidade legal (empresa) conforme necessário, não poderá liberar as variantes usando sugestões de variantes.</span><span class="sxs-lookup"><span data-stu-id="a3e69-177">If you try to release a product master without variants, and then create the variants in each legal entity (company) as they are required, you won't be able to release the variants by using variant suggestions.</span></span> <span data-ttu-id="a3e69-178">Você também não poderá criar as variantes manualmente.</span><span class="sxs-lookup"><span data-stu-id="a3e69-178">You also won't be able to manually create the variants.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-179">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-179">Issue resolution</span></span>

<span data-ttu-id="a3e69-180">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="a3e69-180">This behavior is by design.</span></span> <span data-ttu-id="a3e69-181">As relações de um produto mestre e as dimensões que o mestre pode assumir são mantidas em um nível compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-181">The relations of a product master and the dimensions that the master can take are kept at a shared level.</span></span> <span data-ttu-id="a3e69-182">Portanto, você não pode criar as dimensões disponíveis para um produto mestre compartilhado na entidade legal específica onde essas dimensões são liberadas e, depois, replicar o processo em cada entidade legal onde as dimensões são necessárias.</span><span class="sxs-lookup"><span data-stu-id="a3e69-182">Therefore, you can't create the available dimensions for a shared product master in the specific legal entity where those dimensions are released and then replicate the process in each legal entity where the dimensions are required.</span></span> <span data-ttu-id="a3e69-183">Em vez disso, você deve alterar seu processo de liberação para se adaptar ao processo criado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-183">Instead, you must change your release process to adapt to the designed process.</span></span>

<span data-ttu-id="a3e69-184">Aqui está o processo de liberação de produtos.</span><span class="sxs-lookup"><span data-stu-id="a3e69-184">Here is the process for releasing products.</span></span>

1. <span data-ttu-id="a3e69-185">Crie o produto mestre compartilhado e as dimensões que podem ser liberadas para as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="a3e69-185">Create the shared product master and the dimensions that can be released to the legal entities.</span></span>
1. <span data-ttu-id="a3e69-186">Libere os produtos para as entidades legais usando sugestões de variantes ou adicionando manualmente as combinações que devem ser liberadas.</span><span class="sxs-lookup"><span data-stu-id="a3e69-186">Release the products to the legal entities either by using variant suggestions or by manually adding the combinations that should be released.</span></span>

<span data-ttu-id="a3e69-187">Como alternativa, você pode criar diretamente o produto liberado.</span><span class="sxs-lookup"><span data-stu-id="a3e69-187">Alternatively, you can directly create the released product.</span></span>

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a><span data-ttu-id="a3e69-188">Quando libero uma variante em outra empresa, recebo a seguinte mensagem de erro: "A variante do produto com as dimensões especificadas já foi criada."</span><span class="sxs-lookup"><span data-stu-id="a3e69-188">When I release a variant in another company, I receive the following error message: "Product variant with specified dimensions has already been created."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a3e69-189">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-189">Issue description</span></span>

<span data-ttu-id="a3e69-190">Se uma variante de produto já tiver sido liberada em uma empresa A e você tentar liberá-la na empresa B usando o botão **Novo** na página **Grades de produtos liberadas**, você receberá o seguinte erro mensagem:</span><span class="sxs-lookup"><span data-stu-id="a3e69-190">If a product variant has already been released in a company A, and you try to release it in company B by using the **New** button on the **Released product variants** page, you will receive the following error message:</span></span>

> <span data-ttu-id="a3e69-191">A grade de produto com dimensões especificadas já foi criada.</span><span class="sxs-lookup"><span data-stu-id="a3e69-191">Product variant with specified dimensions has already been created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a3e69-192">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="a3e69-192">Issue resolution</span></span>

<span data-ttu-id="a3e69-193">O botão **Novo** na página **Grades de produtos liberadas** cria a variante e a libera no contexto da empresa.</span><span class="sxs-lookup"><span data-stu-id="a3e69-193">The **New** button on the **Released product variants** page creates the variant and releases it in the company context.</span></span> <span data-ttu-id="a3e69-194">Se a variante já foi criada, você não pode usar o botão **Novo** para liberá-la em outra empresa.</span><span class="sxs-lookup"><span data-stu-id="a3e69-194">If the variant has already been created, you can't use the **New** button to release it in another company.</span></span>

<span data-ttu-id="a3e69-195">Para corrigir o problema, abra a página **Produto mestre** e selecione **Liberar produto** para liberar a variante existente na empresa desejada.</span><span class="sxs-lookup"><span data-stu-id="a3e69-195">To fix the issue, open the **Product master** page, and select **Release product** to release the existing variant in the desired company.</span></span>
