---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5a18fed2eac4c120dca20a1d7797d047639275b9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750585"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="d0726-103">Alternar entre designs de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d0726-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="d0726-104">Fluxo de dados do fornecedor</span><span class="sxs-lookup"><span data-stu-id="d0726-104">Vendor data flow</span></span> 

<span data-ttu-id="d0726-105">Se você optar por usar a tabela **Conta** para armazenar fornecedores do tipo **Organização** e a tabela **Contato** para armazenar fornecedores do tipo **Pessoa**, configure os seguintes fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0726-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="d0726-106">Caso contrário, essa configuração não é necessária.</span><span class="sxs-lookup"><span data-stu-id="d0726-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="d0726-107">Use o design de fornecedor estendido para fornecedores do tipo Organização</span><span class="sxs-lookup"><span data-stu-id="d0726-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="d0726-108">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0726-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="d0726-109">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="d0726-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="d0726-110">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="d0726-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="d0726-111">Criar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="d0726-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="d0726-112">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="d0726-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="d0726-113">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="d0726-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="d0726-114">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d0726-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="d0726-115">Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Contas**.</span><span class="sxs-lookup"><span data-stu-id="d0726-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="d0726-116">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0726-116">Then select **OK**.</span></span> <span data-ttu-id="d0726-117">Este fluxo de trabalho lida com o cenário de criação de fornecedores para a tabela **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d0726-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Processo de fluxo de trabalho Criar Fornecedores na Tabela Contas](media/create_process.png)

2. <span data-ttu-id="d0726-119">Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Contas**.</span><span class="sxs-lookup"><span data-stu-id="d0726-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="d0726-120">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0726-120">Then select **OK**.</span></span> <span data-ttu-id="d0726-121">Este fluxo de trabalho lida com o cenário de atualização de fornecedores para a tabela **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d0726-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="d0726-122">Crie um processo de fluxo de trabalho para a tabela **Conta** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="d0726-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="d0726-123">Crie um processo de fluxo de trabalho para a tabela **Conta** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="d0726-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="d0726-124">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d0726-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="d0726-125">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="d0726-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botão Converter para fluxo de trabalho em segundo plano](media/background_workflow.png)

6. <span data-ttu-id="d0726-127">Ative os fluxos de trabalho que você criou para as tabelas **Conta** e **Fornecedor** a fim de começar a usar a tabela **Conta** para armazenar informações de fornecedores do tipo **Organização**.</span><span class="sxs-lookup"><span data-stu-id="d0726-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="d0726-128">Use o design de fornecedor estendido para fornecedores do tipo Pessoa</span><span class="sxs-lookup"><span data-stu-id="d0726-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="d0726-129">O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0726-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="d0726-130">Você criará um fluxo de trabalho para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="d0726-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="d0726-131">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="d0726-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="d0726-132">Criar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="d0726-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="d0726-133">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="d0726-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="d0726-134">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="d0726-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="d0726-135">Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d0726-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="d0726-136">Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores do tipo Pessoa na Tabela Contatos**.</span><span class="sxs-lookup"><span data-stu-id="d0726-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="d0726-137">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0726-137">Then select **OK**.</span></span> <span data-ttu-id="d0726-138">Este fluxo de trabalho lida com o cenário de criação de fornecedores para a tabela **Contato**.</span><span class="sxs-lookup"><span data-stu-id="d0726-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="d0726-139">Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores do tipo Pessoa na Tabela Contatos**.</span><span class="sxs-lookup"><span data-stu-id="d0726-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="d0726-140">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0726-140">Then select **OK**.</span></span> <span data-ttu-id="d0726-141">Este fluxo de trabalho lida com o cenário de atualização de fornecedores para a tabela **Contato**.</span><span class="sxs-lookup"><span data-stu-id="d0726-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="d0726-142">Crie um processo de fluxo de trabalho para a tabela **Contato** e selecione o modelo **Criar Fornecedores do tipo Pessoa na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="d0726-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="d0726-143">Crie um processo de fluxo de trabalho para a tabela **Contato** e selecione o modelo **Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="d0726-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="d0726-144">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d0726-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="d0726-145">Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="d0726-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="d0726-146">Ative os fluxos de trabalho que você criou nas tabelas **Contato** e **Fornecedor** para começar a usar a tabela **Contato** para armazenar informações de fornecedores do tipo **Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="d0726-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]