--- 
title: "Fechamento em massa do período financeiro"
description: "Este procedimento mostra como colocar um usuário coloca de período ou permanentemente fechar um período ou mais de uma entidade legal por vez."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cafd837be054e96afc10d3b78402bdcc67c43c33
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="63332-103">Fechamento em massa do período financeiro</span><span class="sxs-lookup"><span data-stu-id="63332-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63332-104">Este procedimento mostra como colocar um usuário coloca de período ou permanentemente fechar um período ou mais de uma entidade legal por vez.</span><span class="sxs-lookup"><span data-stu-id="63332-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="63332-105">Além disso, ela mostra como restringir o grupo de usuários para lançar a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="63332-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="63332-106">Vá para Contabilidade > Fechamento de período > Calendários do razão.</span><span class="sxs-lookup"><span data-stu-id="63332-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="63332-107">Observe que a lista das entidades legais exibidas depende do calendário fiscal selecionado na página.</span><span class="sxs-lookup"><span data-stu-id="63332-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="63332-108">Apenas as entidades legais que usam o calendário fiscal selecionado serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="63332-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="63332-109">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="63332-109">Click Edit.</span></span>
3. <span data-ttu-id="63332-110">Selecionar o período para o qual você deseja modificar o status.</span><span class="sxs-lookup"><span data-stu-id="63332-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="63332-111">Selecionar as entidades legais para o qual você deseja atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="63332-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="63332-112">Você poderá selecionar todas rapidamente as entidades legais selecione a marca de seleção do lado superior esquerdo de grade.</span><span class="sxs-lookup"><span data-stu-id="63332-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="63332-113">Selecionar o acesso do módulo de atualização para definir de postagem acesso a um módulo selecionado.</span><span class="sxs-lookup"><span data-stu-id="63332-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="63332-114">O status do módulo também pode ser atualizado ao editar os registros na grade.</span><span class="sxs-lookup"><span data-stu-id="63332-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="63332-115">O botão é útil quando você deseja atualizar rapidamente várias registradoras de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="63332-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="63332-116">Em Módulo do aplicativo, selecione o módulo que deseja atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="63332-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="63332-117">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="63332-117">Click Select.</span></span>
7. <span data-ttu-id="63332-118">Em Nível de acesso, selecione Todos, Nenhum, ou um grupo de usuário específico.</span><span class="sxs-lookup"><span data-stu-id="63332-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="63332-119">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="63332-119">Click Select.</span></span>
    * <span data-ttu-id="63332-120">Tudo indica que todos os usuários com acesso de edição ao módulo podem lançar se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="63332-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="63332-121">Nenhum indica que os usuários não podem lançar nesse módulo se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="63332-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="63332-122">Um grupo de usuários específicos apenas indica que os usuários no grupo são capazes de lançar nesse módulo se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="63332-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="63332-123">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="63332-123">Click Update.</span></span>
9. <span data-ttu-id="63332-124">Selecione outro período para atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="63332-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="63332-125">Selecionar as entidades legais para as quais você deseja atualizar o status do período.</span><span class="sxs-lookup"><span data-stu-id="63332-125">Select the legal entities for which you want to update the period status.</span></span>
11. <span data-ttu-id="63332-126">Selecione o status de períodos atualizados e define o status de em espera, aberta, ou fechou-se permanentemente.</span><span class="sxs-lookup"><span data-stu-id="63332-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="63332-127">Aberto indica o período em que o lançamento é possível, desde que o usuário tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="63332-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="63332-128">Em espera significa que o período não poderá ser lançado, mas o período pode ser reaberto.</span><span class="sxs-lookup"><span data-stu-id="63332-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="63332-129">Permanentemente o fechado significa que o período será fechada e nunca pode ser aberto.</span><span class="sxs-lookup"><span data-stu-id="63332-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="63332-130">Ajustes não podem ser lançados.</span><span class="sxs-lookup"><span data-stu-id="63332-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="63332-131">Não se recomenda definir um período como fechado permanentemente até que todos os ajustes e auditorias estejam completos.</span><span class="sxs-lookup"><span data-stu-id="63332-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="63332-132">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="63332-132">Click Update.</span></span>


