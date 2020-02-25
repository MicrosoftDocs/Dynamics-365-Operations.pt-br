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
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019633"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="d9c09-103">Alternar entre designs de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d9c09-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="d9c09-104">Fluxo de dados do fornecedor</span><span class="sxs-lookup"><span data-stu-id="d9c09-104">Vendor data flow</span></span> 

<span data-ttu-id="d9c09-105">Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer separar as informações de fornecedores das informações de clientes, utilize este design básico de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d9c09-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Fluxo básico de fornecedores](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="d9c09-107">Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer continuar usando a entidade **Conta** para armazenar informações de fornecedores, utilize este design de fornecedor estendido.</span><span class="sxs-lookup"><span data-stu-id="d9c09-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="d9c09-108">Neste design, informações estendidas de fornecedores, como status em espera e o perfil do fornecedor, são armazenadas na entidade **fornecedores** do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d9c09-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Fluxo estendido de fornecedores](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="d9c09-110">Siga as etapas abaixo para usar o design estendido de fornecedor:</span><span class="sxs-lookup"><span data-stu-id="d9c09-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="d9c09-111">O pacote de soluções **SupplyChainCommon** contém os modelos do processo de fluxo de trabalho mostrados na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="d9c09-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d9c09-112">![Modelos do processo de fluxo de trabalho](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="d9c09-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="d9c09-113">Crie novos processos de fluxo de trabalho usando os modelos do processo de fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="d9c09-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="d9c09-114">Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Criar Fornecedores na Entidade Conta** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9c09-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d9c09-115">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d9c09-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d9c09-116">![Criar Fornecedores na Entidade Conta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="d9c09-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="d9c09-117">Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Atualizar Entidade Contas** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9c09-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d9c09-118">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d9c09-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d9c09-119">![Atualizar Entidade Contas](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="d9c09-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="d9c09-120">Crie novos processos de fluxo de trabalho com base nos modelos criados na entidade **Contas**.</span><span class="sxs-lookup"><span data-stu-id="d9c09-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d9c09-121">![Criar fornecedores na entidade fornecedores](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="d9c09-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="d9c09-122">![Atualizar a entidade fornecedores](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="d9c09-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="d9c09-123">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d9c09-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d9c09-124">![Converter para fluxo de trabalho em segundo plano](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="d9c09-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="d9c09-125">Ative os fluxos de trabalho que você criou nas entidades **Conta** e **Fornecedor** para começar a usar a entidade **Conta** para armazenar informações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d9c09-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
