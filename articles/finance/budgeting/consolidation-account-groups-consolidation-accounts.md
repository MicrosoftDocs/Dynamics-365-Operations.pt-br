---
title: Grupos de contas de consolidação e contas adicionais de consolidação
description: Este tópico fornece informações sobre grupos de contas de consolidação e contas de consolidação adicionais e explica como eles são usados no Microsoft Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8db7a60656434aafd8114b08c2c0e9493140f27b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176447"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="edeba-103">Grupos de contas de consolidação e contas adicionais de consolidação</span><span class="sxs-lookup"><span data-stu-id="edeba-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edeba-104">Este tópico fornece informações sobre grupos de contas de consolidação e contas de consolidação adicionais e explica como eles são usados no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="edeba-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 Finance.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="edeba-105">Grupos de contas de consolidação</span><span class="sxs-lookup"><span data-stu-id="edeba-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="edeba-106">Grupos de contas de consolidação permitem que você crie grupos das contas que deseja usar para consolidar dados.</span><span class="sxs-lookup"><span data-stu-id="edeba-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="edeba-107">Frequentemente, um grupo de contas de consolidação representa um plano de contas exigido pelo governo ou mapeia contas para um grupo definido pela matriz da companhia.</span><span class="sxs-lookup"><span data-stu-id="edeba-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="edeba-108">Você pode encontrar grupos de conta de consolidação na área **Configuração** do módulo **Consolidações**.</span><span class="sxs-lookup"><span data-stu-id="edeba-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="edeba-109">Ao adicionar um novo grupo, você insere um identificador exclusivo para o grupo de conta e um nome.</span><span class="sxs-lookup"><span data-stu-id="edeba-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="edeba-110">Contas de consolidação adicionais</span><span class="sxs-lookup"><span data-stu-id="edeba-110">Additional consolidation accounts</span></span>
<span data-ttu-id="edeba-111">Contas de consolidação adicionais permitem atribuir uma conta de um plano de contas existente a um grupo de contas de consolidação.</span><span class="sxs-lookup"><span data-stu-id="edeba-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="edeba-112">Você pode então especificar um valor e um nome de conta de consolidação.</span><span class="sxs-lookup"><span data-stu-id="edeba-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="edeba-113">Você pode encontrar contas de consolidação adicionais na área **Configuração** do módulo **Consolidações**.</span><span class="sxs-lookup"><span data-stu-id="edeba-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="edeba-114">Ao criar uma conta de consolidação, você deve especificar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="edeba-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="edeba-115">**Conta principal** – Este campo é uma pesquisa que mostra todas as contas principais com base no plano de contas selecionado por você na página.</span><span class="sxs-lookup"><span data-stu-id="edeba-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="edeba-116">Ao selecionar uma conta, o nome é automaticamente inserido no campo **Nome da conta principal**.</span><span class="sxs-lookup"><span data-stu-id="edeba-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="edeba-117">**Grupo de contas de consolidação** – Use esse campo para especificar o grupo ao qual a conta será atribuída.</span><span class="sxs-lookup"><span data-stu-id="edeba-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="edeba-118">Se houver consolidação de duas formas diferentes, você deve adicionar a mesma conta a todos os quatro grupos de contas de consolidação.</span><span class="sxs-lookup"><span data-stu-id="edeba-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="edeba-119">**Conta de consolidação** – Insira o valor da conta de consolidação.</span><span class="sxs-lookup"><span data-stu-id="edeba-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="edeba-120">Não é preciso que esse valor seja uma conta de um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="edeba-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="edeba-121">Pode ser qualquer valor que você solicitar.</span><span class="sxs-lookup"><span data-stu-id="edeba-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="edeba-122">**Nome da conta de consolidação** – Insira o nome da conta da forma como ele deve ser exibido nas consultas e nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="edeba-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="edeba-123">**Nível SAT** – Este campo é usado para declarar demonstrativos de conta às autoridades fiscais mexicanas.</span><span class="sxs-lookup"><span data-stu-id="edeba-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="edeba-124">Após ter concluído a criação de seus grupos de contas de consolidação e contas de consolidação adicionais, você poderá selecionar o grupo no Processo de consolidação online.</span><span class="sxs-lookup"><span data-stu-id="edeba-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="edeba-125">Para obter mais informações, consulte [Criar grupos de consolidação e contas de consolidação adicionais](../general-ledger/tasks/create-consolidation-groups.md).</span><span class="sxs-lookup"><span data-stu-id="edeba-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 


