---
title: Atribuição de imposto e substituições
description: Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais de comércio.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74a7eed04648c63c0b19d5de26d2bdbef59aec7d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207576"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="af34f-103"> Substituições e atribuições de impostos</span><span class="sxs-lookup"><span data-stu-id="af34f-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="af34f-104">Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais de comércio.</span><span class="sxs-lookup"><span data-stu-id="af34f-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="af34f-105">Também mostra o processo de criação de uma substituição de impostos e atribuição da mesma ao grupo de substituição de impostos existente.</span><span class="sxs-lookup"><span data-stu-id="af34f-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="af34f-106">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="af34f-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="af34f-107">Vá para Retail e Commerce > Canais > Lojas > Todas as lojas.</span><span class="sxs-lookup"><span data-stu-id="af34f-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="af34f-108">Na lista, clique no link do ID do Canal para "Houston".</span><span class="sxs-lookup"><span data-stu-id="af34f-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="af34f-109">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="af34f-109">Click Edit.</span></span>
    * <span data-ttu-id="af34f-110">O campo "Grupo de impostos sobre vendas" contém a lista de grupos de imposto para a empresa atual.</span><span class="sxs-lookup"><span data-stu-id="af34f-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="af34f-111">O grupo atualmente atribuído é um grupo genérico dos impostos sobre venda de "Texas".</span><span class="sxs-lookup"><span data-stu-id="af34f-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="af34f-112">Também há grupos de impostos para "Washington" e "Washington, King County".</span><span class="sxs-lookup"><span data-stu-id="af34f-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="af34f-113">Os grupos de impostos podem incluir impostos aplicáveis a várias municipalidades.</span><span class="sxs-lookup"><span data-stu-id="af34f-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="af34f-114">O campo "Substituição de imposto" é onde os grupos de imposto de substituição podem ser mapeados ao canal.</span><span class="sxs-lookup"><span data-stu-id="af34f-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="af34f-115">Os grupos da substituição dos impostos sobre venda podem ser usados para agrupar junto impostos sobre venda que cancelam esse trabalho para lojas múltiplas.</span><span class="sxs-lookup"><span data-stu-id="af34f-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="af34f-116">Em vez de atribuir manualmente substituição de impostos sobre venda um por um, o grupo pode ser criado e atribuído diretamente aos canais para ganhar o tempo.</span><span class="sxs-lookup"><span data-stu-id="af34f-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="af34f-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="af34f-117">Click Save.</span></span>
5. <span data-ttu-id="af34f-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="af34f-118">Close the page.</span></span>
6. <span data-ttu-id="af34f-119">Vá para Retail e Commerce > Configuração de canal > Impostos > Substituições de impostos.</span><span class="sxs-lookup"><span data-stu-id="af34f-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="af34f-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="af34f-120">Click New.</span></span>
8. <span data-ttu-id="af34f-121">No campo Substituições de impostos, forneça um nome para sua nova substituição.</span><span class="sxs-lookup"><span data-stu-id="af34f-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="af34f-122">No campo Descrição, insira uma descrição da substituição.</span><span class="sxs-lookup"><span data-stu-id="af34f-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="af34f-123">Ajuste o status para "Habilitar".</span><span class="sxs-lookup"><span data-stu-id="af34f-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="af34f-124">Expandir ou recolher a seção Substituições.</span><span class="sxs-lookup"><span data-stu-id="af34f-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="af34f-125">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="af34f-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="af34f-126">Os grupos dos impostos sobre venda do artigo podem ser usados para cancelar impostos para os artigos específicos que pertencem ao grupo.</span><span class="sxs-lookup"><span data-stu-id="af34f-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="af34f-127">Por exemplo, os alimentos são taxados tipicamente diferentemente dos bens duráveis, e teriam provavelmente seu próprio grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="af34f-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="af34f-128">Os grupos dos impostos sobre venda são grupos de impostos que são aplicáveis a um canal particular.</span><span class="sxs-lookup"><span data-stu-id="af34f-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="af34f-129">Por exemplo, se um canal vende o varejo e um interempresarial, os grupos diferentes dos impostos sobre venda dos artigos podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="af34f-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="af34f-130">Todos os impostos aplicáveis seriam traçados ao grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="af34f-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="af34f-131">Agora você pode selecionar "De" e "Para" impostos ou "Do grupo de impostos" e "Para grupo de impostos" para criar sua substituição de impostos.</span><span class="sxs-lookup"><span data-stu-id="af34f-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="af34f-132">O campo "De" indica o imposto ou o grupo do imposto a ser substituído.</span><span class="sxs-lookup"><span data-stu-id="af34f-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="af34f-133">Substituição pelo grupo dos impostos sobre venda do artigo fornece opções diferentes do que cancelar pelo grupo dos impostos sobre venda.</span><span class="sxs-lookup"><span data-stu-id="af34f-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="af34f-134">A substituição dos impostos sobre venda pode estabelecer-se para cancelar impostos em transações inteiras ou em linhas particulares na transação.</span><span class="sxs-lookup"><span data-stu-id="af34f-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="af34f-135">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="af34f-135">Click Save.</span></span>
14. <span data-ttu-id="af34f-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="af34f-136">Close the page.</span></span>
15. <span data-ttu-id="af34f-137">Vá para Retail e Commerce > Configuração de canal > Impostos > Grupos de substituições de impostos.</span><span class="sxs-lookup"><span data-stu-id="af34f-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="af34f-138">Nesta etapa você atribuiu a ultrapassagem recém-criada dos impostos sobre venda ao grupo da ultrapassagem dos impostos sobre venda atribuído ao canal de Houston.</span><span class="sxs-lookup"><span data-stu-id="af34f-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="af34f-139">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="af34f-139">Click Edit.</span></span>
17. <span data-ttu-id="af34f-140">Expanda ou recolha a seção Configuração.</span><span class="sxs-lookup"><span data-stu-id="af34f-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="af34f-141">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="af34f-141">Click Add.</span></span>
19. <span data-ttu-id="af34f-142">No campo Substituir imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="af34f-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="af34f-143">Selecione a substituição previamente criada dos impostos sobre venda da lista.</span><span class="sxs-lookup"><span data-stu-id="af34f-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="af34f-144">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="af34f-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="af34f-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="af34f-145">Click Save.</span></span>

