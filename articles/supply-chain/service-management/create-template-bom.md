---
title: Criar uma BOM de modelo
description: Você pode criar uma BOM de modelo usando uma variedade de métodos.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 815b6b726e9a76a9294995bc5689b030cf623ec0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202574"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="2fb25-103">Criar uma BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="2fb25-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2fb25-104">Você pode criar uma BOM de modelo usando qualquer um dos seguintes métodos.</span><span class="sxs-lookup"><span data-stu-id="2fb25-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="2fb25-105">Para todos os métodos, os campos **Data de início** e **Data de término** são opcionais e apenas informativos.</span><span class="sxs-lookup"><span data-stu-id="2fb25-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="2fb25-106">Criar uma BOM de modelo manualmente</span><span class="sxs-lookup"><span data-stu-id="2fb25-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="2fb25-107">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="2fb25-108">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="2fb25-109">Em **Copiar linhas de BOM de referência**, selecione a opção **Manual**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="2fb25-110">No campo **Número de item**, insira um item do tipo **BOM**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="2fb25-111">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="2fb25-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="2fb25-112">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="2fb25-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="2fb25-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-113">Click **OK**.</span></span>

<span data-ttu-id="2fb25-114">Uma nova BOM de modelo em branco é criada.</span><span class="sxs-lookup"><span data-stu-id="2fb25-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="2fb25-115">Criar uma BOM de modelo baseada em outra BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="2fb25-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="2fb25-116">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="2fb25-117">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="2fb25-118">Em **Copiar linhas de BOM de referência**, selecione a opção **BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="2fb25-119">No campo **Número de referência**, selecione uma BOM de modelo existente para copiar para sua nova BOM de modelo.</span><span class="sxs-lookup"><span data-stu-id="2fb25-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="2fb25-120">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="2fb25-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="2fb25-121">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="2fb25-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="2fb25-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-122">Click **OK**.</span></span>

<span data-ttu-id="2fb25-123">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM de modelo original.</span><span class="sxs-lookup"><span data-stu-id="2fb25-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="2fb25-124">Criar uma BOM de modelo baseada em um BOM de itens</span><span class="sxs-lookup"><span data-stu-id="2fb25-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="2fb25-125">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="2fb25-126">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="2fb25-127">Em **Copiar linhas da BOM da referência**, selecione **BOM**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="2fb25-128">No campo **Número de referência**, selecione uma versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="2fb25-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="2fb25-129">Um item do tipo BOM é copiado para **Número de item**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="2fb25-130">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="2fb25-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="2fb25-131">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="2fb25-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="2fb25-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-132">Click **OK**.</span></span>

<span data-ttu-id="2fb25-133">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **Lista de materiais**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="2fb25-134">Criar uma BOM de modelo baseada em um BOM de produção</span><span class="sxs-lookup"><span data-stu-id="2fb25-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="2fb25-135">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="2fb25-136">Pressione CTRL+N para abrir o formulário **Criar BOM de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="2fb25-137">Em **Copiar linhas da BOM da referência**, selecione **Produção**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="2fb25-138">No campo **Número de referência**, selecione uma BOM de produção.</span><span class="sxs-lookup"><span data-stu-id="2fb25-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="2fb25-139">No campo **Nome**, digite um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="2fb25-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="2fb25-140">Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.</span><span class="sxs-lookup"><span data-stu-id="2fb25-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="2fb25-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-141">Click **OK**.</span></span>

<span data-ttu-id="2fb25-142">Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **BOM**.</span><span class="sxs-lookup"><span data-stu-id="2fb25-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fb25-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2fb25-143">See also</span></span>

[<span data-ttu-id="2fb25-144">BOMs de modelo</span><span class="sxs-lookup"><span data-stu-id="2fb25-144">Template BOMs</span></span>](template-boms.md)

  


