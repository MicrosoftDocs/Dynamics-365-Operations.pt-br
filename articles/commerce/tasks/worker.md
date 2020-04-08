---
title: Configurar um trabalhador
description: Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd437f549ffc1f8879ce3814ace1193040b280e1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140669"
---
# <a name="configure-a-worker"></a><span data-ttu-id="cd571-103">Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="cd571-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd571-104">Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.</span><span class="sxs-lookup"><span data-stu-id="cd571-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="cd571-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="cd571-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="cd571-106">Criar um grupo de comissão de venda para o trabalhador</span><span class="sxs-lookup"><span data-stu-id="cd571-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="cd571-107">Vá para Vendas e marketing > Comissões > Grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="cd571-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="cd571-108">Os trabalhadores podem ser atribuídos a um ou mais grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="cd571-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="cd571-109">No PDV, você pode escolher qualquer grupo de vendas que contenha trabalhadores do catálogo de endereços da loja.</span><span class="sxs-lookup"><span data-stu-id="cd571-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="cd571-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cd571-110">Click New.</span></span>
3. <span data-ttu-id="cd571-111">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cd571-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="cd571-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cd571-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="cd571-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd571-113">Click Save.</span></span>
6. <span data-ttu-id="cd571-114">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="cd571-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="cd571-115">Clique em Rep. de vendas.</span><span class="sxs-lookup"><span data-stu-id="cd571-115">Click Sales rep.</span></span>
    * <span data-ttu-id="cd571-116">Um grupo de vendas pode conter mais de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="cd571-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="cd571-117">As comissões podem ser divididas entre os trabalhadores com base na sua definição da cota de comissão.</span><span class="sxs-lookup"><span data-stu-id="cd571-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="cd571-118">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd571-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="cd571-119">No campo Cota de comissão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="cd571-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="cd571-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd571-120">Click Save.</span></span>
11. <span data-ttu-id="cd571-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd571-121">Close the page.</span></span>
12. <span data-ttu-id="cd571-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd571-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="cd571-123">Atribuir o grupo de vendas padrão do trabalhador</span><span class="sxs-lookup"><span data-stu-id="cd571-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="cd571-124">Vá para Varejo e Comércio > Funcionários > Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="cd571-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="cd571-125">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cd571-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cd571-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd571-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cd571-127">Clique na guia Comércio.</span><span class="sxs-lookup"><span data-stu-id="cd571-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="cd571-128">Um trabalhador pode ser atribuído a um grupo de vendas padrão.</span><span class="sxs-lookup"><span data-stu-id="cd571-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="cd571-129">O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.</span><span class="sxs-lookup"><span data-stu-id="cd571-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="cd571-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="cd571-130">Click Edit.</span></span>
6. <span data-ttu-id="cd571-131">No campo Grupo padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd571-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="cd571-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd571-132">Click Save.</span></span>

