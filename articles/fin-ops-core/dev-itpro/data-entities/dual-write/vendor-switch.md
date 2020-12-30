---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685500"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="088de-103">Alternar entre designs de fornecedor</span><span class="sxs-lookup"><span data-stu-id="088de-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="088de-104">Fluxo de dados do fornecedor</span><span class="sxs-lookup"><span data-stu-id="088de-104">Vendor data flow</span></span> 

<span data-ttu-id="088de-105">Se você optar por usar a entidade **Conta** para armazenar fornecedores do tipo **Organização** e a entidade **Contato** para armazenar fornecedores do tipo **Pessoa**, configure o seguinte fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="088de-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="088de-106">Caso contrário, essa configuração não é necessária.</span><span class="sxs-lookup"><span data-stu-id="088de-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="088de-107">Use o design de fornecedor estendido para fornecedores do tipo Organização</span><span class="sxs-lookup"><span data-stu-id="088de-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="088de-108">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="088de-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="088de-109">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="088de-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="088de-110">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="088de-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="088de-111">Criar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="088de-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="088de-112">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="088de-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="088de-113">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="088de-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="088de-114">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="088de-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="088de-115">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Contas**.</span><span class="sxs-lookup"><span data-stu-id="088de-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="088de-116">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="088de-116">Then select **OK**.</span></span> <span data-ttu-id="088de-117">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="088de-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Processo de fluxo de trabalho Criar Fornecedores na Tabela Contas](media/create_process.png)

2. <span data-ttu-id="088de-119">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Contas**.</span><span class="sxs-lookup"><span data-stu-id="088de-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="088de-120">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="088de-120">Then select **OK**.</span></span> <span data-ttu-id="088de-121">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="088de-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="088de-122">Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="088de-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="088de-123">Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="088de-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="088de-124">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="088de-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="088de-125">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="088de-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botão Converter para fluxo de trabalho em segundo plano](media/background_workflow.png)

6. <span data-ttu-id="088de-127">Ative os fluxos de trabalho que você criou para as tabelas **Conta** e **Fornecedor** para começar a usar a entidade **Conta** para armazenar informações de fornecedores do tipo **Organização**.</span><span class="sxs-lookup"><span data-stu-id="088de-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="088de-128">Use o design de fornecedor estendido para fornecedores do tipo Pessoa</span><span class="sxs-lookup"><span data-stu-id="088de-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="088de-129">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="088de-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="088de-130">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="088de-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="088de-131">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="088de-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="088de-132">Criar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="088de-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="088de-133">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="088de-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="088de-134">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="088de-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="088de-135">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="088de-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="088de-136">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores do tipo Pessoa na Tabela Contatos**.</span><span class="sxs-lookup"><span data-stu-id="088de-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="088de-137">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="088de-137">Then select **OK**.</span></span> <span data-ttu-id="088de-138">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Contato**.</span><span class="sxs-lookup"><span data-stu-id="088de-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="088de-139">Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores do tipo Pessoa na Tabela Contatos**.</span><span class="sxs-lookup"><span data-stu-id="088de-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="088de-140">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="088de-140">Then select **OK**.</span></span> <span data-ttu-id="088de-141">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Contato**.</span><span class="sxs-lookup"><span data-stu-id="088de-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="088de-142">Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores do tipo Pessoa na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="088de-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="088de-143">Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="088de-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="088de-144">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="088de-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="088de-145">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="088de-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="088de-146">Ative os fluxos de trabalho que você criou nas tabelas **Contato** e **Fornecedor** para começar a usar a entidade **Contato** para armazenar informações de fornecedores do tipo **Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="088de-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
