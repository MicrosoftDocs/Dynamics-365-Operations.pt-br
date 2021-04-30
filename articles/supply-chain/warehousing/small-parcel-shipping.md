---
title: Remessa de pacotes pequenos
description: Este tópico fornece informações sobre o recurso SPS (remessa de pacotes pequenos). Esse recurso permite que o Microsoft Dynamics 365 Supply Chain Management envie detalhes sobre um contêiner embalado para a transportadora e, em seguida, receba dessa transportadora uma etiqueta de remessa, uma taxa de remessa e um número de rastreamento.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3e72959d79e9b3b03e061a0f26750e3bd025219e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910200"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="f8bea-104">Remessa de pacotes pequenos</span><span class="sxs-lookup"><span data-stu-id="f8bea-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f8bea-105">O recurso SPS (remessa de pacotes pequenos) permite que o Microsoft Dynamics 365 Supply Chain Management interaja diretamente com as transportadoras fornecendo uma estrutura para a comunicação por meio de APIs de transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="f8bea-106">Essa funcionalidade é útil ao remeter ordens de venda individuais por meio de transportadoras comerciais em vez de usar a remessa de contêineres ou a remessa de carga parcial (LTL).</span><span class="sxs-lookup"><span data-stu-id="f8bea-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="f8bea-107">O recurso SPS interage com a transportadora por meio de um *mecanismo de taxa* dedicado.</span><span class="sxs-lookup"><span data-stu-id="f8bea-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="f8bea-108">Sua organização deve desenvolver esse mecanismo de taxa em colaboração com a transportadora ou com o serviço de hub de transportadoras.</span><span class="sxs-lookup"><span data-stu-id="f8bea-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="f8bea-109">O mecanismo de taxa permite que o Supply Chain Management envie detalhes sobre um contêiner embalado para a transportadora e, em seguida, receba dessa transportadora uma etiqueta de remessa, uma taxa de remessa e um número de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="f8bea-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="f8bea-110">A taxa de remessa retornada é adicionada à ordem de venda associada como um encargo diverso.</span><span class="sxs-lookup"><span data-stu-id="f8bea-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="f8bea-111">A etiqueta de remessa retornada pode então ser impressa automaticamente usando uma impressora ZPL (Linguagem de Programação Zebra) e aplicada à remessa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="f8bea-112">A transportadora verificará essa etiqueta de remessa quando retirar os pacotes no seu depósito.</span><span class="sxs-lookup"><span data-stu-id="f8bea-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="f8bea-113">Preparar o sistema para oferecer suporte à SPS</span><span class="sxs-lookup"><span data-stu-id="f8bea-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="f8bea-114">Antes de começar a usar a funcionalidade de SPS, você deve ativar o recurso SPS no Gerenciamento de recursos, adicionar seu mecanismo de taxa e configurar os módulos **Gerenciamento de transporte** e **Gerenciamento de depósito** para oferecer suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="f8bea-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="f8bea-115">Ativar o recurso SPS</span><span class="sxs-lookup"><span data-stu-id="f8bea-115">Turn on the SPS feature</span></span>

