---
title: Criar uma ordem de substituição de item
description: Em geral, as ordens de substituição de item são criadas após um produto ser devolvido e inspecionado.
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 784a2522c27e8131f211ffc52319552b3b928cc3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355003"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="68ce1-103">Criar uma ordem de substituição de item</span><span class="sxs-lookup"><span data-stu-id="68ce1-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="68ce1-104">Em geral, as ordens de substituição de item são criadas após um produto ser devolvido e inspecionado.</span><span class="sxs-lookup"><span data-stu-id="68ce1-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="68ce1-105">Contudo, quando for necessário substituir um antes da devolução ou quando o item original não será devolvido, você pode criar imediatamente uma ordem de substituição de item depois que criar uma ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="68ce1-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="68ce1-106">Criar uma ordem de substituição após receber um item que foi devolvido</span><span class="sxs-lookup"><span data-stu-id="68ce1-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="68ce1-107">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="68ce1-108">Crie uma nova ordem de devolução ou selecione uma ordem devolvida na lista para abrir o formulário **Ordem de devolução - Número de ADM: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="68ce1-109">Clique em **Linha de devolução** e depois selecione **Item de substituição**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="68ce1-110">Selecione o item a ser substituído pelo item devolvido.</span><span class="sxs-lookup"><span data-stu-id="68ce1-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="68ce1-111">Insira as especificações do item e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="68ce1-112">Clique em **Guia de remessa** para gerar a guia de remessa da ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="68ce1-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="68ce1-113">Uma ordem de venda é gerada para o item de substituição selecionado.</span><span class="sxs-lookup"><span data-stu-id="68ce1-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="68ce1-114">Depois que a ordem de venda é criada para o item de substituição, os contratos de venda são pesquisados automaticamente e, se houver um contrato de venda aplicável, ele será aplicado à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="68ce1-115">Criar uma ordem de substituição antes de receber um item que será devolvido</span><span class="sxs-lookup"><span data-stu-id="68ce1-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="68ce1-116">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="68ce1-117">Crie uma nova ordem de devolução ou selecione uma na lista para abrir o formulário **Ordem de devolução - Número de ADM: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="68ce1-118">Clique em **Localizar ordem de venda** se quiser identificar a ordem de venda para o item devolvido.</span><span class="sxs-lookup"><span data-stu-id="68ce1-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="68ce1-119">Preencha o formulário **Localizar ordem de venda** e clique em **OK** para fechá-lo e voltar ao formulário **Ordem de devolução - Número de ADM: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="68ce1-120">A linha da ordem de venda para o item devolvido é copiado na ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="68ce1-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="68ce1-121">Clique em **Ordem de substituição** para abrir o formulário **Criar ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="68ce1-122">Marque a caixa de seleção **Copiar linhas de ordem de devolução** para transferir detalhes da ordem de devolução selecionada no formulário **Ordem de devolução - Número de ADM: %1, %2** para esta ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="68ce1-123">Insira ou modifique os detalhes, conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="68ce1-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="68ce1-124">Se você identificou a ordem de venda na etapa 3, e se a linha da ordem de venda para o item devolvido estiver vinculada a um contrato de venda, o identificador do contrato de venda aplicável para a ordem de substituição do item será exibido automaticamente no campo **ID do contrato de venda**.</span><span class="sxs-lookup"><span data-stu-id="68ce1-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="68ce1-125">Clique em **OK** para fechar o formulário **Criar ordem de venda** e abrir o formulário **Ordem de venda**, onde é possível continuar inserindo informações para a nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="68ce1-126">Todas as linhas da ordem de devolução aplicável serão copiadas na nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="68ce1-127">Se o identificador do contrato de venda for exibido automaticamente no campo **ID do contrato de venda**, então o contrato de venda foi vinculado ao cabeçalho da ordem de venda para a ordem de substituição do item.</span><span class="sxs-lookup"><span data-stu-id="68ce1-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="68ce1-128">Se houver um compromisso aplicável no contrato de venda que ainda não tenha sido preenchido, e a ordem de venda foi criada antes da expiração do contrato de venda, um link será estabelecido entre a linha do contrato de venda e a linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="68ce1-129">Consequentemente, as informações do contrato de venda, como o preço do item, serão copiadas na nova linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="68ce1-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


