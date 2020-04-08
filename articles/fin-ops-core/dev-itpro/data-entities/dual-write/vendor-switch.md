---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: ffd7a4c01810578b4abb6942aeff76e5147fafa9
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173030"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="608df-103">Alternar entre designs de fornecedor</span><span class="sxs-lookup"><span data-stu-id="608df-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="608df-104">Fluxo de dados do fornecedor</span><span class="sxs-lookup"><span data-stu-id="608df-104">Vendor data flow</span></span> 

<span data-ttu-id="608df-105">Se você optar por usar a entidade **Conta** para armazenar fornecedores do tipo **Organização** e a entidade **Contato** para armazenar fornecedores do tipo **Pessoa**, configure o seguinte fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="608df-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="608df-106">Caso contrário, essa configuração não é necessária.</span><span class="sxs-lookup"><span data-stu-id="608df-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="608df-107">Use o design de fornecedor estendido para fornecedores do tipo Organização</span><span class="sxs-lookup"><span data-stu-id="608df-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="608df-108">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="608df-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="608df-109">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="608df-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="608df-110">Criar fornecedores na entidade Contas</span><span class="sxs-lookup"><span data-stu-id="608df-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="608df-111">Criar fornecedores na entidade Fornecedores</span><span class="sxs-lookup"><span data-stu-id="608df-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="608df-112">Atualizar fornecedores na entidade Contas</span><span class="sxs-lookup"><span data-stu-id="608df-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="608df-113">Atualizar fornecedores na entidade Fornecedores</span><span class="sxs-lookup"><span data-stu-id="608df-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="608df-114">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="608df-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="608df-115">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores na entidade Contas**.</span><span class="sxs-lookup"><span data-stu-id="608df-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="608df-116">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="608df-116">Then select **OK**.</span></span> <span data-ttu-id="608df-117">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="608df-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Criar fornecedores no processo de fluxo de trabalho da entidade Contas](media/create_process.png)

2. <span data-ttu-id="608df-119">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores na entidade Contas**.</span><span class="sxs-lookup"><span data-stu-id="608df-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="608df-120">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="608df-120">Then select **OK**.</span></span> <span data-ttu-id="608df-121">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="608df-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="608df-122">Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores na entidade Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="608df-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="608df-123">Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores na entidade Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="608df-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="608df-124">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="608df-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="608df-125">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="608df-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botão Converter para fluxo de trabalho em segundo plano](media/background_workflow.png)

6. <span data-ttu-id="608df-127">Ative os fluxos de trabalho que você criou para as entidades **Conta** e **Fornecedor** para começar a usar a entidade **Conta** para armazenar informações de fornecedores do tipo **Organização**.</span><span class="sxs-lookup"><span data-stu-id="608df-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="608df-128">Use o design de fornecedor estendido para fornecedores do tipo Pessoa</span><span class="sxs-lookup"><span data-stu-id="608df-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="608df-129">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="608df-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="608df-130">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="608df-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="608df-131">Criar fornecedores do tipo Pessoa na entidade Fornecedores</span><span class="sxs-lookup"><span data-stu-id="608df-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="608df-132">Criar fornecedores do tipo Pessoa na entidade Contatos</span><span class="sxs-lookup"><span data-stu-id="608df-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="608df-133">Atualizar fornecedores do tipo Pessoa na entidade Contatos</span><span class="sxs-lookup"><span data-stu-id="608df-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="608df-134">Atualizar fornecedores do tipo Pessoa na entidade Fornecedores</span><span class="sxs-lookup"><span data-stu-id="608df-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="608df-135">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="608df-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="608df-136">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores do tipo Pessoa na entidade Contatos**.</span><span class="sxs-lookup"><span data-stu-id="608df-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="608df-137">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="608df-137">Then select **OK**.</span></span> <span data-ttu-id="608df-138">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Contato**.</span><span class="sxs-lookup"><span data-stu-id="608df-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="608df-139">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores do tipo Pessoa na entidade Contatos**.</span><span class="sxs-lookup"><span data-stu-id="608df-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="608df-140">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="608df-140">Then select **OK**.</span></span> <span data-ttu-id="608df-141">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Contato**.</span><span class="sxs-lookup"><span data-stu-id="608df-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="608df-142">Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores do tipo Pessoa na entidade Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="608df-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="608df-143">Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores do tipo Pessoa na entidade Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="608df-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="608df-144">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="608df-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="608df-145">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="608df-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="608df-146">Ative os fluxos de trabalho que você criou nas entidades **Contato** e **Fornecedor** para começar a usar a entidade **Contato** para armazenar informações de fornecedores do tipo **Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="608df-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