<span data-ttu-id="f8bea-116">Para que você possa usar o recurso SPS, ele deverá ser ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="f8bea-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="f8bea-117">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f8bea-118">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f8bea-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f8bea-119">**Módulo:** *Gerenciamento de transporte*</span><span class="sxs-lookup"><span data-stu-id="f8bea-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="f8bea-120">**Nome do recurso:** *Remessa de pacotes pequenos*</span><span class="sxs-lookup"><span data-stu-id="f8bea-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="f8bea-121">Implantar e configurar mecanismos de taxa</span><span class="sxs-lookup"><span data-stu-id="f8bea-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="f8bea-122">O Supply Chain Management não inclui nenhum mecanismo de taxa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="f8bea-123">Você deve obter ou criar os mecanismos de taxa necessários e adicioná-los ao sistema.</span><span class="sxs-lookup"><span data-stu-id="f8bea-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="f8bea-124">No entanto, a Microsoft fornece um mecanismo de taxa de demonstração que pode ser usado para testes.</span><span class="sxs-lookup"><span data-stu-id="f8bea-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="f8bea-125">Baixar e implantar o mecanismo de taxa de demonstração</span><span class="sxs-lookup"><span data-stu-id="f8bea-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="f8bea-126">Siga estas etapas para obter o mecanismo de taxa de demonstração.</span><span class="sxs-lookup"><span data-stu-id="f8bea-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="f8bea-127">No GitHub, baixe a [biblioteca de vínculo dinâmico (DLL) para o mecanismo de taxa de demonstração](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="f8bea-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="f8bea-128">No servidor do Supply Chain Management, salve a DLL na pasta **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="f8bea-129">Criar e implantar mecanismos de taxa funcionais</span><span class="sxs-lookup"><span data-stu-id="f8bea-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="f8bea-130">Para obter informações sobre como criar e implantar mecanismos de taxa funcionais para que possam ser usados em um ambiente de produção ou de teste, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f8bea-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="f8bea-131">​Criar um novo mecanismo de gerenciamento de transporte​</span><span class="sxs-lookup"><span data-stu-id="f8bea-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="f8bea-132">Configurar mecanismos de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="f8bea-132">Set up transportation management engines</span></span>](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="f8bea-133">Para obter mais informações sobre como criar um mecanismo de taxa de SPS, consulte a seguinte postagem de blog: [Remessa de pacotes pequenos: como aproveitar a funcionalidade de remessa de pacotes pequenos no Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="f8bea-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="f8bea-134">Configurar um mecanismo de taxa no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f8bea-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="f8bea-135">Depois de criar e implantar um mecanismo de taxa na SPS, siga estas etapas para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="f8bea-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="f8bea-136">Vá para **Gerenciamento de transporte \> Configuração \> Mecanismos \> Mecanismo de taxa**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="f8bea-137">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="f8bea-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="f8bea-138">Na nova linha, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="f8bea-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="f8bea-139">**Mecanismo de taxa** – Insira um nome exclusivo para o mecanismo de taxa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="f8bea-140">Se você estiver usando o mecanismo de taxa de demonstração, insira *Mecanismo de taxa de demonstração*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="f8bea-141">**Nome** – Insira uma breve descrição do mecanismo de taxa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="f8bea-142">Se você estiver usando o mecanismo de taxa de demonstração, insira *Mecanismo de taxa de demonstração*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="f8bea-143">**ID de metadados de classificação** – Selecione a base que deve ser usada para calcular a taxa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="f8bea-144">Por exemplo, sua taxa pode ser calculada com base na distância.</span><span class="sxs-lookup"><span data-stu-id="f8bea-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="f8bea-145">Se você estiver usando o mecanismo de taxa de demonstração, poderá deixar este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="f8bea-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="f8bea-146">**Assembly do mecanismo** – Insira o nome do arquivo do pacote de DLL implantado.</span><span class="sxs-lookup"><span data-stu-id="f8bea-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="f8bea-147">Se você estiver usando o mecanismo de taxa de demonstração, insira *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="f8bea-148">**Classe do mecanismo** – Insira o nome da classe que foi estabelecido para o mecanismo de taxa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="f8bea-149">Se você estiver usando o mecanismo de taxa de demonstração, insira *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f8bea-150">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="f8bea-150">Example scenario</span></span>

<span data-ttu-id="f8bea-151">Este cenário de exemplo mostra como configurar e usar a SPS depois de preparar o sistema, conforme descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f8bea-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="f8bea-152">Ele usa o mecanismo de taxa de demonstração mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8bea-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="f8bea-153">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="f8bea-153">Make demo data available</span></span>

<span data-ttu-id="f8bea-154">Para trabalhar nesse cenário usando os registros e valores de demonstração especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="f8bea-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="f8bea-155">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="f8bea-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="f8bea-156">Configurar o cenário</span><span class="sxs-lookup"><span data-stu-id="f8bea-156">Set up the scenario</span></span>

<span data-ttu-id="f8bea-157">Para este cenário de exemplo, você deve ter uma transportadora de demonstração, um grupo de transportadoras, uma política de embalagem e um perfil de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="f8bea-158">As subseções a seguir explicam como preparar os registros necessários para o cenário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="f8bea-159">Em um cenário de produção, o processo de configuração normalmente se assemelha ao processo descrito aqui.</span><span class="sxs-lookup"><span data-stu-id="f8bea-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="f8bea-160">No entanto, você definirá valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="f8bea-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="f8bea-161">Configurar transportadoras</span><span class="sxs-lookup"><span data-stu-id="f8bea-161">Set up carriers</span></span>

<span data-ttu-id="f8bea-162">Siga estas etapas para configurar uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="f8bea-163">Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="f8bea-164">No Painel de Ações, selecione **Novo** para adicionar uma transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="f8bea-165">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="f8bea-166">**Transportadora:** *Transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f8bea-167">**Nome:** *Transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f8bea-168">**Modo:** *Terrestre*</span><span class="sxs-lookup"><span data-stu-id="f8bea-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="f8bea-169">Na FastTab **Visão geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f8bea-170">**Ativar transportadora:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="f8bea-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="f8bea-171">**Ativar classificação de transportadora:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="f8bea-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="f8bea-172">Na FastTab **Serviços**, selecione **Novo** para adicionar um serviço à grade.</span><span class="sxs-lookup"><span data-stu-id="f8bea-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="f8bea-173">Defina os seguintes valores para o novo serviço:</span><span class="sxs-lookup"><span data-stu-id="f8bea-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="f8bea-174">**Serviço de transportadora:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f8bea-175">**Nome:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f8bea-176">**Método de transporte:** *Terrestre*</span><span class="sxs-lookup"><span data-stu-id="f8bea-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="f8bea-177">Insira valores arbitrários para todos os outros campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="f8bea-178">(Quando você salvar o novo registro de transportadora, um novo modo de entrega será criado e o campo **Modo de entrega** será definido automaticamente.)</span><span class="sxs-lookup"><span data-stu-id="f8bea-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="f8bea-179">Na FastTab **Perfis de classificação**, selecione **Novo** para adicionar um perfil de classificação à grade.</span><span class="sxs-lookup"><span data-stu-id="f8bea-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="f8bea-180">Defina os seguintes valores para o novo perfil:</span><span class="sxs-lookup"><span data-stu-id="f8bea-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="f8bea-181">**Perfil de classificação:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f8bea-182">**Nome:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f8bea-183">**Mecanismo de taxa:** *Mecanismo de taxa de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="f8bea-184">Insira valores arbitrários para todos os outros campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="f8bea-185">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="f8bea-186">Para obter mais informações sobre como configurar transportadoras, consulte [Configurar transportadoras](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="f8bea-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="f8bea-187">Configurar contas de serviço de transportadora</span><span class="sxs-lookup"><span data-stu-id="f8bea-187">Set up carrier service accounts</span></span>

<span data-ttu-id="f8bea-188">Siga estas etapas para configurar uma conta de serviço de transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="f8bea-189">Vá para **Gerenciamento de transporte \> Configuração \> Classificação \> Conta de serviço de transportadora**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="f8bea-190">No Painel de Ações, selecione **Novo** para adicionar uma conta de serviço de transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="f8bea-191">Defina os seguintes valores para a nova conta:</span><span class="sxs-lookup"><span data-stu-id="f8bea-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="f8bea-192">**Transportadora:** *Transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f8bea-193">**Serviço de transportadora:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="f8bea-194">**Número da conta de cliente de transportadora:** o número da conta de cliente de transportadora usado para verificar e autenticar a conexão com a transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="f8bea-195">A transportadora fornecerá esse valor.</span><span class="sxs-lookup"><span data-stu-id="f8bea-195">Your carrier will provide this value.</span></span> <span data-ttu-id="f8bea-196">Se você estiver usando o serviço de demonstração, poderá inserir um valor arbitrário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="f8bea-197">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="f8bea-197">**Site:** *6*</span></span>
    - <span data-ttu-id="f8bea-198">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="f8bea-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8bea-199">Geralmente, o valor **Número da conta de cliente de transportadora** é o único valor necessário para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f8bea-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="f8bea-200">No entanto, se a transportadora exigir parâmetros de autenticação adicionais, sua organização deverá personalizar esta página para adicionar campos extras, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="f8bea-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="f8bea-201">Configurar uma política de embalagem de contêiner</span><span class="sxs-lookup"><span data-stu-id="f8bea-201">Set up a container packing policy</span></span>

<span data-ttu-id="f8bea-202">Siga estas etapas para configurar uma política de embalagem de contêiner.</span><span class="sxs-lookup"><span data-stu-id="f8bea-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="f8bea-203">Se você ainda não configurou uma definição de impressora ZPL, use o aplicativo Agente de Roteamento de Documentos para configurá-la.</span><span class="sxs-lookup"><span data-stu-id="f8bea-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="f8bea-204">Para obter mais informações, consulte [Visão geral da impressão de documentos](../../fin-ops-core/dev-itpro/analytics/print-documents.md) e tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="f8bea-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="f8bea-205">Vá para **Gerenciamento de depósito \> Configuração \> Contêineres \> Políticas de embalagem de contêiner**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="f8bea-206">No Painel de Ações, selecione **Novo** para adicionar uma política de embalagem de contêiner.</span><span class="sxs-lookup"><span data-stu-id="f8bea-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="f8bea-207">No cabeçalho da nova política, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="f8bea-208">**Política de embalagem de contêiner:** *Política de embalagem de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="f8bea-209">**Descrição:** uma descrição da política</span><span class="sxs-lookup"><span data-stu-id="f8bea-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="f8bea-210">Na FastTab **Visão geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f8bea-211">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="f8bea-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f8bea-212">**Local padrão para remessa final:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="f8bea-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="f8bea-213">**Unidade de peso:** *Kg*</span><span class="sxs-lookup"><span data-stu-id="f8bea-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="f8bea-214">**Política de fechamento de contêiner:** *Liberação automática*</span><span class="sxs-lookup"><span data-stu-id="f8bea-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="f8bea-215">**Política de liberação de contêiner:** *Disponibilizar no local da remessa final*</span><span class="sxs-lookup"><span data-stu-id="f8bea-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="f8bea-216">Na FastTab **Manifesto de contêiner**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f8bea-217">**Manifesto automático no fechamento do contêiner:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="f8bea-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="f8bea-218">**Requisitos de manifesto para contêiner:** *Gerenciamento de transporte*</span><span class="sxs-lookup"><span data-stu-id="f8bea-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="f8bea-219">**Imprimir conteúdo de contêiner:** *Não*</span><span class="sxs-lookup"><span data-stu-id="f8bea-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="f8bea-220">Na FastTab **Impressão de etiqueta de transportadora**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f8bea-221">**Imprimir etiqueta de remessa de contêiner:** *Sempre*</span><span class="sxs-lookup"><span data-stu-id="f8bea-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="f8bea-222">**Nome da impressora:** o nome da impressora ZPL que deve imprimir etiquetas de remessa</span><span class="sxs-lookup"><span data-stu-id="f8bea-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="f8bea-223">Configurar um perfil de embalagem</span><span class="sxs-lookup"><span data-stu-id="f8bea-223">Set up a packing profile</span></span>

<span data-ttu-id="f8bea-224">Siga estas etapas para configurar um perfil de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="f8bea-225">Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="f8bea-226">No Painel de Ações, selecione **Novo** para adicionar um perfil de embalagem à grade.</span><span class="sxs-lookup"><span data-stu-id="f8bea-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="f8bea-227">Defina os seguintes valores para o novo perfil:</span><span class="sxs-lookup"><span data-stu-id="f8bea-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="f8bea-228">**ID do perfil de embalagem:** *Perfil de embalagem de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="f8bea-229">**Descrição:** uma descrição do perfil</span><span class="sxs-lookup"><span data-stu-id="f8bea-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="f8bea-230">**Política de embalagem de contêiner:** *Política de embalagem de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="f8bea-231">**Modo de ID do Contêiner:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="f8bea-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="f8bea-232">**Tipo de contêiner:** *SmallBox*</span><span class="sxs-lookup"><span data-stu-id="f8bea-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="f8bea-233">Configurar um cliente para usar a transportadora de SPS</span><span class="sxs-lookup"><span data-stu-id="f8bea-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="f8bea-234">Siga estas etapas para configurar um cliente de modo que ele possa usar a transportadora que você criou.</span><span class="sxs-lookup"><span data-stu-id="f8bea-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="f8bea-235">Vá para **Contas a receber \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="f8bea-236">Na grade, localize e selecione o cliente *US-027*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="f8bea-237">No Painel de Ações, na guia **Geral**, no grupo **Configurar**, selecione **Contas de cliente de transportadora**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="f8bea-238">Na página **Contas de cliente de transportadora**, no Painel de Ações, selecione **Novo** para adicionar uma conta à grade.</span><span class="sxs-lookup"><span data-stu-id="f8bea-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="f8bea-239">Defina os seguintes valores para a nova conta:</span><span class="sxs-lookup"><span data-stu-id="f8bea-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="f8bea-240">**Transportadora:** *Transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f8bea-241">**Número da conta de cliente de transportadora:** *12345* (O valor não é importante para este cenário, mas ele será referenciado na próxima seção.)</span><span class="sxs-lookup"><span data-stu-id="f8bea-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="f8bea-242">Executar o cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="f8bea-242">Go through the example scenario</span></span>

<span data-ttu-id="f8bea-243">Depois de configurar todos os dados de exemplo conforme descrito na seção anterior, você estará pronto para executar o cenário de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f8bea-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="f8bea-244">Criar uma ordem de venda e processar o trabalho</span><span class="sxs-lookup"><span data-stu-id="f8bea-244">Create a sales order and process the work</span></span>

<span data-ttu-id="f8bea-245">Siga estas etapas para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f8bea-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="f8bea-246">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="f8bea-247">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f8bea-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="f8bea-248">Na caixa de diálogo **Criar ordem de venda**, defina o campo **Conta de cliente** como *US-027*.</span><span class="sxs-lookup"><span data-stu-id="f8bea-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="f8bea-249">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f8bea-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="f8bea-250">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="f8bea-250">The new sales order is opened.</span></span> <span data-ttu-id="f8bea-251">Na FastTab **Cabeçalho da ordem de venda**, defina o campo **Número da conta de cliente de transportadora** como o valor que você selecionou para esse cliente anteriormente (*12345*).</span><span class="sxs-lookup"><span data-stu-id="f8bea-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="f8bea-252">Na seção **Linhas da ordem de venda**, adicione uma linha de venda e defina os seguintes valores para ela:</span><span class="sxs-lookup"><span data-stu-id="f8bea-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="f8bea-253">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f8bea-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="f8bea-254">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="f8bea-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="f8bea-255">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="f8bea-255">**Site:** *6*</span></span>
    - <span data-ttu-id="f8bea-256">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="f8bea-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="f8bea-257">Alterne para a exibição do **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="f8bea-258">Na FastTab **Entrega**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f8bea-259">**Transportadora:** *Transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="f8bea-260">**Serviço de transportadora:** *Serviço de transportadora de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="f8bea-261">Alterne novamente para a exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="f8bea-262">Se for solicitada a atualização do modo de entrega para as linhas de venda, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="f8bea-263">Na seção **Linhas da ordem de venda**, selecione a linha da ordem que você configurou anteriormente e, em seguida, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="f8bea-264">Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="f8bea-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="f8bea-265">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f8bea-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="f8bea-266">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="f8bea-267">O trabalho é criado para mover itens do local de separação para a estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="f8bea-268">Na seção **Linhas da ordem de venda**, selecione **Depósito \> Detalhes da remessa**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="f8bea-269">Na página **Detalhes da remessa**, anote a ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="f8bea-270">Você precisará dela ao embalar a remessa na estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="f8bea-271">Feche a página **Detalhes da remessa** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f8bea-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="f8bea-272">Anote o número da ordem de venda e, em seguida, vá para **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="f8bea-273">Use o número da ordem de venda para localizar e selecionar o trabalho criado para a ordem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="f8bea-274">No Painel de Ações, na guia **Trabalho**, selecione **Concluir trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="f8bea-275">Na página **Conclusão do trabalho**, no campo **ID de Usuário**, selecione uma ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="f8bea-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="f8bea-276">Em seguida, no Painel de Ações, selecione **Validar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="f8bea-277">Se o trabalho for aprovado na validação, selecione **Concluir trabalho** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="f8bea-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="f8bea-278">O trabalho é marcado como concluído para simular a movimentação de itens para a estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f8bea-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="f8bea-279">Embalar a remessa</span><span class="sxs-lookup"><span data-stu-id="f8bea-279">Pack the shipment</span></span>

<span data-ttu-id="f8bea-280">Siga estas etapas para embalar a remessa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="f8bea-281">Vá para **Gerenciamento de depósito \> Configuração \> Trabalhador** e verifique se a sua conta de usuário está associada a uma conta de trabalhador para gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="f8bea-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="f8bea-282">Vá para **Gerenciamento de depósito \> Separação e transporte em contêineres \> Embalar**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="f8bea-283">Na caixa de diálogo **Selecionar estação de embalagem**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f8bea-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f8bea-284">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="f8bea-284">**Site:** *6*</span></span>
    - <span data-ttu-id="f8bea-285">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="f8bea-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="f8bea-286">**Local:** *Embalar*</span><span class="sxs-lookup"><span data-stu-id="f8bea-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="f8bea-287">**ID do perfil de embalagem:** *Perfil de embalagem de demonstração*</span><span class="sxs-lookup"><span data-stu-id="f8bea-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="f8bea-288">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-288">Select **OK**.</span></span>
1. <span data-ttu-id="f8bea-289">A página **Embalar** será exibida.</span><span class="sxs-lookup"><span data-stu-id="f8bea-289">The **Pack** page appears.</span></span> <span data-ttu-id="f8bea-290">Em um cenário de produção, um trabalhador verificará uma placa de licença ou uma ID de remessa.</span><span class="sxs-lookup"><span data-stu-id="f8bea-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="f8bea-291">No entanto, para este cenário, abra a página **Todas as remessas** e procure o número da remessa que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f8bea-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="f8bea-292">Em seguida, insira esse valor no campo **Placa de licença ou remessa** na página **Embalar**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="f8bea-293">Como alternativa, insira a ID de remessa que você anotou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8bea-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="f8bea-294">No Painel de Ação, selecione **Novo contêiner**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="f8bea-295">A caixa de diálogo exibida mostra detalhes sobre o novo contêiner.</span><span class="sxs-lookup"><span data-stu-id="f8bea-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="f8bea-296">Mantenha os valores padrão e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="f8bea-297">Na página **Embalar**, na FastTab **Embalagem de item**, no campo **Identificador**, selecione *A0002* para embalar o item.</span><span class="sxs-lookup"><span data-stu-id="f8bea-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="f8bea-298">O item é adicionado ao contêiner.</span><span class="sxs-lookup"><span data-stu-id="f8bea-298">The item is added to the container.</span></span>
1. <span data-ttu-id="f8bea-299">No Painel de Ações, selecione **Contêineres para remessa**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="f8bea-300">A página **Contêineres para remessa** exibida tem uma linha para o contêiner que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f8bea-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="f8bea-301">No entanto, o campo **ID de manifesto de contêiner** nessa linha está em branco no momento, pois você ainda não recebeu a etiqueta de remessa e o número de rastreamento da transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="f8bea-302">No Painel de Ação, selecione **Fechar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="f8bea-303">Na caixa de diálogo **Fechar contêiner**, defina o campo **Peso bruto** como *1 kg* e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bea-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="f8bea-304">A etiqueta de remessa será impressa agora na impressora ZPL selecionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8bea-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="f8bea-305">Ela deve se assemelhar ao seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="f8bea-305">It should resemble the following example.</span></span>

    <span data-ttu-id="f8bea-306">![Exemplo de etiqueta de remessa](media/sps-label-example.png "Exemplo de etiqueta de remessa")</span><span class="sxs-lookup"><span data-stu-id="f8bea-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="f8bea-307">Observe que os valores **ID de manifesto de contêiner** e **Frete total** foram adicionados como recebidos da transportadora.</span><span class="sxs-lookup"><span data-stu-id="f8bea-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]