---
title: Fechamento em massa do período financeiro
description: Este tópico mostra como colocar um período em espera ou fechar permanentemente um período ou mais de uma entidade legal de uma só vez.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a149b35c6964166207effc799a02cd4c59bbb843
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144973"
---
# <a name="mass-financial-period-close"></a><span data-ttu-id="b0b14-103">Fechamento em massa do período financeiro</span><span class="sxs-lookup"><span data-stu-id="b0b14-103">Mass financial period close</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b0b14-104">Este tópico mostra como colocar um período em espera ou fechar permanentemente um período ou mais de uma entidade legal de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="b0b14-104">This topic shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="b0b14-105">Além disso, ela mostra como restringir o grupo de usuários para lançar a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="b0b14-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="b0b14-106">No painel de navegação, vá para **Módulos > Contabilidade > Fechamento de período > Calendários do razão**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-106">In the navigation pane, go to **Modules > General ledger > Period close > Ledger calendars**.</span></span> <span data-ttu-id="b0b14-107">Observe que a lista das entidades legais exibidas depende do calendário fiscal selecionado na página.</span><span class="sxs-lookup"><span data-stu-id="b0b14-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="b0b14-108">Apenas as entidades legais que usam o calendário fiscal selecionado serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="b0b14-108">Only legal entities using the selected fiscal calendar will display.</span></span>
2. <span data-ttu-id="b0b14-109">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-109">Select **Edit**.</span></span>
3. <span data-ttu-id="b0b14-110">Selecionar o período para o qual você deseja modificar o status.</span><span class="sxs-lookup"><span data-stu-id="b0b14-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="b0b14-111">Selecionar as entidades legais para o qual você deseja atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="b0b14-111">Select the legal entities for which you want to update the status.</span></span> <span data-ttu-id="b0b14-112">Você poderá selecionar todas as entidades legais rapidamente selecionando a marca de seleção do lado superior esquerdo da grade.</span><span class="sxs-lookup"><span data-stu-id="b0b14-112">You can quickly select all legal entities by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="b0b14-113">Selecione **Atualizar acesso ao módulo** para definir o acesso de postagem a um módulo selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0b14-113">Select **Update module access** to define the posting access to a selected module.</span></span> <span data-ttu-id="b0b14-114">O status do módulo também pode ser atualizado ao editar os registros na grade.</span><span class="sxs-lookup"><span data-stu-id="b0b14-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="b0b14-115">O botão é útil quando você deseja atualizar rapidamente várias registradoras de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="b0b14-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="b0b14-116">No módulo **Aplicativo**, selecione o módulo no qual deseja atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="b0b14-116">In the **Application** module, select the module that you want to update the status.</span></span> <span data-ttu-id="b0b14-117">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-117">Click **Select**.</span></span>
7. <span data-ttu-id="b0b14-118">No nível de **Acesso**, selecione **Todos**, **Nenhum** ou um grupo de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="b0b14-118">In the **Access** level, select **All**, **None**, or a specific user group.</span></span> <span data-ttu-id="b0b14-119">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-119">Click **Select**.</span></span> <span data-ttu-id="b0b14-120">Tudo indica que todos os usuários com acesso de edição ao módulo podem lançar se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="b0b14-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="b0b14-121">Nenhum indica que os usuários não podem lançar nesse módulo se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="b0b14-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="b0b14-122">Um grupo de usuários específicos apenas indica que os usuários no grupo são capazes de lançar nesse módulo se o período estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="b0b14-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="b0b14-123">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-123">Select **Update**.</span></span>
9. <span data-ttu-id="b0b14-124">Selecione outro período para atualizar o status.</span><span class="sxs-lookup"><span data-stu-id="b0b14-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="b0b14-125">Selecionar as entidades legais para o qual você deseja atualizar o status do período.</span><span class="sxs-lookup"><span data-stu-id="b0b14-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="b0b14-126">Selecione **Atualizar status do período** e defina o status de **Em espera**, **Aberto** ou **Permanentemente fechado**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-126">Select **Update period status** and set the status of **On hold**, **Open**, or **Permanently closed**.</span></span> <span data-ttu-id="b0b14-127">**Aberto** indica o período em que o lançamento é possível, desde que o usuário tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="b0b14-127">**Open** indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="b0b14-128">**Em espera** significa que o período não poderá ser lançado, mas o período pode ser reaberto.</span><span class="sxs-lookup"><span data-stu-id="b0b14-128">**On hold** means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="b0b14-129">**Permanentemente fechado** significa que o período será fechado e nunca pode ser aberto.</span><span class="sxs-lookup"><span data-stu-id="b0b14-129">**Permanently closed** means the period is closed and can never be opened.</span></span> <span data-ttu-id="b0b14-130">Ajustes não podem ser lançados.</span><span class="sxs-lookup"><span data-stu-id="b0b14-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="b0b14-131">Não se recomenda definir um período como **Permanentemente fechado** até que todos os ajustes e auditorias estejam completos.</span><span class="sxs-lookup"><span data-stu-id="b0b14-131">We do not recommend setting a period to **Permanently closed** until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="b0b14-132">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="b0b14-132">Select **Update**.</span></span>

