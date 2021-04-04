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
ms.openlocfilehash: 120705200f223e31c72290059e8634e7db6f9fdd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232608"
---
# <a name="configure-a-worker"></a><span data-ttu-id="33434-103">Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="33434-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33434-104">Este procedimento demonstra como configurar um trabalhador como um representante de vendas que esteja qualificado para a comissão sobre vendas no PDV.</span><span class="sxs-lookup"><span data-stu-id="33434-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="33434-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="33434-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="33434-106">Criar um grupo de comissão de venda para o trabalhador</span><span class="sxs-lookup"><span data-stu-id="33434-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="33434-107">Vá para Vendas e marketing > Comissões > Grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="33434-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="33434-108">Os trabalhadores podem ser atribuídos a um ou mais grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="33434-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="33434-109">No PDV, você pode escolher qualquer grupo de vendas que contenha trabalhadores do catálogo de endereços da loja.</span><span class="sxs-lookup"><span data-stu-id="33434-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="33434-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="33434-110">Click New.</span></span>
3. <span data-ttu-id="33434-111">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33434-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="33434-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33434-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="33434-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33434-113">Click Save.</span></span>
6. <span data-ttu-id="33434-114">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="33434-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="33434-115">Clique em Rep. de vendas.</span><span class="sxs-lookup"><span data-stu-id="33434-115">Click Sales rep.</span></span>
    * <span data-ttu-id="33434-116">Um grupo de vendas pode conter mais de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="33434-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="33434-117">As comissões podem ser divididas entre os trabalhadores com base na sua definição da cota de comissão.</span><span class="sxs-lookup"><span data-stu-id="33434-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="33434-118">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="33434-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="33434-119">No campo Cota de comissão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="33434-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="33434-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33434-120">Click Save.</span></span>
11. <span data-ttu-id="33434-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="33434-121">Close the page.</span></span>
12. <span data-ttu-id="33434-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="33434-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="33434-123">Atribuir o grupo de vendas padrão do trabalhador</span><span class="sxs-lookup"><span data-stu-id="33434-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="33434-124">Vá para Varejo e Comércio > Funcionários > Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="33434-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="33434-125">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="33434-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="33434-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33434-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="33434-127">Clique na guia Comércio.</span><span class="sxs-lookup"><span data-stu-id="33434-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="33434-128">Um trabalhador pode ser atribuído a um grupo de vendas padrão.</span><span class="sxs-lookup"><span data-stu-id="33434-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="33434-129">O grupo de vendas padrão será automaticamente adicionado às linhas de vendas no PDV se a opção estiver habilitada no perfil de funcionalidade da loja.</span><span class="sxs-lookup"><span data-stu-id="33434-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="33434-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="33434-130">Click Edit.</span></span>
6. <span data-ttu-id="33434-131">No campo Grupo padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="33434-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="33434-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33434-132">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]