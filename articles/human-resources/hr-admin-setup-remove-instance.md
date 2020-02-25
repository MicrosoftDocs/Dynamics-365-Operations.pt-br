---
title: Remover uma instância
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008043"
---
# <a name="remove-an-instance"></a><span data-ttu-id="9a060-102">Remover uma instância</span><span class="sxs-lookup"><span data-stu-id="9a060-102">Remove an instance</span></span>

<span data-ttu-id="9a060-103">Este artigo mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9a060-103">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="9a060-104">Remover um ambiente de test drive</span><span class="sxs-lookup"><span data-stu-id="9a060-104">Remove a test drive environment</span></span>

<span data-ttu-id="9a060-105">Os test drives do Human Resources são provisionados com uma política de vencimento de 60 dias.</span><span class="sxs-lookup"><span data-stu-id="9a060-105">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="9a060-106">No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="9a060-106">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="9a060-107">Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9a060-107">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="9a060-108">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="9a060-108">Select **Environments**.</span></span>
3. <span data-ttu-id="9a060-109">Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="9a060-109">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="9a060-110">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="9a060-110">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="9a060-111">O ambiente de test drive existente será removido.</span><span class="sxs-lookup"><span data-stu-id="9a060-111">The existing test drive environment will be removed.</span></span> <span data-ttu-id="9a060-112">Quando for removido, inscreva-se em um novo ambiente de test drive.</span><span class="sxs-lookup"><span data-stu-id="9a060-112">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="9a060-113">Remover um ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="9a060-113">Remove a production environment</span></span>

<span data-ttu-id="9a060-114">Este tópico pressupõe que você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA).</span><span class="sxs-lookup"><span data-stu-id="9a060-114">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="9a060-115">Como um ambiente único do Human Resources é contido em um ambiente único do Power Apps, há duas opções a serem consideradas.</span><span class="sxs-lookup"><span data-stu-id="9a060-115">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="9a060-116">A primeira opção envolve a remoção de todo o ambiente do Power Apps; a segunda opção envolve somente a remoção do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9a060-116">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="9a060-117">A primeira opção é preferível quando você tiver criado um ambiente do Power Apps especificamente para provisionar o Human Resources e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida.</span><span class="sxs-lookup"><span data-stu-id="9a060-117">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="9a060-118">A segunda opção será recomendável quando você tiver um ambiente estabelecido do Power Apps preenchido com dados avançados aproveitados no Power Apps e no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="9a060-118">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="9a060-119">Antes de remover o ambiente do Power Apps, verifique se ele não está sendo usado para integrações de dados avançados fora do escopo do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9a060-119">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="9a060-120">Observe também que os ambientes do Power Apps não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="9a060-120">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="9a060-121">Para remover todo o ambiente do Power Apps, incluindo o Human Resources e os aplicativos e fluxos associados:</span><span class="sxs-lookup"><span data-stu-id="9a060-121">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="9a060-122">Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9a060-122">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="9a060-123">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="9a060-123">Select **Environments**.</span></span>
3. <span data-ttu-id="9a060-124">Selecione o ambiente a ser removido.</span><span class="sxs-lookup"><span data-stu-id="9a060-124">Select the environment to be removed.</span></span>
4. <span data-ttu-id="9a060-125">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="9a060-125">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="9a060-126">Aguarde até que a exclusão seja concluída.</span><span class="sxs-lookup"><span data-stu-id="9a060-126">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="9a060-127">Entre no [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) usando a conta utilizada para inscrever-se no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9a060-127">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="9a060-128">Selecione o projeto do Human Resources que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="9a060-128">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="9a060-129">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="9a060-129">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="9a060-130">Selecione a instância a ser removida.</span><span class="sxs-lookup"><span data-stu-id="9a060-130">Select the instance to remove.</span></span> 
10. <span data-ttu-id="9a060-131">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="9a060-131">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="9a060-132">Para remover um ambiente do Human Resources de um ambiente existente do Power Apps, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9a060-132">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="9a060-133">Observe que a necessidade de envolver o suporte e contatar a equipe do Human Resources DevOps é temporária até que esse recurso seja habilitado diretamente no LCS.</span><span class="sxs-lookup"><span data-stu-id="9a060-133">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="9a060-134">Contate o suporte para iniciar uma solicitação de remoção.</span><span class="sxs-lookup"><span data-stu-id="9a060-134">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="9a060-135">A equipe de suporte iniciará uma solicitação de remoção com a equipe do Human Resources DevOps.</span><span class="sxs-lookup"><span data-stu-id="9a060-135">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="9a060-136">Continue após ser informado de que o ambiente foi removido.</span><span class="sxs-lookup"><span data-stu-id="9a060-136">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="9a060-137">Entre no LCS usando a conta utilizada para inscrever-se no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9a060-137">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="9a060-138">Selecione o projeto do Human Resources que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="9a060-138">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="9a060-139">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="9a060-139">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="9a060-140">Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Reprovado**.</span><span class="sxs-lookup"><span data-stu-id="9a060-140">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="9a060-141">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="9a060-141">Select **Remove instance** and confirm your decision.</span></span> 
