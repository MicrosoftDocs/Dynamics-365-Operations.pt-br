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
ms.openlocfilehash: 4867ad67dc570ab42420ba12fc7dc2da6b5ba503
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548246"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="9f242-103">Criar ordens de call center</span><span class="sxs-lookup"><span data-stu-id="9f242-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9f242-104">Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="9f242-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="9f242-105">Este procedimento usa a empresa de dados de demonstração USRT e destina-se ao funcionário de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="9f242-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="9f242-106">Pré-requisitos: O usuário que conclui o procedimento é configurado como usuário do call center e o catálogo semestral da Fabrikam é publicado com pelo menos um código fonte nele.</span><span class="sxs-lookup"><span data-stu-id="9f242-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="9f242-107">Vá para Varejo e comércio > Clientes > SAC.</span><span class="sxs-lookup"><span data-stu-id="9f242-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="9f242-108">No campo Texto da pesquisa, insira os critérios de pesquisa para pesquisar o cliente.</span><span class="sxs-lookup"><span data-stu-id="9f242-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="9f242-109">Para este procedimento de exemplo, digite 'Karen' e pressione tab.</span><span class="sxs-lookup"><span data-stu-id="9f242-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="9f242-110">Clique em Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="9f242-110">Click Search.</span></span>
    * <span data-ttu-id="9f242-111">Uma vez que há somente uma cliente chamada Karen nos dados de demonstração, eles serão automaticamente selecionados.</span><span class="sxs-lookup"><span data-stu-id="9f242-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="9f242-112">Clique em Nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="9f242-112">Click New sales order.</span></span>
5. <span data-ttu-id="9f242-113">Expanda ou recolha a seção do Cabeçalho de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="9f242-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="9f242-114">Selecione o código fonte para o catálogo.</span><span class="sxs-lookup"><span data-stu-id="9f242-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="9f242-115">Se não houver nenhum Código fonte ativo, você pode fechar o Campo de origem e ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="9f242-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="9f242-116">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="9f242-116">Click Add line.</span></span>
8. <span data-ttu-id="9f242-117">No campo número do item, digite o termo de pesquisa do item.</span><span class="sxs-lookup"><span data-stu-id="9f242-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="9f242-118">Para este procedimento de exemplo, insira um número de item parcial de '8111' e pressione tab. Isso fará surgir a janela de pesquisa de itens.</span><span class="sxs-lookup"><span data-stu-id="9f242-118">For this sample procedure enter a partial item number of '8111' and press tab. This will pop up the item search window.</span></span>  
9. <span data-ttu-id="9f242-119">Selecionar o produto para ser adicionado à ordem de venda</span><span class="sxs-lookup"><span data-stu-id="9f242-119">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="9f242-120">Insira a quantidade de vendas.</span><span class="sxs-lookup"><span data-stu-id="9f242-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="9f242-121">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="9f242-121">Click Create.</span></span>
12. <span data-ttu-id="9f242-122">Clique em Concluir para capturar o pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="9f242-122">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="9f242-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9f242-123">Click Add.</span></span>
    * <span data-ttu-id="9f242-124">A opção Adicionar link está na guia Pagamentos. Expanda a guia Pagamentos se ela estiver recolhida.</span><span class="sxs-lookup"><span data-stu-id="9f242-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="9f242-125">Selecione o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9f242-125">Select the payment method.</span></span>
    * <span data-ttu-id="9f242-126">Para este procedimento, selecione o método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="9f242-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="9f242-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f242-127">Close the page.</span></span>
16. <span data-ttu-id="9f242-128">Insira o valor.</span><span class="sxs-lookup"><span data-stu-id="9f242-128">Enter the amount.</span></span>
    * <span data-ttu-id="9f242-129">Para este procedimento, insira um valor igual ao saldo da ordem que pode ser visto na página Resumo da ordem de venda, à esquerda do campo de valor.</span><span class="sxs-lookup"><span data-stu-id="9f242-129">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="9f242-130">Isto permitirá que você conclua a ordem como totalmente paga.</span><span class="sxs-lookup"><span data-stu-id="9f242-130">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="9f242-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9f242-131">Click OK.</span></span>
18. <span data-ttu-id="9f242-132">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="9f242-132">Click Submit.</span></span>

