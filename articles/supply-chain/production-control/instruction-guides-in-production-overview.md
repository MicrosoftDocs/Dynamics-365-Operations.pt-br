---
title: Fornecer guias de realidade combinada para trabalhadores na produção
description: Este tópico explica como integrar o módulo de gerenciamento de produção no Microsoft Dynamics 365 Supply Chain Management ao Dynamics 365 Guides.
author: cabeln
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 15595c46f9d6ff91f6fd618859e9f059ae88bd78
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910080"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a><span data-ttu-id="bbc15-103">Fornecer guias de realidade combinada para trabalhadores na produção</span><span class="sxs-lookup"><span data-stu-id="bbc15-103">Provide mixed-reality Guides for workers in production</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bbc15-104">Os trabalhadores em processos de produção se beneficiarão das instruções relevantes fornecidas no momento certo no contexto do seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-104">Workers in production processes will benefit from relevant instructions that are provided at the right time in the context of their work.</span></span> <span data-ttu-id="bbc15-105">As *instruções* se aplicam a vários domínios de trabalho, incluindo: montagem, serviço, operações, certificação e segurança.</span><span class="sxs-lookup"><span data-stu-id="bbc15-105">*Instructions* apply in several domains of work, including: assembly, service, operations, certification, and safety.</span></span> <span data-ttu-id="bbc15-106">Em todas essas principais funções de negócios, as instruções de treinamento contínuo podem ajudar a capacitar os trabalhadores a produzir mais e a trabalhar melhor.</span><span class="sxs-lookup"><span data-stu-id="bbc15-106">Across all of these core business functions, ongoing training instructions can help empower workers to achieve more and work better.</span></span>

## <a name="introduction"></a><span data-ttu-id="bbc15-107">Introdução</span><span class="sxs-lookup"><span data-stu-id="bbc15-107">Introduction</span></span>

