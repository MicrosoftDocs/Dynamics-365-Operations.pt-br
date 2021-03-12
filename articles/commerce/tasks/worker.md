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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 73c200f7f6ff0aa5672e50c539bfaa5e30213185
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003594"
---
# <a name="configure-a-worker"></a><span data-ttu-id="55174-103">Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="55174-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55174-104">Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.</span><span class="sxs-lookup"><span data-stu-id="55174-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="55174-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="55174-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="55174-106">Criar um grupo de comissão de venda para o trabalhador</span><span class="sxs-lookup"><span data-stu-id="55174-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="55174-107">Vá para Vendas e marketing > Comissões > Grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="55174-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="55174-108">Os trabalhadores podem ser atribuídos a um ou mais grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="55174-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="55174-109">No PDV, você pode escolher qualquer grupo de vendas que contenha trabalhadores do catálogo de endereços da loja.</span><span class="sxs-lookup"><span data-stu-id="55174-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="55174-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="55174-110">Click New.</span></span>
3. <span data-ttu-id="55174-111">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="55174-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="55174-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="55174-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="55174-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="55174-113">Click Save.</span></span>
6. <span data-ttu-id="55174-114">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="55174-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="55174-115">Clique em Rep. de vendas.</span><span class="sxs-lookup"><span data-stu-id="55174-115">Click Sales rep.</span></span>
    * <span data-ttu-id="55174-116">Um grupo de vendas pode conter mais de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="55174-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="55174-117">As comissões podem ser divididas entre os trabalhadores com base na sua definição da cota de comissão.</span><span class="sxs-lookup"><span data-stu-id="55174-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="55174-118">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="55174-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="55174-119">No campo Cota de comissão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="55174-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="55174-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="55174-120">Click Save.</span></span>
11. <span data-ttu-id="55174-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="55174-121">Close the page.</span></span>
12. <span data-ttu-id="55174-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="55174-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="55174-123">Atribuir o grupo de vendas padrão do trabalhador</span><span class="sxs-lookup"><span data-stu-id="55174-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="55174-124">Vá para Varejo e Comércio > Funcionários > Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="55174-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="55174-125">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="55174-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="55174-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="55174-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="55174-127">Clique na guia Comércio.</span><span class="sxs-lookup"><span data-stu-id="55174-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="55174-128">Um trabalhador pode ser atribuído a um grupo de vendas padrão.</span><span class="sxs-lookup"><span data-stu-id="55174-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="55174-129">O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.</span><span class="sxs-lookup"><span data-stu-id="55174-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="55174-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="55174-130">Click Edit.</span></span>
6. <span data-ttu-id="55174-131">No campo Grupo padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="55174-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="55174-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="55174-132">Click Save.</span></span>

