---
title: Pesquisa de estoque no Ponto de Venda
description: "Este tópico descreve as opções disponíveis para exibir informações de estoque no ponto de venda (PDV)."
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ff11cf7b23c48675b108d7d03d241fcec2cb792a
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="inventory-lookup-in-the-point-of-sale"></a><span data-ttu-id="c2760-103">Pesquisa de estoque no Ponto de Venda</span><span class="sxs-lookup"><span data-stu-id="c2760-103">Inventory lookup in the Point of Sale</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="c2760-104">A Pesquisa de estoque no Ponto de Venda (PDV) ajuda os varejistas a atingirem a excelência operacional em tempo real e a obterem insights conectando lojas, o PDS e o back office.</span><span class="sxs-lookup"><span data-stu-id="c2760-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="c2760-105">Essa funcionalidade fornece uma visão exata em tempo real de estoque do produto pelas lojas e centros de distribuição.</span><span class="sxs-lookup"><span data-stu-id="c2760-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="c2760-106">Também ajuda os varejista a determinar poupanças de gastos e eficiências adicionais melhorando o planejamento de estoque em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c2760-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="c2760-107">Uma exibição exata de tempo real de estoque em uma organização ajuda os associados da loja a fornecerem serviço ao cliente oportuno, superior.</span><span class="sxs-lookup"><span data-stu-id="c2760-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="c2760-108">O momento mas importante é aquele em que o cliente está pronto para tomar uma decisão de compra.</span><span class="sxs-lookup"><span data-stu-id="c2760-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="c2760-109">É importante que os caixas da loja tenham informações de estoque em tempo real ao seu alcance, para que possam prometer entrega e retirada do produto precisamente.</span><span class="sxs-lookup"><span data-stu-id="c2760-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="c2760-110">Você pode abrir a página **Pesquisa de estoque** do espaço de trabalho **Retail Modern POS** ou do espaço de trabalho **Retail Cloud POS**.</span><span class="sxs-lookup"><span data-stu-id="c2760-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Quadro de pesquisa de estoque na home page do PDV](media/POSHomepage.png)

<span data-ttu-id="c2760-112">Na página **Pesquisa de estoque** , você pode usar o teclado numérico para inserir um número do produto.</span><span class="sxs-lookup"><span data-stu-id="c2760-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="c2760-113">Você pode exibir a quantidade disponível para várias lojas e depósitos.</span><span class="sxs-lookup"><span data-stu-id="c2760-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Página padrão de pesquisa de estoque](media/InventoryLookUp.png)

<span data-ttu-id="c2760-115">Quantidades **Reservadas** e **Encomendas** também são mostradas para cada local.</span><span class="sxs-lookup"><span data-stu-id="c2760-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="c2760-116">**Reservada** – Esta quantidade refere-se ao valor **Físico reservado** do back office para o número do produto especificado no local.</span><span class="sxs-lookup"><span data-stu-id="c2760-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="c2760-117">**Encomendado** – Esta quantidade refere-se ao valor **Total encomendado** do back office para o número do produto especificado no local.</span><span class="sxs-lookup"><span data-stu-id="c2760-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="c2760-118">Os locais nos quais as informações de disponibilidade de estoque são mostradas</span><span class="sxs-lookup"><span data-stu-id="c2760-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="c2760-119">A lista de locais incluem dois tipos de entidades:</span><span class="sxs-lookup"><span data-stu-id="c2760-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="c2760-120">**Lojas de varejo** – A lista mostra as lojas configuradas usando o grupo de localizadores de lojas da loja atual na sede de varejo.</span><span class="sxs-lookup"><span data-stu-id="c2760-120">**Retail stores** – The list shows stores that are configured by using the store locator group for the current store in the Retail headquarters.</span></span> 
- <span data-ttu-id="c2760-121">**Centros de distribuição** – Os vários tipos de centros de distribuição (como depósitos) podem ser configurados no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="c2760-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="c2760-122">Entretanto, a lista mostra informações de disponibilidade de estoque somente para centros de distribuição do tipo **Padrão** .</span><span class="sxs-lookup"><span data-stu-id="c2760-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="c2760-123">A disponibilidade das informações de estoque não é exibida para os depósitos dos tipos **Trânsito**, **Quarentena** e **Mercadorias no Roteiro** para o PDV.</span><span class="sxs-lookup"><span data-stu-id="c2760-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="c2760-124">Na página **Pesquisa de estoque** , você pode exibir as quantidades disponíveis para promessa (ATP) de cada loja, além das quantidades atuais disponíveis, quantidades reservadas e as quantidades encomendadas.</span><span class="sxs-lookup"><span data-stu-id="c2760-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="c2760-125">Selecione a loja para exibir as informações ATP e, em seguida, seledione **Mostrar disponibilidade da loja**.</span><span class="sxs-lookup"><span data-stu-id="c2760-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![Quantidades do ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="c2760-127">Abrindo a exibição da matriz com base na Dimensão para motrar todas as grades</span><span class="sxs-lookup"><span data-stu-id="c2760-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="c2760-128">Na **Detalhes do produto** de um produto mestre ou na página **Pesquisa de estoque** , selecione **Exibir todas as grades** na barra do aplicativo na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="c2760-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="c2760-129">A exibição **Matriz com base na dimensão** da inicialização inicial dessas páginas mostra as informações sobre disponibilidade de estoque para todas as grades de um produto para a loja atual.</span><span class="sxs-lookup"><span data-stu-id="c2760-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="c2760-130">O botão **Exiba todas as grades** está disponível apenas para os produtos mestre de itens com grades de produto.</span><span class="sxs-lookup"><span data-stu-id="c2760-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="c2760-131">Não está disponível para produtos autônomos ou kits.</span><span class="sxs-lookup"><span data-stu-id="c2760-131">It isn't available for standalone products or kits.</span></span>

