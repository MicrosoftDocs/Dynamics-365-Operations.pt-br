---
title: Criar uma BOM de modelo
description: "Você pode criar uma BOM de modelo usando uma variedade de métodos."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 89c5d45ac27a8678c51fb63c0326c2802a094596
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-template-bom"></a><span data-ttu-id="f5258-103">Criar uma BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="f5258-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f5258-104">Você pode criar uma BOM de modelo usando qualquer um dos seguintes métodos.</span><span class="sxs-lookup"><span data-stu-id="f5258-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="f5258-105">Para todos os métodos, os campos **Data de início** e **Data de término** são opcionais e apenas informativos.</span><span class="sxs-lookup"><span data-stu-id="f5258-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="f5258-106">Criar uma BOM de modelo manualmente</span><span class="sxs-lookup"><span data-stu-id="f5258-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="f5258-107">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f5258-108">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f5258-109">Em **Copiar linhas de BOM de referência**, selecione a opção **Manual**.</span><span class="sxs-lookup"><span data-stu-id="f5258-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="f5258-110">No campo **Número de item**, insira um item do tipo **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f5258-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="f5258-111">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f5258-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f5258-112">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="f5258-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f5258-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5258-113">Click **OK**.</span></span>

<span data-ttu-id="f5258-114">Uma nova BOM de modelo em branco é criada.</span><span class="sxs-lookup"><span data-stu-id="f5258-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="f5258-115">Criar uma BOM de modelo baseada em outra BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="f5258-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="f5258-116">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f5258-117">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f5258-118">Em **Copiar linhas de BOM de referência**, selecione a opção **BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="f5258-119">No campo **Número de referência**, selecione uma BOM de modelo existente para copiar para sua nova BOM de modelo.</span><span class="sxs-lookup"><span data-stu-id="f5258-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="f5258-120">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f5258-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f5258-121">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="f5258-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f5258-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5258-122">Click **OK**.</span></span>

<span data-ttu-id="f5258-123">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM de modelo original.</span><span class="sxs-lookup"><span data-stu-id="f5258-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="f5258-124">Criar uma BOM de modelo baseada em um BOM de itens</span><span class="sxs-lookup"><span data-stu-id="f5258-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="f5258-125">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f5258-126">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f5258-127">Em **Copiar linhas da BOM da referência**, selecione **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f5258-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="f5258-128">No campo **Número de referência**, selecione uma versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="f5258-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="f5258-129">Um item do tipo BOM é copiado para **Número de item**.</span><span class="sxs-lookup"><span data-stu-id="f5258-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="f5258-130">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f5258-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f5258-131">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="f5258-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f5258-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5258-132">Click **OK**.</span></span>

<span data-ttu-id="f5258-133">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **Lista de materiais**.</span><span class="sxs-lookup"><span data-stu-id="f5258-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="f5258-134">Criar uma BOM de modelo baseada em um BOM de produção</span><span class="sxs-lookup"><span data-stu-id="f5258-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="f5258-135">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f5258-136">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="f5258-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f5258-137">Em **Copiar linhas da BOM da referência**, selecione **Produção**.</span><span class="sxs-lookup"><span data-stu-id="f5258-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="f5258-138">No campo **Número de referência**, selecione uma BOM de produção.</span><span class="sxs-lookup"><span data-stu-id="f5258-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="f5258-139">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f5258-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f5258-140">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="f5258-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f5258-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5258-141">Click **OK**.</span></span>

<span data-ttu-id="f5258-142">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f5258-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5258-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f5258-143">See also</span></span>

[<span data-ttu-id="f5258-144">BOMs de modelo</span><span class="sxs-lookup"><span data-stu-id="f5258-144">Template BOMs</span></span>](template-boms.md)

  