<span data-ttu-id="bbc15-108">Você pode fornecer instruções de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="bbc15-108">You can provide instructions in different ways.</span></span> <span data-ttu-id="bbc15-109">Um sistema eficiente que faz envios pronto para uso usa o [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span><span class="sxs-lookup"><span data-stu-id="bbc15-109">One efficient system that ships out of the box uses [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span></span>

<span data-ttu-id="bbc15-110">O Dynamics 365 Guides pode ajudar a capacitar seus funcionários com aprendizado prático.</span><span class="sxs-lookup"><span data-stu-id="bbc15-110">Dynamics 365 Guides can help empower your employees with hands-on learning.</span></span> <span data-ttu-id="bbc15-111">Você pode definir processos padronizados com instruções passo a passo que orientam seus funcionários para as ferramentas e peças necessárias e mostram aos funcionários como usar essas ferramentas em situações reais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-111">You can define standardized processes with step-by-step instructions that guide your employees to the tools and parts they need and show employees how to use these tools in real work situations.</span></span>

<span data-ttu-id="bbc15-112">Você pode anexar guias a vários aspectos do controle de produção, incluindo:</span><span class="sxs-lookup"><span data-stu-id="bbc15-112">You can attach guides to various aspects of production control including:</span></span>

- [<span data-ttu-id="bbc15-113">Recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-113">Resources</span></span>](#resources)
- [<span data-ttu-id="bbc15-114">Grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-114">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="bbc15-115">Produtos liberados</span><span class="sxs-lookup"><span data-stu-id="bbc15-115">Released products</span></span>](#released-products)
- [<span data-ttu-id="bbc15-116">Fórmulas</span><span class="sxs-lookup"><span data-stu-id="bbc15-116">Formulas</span></span>](#formulas)
- [<span data-ttu-id="bbc15-117">Versões da fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-117">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="bbc15-118">Listas de materiais (BOMs)</span><span class="sxs-lookup"><span data-stu-id="bbc15-118">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="bbc15-119">Versões da BOM</span><span class="sxs-lookup"><span data-stu-id="bbc15-119">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="bbc15-120">Roteiros</span><span class="sxs-lookup"><span data-stu-id="bbc15-120">Routes</span></span>](#routes)
- [<span data-ttu-id="bbc15-121">Versões de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-121">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="bbc15-122">Relações de operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-122">Route operation relations</span></span>](#route-operation-relations)

> [!NOTE]
> <span data-ttu-id="bbc15-123">Você também pode anexar guias com o gerenciamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="bbc15-123">You can also attach Guides with Asset Management.</span></span> <span data-ttu-id="bbc15-124">Para obter mais informações sobre essa opção consulte [Integrar o Dynamics 365 Supply Chain Management (gerenciamento de ativos) ao Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-124">For more information about that option, see [Integrate Dynamics 365 Supply Chain Management (Asset Management) with Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span></span>

<span data-ttu-id="bbc15-125">Quando um trabalhador de linha de frente escolhe um trabalho no chão de fábrica por meio do Supply Chain Management, ele pode ver [os guias relevantes](#logic) no cartão de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-125">When a first-line worker chooses a job on the shop floor through Supply Chain Management, the worker can see [the relevant guides](#logic) on the job card.</span></span> <span data-ttu-id="bbc15-126">Quando o trabalhador escolhe um guia específico, um código QR para esse guia é mostrado na tela.</span><span class="sxs-lookup"><span data-stu-id="bbc15-126">When the worker chooses a specific guide, a QR code for that guide is shown on the screen.</span></span> <span data-ttu-id="bbc15-127">O trabalhador usa o HoloLens para digitalizar o código QR, que inicia os guias e mostra as instruções necessárias.</span><span class="sxs-lookup"><span data-stu-id="bbc15-127">The worker then uses their HoloLens to scan the QR code, which launches Guides and shows the required instructions.</span></span>

<span data-ttu-id="bbc15-128">As subseções a seguir descrevem alguns cenários selecionados nos quais as empresas em vários setores podem obter o maior valor ao usar guias para apresentar instruções de manufatura.</span><span class="sxs-lookup"><span data-stu-id="bbc15-128">The following subsections describe a few selected scenarios where companies across industries can see the biggest value when using Guides to present instructions for manufacturing.</span></span>

### <a name="assembly"></a><span data-ttu-id="bbc15-129">Montagem</span><span class="sxs-lookup"><span data-stu-id="bbc15-129">Assembly</span></span>

<span data-ttu-id="bbc15-130">![Usar guias em tarefas de montagem](media/instruction-guides-hero-assembly.png "Usar guias em tarefas de serviço")</span><span class="sxs-lookup"><span data-stu-id="bbc15-130">![Use Guides in assembly tasks](media/instruction-guides-hero-assembly.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="bbc15-131">As instruções nas operações de montagem mostram aos trabalhadores as ferramentas e as peças necessárias e como usá-las em situações reais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-131">Instructions in assembly operations show workers the tools and parts they need and how to use them in real work situations.</span></span>

<span data-ttu-id="bbc15-132">Os gerentes de produção podem criar e atribuir guias, por exemplo, para [roteiros de produção](routes-operations.md), [relações de operação](routes-operations.md#operation-relations) ou [listas de materiais](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-132">Production managers can create and assign Guides, for example, for [production routes](routes-operations.md), [operation relations](routes-operations.md#operation-relations), or [bills of material](bill-of-material-bom.md).</span></span> <span data-ttu-id="bbc15-133">Os trabalhadores encontrarão as instruções relevantes sobre a respectiva experiência operacional no chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="bbc15-133">Workers will find the relevant instructions on the respective operation experience on the shop floor.</span></span>

### <a name="service"></a><span data-ttu-id="bbc15-134">Serviço</span><span class="sxs-lookup"><span data-stu-id="bbc15-134">Service</span></span>

<span data-ttu-id="bbc15-135">![Usar guias em tarefas de serviço](media/instruction-guides-hero-service.png "Usar guias em tarefas de serviço")</span><span class="sxs-lookup"><span data-stu-id="bbc15-135">![Use Guides in service tasks](media/instruction-guides-hero-service.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="bbc15-136">Capacite técnicos com instruções guiadas no local do trabalho, eliminando a necessidade de programar visitas adicionais.</span><span class="sxs-lookup"><span data-stu-id="bbc15-136">Equip technicians with guided instructions at the job site, eliminating the need to schedule additional visits.</span></span>

<span data-ttu-id="bbc15-137">Os gerentes de serviço podem atribuir guias, por exemplo, a [produtos específicos](../../commerce/product.md) que passam por rotinas de avaliação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-137">Service managers can assign Guides, for example, to specific [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="quality"></a><span data-ttu-id="bbc15-138">Qualidade</span><span class="sxs-lookup"><span data-stu-id="bbc15-138">Quality</span></span>

<span data-ttu-id="bbc15-139">![Usar guias em tarefas de controle de qualidade](media/instruction-guides-hero-quality.png "Usar guias em tarefas de controle de qualidade")</span><span class="sxs-lookup"><span data-stu-id="bbc15-139">![Use Guides in quality assurance tasks](media/instruction-guides-hero-quality.png "Use Guides in quality assurance tasks")</span></span>

<span data-ttu-id="bbc15-140">Implemente novos processos e garanta maior consistência ao transformar o conhecimento dos funcionários em uma ferramenta repetível.</span><span class="sxs-lookup"><span data-stu-id="bbc15-140">Rollout new processes and ensure increased consistency by turning employee knowledge into a repeatable tool.</span></span>

<span data-ttu-id="bbc15-141">Os gerentes de controle de qualidade podem atribuir os guias, por exemplo, a [produtos específicos](../../commerce/product.md) que passam por rotinas de avaliação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-141">Quality assurance managers can assign guides, for example, to [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="certifications"></a><span data-ttu-id="bbc15-142">Certificações</span><span class="sxs-lookup"><span data-stu-id="bbc15-142">Certifications</span></span>

<span data-ttu-id="bbc15-143">![Usar guias para tarefas relacionadas à certificação](media/instruction-guides-hero-certification.png "Usar guias para tarefas relacionadas à certificação")</span><span class="sxs-lookup"><span data-stu-id="bbc15-143">![Use Guides for certification related tasks](media/instruction-guides-hero-certification.png "Use Guides for certification related tasks")</span></span>

<span data-ttu-id="bbc15-144">Certifique-se de que cada funcionário atenda a altos padrões, identificando rapidamente quem precisa de ajuda e onde.</span><span class="sxs-lookup"><span data-stu-id="bbc15-144">Ensure every employee meets high standards by quickly identifying who needs help and where.</span></span>

### <a name="safety"></a><span data-ttu-id="bbc15-145">Segurança</span><span class="sxs-lookup"><span data-stu-id="bbc15-145">Safety</span></span>

<span data-ttu-id="bbc15-146">![Usar guias nas instruções de segurança do trabalho](media/instruction-guides-hero-safety.png "Usar guias nas instruções de segurança do trabalho")</span><span class="sxs-lookup"><span data-stu-id="bbc15-146">![Use Guides in work safety instructions](media/instruction-guides-hero-safety.png "Use Guides in work safety instructions")</span></span>

<span data-ttu-id="bbc15-147">Forneça instruções que orientem sobre procedimentos perigosos virtualmente antes de tentativas no ambiente físico.</span><span class="sxs-lookup"><span data-stu-id="bbc15-147">Provide instructions that walk through dangerous procedures virtually before attempting in the physical environment.</span></span> <span data-ttu-id="bbc15-148">Com uma abordagem de realidade misturada, os funcionários podem experimentar procedimentos perigosos virtualmente.</span><span class="sxs-lookup"><span data-stu-id="bbc15-148">With a mixed reality approach, workers can experience dangerous procedures virtually.</span></span>

<span data-ttu-id="bbc15-149">Os gerentes de produção podem fornecer instruções de manuseio dedicadas para procedimentos de manuseio de material tóxico ou de manuseio delicado, atribuindo instruções a [itens de produção](../../commerce/product.md), [roteiros](routes-operations.md) e [operações](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="bbc15-149">Production managers can provide dedicated handling instructions for hazardous material handling or delicate handling procedures by assigning instructions to [product items](../../commerce/product.md), [routes](routes-operations.md), and [operations](routes-operations.md#operation-relations).</span></span>

## <a name="get-started-with-instructions-and-guides"></a><span data-ttu-id="bbc15-150">Introdução a instruções e guias</span><span class="sxs-lookup"><span data-stu-id="bbc15-150">Get started with instructions and Guides</span></span>

<span data-ttu-id="bbc15-151">Para habilitar as instruções em processos de produção, o Supply Chain Management oferece uma integração pronta para uso com o Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="bbc15-151">To enable instructions in production processes, Supply Chain Management provides an out-of-the-box integration with Dynamics 365 Guides.</span></span> <span data-ttu-id="bbc15-152">Uma instância do aplicativo licenciada e instalada do Guides é necessária para criar, manter e atribuir instruções de realidade misturada a ativos de produção e trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-152">A licensed and installed application instance of Guides is required to build, maintain, and assign mixed reality instructions to production assets and work.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="bbc15-153">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bbc15-153">Prerequisites</span></span>

<span data-ttu-id="bbc15-154">Para usar esse recurso, o sistema deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bbc15-154">To use this feature, your system must include the following:</span></span>

- <span data-ttu-id="bbc15-155">Dynamics 365 Supply Chain Management versão 10.0.15 ou posterior</span><span class="sxs-lookup"><span data-stu-id="bbc15-155">Dynamics 365 Supply Chain Management version 10.0.15 or later</span></span>
- <span data-ttu-id="bbc15-156">[Gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md) para aplicativos do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bbc15-156">[Dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md) for Supply Chain Management apps.</span></span>
- <span data-ttu-id="bbc15-157">[Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versão 400.0.1.48 ou posterior</span><span class="sxs-lookup"><span data-stu-id="bbc15-157">[Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 or later</span></span>

### <a name="turn-on-the-feature"></a><span data-ttu-id="bbc15-158">Ativar o recurso</span><span class="sxs-lookup"><span data-stu-id="bbc15-158">Turn on the feature</span></span>

<span data-ttu-id="bbc15-159">Para disponibilizar o recurso no sistema, você deve habilitar suas chaves de configuração.</span><span class="sxs-lookup"><span data-stu-id="bbc15-159">To make the feature available on your system, you must enable its configuration keys.</span></span> <span data-ttu-id="bbc15-160">Você precisa fazer isso apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="bbc15-160">You only need to do this once.</span></span> <span data-ttu-id="bbc15-161">Para isso, um administrador deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bbc15-161">To do this, an administrator must do the following:</span></span>

1. <span data-ttu-id="bbc15-162">Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-162">Place your system into maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="bbc15-163">Vá para **Administração de sistema \> Configurar \> Configuração de licença**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-163">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="bbc15-164">Expanda a seção **Realidade misturada** e marque a caixa de seleção **Guia de realidade misturada**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-164">Expand the **Mixed reality** section and then select the **Mixed reality guide** check box.</span></span>
1. <span data-ttu-id="bbc15-165">Expanda a seção **Gerenciamento de produção** e marque a caixa de seleção **Instruções de produção**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-165">Expand the **Production management** section and then select the **Production instructions** check box.</span></span>
1. <span data-ttu-id="bbc15-166">Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-166">Turn off maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a><span data-ttu-id="bbc15-167">Configurar como os guias são exibidos no chão de fábrica</span><span class="sxs-lookup"><span data-stu-id="bbc15-167">Configure how Guides appear on the shop floor</span></span>

<span data-ttu-id="bbc15-168">Para configurar como os guias são exibidos no chão de fábrica, acesse **Realidade misturada \> Dynamics 365 Guides \> Configurar a integração de guias**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-168">To configure how Guides appear on the shop floor, go to **Mixed Reality \> Dynamics 365 Guides \> Configure Guides integration**.</span></span>

<span data-ttu-id="bbc15-169">![Configurar a integração de guias para manufatura](media/instruction-guides-configure-integration.png "Configurar a integração de guias para manufatura")</span><span class="sxs-lookup"><span data-stu-id="bbc15-169">![Configure Guide integration for manufacturing](media/instruction-guides-configure-integration.png "Configure Guide integration for manufacturing")</span></span>

<span data-ttu-id="bbc15-170">Defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="bbc15-170">Set the following fields:</span></span>

- <span data-ttu-id="bbc15-171">**URL do Microsoft Dataverse** - especifique a URL do ambiente do Microsoft Dataverse em que você cria o Guides.</span><span class="sxs-lookup"><span data-stu-id="bbc15-171">**Microsoft Dataverse URL** - Specify the URL for the Microsoft Dataverse environment where you create your Guides.</span></span> <span data-ttu-id="bbc15-172">O formato é "contoso.crm4.dynamics.com", em que a primeira parte da URL normalmente é chamada de organização (como "contoso."), a segunda parte é específica da região de dados do ambiente (por exemplo, "crm4.") e a última parte é o domínio (como "dynamics.com").</span><span class="sxs-lookup"><span data-stu-id="bbc15-172">The format is "contoso.crm4.dynamics.com", where the first part of the URL is typically named after your organization (such as "contoso."), the second part is specific to the data region of your environment (such as "crm4."), and the last part is the domain (such as "dynamics.com").</span></span> <span data-ttu-id="bbc15-173">Uma forma de encontrar a URL certa é acessar [home.dynamics.com](https://home.dynamics.com/) e abrir o aplicativo Guides.</span><span class="sxs-lookup"><span data-stu-id="bbc15-173">One way to find the right URL is to go to [home.dynamics.com](https://home.dynamics.com/) and then open your Guides app.</span></span> <span data-ttu-id="bbc15-174">Quando o Guides for aberto, você verá a URL na barra de endereços do navegador (só considere a URL básica, que deve ser semelhante ao exemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="bbc15-174">When Guides opens, you will see the URL in the address bar of your browser (only take the base URL, which should resemble the previous example).</span></span> <span data-ttu-id="bbc15-175">Esse valor é usado para compor os endereços das guias e será codificado nos códigos QR.</span><span class="sxs-lookup"><span data-stu-id="bbc15-175">This value is used to compose addresses for your guides and will be encoded into the QR codes."</span></span>
- <span data-ttu-id="bbc15-176">**Código QR** - Defina o tamanho do código QR renderizado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-176">**QR code size** - Set the size of the rendered QR code.</span></span> <span data-ttu-id="bbc15-177">É recomendável escolher um tamanho que ocupará a maior parte da tela de exibição, mas não mais.</span><span class="sxs-lookup"><span data-stu-id="bbc15-177">We recommend choosing a size that will fill most of your display screen, but not more.</span></span> <span data-ttu-id="bbc15-178">Normalmente, *15* é um bom valor.</span><span class="sxs-lookup"><span data-stu-id="bbc15-178">Typically, *15* is a good value.</span></span>
- <span data-ttu-id="bbc15-179">**Nível de correção de erro do código QR** - Defina a granularidade do código QR.</span><span class="sxs-lookup"><span data-stu-id="bbc15-179">**QR code error correction level** - Set the granularity of the QR code.</span></span> <span data-ttu-id="bbc15-180">A granularidade mais alta pode ajudar a aumentar a confiabilidade do código, mas o seu **tamanho de código QR** deve ser grande o suficiente para oferecer suporte ao nível de detalhes exigido pelo nível de correção selecionado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-180">Higher granularity can help increase the code's reliability, but your **QR code size** must be large enough to support the level of detail required by your selected correction level.</span></span>

> [!TIP]
> - <span data-ttu-id="bbc15-181">Os tamanhos de código QR que são grandes demais para sua tela demorarão um pouco mais para serem processados e serão redimensionados para se ajustarem à tela.</span><span class="sxs-lookup"><span data-stu-id="bbc15-181">QR codes sizes that are too large for your display will take a bit longer to render and then be scaled down to fit your display.</span></span> <span data-ttu-id="bbc15-182">Eles não oferecem uma vantagem.</span><span class="sxs-lookup"><span data-stu-id="bbc15-182">These do not provide a benefit.</span></span>
> - <span data-ttu-id="bbc15-183">Os tamanhos de código QR que são muito pequenos podem diminuir a capacidade de o HoloLens ler o código adequadamente em alguns ambientes.</span><span class="sxs-lookup"><span data-stu-id="bbc15-183">QR code sizes that are too small may decrease the ability of HoloLens to read the code properly in some environments.</span></span>
> - <span data-ttu-id="bbc15-184">Recomendamos que você teste as configurações de cada dispositivo que exibirá os códigos QR para os usuários do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bbc15-184">We recommend that you test the settings for each device that will display QR codes for HoloLens users.</span></span> <span data-ttu-id="bbc15-185">Escolha as configurações que oferecem legibilidade suficiente no seu ambiente de chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="bbc15-185">Choose settings that provide sufficient readability in your shop floor environment.</span></span>  

## <a name="get-an-overview-of-all-guide-assignments"></a><span data-ttu-id="bbc15-186">Obter uma visão geral de todas as atribuições de guias</span><span class="sxs-lookup"><span data-stu-id="bbc15-186">Get an overview of all Guide assignments</span></span>

<span data-ttu-id="bbc15-187">Use a página **Todos os guias** para ver a lista de todos os guias disponíveis na sua organização e todas as atribuições aos seus processos e recursos de produção.</span><span class="sxs-lookup"><span data-stu-id="bbc15-187">Use the **All Guides** page to see the list of all available Guides in your organization and all assignments to your production processes and resources.</span></span> <span data-ttu-id="bbc15-188">Para abri-la, acesse **Realidade misturada \> Guias \> Todos os guias**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-188">To open it, go to **Mixed reality \> Guides \> All Guides**.</span></span> <span data-ttu-id="bbc15-189">A lista na parte superior mostra todos os guias disponíveis, e você pode usar o campo aqui para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="bbc15-189">The list at the top shows all the available Guides and you can use the field here to filter the list.</span></span> <span data-ttu-id="bbc15-190">A lista na parte inferior mostra todas as atribuições de guias e fornece uma barra de ferramentas para gerenciá-las.</span><span class="sxs-lookup"><span data-stu-id="bbc15-190">The list at the bottom shows all Guide assignments and provides a toolbar for managing them.</span></span>

<span data-ttu-id="bbc15-191">![Gerenciar guias](media/instruction-guides-allguides.png "Gerenciar guias")</span><span class="sxs-lookup"><span data-stu-id="bbc15-191">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

<span data-ttu-id="bbc15-192">As seções a seguir descrevem os tipos de objetos para os quais você pode atribuir guias.</span><span class="sxs-lookup"><span data-stu-id="bbc15-192">The following sections describe the types of objects that you can assign Guides to.</span></span> <span data-ttu-id="bbc15-193">Cada guia atribuído fornece instruções anexadas automaticamente aos respectivos trabalhos de produção e estarão disponíveis no chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="bbc15-193">Each assigned guide provides instructions that are automatically attached to the respective production jobs and will be available on the shop floor.</span></span>

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a><span data-ttu-id="bbc15-194">Associar um guia a um recurso</span><span class="sxs-lookup"><span data-stu-id="bbc15-194">Associate a Guide to a resource</span></span>

<span data-ttu-id="bbc15-195">Adicione um guia a um [recurso](operations-resources.md) para oferecer o guia no contexto de trabalhos de produção relevantes.</span><span class="sxs-lookup"><span data-stu-id="bbc15-195">Add a Guide to a [resource](operations-resources.md) to offer the Guide in the context of relevant production jobs.</span></span>

### <a name="typical-scenario-using-resources"></a><span data-ttu-id="bbc15-196">Cenário típico usando recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-196">Typical scenario using resources</span></span>

<span data-ttu-id="bbc15-197">Por exemplo, você pode anexar um guia com instruções gerais de segurança ou manipulação de máquinas a um recurso do tipo de máquina.</span><span class="sxs-lookup"><span data-stu-id="bbc15-197">For example, you could attach a Guide with general machine security or handling instructions to a resource of type machine.</span></span> <span data-ttu-id="bbc15-198">Em seguida, o guia estará disponível em cada trabalho que for executado no computador.</span><span class="sxs-lookup"><span data-stu-id="bbc15-198">Then, the Guide will be available on every job that is performed on the machine.</span></span>

### <a name="add-a-guide-to-a-resource"></a><span data-ttu-id="bbc15-199">Adicionar um guia a um recurso</span><span class="sxs-lookup"><span data-stu-id="bbc15-199">Add a Guide to a resource</span></span>

<span data-ttu-id="bbc15-200">Para adicionar um guia a um recurso:</span><span class="sxs-lookup"><span data-stu-id="bbc15-200">To add a Guide to a resource:</span></span>

1. <span data-ttu-id="bbc15-201">Acesse **Controle de produção \> Configuração \> Recursos \> Recursos**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-201">Go to **Production control \> Setup \> Resources \> Resources**.</span></span>
1. <span data-ttu-id="bbc15-202">No painel de lista, selecione o recurso para o qual deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-202">From the list pane, select the resource you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-203">Expanda a FastTab **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-203">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="bbc15-204">Selecione **Adicionar** na barra de ferramentas **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-204">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="bbc15-205">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-205">A new line is added to the grid.</span></span>
1. <span data-ttu-id="bbc15-206">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-206">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="bbc15-207">Se você tiver muitos guias, poderá filtrar a lista para localizar o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="bbc15-207">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="bbc15-208">![Gerenciar guias](media/instruction-guides-allguides.png "Gerenciar guias")</span><span class="sxs-lookup"><span data-stu-id="bbc15-208">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a><span data-ttu-id="bbc15-209">Associar um guia a um grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-209">Associate a Guide to a resource group</span></span>

<span data-ttu-id="bbc15-210">Você pode adicionar um guia aos [grupos de recursos](tasks/define-discrete-manufacturing-resource-group.md), se usá-los para gerenciar grupos de máquinas, linhas de produção ou células de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-210">You can add a guide to [resource groups](tasks/define-discrete-manufacturing-resource-group.md) if you use them to manage groups of machines, production lines, or work cells.</span></span>

### <a name="typical-scenarios-using-resource-groups"></a><span data-ttu-id="bbc15-211">Cenários típicos usando grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-211">Typical scenarios using resource groups</span></span>

<span data-ttu-id="bbc15-212">**Exemplo 1:** você definiu um grupo de recursos para várias máquinas do mesmo modelo.</span><span class="sxs-lookup"><span data-stu-id="bbc15-212">**Example 1:** You have defined a resource group for several machines of the same model.</span></span> <span data-ttu-id="bbc15-213">Em vez de atribuir o guia relevante de instruções de manuseio para o modelo de máquina a cada recurso relevante, você pode atribuí-lo ao grupo de recursos que reflete esse modelo de máquina.</span><span class="sxs-lookup"><span data-stu-id="bbc15-213">Instead of assigning the relevant handling instruction guide for the machine model to every relevant resource, you could instead assign the Guide to the resource group that reflects that machine model.</span></span>

<span data-ttu-id="bbc15-214">**Exemplo 2:** você definiu um grupo de recursos para uma célula de trabalho que contém máquinas diferentes e tem um guia que fornece instruções gerais sobre como manter a célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-214">**Example 2:** You have defined a resource group for a work cell that contains different machines and you have a Guide that provides general instructions for how to maintain the work cell.</span></span> <span data-ttu-id="bbc15-215">O guia se aplica a qualquer atividade de produção nesta célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-215">The Guide applies to any production activity in this work cell.</span></span>

### <a name="add-a-guide-to-a-resource-group"></a><span data-ttu-id="bbc15-216">Adicionar um guia a um grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-216">Add a Guide to a resource group</span></span>

<span data-ttu-id="bbc15-217">Para adicionar um guia a um grupo de recursos:</span><span class="sxs-lookup"><span data-stu-id="bbc15-217">To add a Guide to a resource group:</span></span>

1. <span data-ttu-id="bbc15-218">Acesse **Controle de produção \> Configuração \> Recursos \> Grupos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-218">Go to **Production control \> Setup \> Resources \> Resource groups**.</span></span>
1. <span data-ttu-id="bbc15-219">No painel de lista, selecione o grupo de recursos para o qual deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-219">From the list pane, select the resource group you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-220">Expanda a FastTab **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-220">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="bbc15-221">Selecione **Adicionar** na barra de ferramentas **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-221">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="bbc15-222">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-222">A new line is added to the grid.</span></span>
1. <span data-ttu-id="bbc15-223">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-223">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="bbc15-224">Se você tiver muitos guias, poderá filtrar a lista para localizar o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="bbc15-224">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="bbc15-225">![Adicionar um guia a um grupo de recursos](media/instruction-guides-resourcegroup.png "Adicionar um guia a um grupo de recursos")</span><span class="sxs-lookup"><span data-stu-id="bbc15-225">![Adding a Guide to a resource group](media/instruction-guides-resourcegroup.png "Adding a Guide to a resource group")</span></span>

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a><span data-ttu-id="bbc15-226">Associar um guia a um produto liberado</span><span class="sxs-lookup"><span data-stu-id="bbc15-226">Associate a Guide to a released product</span></span>

<span data-ttu-id="bbc15-227">Você pode adicionar um guia a qualquer [produto liberado](../pim/tasks/create-released-product-single-company.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-227">You can add a guide to any [released product](../pim/tasks/create-released-product-single-company.md).</span></span>

### <a name="typical-scenario-using-released-products"></a><span data-ttu-id="bbc15-228">Cenário típico usando produtos liberados</span><span class="sxs-lookup"><span data-stu-id="bbc15-228">Typical scenario using released products</span></span>

<span data-ttu-id="bbc15-229">Os guias de nível de produto ajudam os trabalhadores do chão de fábrica com instruções relevantes para operar ou manusear um produto ou item específico liberado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-229">Product-level Guides help shop floor workers with instructions relevant to operating or handling a specific released product or item.</span></span>

### <a name="add-a-guide-to-a-released-product"></a><span data-ttu-id="bbc15-230">Adicionar um guia a um produto liberado</span><span class="sxs-lookup"><span data-stu-id="bbc15-230">Add a Guide to a released product</span></span>

<span data-ttu-id="bbc15-231">Para adicionar um guia a um produto liberado:</span><span class="sxs-lookup"><span data-stu-id="bbc15-231">To add a Guide to a released product:</span></span>

1. <span data-ttu-id="bbc15-232">Vá para **Gerenciamento de informações de produção \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-232">Go to **Production information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="bbc15-233">Abra o produto ao qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-233">Open the product you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-234">No Painel de ações, abra a guia **Engenheiro** e, no grupo **Exibir**, selecione **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-234">On the Action Pane, open the **Engineer** tab and from the **View** group, select **Associated Guides**.</span></span>
1. <span data-ttu-id="bbc15-235">A página **Guias associados** é aberta para o produto selecionado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-235">The **Associated Guides** page opens for your selected product.</span></span>
1. <span data-ttu-id="bbc15-236">Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-236">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="bbc15-237">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-237">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-238">![Adicionar um guia a um produto liberado](media/instruction-guides-ReleasedProduct-AddGuides.png "Adicionar um guia a um produto liberado")</span><span class="sxs-lookup"><span data-stu-id="bbc15-238">![Adding a Guide to a released product](media/instruction-guides-ReleasedProduct-AddGuides.png "Adding a Guide to a released product")</span></span>

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a><span data-ttu-id="bbc15-239">Associar um guia a uma fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-239">Associate a Guide to a formula</span></span>

<span data-ttu-id="bbc15-240">Você pode adicionar um guia a qualquer [fórmula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span><span class="sxs-lookup"><span data-stu-id="bbc15-240">You can add a guide to any [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span></span>

### <a name="typical-scenario-using-formulas"></a><span data-ttu-id="bbc15-241">Cenário típico usando fórmulas</span><span class="sxs-lookup"><span data-stu-id="bbc15-241">Typical scenario using formulas</span></span>
  
<span data-ttu-id="bbc15-242">Os guias de nível de fórmula oferecem aos funcionários de chão de fábrica as instruções orientadas sobre manuseio no contexto de uma fórmula ou receita.</span><span class="sxs-lookup"><span data-stu-id="bbc15-242">Formula-level Guides provide shop floor workers with guided handling instructions in the context of a formula or recipe.</span></span> <span data-ttu-id="bbc15-243">Os guias também podem ser atribuídos a versões de uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="bbc15-243">Guides can also be assigned to versions of a formula.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc15-244">Você pode atribuir orientações relevantes para processos de produção com base em uma fórmula a um roteiro, uma versão de roteiro ou relações de operação de roteiro.</span><span class="sxs-lookup"><span data-stu-id="bbc15-244">You can assign guidance relevant for production processes based on a formula to a route, route version, or route operation relations.</span></span>  

> <span data-ttu-id="bbc15-245">Não é possível anexar guias a linhas individuais de fórmulas no momento.</span><span class="sxs-lookup"><span data-stu-id="bbc15-245">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula"></a><span data-ttu-id="bbc15-246">Adicionar um guia a uma fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-246">Add a Guide to a formula</span></span>

<span data-ttu-id="bbc15-247">Para adicionar um guia a uma fórmula:</span><span class="sxs-lookup"><span data-stu-id="bbc15-247">To add a Guide to a formula:</span></span>

1. <span data-ttu-id="bbc15-248">Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-248">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="bbc15-249">Abra a fórmula à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-249">Open the formula you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-250">Abra a guia **Cabeçalho** acima da FastTab superior.</span><span class="sxs-lookup"><span data-stu-id="bbc15-250">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="bbc15-251">Expanda a FastTab **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-251">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="bbc15-252">Selecione **Adicionar** na barra de ferramentas **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-252">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="bbc15-253">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-253">A new line is added to the grid.</span></span>
1. <span data-ttu-id="bbc15-254">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-254">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-255">![Adicionar um guia a uma fórmula](media/instruction-guides-Formula.png "Adicionar um guia a uma fórmula")</span><span class="sxs-lookup"><span data-stu-id="bbc15-255">![Adding a Guide to a formula](media/instruction-guides-Formula.png "Adding a Guide to a formula")</span></span>

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a><span data-ttu-id="bbc15-256">Associar um guia a uma versão de fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-256">Associate a Guide to a formula version</span></span>

<span data-ttu-id="bbc15-257">Você pode adicionar um guia a qualquer [versão de fórmula](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="bbc15-257">You can add a guide to any [formula version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-formula-versions"></a><span data-ttu-id="bbc15-258">Cenário típico usando versões de fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-258">Typical scenario using formula versions</span></span>

<span data-ttu-id="bbc15-259">Os guias anexados a uma versão individual de uma fórmula oferecem aos trabalhadores de chão de fábrica as instruções que orientam sobre a produção dessa versão da receita de fórmula.</span><span class="sxs-lookup"><span data-stu-id="bbc15-259">Guides attached to an individual version of a formula provide shop floor workers with instructions that walk through the production of that version of the formula recipe.</span></span>

> [!TIP]
> <span data-ttu-id="bbc15-260">Você pode atribuir orientações relevantes para processos de produção com base nesta versão de fórmula a um roteiro, uma versão de roteiro ou relações de operação de roteiro.</span><span class="sxs-lookup"><span data-stu-id="bbc15-260">You can assign guidance relevant for production processes based on this formula version to a route, route version, or route operation relations.</span></span>  

> [!NOTE]
> <span data-ttu-id="bbc15-261">Não é possível anexar guias a linhas individuais de fórmulas no momento.</span><span class="sxs-lookup"><span data-stu-id="bbc15-261">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula-version"></a><span data-ttu-id="bbc15-262">Adicionar um guia a uma versão de fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-262">Add a Guide to a formula version</span></span>

<span data-ttu-id="bbc15-263">Para adicionar um guia a uma versão de fórmula:</span><span class="sxs-lookup"><span data-stu-id="bbc15-263">To add a Guide to a formula version:</span></span>

1. <span data-ttu-id="bbc15-264">Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-264">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="bbc15-265">Abra a fórmula que inclui uma versão à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-265">Open the formula that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-266">Abra a guia **Cabeçalho** acima da FastTab superior.</span><span class="sxs-lookup"><span data-stu-id="bbc15-266">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="bbc15-267">Na FastTab **Versões da fórmula**, selecione a versão à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-267">On the **Formula versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-268">Na barra de ferramentas **Versões de fórmula**, selecione **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-268">On the **Formula versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="bbc15-269">![Abrir os guias associados a uma versão de fórmula selecionada](media/instruction-guides-FormulaVersion.png "Abrir os guia associados a uma versão de fórmula selecionada")</span><span class="sxs-lookup"><span data-stu-id="bbc15-269">![Open the Guides associated with a selected formula version](media/instruction-guides-FormulaVersion.png "Open the Guides associated with a selected formula version")</span></span>
1. <span data-ttu-id="bbc15-270">A página **Guias associados** é aberta para a versão de fórmula.</span><span class="sxs-lookup"><span data-stu-id="bbc15-270">The **Associated Guides** page opens for your formula version.</span></span>
1. <span data-ttu-id="bbc15-271">Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-271">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="bbc15-272">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-272">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-273">![Adicionar um guia a uma versão de fórmula](media/instruction-guides-FormulaVersionAddGuide.png "Adicionar um guia a uma versão de fórmula")</span><span class="sxs-lookup"><span data-stu-id="bbc15-273">![Adding a Guide to a formula version](media/instruction-guides-FormulaVersionAddGuide.png "Adding a Guide to a formula version")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a><span data-ttu-id="bbc15-274">Associar um guia a uma lista de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-274">Associate a Guide to a bill of materials</span></span>

<span data-ttu-id="bbc15-275">Você pode adicionar um guia a qualquer [lista de materiais](bill-of-material-bom.md) (BOM).</span><span class="sxs-lookup"><span data-stu-id="bbc15-275">You can add a guide to any [bill of materials](bill-of-material-bom.md) (BOM).</span></span>

### <a name="typical-scenario-using-bills-of-materials"></a><span data-ttu-id="bbc15-276">Cenário típico usando listas de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-276">Typical scenario using bills of materials</span></span>

<span data-ttu-id="bbc15-277">Os guias anexados a uma BOM oferecem aos trabalhadores de chão de fábrica as instruções que explicam como preparar e manusear o material de uma BOM.</span><span class="sxs-lookup"><span data-stu-id="bbc15-277">Guides attached to a BOM provide shop floor workers with instructions that explain how to prepare and handle material from a BOM.</span></span> <span data-ttu-id="bbc15-278">Os guias também podem ser atribuídos a versões de uma BOM.</span><span class="sxs-lookup"><span data-stu-id="bbc15-278">Guides can also be assigned to versions of a BOM.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc15-279">Não é possível anexar guias a linhas individuais de BOM no momento.</span><span class="sxs-lookup"><span data-stu-id="bbc15-279">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials"></a><span data-ttu-id="bbc15-280">Adicionar um guia a uma lista de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-280">Add a Guide to a bill of materials</span></span>

<span data-ttu-id="bbc15-281">Para adicionar um guia a uma lista de materiais:</span><span class="sxs-lookup"><span data-stu-id="bbc15-281">To add a Guide to a bill of material:</span></span>

1. <span data-ttu-id="bbc15-282">Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Listas de materiais**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-282">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="bbc15-283">Abra a lista de materiais à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-283">Open the bill of materials that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-284">Abra a guia **Cabeçalho** acima da FastTab superior.</span><span class="sxs-lookup"><span data-stu-id="bbc15-284">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="bbc15-285">Expanda a FastTab **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-285">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="bbc15-286">Selecione **Adicionar** na barra de ferramentas **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-286">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="bbc15-287">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-287">A new line is added to the grid.</span></span>
1. <span data-ttu-id="bbc15-288">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-288">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-289">![Adicionar um guia a uma BOM](media/instruction-guides-BOM.png "Adicionar um guia a uma BOM")</span><span class="sxs-lookup"><span data-stu-id="bbc15-289">![Adding a Guide to a BOM](media/instruction-guides-BOM.png "Adding a Guide to a BOM")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a><span data-ttu-id="bbc15-290">Associar um guia a uma versão de lista de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-290">Associate a Guide to a bill of materials version</span></span>

<span data-ttu-id="bbc15-291">Você pode adicionar um guia a qualquer [versão de lista de materiais](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="bbc15-291">You can add a guide to any [bill of materials version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-bill-of-materials-versions"></a><span data-ttu-id="bbc15-292">Cenário típico usando versões de lista de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-292">Typical scenario using bill of materials versions</span></span>

<span data-ttu-id="bbc15-293">Os guias anexados a uma versão individual de BOM oferecem aos trabalhadores de chão de fábrica as instruções que explicam como preparar e manipular o material para uma versão de uma BOM diferente da BOM genérica ou de outras versões dela.</span><span class="sxs-lookup"><span data-stu-id="bbc15-293">Guides attached to an individual BOM version provide shop floor workers with instructions that explain how to prepare and handle material for a version of a BOM that is different from the generic BOM or other versions of it.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc15-294">Não é possível anexar guias a linhas individuais de BOM no momento.</span><span class="sxs-lookup"><span data-stu-id="bbc15-294">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials-version"></a><span data-ttu-id="bbc15-295">Adicionar um guia a uma versão de lista de materiais</span><span class="sxs-lookup"><span data-stu-id="bbc15-295">Add a Guide to a bill of materials version</span></span>

<span data-ttu-id="bbc15-296">Para adicionar um guia a uma versão de lista de materiais:</span><span class="sxs-lookup"><span data-stu-id="bbc15-296">To add a Guide to a bill of materials version:</span></span>

1. <span data-ttu-id="bbc15-297">Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Listas de materiais**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-297">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="bbc15-298">Abra a BOM que inclui uma versão à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-298">Open the BOM that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-299">Abra a guia **Cabeçalho** acima da FastTab superior.</span><span class="sxs-lookup"><span data-stu-id="bbc15-299">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="bbc15-300">Na FastTab **Versões de BOM**, selecione a versão à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-300">On the **BOM versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-301">Na barra de ferramentas **Versões de BOM**, selecione **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-301">On the **BOM versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="bbc15-302">![Abrir os guias associados a uma versão de BOM selecionada](media/instruction-guides-BOMVersion.png "Abrir os guias associados a uma versão de BOM selecionada")</span><span class="sxs-lookup"><span data-stu-id="bbc15-302">![Open the Guides associated with a selected BOM version](media/instruction-guides-BOMVersion.png "Open the Guides associated with a selected BOM version")</span></span>
1. <span data-ttu-id="bbc15-303">A página **Guias associados** é aberta para a versão de BOM.</span><span class="sxs-lookup"><span data-stu-id="bbc15-303">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="bbc15-304">Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-304">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="bbc15-305">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-305">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-306">![Adicionar um guia a uma versão de BOM](media/instruction-guides-BOMVersionAddGuide.png "Adicionar um guia a uma versão de BOM")</span><span class="sxs-lookup"><span data-stu-id="bbc15-306">![Adding a Guide to a BOM version](media/instruction-guides-BOMVersionAddGuide.png "Adding a Guide to a BOM version")</span></span>

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a><span data-ttu-id="bbc15-307">Associar um guia a um roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-307">Associate a Guide to a route</span></span>

<span data-ttu-id="bbc15-308">Você pode adicionar um guia a qualquer [roteiro](routes-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bbc15-308">You can add a guide to any [route](routes-operations.md).</span></span>

### <a name="typical-scenario-using-routes"></a><span data-ttu-id="bbc15-309">Cenário típico usando roteiros</span><span class="sxs-lookup"><span data-stu-id="bbc15-309">Typical scenario using routes</span></span>

<span data-ttu-id="bbc15-310">Normalmente, os roteiros são usados para especificar como um determinado produto liberado deve ser produzido com base em uma BOM ou em uma versão de BOM e com um conjunto de recursos ou grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="bbc15-310">Routes are typically used to specify how a certain released product shall be produced based on a BOM or BOM version and with a set of resources or resource groups.</span></span>

<span data-ttu-id="bbc15-311">Atribua um guia a um roteiro para oferecer instruções passo a passo para o respectivo processo de produção.</span><span class="sxs-lookup"><span data-stu-id="bbc15-311">Assign a Guide to a route to provide step-by-step instructions for the respective production process.</span></span>

### <a name="add-a-guide-to-a-route"></a><span data-ttu-id="bbc15-312">Adicionar um guia a um roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-312">Add a Guide to a route</span></span>

<span data-ttu-id="bbc15-313">Para adicionar um guia a um roteiro:</span><span class="sxs-lookup"><span data-stu-id="bbc15-313">To add a Guide to a route:</span></span>

1. <span data-ttu-id="bbc15-314">Acesse **Controle de produção \> Todos os roteiros**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-314">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="bbc15-315">Abra o roteiro ao qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-315">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-316">Expanda a FastTab **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-316">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="bbc15-317">Selecione **Adicionar** na barra de ferramentas **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-317">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="bbc15-318">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-318">A new line is added to the grid.</span></span>
1. <span data-ttu-id="bbc15-319">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-319">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-320">![Adicionar um guia a um roteiro](media/instruction-guides-Route.png "Adicionar um guia a um roteiro")</span><span class="sxs-lookup"><span data-stu-id="bbc15-320">![Adding a Guide to a route](media/instruction-guides-Route.png "Adding a Guide to a route")</span></span>

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a><span data-ttu-id="bbc15-321">Associar um guia a uma versão de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-321">Associate a Guide to a route version</span></span>

<span data-ttu-id="bbc15-322">Você pode adicionar um guia a qualquer [versão de roteiro](routes-operations.md#route-versions).</span><span class="sxs-lookup"><span data-stu-id="bbc15-322">You can add a guide to any [route version](routes-operations.md#route-versions).</span></span>

### <a name="typical-scenario-using-route-versions"></a><span data-ttu-id="bbc15-323">Cenário típico usando versões de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-323">Typical scenario using route versions</span></span>

<span data-ttu-id="bbc15-324">Normalmente, as versões de roteiro são usadas para especificar grades de processos de produção com base em um roteiro existente.</span><span class="sxs-lookup"><span data-stu-id="bbc15-324">Routes versions are typically used to specify variants of production processes based on an existing route.</span></span> <span data-ttu-id="bbc15-325">Você pode atribuir guias diferentes a cada versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="bbc15-325">You can assign different Guides to each route version.</span></span>

### <a name="add-a-guide-to-a-route-version"></a><span data-ttu-id="bbc15-326">Adicionar um guia a uma versão de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-326">Add a Guide to a route version</span></span>

<span data-ttu-id="bbc15-327">Para adicionar um guia a uma versão de roteiro:</span><span class="sxs-lookup"><span data-stu-id="bbc15-327">To add a Guide to a route version:</span></span>

1. <span data-ttu-id="bbc15-328">Acesse **Controle de produção \> Todos os roteiros**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-328">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="bbc15-329">Abra o roteiro ao qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-329">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-330">Na FastTab **Versões**, selecione a versão à qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-330">On the **Versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-331">Na barra de ferramentas **Versões**, selecione **Guias associados**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-331">On the **Versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="bbc15-332">![Abrir os guias associados a uma versão de roteiro selecionada](media/instruction-guides-RouteVersion.png "Abrir os guias associados a uma versão de roteiro selecionada")</span><span class="sxs-lookup"><span data-stu-id="bbc15-332">![Open the Guides associated with a selected route version](media/instruction-guides-RouteVersion.png "Open the Guides associated with a selected route version")</span></span>
1. <span data-ttu-id="bbc15-333">A página **Guias associados** é aberta para a versão de BOM.</span><span class="sxs-lookup"><span data-stu-id="bbc15-333">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="bbc15-334">Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-334">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="bbc15-335">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-335">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="bbc15-336">![Adicionar um guia a uma versão de roteiro](media/instruction-guides-RouteVersionAddGuide.png "Adicionar um guia a uma versão de roteiro")</span><span class="sxs-lookup"><span data-stu-id="bbc15-336">![Adding a Guide to a route version](media/instruction-guides-RouteVersionAddGuide.png "Adding a Guide to a route version")</span></span>

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a><span data-ttu-id="bbc15-337">Associar um guia a uma relação de operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-337">Associate a Guide to a route operation relation</span></span>

<span data-ttu-id="bbc15-338">Você pode adicionar um guia a qualquer [relação de operação de roteiro](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="bbc15-338">You can add a guide to any [route operation relation](routes-operations.md#operation-relations).</span></span>

### <a name="typical-scenario-using-route-operation-relations"></a><span data-ttu-id="bbc15-339">Cenário típico usando relações de operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-339">Typical scenario using route operation relations</span></span>

<span data-ttu-id="bbc15-340">As relações de operação são a maneira mais específica de adicionar orientações a um processo de produto e suas operações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bbc15-340">Operation relations are the most specific way to add guidance to a product process and its related operations.</span></span> <span data-ttu-id="bbc15-341">Você pode especificar orientações para cada operação em um roteiro e especificar orientações diferentes para qualquer tipo de contexto de relação especificado para um roteiro, como para configurações, itens específicos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bbc15-341">You can specify guidance for each operation in a route and specify different guidance for any type of relation context specified for a route, such as for specific items, configurations, and more.</span></span> <span data-ttu-id="bbc15-342">Você também pode especificar a quais estágios da operação as orientações se aplicam (como configuração, enfileiramento, processo ou transporte).</span><span class="sxs-lookup"><span data-stu-id="bbc15-342">You can also specify to which stages in the operation the guidance applies (such as setup, queueing, process, or transport).</span></span>

> [!NOTE]
> <span data-ttu-id="bbc15-343">Se você especificar guias para várias relações de operação de um roteiro, entre esses guias, somente o guia da relação mais específica será exibido no chão de fábrica para o trabalho gerado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-343">If you specify guides for several operation relations of a route, among those guides, only the guide from the most specific relation will be show on the shop floor for the generated job.</span></span>

### <a name="add-a-guide-to-a-route-operation-relation"></a><span data-ttu-id="bbc15-344">Adicionar um guia a uma relação de operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-344">Add a Guide to a route operation relation</span></span>

<span data-ttu-id="bbc15-345">Para adicionar um guia a uma relação de operação de roteiro:</span><span class="sxs-lookup"><span data-stu-id="bbc15-345">To add a Guide to a route operation relation:</span></span>

1. <span data-ttu-id="bbc15-346">Acesse **Controle de produção \> Todos os roteiros**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-346">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="bbc15-347">Abra o roteiro ao qual você deseja atribuir um guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-347">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="bbc15-348">No Painel de ações, abra a guia **Roteiro** e, no grupo **Manter**, selecione **Detalhes do roteiro**.</span><span class="sxs-lookup"><span data-stu-id="bbc15-348">On the Action Pane, open the **Route** tab and from the **Maintain** group, select **Route details**.</span></span>
1. <span data-ttu-id="bbc15-349">A **Detalhes do roteiro** é aberta para o roteiro selecionado.</span><span class="sxs-lookup"><span data-stu-id="bbc15-349">The **Route details** page opens for your selected rout.</span></span>
1. <span data-ttu-id="bbc15-350">Na grade superior, selecione a operação para a qual você deseja oferecer orientações.</span><span class="sxs-lookup"><span data-stu-id="bbc15-350">In the top grid, select the operation you want to provide guidance for.</span></span>
1. <span data-ttu-id="bbc15-351">Na grade inferior, selecione uma relação específica (ou a relação genérica **Todos**).</span><span class="sxs-lookup"><span data-stu-id="bbc15-351">In the bottom grid, select a specific relation (or the generic **All** relation).</span></span>
    <span data-ttu-id="bbc15-352">![Selecionar uma operação e uma relação](media/instruction-guides-RouteOperationRelation.png "Selecionar uma operação e uma relação")</span><span class="sxs-lookup"><span data-stu-id="bbc15-352">![Select an operation and then a relation](media/instruction-guides-RouteOperationRelation.png "Select an operation and then a relation")</span></span>
1. <span data-ttu-id="bbc15-353">Acima da grade inferior, abra a guia **Guias associados**. ![A guia Guias associados](media/instruction-guides-RouteOperationRelation-AddGuide.png "A guia Guias associados")</span><span class="sxs-lookup"><span data-stu-id="bbc15-353">Above the bottom gird, open the **Associated Guides** tab.  ![The Associated Guides tab](media/instruction-guides-RouteOperationRelation-AddGuide.png "The Associated Guides tab")</span></span>
1. <span data-ttu-id="bbc15-354">Selecione **Adicionar** na barra de ferramentas na parte superior da grade inferior para adicionar uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bbc15-354">Select **Add** from the toolbar at the top of the bottom grid to add a new line to the grid.</span></span>
1. <span data-ttu-id="bbc15-355">Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="bbc15-355">For the new row, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="bbc15-356">No restante da linha, marque a caixa de seleção para cada contexto em que o guia selecionado deve estar disponível.</span><span class="sxs-lookup"><span data-stu-id="bbc15-356">In the rest of the row, select the check box for each context where the selected Guide should be available.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc15-357">Você pode adicionar um ou mais guias para cada estágio de cada operação.</span><span class="sxs-lookup"><span data-stu-id="bbc15-357">You can add one or more guides for each stage of each operation.</span></span>

## <a name="select-guides-from-the-shop-floor-execution-interface"></a><span data-ttu-id="bbc15-358">Selecionar guias na interface de execução do chão de fábrica</span><span class="sxs-lookup"><span data-stu-id="bbc15-358">Select guides from the shop floor execution interface</span></span>

<span data-ttu-id="bbc15-359">Quando um trabalhador abre uma lista de trabalhos na interface de execução do chão de fábrica, o Supply Chain Management localiza os guias relevantes para os trabalhos exibidos.</span><span class="sxs-lookup"><span data-stu-id="bbc15-359">When a worker opens a job list on the shop floor execution interface, Supply Chain Management finds the relevant guides for the jobs shown.</span></span> <span data-ttu-id="bbc15-360">Use o botão **Guias** para exibir os guias relevantes.</span><span class="sxs-lookup"><span data-stu-id="bbc15-360">Use the **Guides** button to view the relevant guides.</span></span>

<span data-ttu-id="bbc15-361">![O botão Guias na interface de execução do chão de fábrica](media/instruction-guides-Shopfloor1.png "O botão Guias na interface de execução do chão de fábrica")</span><span class="sxs-lookup"><span data-stu-id="bbc15-361">![Guides button in the shop floor execution interface](media/instruction-guides-Shopfloor1.png "Guides button in the shop floor execution interface")</span></span>

<span data-ttu-id="bbc15-362">Em seguida, coloque um HoloLens e acesse o respectivo guia ao olhar para o código QR e ative o respectivo guia.</span><span class="sxs-lookup"><span data-stu-id="bbc15-362">Then put on a HoloLens and access the respective guide by glancing at the QR code and activating the respective Guide.</span></span>

<span data-ttu-id="bbc15-363">![Código QR para acessar guias usando um HoloLens](media/instruction-guides-Shopfloor2.png "Código QR para acessar guias usando um HoloLens")</span><span class="sxs-lookup"><span data-stu-id="bbc15-363">![QR code to access guides using a HoloLens](media/instruction-guides-Shopfloor2.png "QR code to access guides using a HoloLens")</span></span>

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a><span data-ttu-id="bbc15-364">Resolver a lógica para selecionar guias</span><span class="sxs-lookup"><span data-stu-id="bbc15-364">Resolving the logic for selecting Guides</span></span>

<span data-ttu-id="bbc15-365">Você pode adicionar guias aos seguintes dados de produção:</span><span class="sxs-lookup"><span data-stu-id="bbc15-365">You can add Guides to the following production data:</span></span>

- [<span data-ttu-id="bbc15-366">Recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-366">Resources</span></span>](#resources)
- [<span data-ttu-id="bbc15-367">Grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="bbc15-367">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="bbc15-368">Produtos liberados</span><span class="sxs-lookup"><span data-stu-id="bbc15-368">Released products</span></span>](#released-products)
- [<span data-ttu-id="bbc15-369">Fórmulas</span><span class="sxs-lookup"><span data-stu-id="bbc15-369">Formulas</span></span>](#formulas)
- [<span data-ttu-id="bbc15-370">Versões da fórmula</span><span class="sxs-lookup"><span data-stu-id="bbc15-370">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="bbc15-371">Listas de materiais (BOMs)</span><span class="sxs-lookup"><span data-stu-id="bbc15-371">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="bbc15-372">Versões da BOM</span><span class="sxs-lookup"><span data-stu-id="bbc15-372">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="bbc15-373">Roteiros</span><span class="sxs-lookup"><span data-stu-id="bbc15-373">Routes</span></span>](#routes)
- [<span data-ttu-id="bbc15-374">Versões de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-374">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="bbc15-375">Relações da operação de roteiro</span><span class="sxs-lookup"><span data-stu-id="bbc15-375">Route operation relations</span></span>](#route-operation-relations)

<span data-ttu-id="bbc15-376">Quando o Supply Chain Management gera os trabalhos para o chão de produção, ele coleta os guias relevantes dessas fontes.</span><span class="sxs-lookup"><span data-stu-id="bbc15-376">When Supply Chain Management generates the jobs for the production floor, it will collect the relevant Guides from those sources.</span></span> <span data-ttu-id="bbc15-377">Anote as seguintes regras importantes:</span><span class="sxs-lookup"><span data-stu-id="bbc15-377">Take note of the following important rules.</span></span>

- <span data-ttu-id="bbc15-378">Se você anexar uma versão de BOM ou uma versão de fórmula a um roteiro ou a uma ordem de produção, qualquer guia associado a essa versão, e também os guias anexados à BOM ou fórmula pai dessa versão, será exibido no trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-378">If you attach a BOM version or formula version to a route or production order, then any Guides attached to this version, and also the Guides attached to the parent BOM or formula of that version, will be shown on the job.</span></span>
- <span data-ttu-id="bbc15-379">Se você anexar uma versão de roteiro a uma ordem de produção, qualquer guia associado a essa versão, e também os guias anexados ao roteiro pai dessa versão, será exibido no trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-379">If you attach a route version to a production order, then any Guides attached to this version, and also the Guides attached to the parent route of that version, will be shown on the job.</span></span>
- <span data-ttu-id="bbc15-380">Se você definir várias relações de operação de roteiro que incluem a relação *Todos* e atribuir guias a elas, somente os guias da relação mais específica serão exibidos para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="bbc15-380">If you define several route operation relations that include the *All* relation and assign Guides to those, only the Guides from the most specific relation will be shown for the job.</span></span>  

<span data-ttu-id="bbc15-381">![Diagrama para resolver os guias relevantes](media/instruction-guides-Resolve.png "Diagrama para resolver os guias relevantes")</span><span class="sxs-lookup"><span data-stu-id="bbc15-381">![Diagram on resolving the relevant Guides](media/instruction-guides-Resolve.png "Diagram on resolving the relevant Guides")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]