![Exiba todas as grades na página de pesquisa de estoque](media/StandardToMatrix.png)

<span data-ttu-id="c2760-133">Selecione **Exibir todas as grades** na página **Detalhes do produto** de um produto mestre ou na página **Pesquisa de estoque**, sem selecionar um local, vá para a exibição **Matriz com base na dimensão** para exibir as informações de disponibilidade de estoque para todas as grades de um produto da loja atual.</span><span class="sxs-lookup"><span data-stu-id="c2760-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Exibição da matriz com base na dimensão para a página de pesquisa de Estoque](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="c2760-135">Na ilustração anterior, a ordem de exibição das dimensões é alfabética, pois a ordem de exibição das dimensões não foi configurada para o produto selecionado.</span><span class="sxs-lookup"><span data-stu-id="c2760-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="c2760-136">Na exibição **Matriz com base na dimensão** , as células das grades do produto incluem um valor disponível no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="c2760-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="c2760-137">A tabela a seguir explica o significado vários valores.</span><span class="sxs-lookup"><span data-stu-id="c2760-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="c2760-138">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="c2760-138">On-hand value</span></span>                            | <span data-ttu-id="c2760-139">descrição</span><span class="sxs-lookup"><span data-stu-id="c2760-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="c2760-140">Valor numérico que é maior que 0 (zero)</span><span class="sxs-lookup"><span data-stu-id="c2760-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="c2760-141">Uma grade foi liberada para o local selecionado e você pode executar ações adicionais na célula.</span><span class="sxs-lookup"><span data-stu-id="c2760-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="c2760-142">(Essas ações são descritas em mais detalhes posteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="c2760-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="c2760-143">**0** (zero)</span><span class="sxs-lookup"><span data-stu-id="c2760-143">**0** (zero)</span></span>                             | <span data-ttu-id="c2760-144">Uma grade foi liberada para o local selecionado, mas o item não está disponível no local selecionado.</span><span class="sxs-lookup"><span data-stu-id="c2760-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="c2760-145">Entretanto, você pode executar ações adicionais na célula.</span><span class="sxs-lookup"><span data-stu-id="c2760-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="c2760-146">(Essas ações são descritas em mais detalhes posteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="c2760-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="c2760-147">**n/a** ou uma célula inativa</span><span class="sxs-lookup"><span data-stu-id="c2760-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="c2760-148">Uma grade não foi liberada para o local selecionado, e você pode não pode executar ações adicionais na célula.</span><span class="sxs-lookup"><span data-stu-id="c2760-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="c2760-149">Você também pode alterar a tabela dinâmica de dimensões marcando a nova dimensão a ser usada.</span><span class="sxs-lookup"><span data-stu-id="c2760-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span> 

![Alterando a tabela dinâmica](media/ChangePivot.png)

![Tabela dinâmica alterada](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="c2760-152">Nas ilustrações anteriores, a ordem de exibição das dimensões para o produto selecionado personalizada (não alfabética).</span><span class="sxs-lookup"><span data-stu-id="c2760-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="c2760-153">É baseana na ordem de exibição de dimensões definida no back office.</span><span class="sxs-lookup"><span data-stu-id="c2760-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="c2760-154">Além disso, na exibição **Matriz com base na dimensão** , mais ações podem ser executadas para ajudar a impulsionar a produtividade de um associado da loja.</span><span class="sxs-lookup"><span data-stu-id="c2760-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="c2760-155">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="c2760-155">Here are some examples:</span></span>

- <span data-ttu-id="c2760-156">Alterar o local da loja para pesquisar a disponibilidade de estoque de todas as grades de produto em outros locais.</span><span class="sxs-lookup"><span data-stu-id="c2760-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="c2760-157">Esses locais incluem outras lojas nos centros de distribuição e no grupo de localizadores da loja do tipo **Padrão** .</span><span class="sxs-lookup"><span data-stu-id="c2760-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="c2760-158">Vender uma grade de produto individual para um cliente usando pague e leve, retirada na loja ou remessa para um endereço.</span><span class="sxs-lookup"><span data-stu-id="c2760-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="c2760-159">Forneça ao cliente informações ATP para uma grade de produtos individuais em um local específico.</span><span class="sxs-lookup"><span data-stu-id="c2760-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![Ações adicionais sobre quadros da grade](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="c2760-161">Na ilustração anterior, a ordem de exibição das dimensões é alfabética, pois a ordem de exibição das dimensões não foi configurada para o produto selecionado.</span><span class="sxs-lookup"><span data-stu-id="c2760-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="c2760-162">A tabela a seguir fornece mais informações sobre ações adicionais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c2760-162">The following table provides more information about the additional actions that are available.</span></span>


|        <span data-ttu-id="c2760-163">Ação</span><span class="sxs-lookup"><span data-stu-id="c2760-163">Action</span></span>        |                                                                                                                    <span data-ttu-id="c2760-164">descrição</span><span class="sxs-lookup"><span data-stu-id="c2760-164">Description</span></span>                                                                                                                    |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="c2760-165">Vender agora</span><span class="sxs-lookup"><span data-stu-id="c2760-165">Sell now</span></span>       |                               <span data-ttu-id="c2760-166">Adicionar a grade de itens selecionada para a transação e redirecionar o usuário para a tela da transação.</span><span class="sxs-lookup"><span data-stu-id="c2760-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="c2760-167">(Esta ação não está disponível quando o local selecionado é um centro de distribuição.)</span><span class="sxs-lookup"><span data-stu-id="c2760-167">(This action isn't available when the selected location is a distribution center.)</span></span>                               |
|   <span data-ttu-id="c2760-168">Retirar na loja</span><span class="sxs-lookup"><span data-stu-id="c2760-168">Pick up in store</span></span>   |      <span data-ttu-id="c2760-169">Criar uma ordem de cliente para a grade do produto que será retirada do local selecionado e redirecionar o usuário para a tela da transação.</span><span class="sxs-lookup"><span data-stu-id="c2760-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="c2760-170">(Esta ação não está disponível quando o local selecionado é um centro de distribuição.)</span><span class="sxs-lookup"><span data-stu-id="c2760-170">(This action isn't available when the selected location is a distribution center.)</span></span>       |
|     <span data-ttu-id="c2760-171">Enviar produto</span><span class="sxs-lookup"><span data-stu-id="c2760-171">Ship product</span></span>     |                                                 <span data-ttu-id="c2760-172">Criar uma ordem de cliente para a grade do produto que será enviada do local selecionado e redirecionar o usuário para a tela da transação.</span><span class="sxs-lookup"><span data-stu-id="c2760-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span>                                                 |
|     <span data-ttu-id="c2760-173">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c2760-173">Availability</span></span>     |                                                                             <span data-ttu-id="c2760-174">Mostra as informações de ATP para a combinação de grade selecionada para o local selecionado.</span><span class="sxs-lookup"><span data-stu-id="c2760-174">Show the ATP information for the selected variant combination for the selected location.</span></span>                                                                              |
|  <span data-ttu-id="c2760-175">Mostrar todos os locais</span><span class="sxs-lookup"><span data-stu-id="c2760-175">Show all locations</span></span>  | <span data-ttu-id="c2760-176">Alterne para as informações de exibição padrão de pesquisa de estoque e de disponibilidade de estoque de destaque para a grade de item em todas as lojas no grupo de localizador de loja e, também em centros de distribuição do tipo <strong>Padrão/padrão</strong>.</span><span class="sxs-lookup"><span data-stu-id="c2760-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the <strong>Standard/Default</strong> type.</span></span> |
| <span data-ttu-id="c2760-177">Exibir detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="c2760-177">View product details</span></span> |                                                                         <span data-ttu-id="c2760-178">Redirecionar o usuário para a página <strong>Detalhes do produto</strong> do produto mestre associado.</span><span class="sxs-lookup"><span data-stu-id="c2760-178">Redirect the user to the <strong>Product details</strong> page of the associated product master.</span></span>                                                                          |


