---
title: Registrar o recebimento de itens devolvidos
description: Você pode registrar o recibo de itens devolvidos usando o formulário de Visão geral de entrada ou o formulário de Registro.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e1da5fee9607bf9f38c90d3db891ffa212ab01f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219284"
---
# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="6420e-103">Registrar o recebimento de itens devolvidos</span><span class="sxs-lookup"><span data-stu-id="6420e-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6420e-104">Há dois métodos para registrar o recebimento de itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="6420e-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="6420e-105">O primeiro método é um processo de recebimento de depósito que use o formulário de **Visão geral de entrada**.</span><span class="sxs-lookup"><span data-stu-id="6420e-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="6420e-106">O segundo usa o formulário de **Registro**.</span><span class="sxs-lookup"><span data-stu-id="6420e-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="6420e-107">Registrar o recebimento de itens devolvidos com o formulário Visão geral de entrada</span><span class="sxs-lookup"><span data-stu-id="6420e-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="6420e-108">Você pode usar o formulário **Visão geral de entrada** para identificar uma remessa de devolução pelo número da Autorização de Devolução de Material (ADM).</span><span class="sxs-lookup"><span data-stu-id="6420e-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="6420e-109">Se um nome de diário estiver definido na guia de **Configuração**, e as linhas do diário que correspondem às linhas selecionadas no formulário de **Visão geral de entrada** existirem, um novo cabeçalho de diário é criado quando você clica em **Iniciar entrada**.</span><span class="sxs-lookup"><span data-stu-id="6420e-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="6420e-110">Clique em **Gerenciamento de estoque** \> **Periódico** \> **Visão geral de entrada**.</span><span class="sxs-lookup"><span data-stu-id="6420e-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="6420e-111">No campo **Nome de instalação**, selecione **Devolver ordem** e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="6420e-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="6420e-112">Você pode usar os campos <STRONG>Intervalo</STRONG> para restringir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6420e-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="6420e-113">Digite ou selecione o número de ADM no campo <STRONG>Número de ADM</STRONG> para obter um resultado exato.</span><span class="sxs-lookup"><span data-stu-id="6420e-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="6420e-114">Para definir e salvar um conjunto de filtros que restringirá quais entrada de chegada são exibidas, clique na guia <STRONG>Configuração</STRONG>. Os filtros disponíveis incluem tipos, depósitos e docas.</span><span class="sxs-lookup"><span data-stu-id="6420e-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="6420e-115">As ordens de devolução não podem ser misturadas com outros outras entrada no formulário de <STRONG>Visão geral de entrada</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6420e-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="6420e-116">Portanto, a referência será sempre ordem de venda, mas nenhuma ID de ordem de venda será especificado no cabeçalho do diário.</span><span class="sxs-lookup"><span data-stu-id="6420e-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="6420e-117">Na tabela **Recibos**, localize a linha que corresponde ao item devolvido e selecione a caixa na coluna **Selecionar para entrada**.</span><span class="sxs-lookup"><span data-stu-id="6420e-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="6420e-118">Para excluir determinadas linhas do recibo de devolução, como itens da ordem original que não foram incluídos na remessa de devolução, desmarque as caixas **Selecionar para entrada** associadas na tabela **Linhas** na parte inferior do formulário.</span><span class="sxs-lookup"><span data-stu-id="6420e-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="6420e-119">Clique no botão de **Iniciar entrada** para criar um diário de entrada.</span><span class="sxs-lookup"><span data-stu-id="6420e-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="6420e-120">Você pode selecionar várias ordens de devolução e incluir todas em um único processo de entrada.</span><span class="sxs-lookup"><span data-stu-id="6420e-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="6420e-121">Cada linha de ordem de devolução será copiada em uma linha de diário de entrada de item correspondente.</span><span class="sxs-lookup"><span data-stu-id="6420e-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="6420e-122">Você também pode criar manualmente um diário de entrada usando o formulário de <STRONG>Entrada de item</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6420e-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="6420e-123">Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Chegada de item**.</span><span class="sxs-lookup"><span data-stu-id="6420e-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="6420e-124">Selecione o diário de entrada que você acabou de criar e clique em **Linhas** para abrir o formulário de **Linhas do diário, localizações**.</span><span class="sxs-lookup"><span data-stu-id="6420e-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="6420e-125">Na guia **Geral**, ajuste o número no campo **Quantidade**, se necessário, e então atribua um código de disposição no campo de **Código de disposição**.</span><span class="sxs-lookup"><span data-stu-id="6420e-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="6420e-126">Como alternativa, você pode marcar a caixa de seleção de **Gerenciamento de quarentena** para que os itens devolvidos sejam enviados a um processo de inspeção no contexto de uma ordem de quarentena.</span><span class="sxs-lookup"><span data-stu-id="6420e-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="6420e-127">Se você envia os itens devolvidos com a quarentena, não é possível especificar um código de disposição.</span><span class="sxs-lookup"><span data-stu-id="6420e-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="6420e-128">Clique no botão **Validar**.</span><span class="sxs-lookup"><span data-stu-id="6420e-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="6420e-129">Se não houver erros no processo de validação, clique em **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="6420e-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="6420e-130">Registrar o recebimento de itens devolvidos com o formulário Visão geral de entrada</span><span class="sxs-lookup"><span data-stu-id="6420e-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="6420e-131">Como uma alternativa ao usar o formulário de **Visão geral de entrada**, você pode usar o formulário de **Registro** para registrar a entrada de itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="6420e-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="6420e-132">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="6420e-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="6420e-133">Crie uma nova ordem de devolução ou abra a ordem de devolução na lista.</span><span class="sxs-lookup"><span data-stu-id="6420e-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="6420e-134">Na Guia Rápida **Linhas**, selecione a ordem de devolução apropriada.</span><span class="sxs-lookup"><span data-stu-id="6420e-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="6420e-135">Clique em **Atualizar linha** e em **Registro**.</span><span class="sxs-lookup"><span data-stu-id="6420e-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="6420e-136">Atribua um código de disposição no campo de **Código de disposição**, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6420e-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="6420e-137">Não é possível enviar o item para inspeção como uma ordem de quarentena usando o formulário de <STRONG>Registro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6420e-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="6420e-138">Na grade de **Transações**, selecione a transação a ser registrada.</span><span class="sxs-lookup"><span data-stu-id="6420e-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="6420e-139">Na grade **Registrar agora**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6420e-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="6420e-140">Repita as duas etapas anteriores até que todos os itens devolvidos apareçam na grade de **Registrar agora**.</span><span class="sxs-lookup"><span data-stu-id="6420e-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="6420e-141">Clique em **Lançar todos**.</span><span class="sxs-lookup"><span data-stu-id="6420e-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6420e-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6420e-142">See also</span></span>

<span data-ttu-id="6420e-143">[Visão geral de entrada (formulário)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6420e-143">[Arrival overview (form)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]