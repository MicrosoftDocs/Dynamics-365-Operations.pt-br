--- 
title: " Configurar um trabalhador"
description: "Este procedimento demonstra como configurar um trabalhador de varejo como representante de vendas que esteja qualificado para a comissão sobre vendas no PDV."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 721c075aa7bbe9d1ed439a84cae907e3db3aafa8
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---
# <a name="configure-a-worker"></a><span data-ttu-id="78e3f-103"> Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="78e3f-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="78e3f-104">Este procedimento demonstra como configurar um trabalhador de varejo como representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.</span><span class="sxs-lookup"><span data-stu-id="78e3f-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="78e3f-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="78e3f-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="78e3f-106">Criar um grupo de comissão de venda para o trabalhador</span><span class="sxs-lookup"><span data-stu-id="78e3f-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="78e3f-107">Vá para Vendas e marketing > Comissões > Grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="78e3f-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="78e3f-108">Os trabalhadores podem ser atribuídos a um ou mais grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="78e3f-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="78e3f-109">No PDV, você pode escolher qualquer grupo de vendas que contenha trabalhadores do catálogo de endereços da loja.</span><span class="sxs-lookup"><span data-stu-id="78e3f-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="78e3f-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="78e3f-110">Click New.</span></span>
3. <span data-ttu-id="78e3f-111">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="78e3f-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="78e3f-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="78e3f-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="78e3f-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78e3f-113">Click Save.</span></span>
6. <span data-ttu-id="78e3f-114">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="78e3f-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="78e3f-115">Clique em Rep. de vendas.</span><span class="sxs-lookup"><span data-stu-id="78e3f-115">Click Sales rep.</span></span>
    * <span data-ttu-id="78e3f-116">Um grupo de vendas pode conter mais de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="78e3f-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="78e3f-117">As comissões podem ser divididas entre os trabalhadores com base na sua definição da cota de comissão.</span><span class="sxs-lookup"><span data-stu-id="78e3f-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="78e3f-118">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="78e3f-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="78e3f-119">No campo Cota de comissão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="78e3f-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="78e3f-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78e3f-120">Click Save.</span></span>
11. <span data-ttu-id="78e3f-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="78e3f-121">Close the page.</span></span>
12. <span data-ttu-id="78e3f-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="78e3f-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="78e3f-123">Atribuir o grupo de vendas padrão do trabalhador</span><span class="sxs-lookup"><span data-stu-id="78e3f-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="78e3f-124">Vá para Varejo e comércio > Funcionários > Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="78e3f-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="78e3f-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="78e3f-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="78e3f-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="78e3f-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="78e3f-127">Clique na guia Varejo.</span><span class="sxs-lookup"><span data-stu-id="78e3f-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="78e3f-128">Um trabalhador pode ser atribuído a um grupo de vendas padrão.</span><span class="sxs-lookup"><span data-stu-id="78e3f-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="78e3f-129">O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.</span><span class="sxs-lookup"><span data-stu-id="78e3f-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="78e3f-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="78e3f-130">Click Edit.</span></span>
6. <span data-ttu-id="78e3f-131">No campo Grupo padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="78e3f-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="78e3f-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78e3f-132">Click Save.</span></span>


