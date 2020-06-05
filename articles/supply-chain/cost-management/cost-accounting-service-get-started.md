---
title: Introdução ao serviço de contabilidade de custos (versão prévia particular)
description: Este tópico oferece detalhes de licenciamento e instruções de instalação do serviço de contabilidade de custos.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: a82af9e8ec1806f470103897389d0316d33a4a06
ms.sourcegitcommit: 7fec9dc5297ed6e687d4a0dff099922d59d6a830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372727"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a><span data-ttu-id="69239-103">Introdução ao serviço de contabilidade de custos (versão prévia particular)</span><span class="sxs-lookup"><span data-stu-id="69239-103">Get started with the cost accounting service (private preview)</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="69239-104">A funcionalidade que é descrita neste tópico está disponível como parte de uma versão prévia particular.</span><span class="sxs-lookup"><span data-stu-id="69239-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="69239-105">O conteúdo deste tópico e a funcionalidade nele descrita estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="69239-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="69239-106">Para obter informações sobre as versões prévias, consulte [Perguntas frequentes sobre as atualizações de serviço One Version](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="69239-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="69239-107">O serviço de contabilidade de custos permite realizar múltiplas contabilidades de estoque nos razões de contabilização de custos configurados.</span><span class="sxs-lookup"><span data-stu-id="69239-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="69239-108">Associe cada razão de contabilização de custos a uma *convenção*.</span><span class="sxs-lookup"><span data-stu-id="69239-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="69239-109">Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:</span><span class="sxs-lookup"><span data-stu-id="69239-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="69239-110">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="69239-110">Cost object</span></span>
- <span data-ttu-id="69239-111">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="69239-111">Input measurement basis</span></span>
- <span data-ttu-id="69239-112">Pressuposição de fluxo de custos</span><span class="sxs-lookup"><span data-stu-id="69239-112">Cost flow assumption</span></span>
- <span data-ttu-id="69239-113">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="69239-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="69239-114">Mesmo depois de ativar o serviço de contabilização de custos, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.</span><span class="sxs-lookup"><span data-stu-id="69239-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="69239-115">O serviço de contabilização de serviço é um complemento.</span><span class="sxs-lookup"><span data-stu-id="69239-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="69239-116">Para disponibilizar os recursos, é necessário instalá-los a partir do Lifecycle Services (LCS) Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="69239-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="69239-117">Portanto, é possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="69239-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="69239-118">O serviço de contabilidade de custos atualmente não oferece suporte a todos os recursos de gerenciamento integrados ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="69239-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="69239-119">Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="69239-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a><span data-ttu-id="69239-120">Como obter o serviço de contabilidade de custos (versão prévia particular)</span><span class="sxs-lookup"><span data-stu-id="69239-120">How to get the cost accounting service (private preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69239-121">Para usar o serviço de contabilidade de custos, é necessário ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox) com o Dynamics 365 Supply Chain Management versão 10.0.11 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="69239-121">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="69239-122">Para inscrever-se na versão prévia particular do serviço de contabilidade de custos, envie sua ID de ambiente do LCS por email para [serviço de contabilidade de custos (versão prévia particular)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span><span class="sxs-lookup"><span data-stu-id="69239-122">To sign up for the cost accounting service private preview, please send your LCS environment ID by email to [Cost accounting service (private preview)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span></span> <span data-ttu-id="69239-123">Ao aprová-lo no programa, enviaremos um email de acompanhamento que contém uma chave beta de serviço de contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="69239-123">On approving you for the program, we will send you a follow up email that contains a cost accounting service beta key.</span></span> <span data-ttu-id="69239-124">Ao receber a chave beta, você pode continuar [com a instalação do suplemento](#install).</span><span class="sxs-lookup"><span data-stu-id="69239-124">On receiving the beta key, you can proceed by [installing the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="69239-125">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="69239-125">Licensing</span></span>

<span data-ttu-id="69239-126">O serviço de contabilidade de custos é licenciado com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="69239-126">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="69239-127">Não é necessário comprar uma licença adicional para usar o serviço de contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="69239-127">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="69239-128">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="69239-128">Install the add-in</span></span>

<span data-ttu-id="69239-129">Para usar o serviço de contabilidade de custos, instale o complemento do serviço de contabilidade de custos para o Supply Chain Management conforme descrito no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="69239-129">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="69239-130">[Inscreva-se](#sign-up) no serviço de contabilidade de custos (versão prévia particular).</span><span class="sxs-lookup"><span data-stu-id="69239-130">[Sign up](#sign-up) for the cost accounting service (private preview).</span></span>

1. <span data-ttu-id="69239-131">Entre no LCS.</span><span class="sxs-lookup"><span data-stu-id="69239-131">Sign in to LCS.</span></span>

1. <span data-ttu-id="69239-132">Vá para **Gerenciamento da versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="69239-132">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="69239-133">Selecione o sinal de mais (**+**).</span><span class="sxs-lookup"><span data-stu-id="69239-133">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="69239-134">No campo **Código**, insira a chave beta do complemento do serviço de contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="69239-134">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="69239-135">(Você deve ter recebido a chave por email.)</span><span class="sxs-lookup"><span data-stu-id="69239-135">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="69239-136">Selecione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="69239-136">Select **Unblock**.</span></span>

1. <span data-ttu-id="69239-137">Abra o ambiente LCS ao qual deseja adicionar o serviço.</span><span class="sxs-lookup"><span data-stu-id="69239-137">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="69239-138">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="69239-138">Go to **Full details**.</span></span>

1. <span data-ttu-id="69239-139">Role para baixo até a Guia Rápida **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="69239-139">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="69239-140">Selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="69239-140">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="69239-141">Selecione **Serviço de contabilidade de custos**.</span><span class="sxs-lookup"><span data-stu-id="69239-141">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="69239-142">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="69239-142">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="69239-143">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="69239-143">Select **Install**.</span></span>

1. <span data-ttu-id="69239-144">Na Guia Rápida **Complementos do ambiente**, você verá que o serviço de contabilidade de custos está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="69239-144">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="69239-145">Após alguns minutos, o status deve mudar de **Instalando** para **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="69239-145">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="69239-146">(Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, o serviço de contabilidade de custos já está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="69239-146">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="69239-147">Configurar a integração</span><span class="sxs-lookup"><span data-stu-id="69239-147">Set up the integration</span></span>

<span data-ttu-id="69239-148">Para configurar a integração entre o serviço de contabilidade de serviços e o Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="69239-148">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="69239-149">Vá para **Administração do sistema > Gerenciamento de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="69239-149">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="69239-150">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="69239-150">Select **Check for updates**.</span></span>

1. <span data-ttu-id="69239-151">Abra a guia **Todos** e procure o recurso chamado de *Serviço de contabilidade de custos*.</span><span class="sxs-lookup"><span data-stu-id="69239-151">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="69239-152">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="69239-152">Select **Enable now**.</span></span>

1. <span data-ttu-id="69239-153">Vá para **Gerenciamento de custos > Serviço de contabilidade de custos > Configuração > Parâmetros do serviço de contabilidade de custos > Parâmetros de integrações**.</span><span class="sxs-lookup"><span data-stu-id="69239-153">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="69239-154">No campo **ID do aplicativo**, insira o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="69239-154">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="69239-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="69239-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="69239-156">No campo **Ponto de extremidade do serviço de dados**, insira a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="69239-156">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="69239-157">No campo **Ponto de extremidade do serviço de contabilidade de custos**, insira a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="69239-157">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="69239-158">Agora o serviço de contabilidade de custos está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="69239-158">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="69239-159">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="69239-159">Related resources</span></span>

[<span data-ttu-id="69239-160">Home page do serviço de contabilidade de custos</span><span class="sxs-lookup"><span data-stu-id="69239-160">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
