--- 
title: "Atribuição de imposto e substituições"
description: Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais varejos.
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 2420dceeb321ed11dbf6d7d9c09e3a579d65134c
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="cd5c0-103">Atribuição de imposto e substituições</span><span class="sxs-lookup"><span data-stu-id="cd5c0-103">Sales tax assignment and overrides</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd5c0-104">Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais varejos.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-104">This procedure demonstrates how to assign sales tax groups to retail channels.</span></span> <span data-ttu-id="cd5c0-105">Também mostra o processo de criação de uma substituição de impostos e atribuição da mesma ao grupo de substituição de impostos existente.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="cd5c0-106">Este procedimento</span><span class="sxs-lookup"><span data-stu-id="cd5c0-106">This procedure</span></span>

<span data-ttu-id="cd5c0-107">usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-107">uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="cd5c0-108">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-108">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="cd5c0-109">Na lista, clique no link do ID do canal de varejo para "Houston".</span><span class="sxs-lookup"><span data-stu-id="cd5c0-109">In the list, click the Retail Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="cd5c0-110">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-110">Click Edit.</span></span>
    * <span data-ttu-id="cd5c0-111">O campo "Grupo de impostos sobre vendas" contém a lista de grupos de imposto para a empresa atual.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-111">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="cd5c0-112">O grupo atualmente atribuído é um grupo genérico dos impostos sobre venda de "Texas".</span><span class="sxs-lookup"><span data-stu-id="cd5c0-112">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="cd5c0-113">Também há grupos de impostos para "Washington" e "Washington, King County".</span><span class="sxs-lookup"><span data-stu-id="cd5c0-113">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="cd5c0-114">Os grupos de impostos podem incluir impostos aplicáveis a várias municipalidades.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-114">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="cd5c0-115">O campo "Substituição de imposto" é onde os grupos de imposto de substituição podem ser mapeados ao canal.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-115">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="cd5c0-116">Os grupos da substituição dos impostos sobre venda podem ser usados para agrupar junto impostos sobre venda que cancelam esse trabalho para lojas múltiplas.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-116">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="cd5c0-117">Em vez de atribuir manualmente substituição de impostos sobre venda um por um, o grupo pode ser criado e atribuído diretamente aos canais para ganhar o tempo.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-117">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="cd5c0-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-118">Click Save.</span></span>
5. <span data-ttu-id="cd5c0-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-119">Close the page.</span></span>
6. <span data-ttu-id="cd5c0-120">Vá para Varejo e comércio > Configuração de canal > Impostos > Substituições de impostos.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-120">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="cd5c0-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-121">Click New.</span></span>
8. <span data-ttu-id="cd5c0-122">No campo Substituições de impostos, forneça um nome para sua nova substituição.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-122">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="cd5c0-123">No campo Descrição, insira uma descrição da substituição.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-123">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="cd5c0-124">Ajuste o status para "Habilitar".</span><span class="sxs-lookup"><span data-stu-id="cd5c0-124">Set the status to "Enable."</span></span>
11. <span data-ttu-id="cd5c0-125">Expandir ou recolher a seção Substituições.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-125">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="cd5c0-126">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-126">In the Type field, select an option.</span></span>
    * <span data-ttu-id="cd5c0-127">Os grupos dos impostos sobre venda do artigo podem ser usados para cancelar impostos para os artigos específicos que pertencem ao grupo.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-127">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="cd5c0-128">Por exemplo, os alimentos são taxados tipicamente diferentemente dos bens duráveis, e teriam provavelmente seu próprio grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-128">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span>     <span data-ttu-id="cd5c0-129">Os grupos dos impostos sobre venda são grupos de impostos que são aplicáveis a um canal particular.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-129">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="cd5c0-130">Por exemplo, se um canal vende o varejo e um interempresarial, os grupos diferentes dos impostos sobre venda dos artigos podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-130">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="cd5c0-131">Todos os impostos aplicáveis seriam traçados ao grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-131">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="cd5c0-132">Agora você pode selecionar "De" e "Para" impostos ou "Do grupo de impostos" e "Para grupo de impostos" para criar sua substituição de impostos.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-132">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span>    <span data-ttu-id="cd5c0-133">O campo "De" indica o imposto ou o grupo do imposto a ser substituído.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-133">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="cd5c0-134">Substituição pelo grupo dos impostos sobre venda do artigo fornece opções diferentes do que cancelar pelo grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-134">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span>    <span data-ttu-id="cd5c0-135">A substituição dos impostos sobre venda pode estabelecer-se para cancelar impostos em transações inteiras ou em linhas particulares na transação.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-135">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="cd5c0-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-136">Click Save.</span></span>
14. <span data-ttu-id="cd5c0-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-137">Close the page.</span></span>
15. <span data-ttu-id="cd5c0-138">Vá para Varejo e comércio > Configuração de canal > Impostos > Grupos de substituições de impostos.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-138">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="cd5c0-139">Nesta etapa você atribuiu a ultrapassagem recém-criada dos impostos sobre venda ao grupo da ultrapassagem dos impostos sobre venda atribuído ao canal de Houston.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-139">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="cd5c0-140">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-140">Click Edit.</span></span>
17. <span data-ttu-id="cd5c0-141">Expanda ou recolha a seção Configuração.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-141">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="cd5c0-142">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-142">Click Add.</span></span>
19. <span data-ttu-id="cd5c0-143">No campo Substituir imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-143">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="cd5c0-144">Selecione a substituição previamente criada dos impostos sobre venda da lista.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-144">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="cd5c0-145">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-145">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="cd5c0-146">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd5c0-146">Click Save.</span></span>


