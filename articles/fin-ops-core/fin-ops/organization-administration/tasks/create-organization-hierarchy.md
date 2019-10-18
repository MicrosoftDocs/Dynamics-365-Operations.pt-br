---
title: Criar uma hierarquia da organização
description: Use o procedimento a seguir para criar uma hierarquia organizacional.
author: sericks007
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48c8564694b22a5110341d853a79096fbe805c91
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176498"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="55d1b-103">Criar uma hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="55d1b-103">Create an organization hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55d1b-104">Use o procedimento a seguir para criar uma hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="55d1b-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="55d1b-105">Você pode usar hierarquias organizacionais para exibir e fazer relatórios sobre a empresa sob várias perspectivas.</span><span class="sxs-lookup"><span data-stu-id="55d1b-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="55d1b-106">Por exemplo, você pode configurar uma hierarquia para relatórios de impostos, legais ou estatutários.</span><span class="sxs-lookup"><span data-stu-id="55d1b-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="55d1b-107">Você pode configurar outra hierarquia para criar relatórios sobre informações financeiras que não são necessárias legalmente, mas que são usadas para fins de relatórios internos.</span><span class="sxs-lookup"><span data-stu-id="55d1b-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="55d1b-108">Antes de criar uma hierarquia organizacional, você deve criar organizações.</span><span class="sxs-lookup"><span data-stu-id="55d1b-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="55d1b-109">Para obter mais informações, consulte "Criar uma pessoa jurídica" ou "Criar as tarefas de uma unidade operacional".</span><span class="sxs-lookup"><span data-stu-id="55d1b-109">For more information, see the “Create a legal entity” or “Create an operating unit” tasks.</span></span> <span data-ttu-id="55d1b-110">Você também pode departamentos e equipes.</span><span class="sxs-lookup"><span data-stu-id="55d1b-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="55d1b-111">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="55d1b-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="55d1b-112">Criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="55d1b-112">Create a hierarchy</span></span>
1. <span data-ttu-id="55d1b-113">Vá para **Painel de Navegação > Módulos > Administração da organização > Organizações > Hierarquias da organização**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="55d1b-114">No **Painel de Ações**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="55d1b-115">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="55d1b-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="55d1b-116">Na seção **Finalidade**, clique em **Atribuir finalidade**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="55d1b-117">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="55d1b-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="55d1b-118">Selecione uma finalidade para atribuir a hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="55d1b-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="55d1b-119">Na seção **Hierarquias atribuídas**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-119">In the **Assigned hierarchies** sectiom, click **Add**.</span></span>
7. <span data-ttu-id="55d1b-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="55d1b-120">In the list, mark the selected row.</span></span> <span data-ttu-id="55d1b-121">Localizar a hierarquia que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="55d1b-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="55d1b-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="55d1b-123">Adicionar organizações à hierarquia</span><span class="sxs-lookup"><span data-stu-id="55d1b-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="55d1b-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="55d1b-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="55d1b-125">Selecionar sua hierarquia.</span><span class="sxs-lookup"><span data-stu-id="55d1b-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="55d1b-126">Na seção **Hierarquias atribuídas**, clique em **Exibir hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="55d1b-127">Adicione organizações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="55d1b-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="55d1b-128">Para adicionar uma organização, clique em **Editar** e **Inserir** para adicionar a organização.</span><span class="sxs-lookup"><span data-stu-id="55d1b-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="55d1b-129">Ao terminar de fazer alterações, você pode **salvar** um rascunho e/ou **publicar** as alterações.</span><span class="sxs-lookup"><span data-stu-id="55d1b-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  

