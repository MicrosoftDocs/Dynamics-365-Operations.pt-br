---
title: Criar ordens de call center
description: Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dce2fdd9d91c2bd867f0455573733aefb0796fa7
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107343"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="24f77-103">Criar ordens de call center</span><span class="sxs-lookup"><span data-stu-id="24f77-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24f77-104">Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="24f77-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="24f77-105">Este procedimento usa a empresa de dados de demonstração USRT e destina-se ao funcionário de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="24f77-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="24f77-106">Pré-requisitos: O usuário que conclui o procedimento é configurado como usuário do call center e o catálogo semestral da Fabrikam é publicado com pelo menos um código fonte nele.</span><span class="sxs-lookup"><span data-stu-id="24f77-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="24f77-107">Vá para **Retail e Commerce \> Clientes \> Customer service**.</span><span class="sxs-lookup"><span data-stu-id="24f77-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="24f77-108">Para **Texto da Pesquisa** , insira os critérios de pesquisa para pesquisar o cliente.</span><span class="sxs-lookup"><span data-stu-id="24f77-108">For **SearchText** , enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="24f77-109">Para este procedimento de exemplo, insira "Karen" e selecione **Tab**.</span><span class="sxs-lookup"><span data-stu-id="24f77-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="24f77-110">Selecione Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="24f77-110">Select Search.</span></span>
    * <span data-ttu-id="24f77-111">Uma vez que há somente uma cliente chamada "Karen" nos dados de demonstração, o resultado será automaticamente selecionado.</span><span class="sxs-lookup"><span data-stu-id="24f77-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="24f77-112">Selecione **Nova ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="24f77-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="24f77-113">Expanda ou recolha a seção de cabeçalho **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="24f77-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="24f77-114">Selecione o código fonte para o catálogo.</span><span class="sxs-lookup"><span data-stu-id="24f77-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="24f77-115">Se não houver nenhum código fonte ativo, você poderá ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="24f77-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="24f77-116">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="24f77-116">Select **Add line**.</span></span>
8. <span data-ttu-id="24f77-117">Para **Número do item** , insira o termo de pesquisa do item.</span><span class="sxs-lookup"><span data-stu-id="24f77-117">For **Item number** , enter the item search term.</span></span>
    * <span data-ttu-id="24f77-118">Para este procedimento de exemplo, insira um número de item parcial de '8111' e pressione tab. Essa ação fará surgir a janela de pesquisa de itens.</span><span class="sxs-lookup"><span data-stu-id="24f77-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="24f77-119">Selecione o produto a ser adicionado à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="24f77-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="24f77-120">Insira a quantidade de vendas.</span><span class="sxs-lookup"><span data-stu-id="24f77-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="24f77-121">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="24f77-121">Select **Create**.</span></span>
12. <span data-ttu-id="24f77-122">Selecione **Concluir** para capturar o pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="24f77-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="24f77-123">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="24f77-123">Select **Add**.</span></span>
    * <span data-ttu-id="24f77-124">A opção Adicionar link está na guia Pagamentos. Expanda a guia Pagamentos se ela estiver recolhida.</span><span class="sxs-lookup"><span data-stu-id="24f77-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="24f77-125">Selecione o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="24f77-125">Select the payment method.</span></span>
    * <span data-ttu-id="24f77-126">Para este procedimento, selecione o método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="24f77-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="24f77-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="24f77-127">Close the page.</span></span>
16. <span data-ttu-id="24f77-128">Insira o valor.</span><span class="sxs-lookup"><span data-stu-id="24f77-128">Enter the amount.</span></span>
    * <span data-ttu-id="24f77-129">Para este procedimento, insira um valor igual ao saldo da ordem que pode ser visto na página Resumo da ordem de venda, à esquerda do campo de valor.</span><span class="sxs-lookup"><span data-stu-id="24f77-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="24f77-130">Essa ação permitirá que você conclua a ordem como totalmente paga.</span><span class="sxs-lookup"><span data-stu-id="24f77-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="24f77-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="24f77-131">Select **OK**.</span></span>
18. <span data-ttu-id="24f77-132">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="24f77-132">Select **Submit**.</span></span>

