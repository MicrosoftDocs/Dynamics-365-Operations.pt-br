---
title: Remover uma instância
description: Este artigo mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e6d1eff32b6f925541760f0c0408238f3c4d947
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466847"
---
# <a name="remove-an-instance"></a><span data-ttu-id="d7a70-103">Remover uma instância</span><span class="sxs-lookup"><span data-stu-id="d7a70-103">Remove an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d7a70-104">Este artigo mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d7a70-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="d7a70-105">Remover um ambiente de test drive</span><span class="sxs-lookup"><span data-stu-id="d7a70-105">Remove a test drive environment</span></span>

<span data-ttu-id="d7a70-106">Os test drives do Human Resources são provisionados com uma política de vencimento de 60 dias.</span><span class="sxs-lookup"><span data-stu-id="d7a70-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="d7a70-107">No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="d7a70-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="d7a70-108">Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d7a70-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="d7a70-109">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-109">Select **Environments**.</span></span>
3. <span data-ttu-id="d7a70-110">Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="d7a70-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="d7a70-111">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="d7a70-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="d7a70-112">O ambiente de test drive existente será removido.</span><span class="sxs-lookup"><span data-stu-id="d7a70-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="d7a70-113">Quando for removido, inscreva-se em um novo ambiente de test drive.</span><span class="sxs-lookup"><span data-stu-id="d7a70-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="d7a70-114">Remover um ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="d7a70-114">Remove a production environment</span></span>

<span data-ttu-id="d7a70-115">Este tópico pressupõe que você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA).</span><span class="sxs-lookup"><span data-stu-id="d7a70-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="d7a70-116">Como um ambiente único do Human Resources é contido em um ambiente único do Power Apps, há duas opções a serem consideradas.</span><span class="sxs-lookup"><span data-stu-id="d7a70-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="d7a70-117">A primeira opção envolve a remoção de todo o ambiente do Power Apps; a segunda opção envolve somente a remoção do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d7a70-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="d7a70-118">A primeira opção é preferível quando você tiver criado um ambiente do Power Apps especificamente para provisionar o Human Resources e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida.</span><span class="sxs-lookup"><span data-stu-id="d7a70-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="d7a70-119">A segunda opção será recomendável quando você tiver um ambiente estabelecido do Power Apps preenchido com dados avançados aproveitados no Power Apps e no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d7a70-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="d7a70-120">Antes de remover o ambiente do Power Apps, verifique se ele não está sendo usado para integrações de dados avançados fora do escopo do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d7a70-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="d7a70-121">Observe também que os ambientes do Power Apps não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="d7a70-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="d7a70-122">Para remover todo o ambiente do Power Apps, incluindo o Human Resources e os aplicativos e fluxos associados:</span><span class="sxs-lookup"><span data-stu-id="d7a70-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="d7a70-123">Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d7a70-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="d7a70-124">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-124">Select **Environments**.</span></span>
3. <span data-ttu-id="d7a70-125">Selecione o ambiente a ser removido.</span><span class="sxs-lookup"><span data-stu-id="d7a70-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="d7a70-126">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="d7a70-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="d7a70-127">Aguarde até que a exclusão seja concluída.</span><span class="sxs-lookup"><span data-stu-id="d7a70-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="d7a70-128">Entre no [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) usando a conta utilizada para inscrever-se no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d7a70-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="d7a70-129">Selecione o projeto do Human Resources que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="d7a70-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="d7a70-130">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="d7a70-131">Selecione a instância a ser removida.</span><span class="sxs-lookup"><span data-stu-id="d7a70-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="d7a70-132">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="d7a70-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="d7a70-133">Para remover um ambiente do Human Resources de um ambiente existente do Power Apps, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d7a70-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="d7a70-134">Observe que a necessidade de envolver o suporte e contatar a equipe do Human Resources DevOps é temporária até que esse recurso seja habilitado diretamente no LCS.</span><span class="sxs-lookup"><span data-stu-id="d7a70-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="d7a70-135">Contate o suporte para iniciar uma solicitação de remoção.</span><span class="sxs-lookup"><span data-stu-id="d7a70-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="d7a70-136">A equipe de suporte iniciará uma solicitação de remoção com a equipe do Human Resources DevOps.</span><span class="sxs-lookup"><span data-stu-id="d7a70-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="d7a70-137">Continue após ser informado de que o ambiente foi removido.</span><span class="sxs-lookup"><span data-stu-id="d7a70-137">Continue after you receive word that the environment has been removed.</span></span>
4. <span data-ttu-id="d7a70-138">Entre no LCS usando a conta utilizada para inscrever-se no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d7a70-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="d7a70-139">Selecione o projeto do Human Resources que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="d7a70-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="d7a70-140">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="d7a70-141">Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Deleted**.</span></span>
8. <span data-ttu-id="d7a70-142">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="d7a70-142">Select **Remove instance** and confirm your decision.</span></span> 

## <a name="recover-a-soft-deleted-environment"></a><span data-ttu-id="d7a70-143">Recuperar um ambiente excluído de forma reversível</span><span class="sxs-lookup"><span data-stu-id="d7a70-143">Recover a soft-deleted environment</span></span>

<span data-ttu-id="d7a70-144">Se você excluir o ambiente do Power Apps ao qual o seu ambiente de Recursos Humanos está conectado, o status do ambiente de Recursos Humanos no Lifecycle Services será **Excluído de forma reversível**.</span><span class="sxs-lookup"><span data-stu-id="d7a70-144">If you delete the Power Apps environment that your Human Resources environment is connected to, the status of the Human Resources environment in Lifecycle Services will be **Soft deleted**.</span></span> <span data-ttu-id="d7a70-145">Nesse caso, os usuários não podem se conectar aos Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="d7a70-145">In this case, users can't connect to Human Resources.</span></span>

<span data-ttu-id="d7a70-146">Para restaurar o ambiente:</span><span class="sxs-lookup"><span data-stu-id="d7a70-146">To restore the environment:</span></span>

1. <span data-ttu-id="d7a70-147">Siga as instruções no [ambiente Recuperar o Power Apps](/power-platform/admin/recover-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d7a70-147">Follow the instructions in [Recover the Power Apps environment](/power-platform/admin/recover-environment.md).</span></span>

2. <span data-ttu-id="d7a70-148">Entre em contato com o suporte para restaurar o ambiente de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="d7a70-148">Contact Support to restore the Human Resources environment.</span></span> <span data-ttu-id="d7a70-149">Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="d7a70-149">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

> [!Warning]
> <span data-ttu-id="d7a70-150">Os ambientes do Power Apps só são salvos por sete dias após a exclusão.</span><span class="sxs-lookup"><span data-stu-id="d7a70-150">Power Apps environments are only saved for seven days after deletion.</span></span> <span data-ttu-id="d7a70-151">Você deve recuperar o ambiente no período de sete dias.</span><span class="sxs-lookup"><span data-stu-id="d7a70-151">You must recover the environment within the seven day period.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]