---
title: Criar grupos de permissões de PDV
description: Este tópico explica como criar um grupo de permissões de PDV.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6f9f8f970f336a0cce6bcac78e32a1b7fe0a252
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021607"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="5b482-103">Criar grupos de permissões de PDV</span><span class="sxs-lookup"><span data-stu-id="5b482-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5b482-104">Este tópico explica como criar um grupo de permissões de PDV.</span><span class="sxs-lookup"><span data-stu-id="5b482-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="5b482-105">A empresa de dados de demonstração usada para criar esta tarefa é USRT.</span><span class="sxs-lookup"><span data-stu-id="5b482-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="5b482-106">Esta tarefa é destinada à função Gerente de operações de comércio.</span><span class="sxs-lookup"><span data-stu-id="5b482-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="5b482-107">No painel de navegação, vá para **Módulos > Varejo e Comércio > Funcionários > Grupos de permissões**.</span><span class="sxs-lookup"><span data-stu-id="5b482-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="5b482-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5b482-108">Select **New**.</span></span>
3. <span data-ttu-id="5b482-109">No campo **ID do grupo de permissões de PDV**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5b482-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="5b482-110">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5b482-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="5b482-111">Selecione **Sim** no campo **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="5b482-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="5b482-112">Agora você pode habilitar ou desabilitar várias permissões para seu grupo de permissões de PDV.</span><span class="sxs-lookup"><span data-stu-id="5b482-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="5b482-113">Para algumas permissões, você pode definir um valor que será usado para avaliar se o usuário do PDV pode executar a ação.</span><span class="sxs-lookup"><span data-stu-id="5b482-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="5b482-114">Este guia de tarefas mostra como habilitar algumas permissões que podem ser dadas a um caixa.</span><span class="sxs-lookup"><span data-stu-id="5b482-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="5b482-115">Selecione **Sim** no **campo Permitir criar ordem**.</span><span class="sxs-lookup"><span data-stu-id="5b482-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="5b482-116">Selecione **Sim** no campo **Permitir editar ordem**.</span><span class="sxs-lookup"><span data-stu-id="5b482-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="5b482-117">Selecione **Sim** no campo **Permitir recuperar ordem**.</span><span class="sxs-lookup"><span data-stu-id="5b482-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="5b482-118">Selecione **Sim** no campo **Permitir alteração de senha**.</span><span class="sxs-lookup"><span data-stu-id="5b482-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="5b482-119">Selecione **Sim** no campo **Permitir fechamento cego**.</span><span class="sxs-lookup"><span data-stu-id="5b482-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="5b482-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5b482-120">Select **Save**.</span></span> <span data-ttu-id="5b482-121">Depois que as alterações forem salvas, será necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais de comércio.</span><span class="sxs-lookup"><span data-stu-id="5b482-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="5b482-122">No Painel de Navegação, vá para **Módulos > Recursos humanos > Trabalhos > Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="5b482-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="5b482-123">A seguir, atribuiremos o grupo de permissões de PDV a um trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b482-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="5b482-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="5b482-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5b482-125">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5b482-125">Select **Edit**.</span></span>
15. <span data-ttu-id="5b482-126">Expanda a seção **Classificação do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5b482-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="5b482-127">No campo grupo de permissões de PDV, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5b482-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="5b482-128">Todos os trabalhadores em posições para esse trabalho usarão estas configurações de grupo de permissões de PDV a menos que as permissões de PDV dos trabalhadores tenham sido substituídas em suas posições.</span><span class="sxs-lookup"><span data-stu-id="5b482-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="5b482-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5b482-129">Select **Save**.</span></span> <span data-ttu-id="5b482-130">Depois que as alterações forem salvas, será necessário executar a agenda de distribuição da equipe para enviar as alterações aos canais.</span><span class="sxs-lookup"><span data-stu-id="5b482-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  

