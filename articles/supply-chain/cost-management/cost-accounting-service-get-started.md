---
title: Introdução ao serviço de contabilidade de custos
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
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276888"
---
# <a name="get-started-with-the-cost-accounting-service"></a><span data-ttu-id="9684d-103">Introdução ao serviço de contabilidade de custos</span><span class="sxs-lookup"><span data-stu-id="9684d-103">Get started with the cost accounting service</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="9684d-104">A funcionalidade que é descrita neste tópico está disponível como parte de uma versão prévia particular.</span><span class="sxs-lookup"><span data-stu-id="9684d-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="9684d-105">O conteúdo deste tópico e a funcionalidade nele descrita estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="9684d-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="9684d-106">Para obter informações sobre as versões prévias, consulte [Perguntas frequentes sobre as atualizações de serviço One Version](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="9684d-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="9684d-107">O serviço de contabilidade de custos permite realizar múltiplas contabilidades de estoque nos razões de contabilização de custos configurados.</span><span class="sxs-lookup"><span data-stu-id="9684d-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="9684d-108">Associe cada razão de contabilização de custos a uma *convenção*.</span><span class="sxs-lookup"><span data-stu-id="9684d-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="9684d-109">Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:</span><span class="sxs-lookup"><span data-stu-id="9684d-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="9684d-110">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="9684d-110">Cost object</span></span>
- <span data-ttu-id="9684d-111">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="9684d-111">Input measurement basis</span></span>
- <span data-ttu-id="9684d-112">Pressuposição de fluxo de custos</span><span class="sxs-lookup"><span data-stu-id="9684d-112">Cost flow assumption</span></span>
- <span data-ttu-id="9684d-113">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="9684d-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="9684d-114">Mesmo depois de ativar o serviço de contabilização de custos, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.</span><span class="sxs-lookup"><span data-stu-id="9684d-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="9684d-115">O serviço de contabilização de serviço é um complemento.</span><span class="sxs-lookup"><span data-stu-id="9684d-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="9684d-116">Para disponibilizar os recursos, é necessário instalá-los a partir do Lifecycle Services (LCS) Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="9684d-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9684d-117">Portanto, é possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="9684d-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="9684d-118">O serviço de contabilidade de custos atualmente não oferece suporte a todos os recursos de gerenciamento integrados ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9684d-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="9684d-119">Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="9684d-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="9684d-120">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="9684d-120">Licensing</span></span>

<span data-ttu-id="9684d-121">O serviço de contabilidade de custos é licenciado com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9684d-121">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="9684d-122">Não é necessário comprar uma licença adicional para usar o serviço de contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="9684d-122">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><span data-ttu-id="9684d-123">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="9684d-123">Install the add-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9684d-124">Para usar o serviço de contabilidade de custos, é necessário ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox) com o Dynamics 365 Supply Chain Management versão 10.0.11 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9684d-124">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="9684d-125">Para usar o serviço de contabilidade de custos, instale o complemento do serviço de contabilidade de custos para o Supply Chain Management conforme descrito no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="9684d-125">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="9684d-126">Entre no LCS.</span><span class="sxs-lookup"><span data-stu-id="9684d-126">Sign in to LCS.</span></span>

1. <span data-ttu-id="9684d-127">Vá para **Gerenciamento da versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="9684d-127">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="9684d-128">Selecione o sinal de mais (**+**).</span><span class="sxs-lookup"><span data-stu-id="9684d-128">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="9684d-129">No campo **Código**, insira a chave beta do complemento do serviço de contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="9684d-129">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="9684d-130">(Você deve ter recebido a chave por email.)</span><span class="sxs-lookup"><span data-stu-id="9684d-130">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="9684d-131">Selecione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="9684d-131">Select **Unblock**.</span></span>

1. <span data-ttu-id="9684d-132">Abra o ambiente LCS ao qual deseja adicionar o serviço.</span><span class="sxs-lookup"><span data-stu-id="9684d-132">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="9684d-133">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="9684d-133">Go to **Full details**.</span></span>

1. <span data-ttu-id="9684d-134">Role para baixo até a FastTab **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="9684d-134">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="9684d-135">Selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="9684d-135">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="9684d-136">Selecione **Serviço de contabilidade de custos**.</span><span class="sxs-lookup"><span data-stu-id="9684d-136">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="9684d-137">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="9684d-137">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="9684d-138">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9684d-138">Select **Install**.</span></span>

1. <span data-ttu-id="9684d-139">Na FastTab **Complementos do ambiente**, você verá que o serviço de contabilidade de custos está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="9684d-139">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="9684d-140">Após alguns minutos, o status deve mudar de **Instalando** para **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="9684d-140">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="9684d-141">(Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, o serviço de contabilidade de custos já está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="9684d-141">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="9684d-142">Configurar a integração</span><span class="sxs-lookup"><span data-stu-id="9684d-142">Set up the integration</span></span>

<span data-ttu-id="9684d-143">Para configurar a integração entre o serviço de contabilidade de serviços e o Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="9684d-143">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="9684d-144">Vá para **Administração do sistema > Gerenciamento de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="9684d-144">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="9684d-145">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="9684d-145">Select **Check for updates**.</span></span>

1. <span data-ttu-id="9684d-146">Abra a guia **Todos** e procure o recurso chamado de *Serviço de contabilidade de custos*.</span><span class="sxs-lookup"><span data-stu-id="9684d-146">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="9684d-147">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="9684d-147">Select **Enable now**.</span></span>

1. <span data-ttu-id="9684d-148">Vá para **Gerenciamento de custos > Serviço de contabilidade de custos > Configuração > Parâmetros do serviço de contabilidade de custos > Parâmetros de integrações**.</span><span class="sxs-lookup"><span data-stu-id="9684d-148">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="9684d-149">No campo **ID do aplicativo**, insira o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="9684d-149">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="9684d-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="9684d-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="9684d-151">No campo **Ponto de extremidade do serviço de dados**, insira a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="9684d-151">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="9684d-152">No campo **Ponto de extremidade do serviço de contabilidade de custos**, insira a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="9684d-152">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="9684d-153">Agora o serviço de contabilidade de custos está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="9684d-153">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="9684d-154">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="9684d-154">Related resources</span></span>

[<span data-ttu-id="9684d-155">Home page do serviço de contabilidade de custos</span><span class="sxs-lookup"><span data-stu-id="9684d-155">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
