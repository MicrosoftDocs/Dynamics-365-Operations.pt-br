---
title: Alternar entre designs de fornecedor
description: ''
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
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772355"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="d7897-102">Alternar entre designs de fornecedor</span><span class="sxs-lookup"><span data-stu-id="d7897-102">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="d7897-103">Fluxo de dados do fornecedor</span><span class="sxs-lookup"><span data-stu-id="d7897-103">Vendor data flow</span></span> 

<span data-ttu-id="d7897-104">Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer separar as informações de fornecedores das informações de clientes, utilize este design básico de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d7897-104">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Fluxo básico de fornecedores](media/dual-write-switch-1.png)
 
<span data-ttu-id="d7897-106">Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer continuar usando a entidade **Conta** para armazenar informações de fornecedores, utilize este design de fornecedor estendido.</span><span class="sxs-lookup"><span data-stu-id="d7897-106">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="d7897-107">Neste design, informações estendidas de fornecedores, como status em espera e o perfil do fornecedor, são armazenadas na entidade **fornecedores** do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d7897-107">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Fluxo estendido de fornecedores](media/dual-write-switch-2.png)
 
<span data-ttu-id="d7897-109">Siga as etapas abaixo para usar o design estendido de fornecedor:</span><span class="sxs-lookup"><span data-stu-id="d7897-109">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="d7897-110">O pacote de soluções **SupplyChainCommon** contém os modelos do processo de fluxo de trabalho mostrados na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="d7897-110">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7897-111">![Modelos do processo de fluxo de trabalho](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="d7897-111">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="d7897-112">Crie novos processos de fluxo de trabalho usando os modelos do processo de fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="d7897-112">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="d7897-113">Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Criar Fornecedores na Entidade Conta** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7897-113">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d7897-114">Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d7897-114">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d7897-115">![Criar Fornecedores na Entidade Conta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="d7897-115">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="d7897-116">Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Atualizar Entidade Contas** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7897-116">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d7897-117">Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d7897-117">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d7897-118">![Atualizar Entidade Contas](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="d7897-118">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="d7897-119">Crie novos processos de fluxo de trabalho com base nos modelos criados na entidade **Contas**.</span><span class="sxs-lookup"><span data-stu-id="d7897-119">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d7897-120">![Criar fornecedores na entidade fornecedores](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="d7897-120">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="d7897-121">![Atualizar a entidade fornecedores](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="d7897-121">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="d7897-122">Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d7897-122">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d7897-123">![Converter para fluxo de trabalho em segundo plano](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="d7897-123">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="d7897-124">Ative os fluxos de trabalho que você criou nas entidades **Conta** e **Fornecedor** para começar a usar a entidade **Conta** do Customer Engagement para armazenar informações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d7897-124">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the Customer Engagement **Account** entity for storing vendor information.</span></span> 
 
