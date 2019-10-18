---
title: Remover ambientes do Talent
description: Este tópico mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: d608ee3ad90d23279557e5e9be4d398ffac3a266
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010606"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="22cf0-103">Remover ambientes do Talent</span><span class="sxs-lookup"><span data-stu-id="22cf0-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="22cf0-104">Este tópico mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="22cf0-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="22cf0-105">Removendo um ambiente de test drive</span><span class="sxs-lookup"><span data-stu-id="22cf0-105">Removing a test drive environment</span></span>

<span data-ttu-id="22cf0-106">Os test drives do Talent são provisionados com uma política de vencimento de 60 dias.</span><span class="sxs-lookup"><span data-stu-id="22cf0-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="22cf0-107">No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="22cf0-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="22cf0-108">Navegue até o [Centro de administração do PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="22cf0-108">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="22cf0-109">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="22cf0-109">Select **Environments**.</span></span>
3. <span data-ttu-id="22cf0-110">Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="22cf0-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="22cf0-111">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="22cf0-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="22cf0-112">O ambiente de test drive existente será removido.</span><span class="sxs-lookup"><span data-stu-id="22cf0-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="22cf0-113">Quando for removido, inscreva-se em um novo ambiente de test drive.</span><span class="sxs-lookup"><span data-stu-id="22cf0-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="22cf0-114">Removendo um ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="22cf0-114">Removing a production environment</span></span>

<span data-ttu-id="22cf0-115">Este tópico pressupõe que você adquiriu o Talent por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA).</span><span class="sxs-lookup"><span data-stu-id="22cf0-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="22cf0-116">Como um ambiente único do Talent é “contido" em um ambiente único do PowerApps, há duas opções a serem consideradas.</span><span class="sxs-lookup"><span data-stu-id="22cf0-116">Since a single Talent environment is “contained” within a single PowerApps environment, there are two options to consider.</span></span> <span data-ttu-id="22cf0-117">A primeira opção envolve a remoção de todo o ambiente do PowerApps; a segunda opção envolve somente a remoção do Talent.</span><span class="sxs-lookup"><span data-stu-id="22cf0-117">The first option involves removing the entire PowerApps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="22cf0-118">A primeira opção é preferível quando você tiver criado um ambiente do PowerApps especificamente para provisionar o Talent e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida.</span><span class="sxs-lookup"><span data-stu-id="22cf0-118">The first option is preferred when you have created a PowerApps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="22cf0-119">A segunda opção é recomendável quando você tiver um ambiente estabelecido do PowerApps preenchido com dados avançados aproveitados no PowerApps e nos fluxos.</span><span class="sxs-lookup"><span data-stu-id="22cf0-119">The second option is appropriate when you have an established PowerApps environment populated with rich data that's leveraged in PowerApps and Flows.</span></span>

> [!Important]
> <span data-ttu-id="22cf0-120">Antes de remover o ambiente do PowerApps, verifique se ele não está sendo usado para integrações de dados avançados fora do escopo do Talent.</span><span class="sxs-lookup"><span data-stu-id="22cf0-120">Before removing the PowerApps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="22cf0-121">Observe também que os ambientes do PowerApps não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="22cf0-121">Also note that the default PowerApps environments cannot be removed.</span></span> 

<span data-ttu-id="22cf0-122">Para remover todo o ambiente do PowerApps, incluindo o Talent e os aplicativos e fluxos associados:</span><span class="sxs-lookup"><span data-stu-id="22cf0-122">To remove the entire PowerApps environment, including Talent and the associated Apps and Flows:</span></span>

1. <span data-ttu-id="22cf0-123">Navegue até o [Centro de administração do PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="22cf0-123">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="22cf0-124">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="22cf0-124">Select **Environments**.</span></span>
3. <span data-ttu-id="22cf0-125">Selecione o ambiente a ser removido.</span><span class="sxs-lookup"><span data-stu-id="22cf0-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="22cf0-126">Selecione **Excluir** e confirme a decisão.</span><span class="sxs-lookup"><span data-stu-id="22cf0-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="22cf0-127">Aguarde até que a exclusão seja concluída.</span><span class="sxs-lookup"><span data-stu-id="22cf0-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="22cf0-128">Entre no [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) usando a conta utilizada para inscrever-se no Talent.</span><span class="sxs-lookup"><span data-stu-id="22cf0-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="22cf0-129">Selecione o projeto do Talent que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="22cf0-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="22cf0-130">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**.</span><span class="sxs-lookup"><span data-stu-id="22cf0-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="22cf0-131">Selecione a instância a ser removida.</span><span class="sxs-lookup"><span data-stu-id="22cf0-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="22cf0-132">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="22cf0-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="22cf0-133">Para remover um ambiente do Talent de um ambiente existente do PowerApps, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="22cf0-133">To remove a Talent environment from an existing PowerApps environment, complete the following steps.</span></span> <span data-ttu-id="22cf0-134">Observe que a necessidade de envolver o suporte e contatar a equipe do Talent DevOps é temporária até que esse recurso seja habilitado diretamente no LCS.</span><span class="sxs-lookup"><span data-stu-id="22cf0-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="22cf0-135">Contate o suporte para iniciar uma solicitação de remoção.</span><span class="sxs-lookup"><span data-stu-id="22cf0-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="22cf0-136">A equipe de suporte iniciará uma solicitação de remoção com a equipe do Talent DevOps.</span><span class="sxs-lookup"><span data-stu-id="22cf0-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="22cf0-137">Continue após ser informado de que o ambiente foi removido.</span><span class="sxs-lookup"><span data-stu-id="22cf0-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="22cf0-138">Entre no LCS usando a conta utilizada para inscrever-se no Talent.</span><span class="sxs-lookup"><span data-stu-id="22cf0-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="22cf0-139">Selecione o projeto do Talent que contém o ambiente.</span><span class="sxs-lookup"><span data-stu-id="22cf0-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="22cf0-140">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**.</span><span class="sxs-lookup"><span data-stu-id="22cf0-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="22cf0-141">Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Reprovado**.</span><span class="sxs-lookup"><span data-stu-id="22cf0-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="22cf0-142">Selecione **Remover instância** e confirme sua decisão.</span><span class="sxs-lookup"><span data-stu-id="22cf0-142">Select **Remove instance** and confirm your decision.</span></span> 

