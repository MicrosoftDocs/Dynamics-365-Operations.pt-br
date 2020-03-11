---
title: Visão geral de gravação dupla
description: Este tópico fornece uma visão geral de gravação dupla. A gravação dupla é uma infraestrutura que fornece interação quase em tempo real entre aplicativos baseados em modelo do Microsoft Dynamics 365 e aplicativos do Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075970"
---
# <a name="dual-write-overview"></a><span data-ttu-id="496d5-104">Visão geral de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="496d5-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a><span data-ttu-id="496d5-105">O que é gravação dupla?</span><span class="sxs-lookup"><span data-stu-id="496d5-105">What is dual-write?</span></span>

<span data-ttu-id="496d5-106">A gravação dupla é uma infraestrutura pronta para uso que fornece interação quase em tempo real entre aplicativos baseados em modelo no Microsoft Dynamics 365 e aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="496d5-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="496d5-107">Quando dados sobre clientes, produtos, pessoas e operações fluem além dos limites dos aplicativos, todos os departamentos de uma organização são capacitados.</span><span class="sxs-lookup"><span data-stu-id="496d5-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="496d5-108">A gravação dupla fornece integração bidirecional extremamente interligada entre aplicativos do Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="496d5-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="496d5-109">Qualquer alteração de dados nos aplicativos do Finance and Operations causa gravações no Common Data Service e qualquer alteração de dados no Common Data Service causa gravações nos aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="496d5-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="496d5-110">Esse fluxo de dados automatizado fornece uma experiência de usuário integrada nos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="496d5-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Relação de dados entre aplicativos](media/dual-write-overview.jpg)

<span data-ttu-id="496d5-112">A gravação dupla tem dois aspectos: um *infraestrutura* e um *aplicativo*.</span><span class="sxs-lookup"><span data-stu-id="496d5-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="496d5-113">Infraestrutura</span><span class="sxs-lookup"><span data-stu-id="496d5-113">Infrastructure</span></span>

<span data-ttu-id="496d5-114">A infraestrutura de gravação dupla é extensível e confiável e inclui os seguintes recursos principais:</span><span class="sxs-lookup"><span data-stu-id="496d5-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="496d5-115">Fluxo de dados síncrono e bidirecional entre aplicativos</span><span class="sxs-lookup"><span data-stu-id="496d5-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="496d5-116">Sincronização, juntamente com os modos de reprodução, pausa e recuperação para oferecer suporte ao sistema durante os modos online e offline/assíncrono.</span><span class="sxs-lookup"><span data-stu-id="496d5-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="496d5-117">Capacidade de sincronizar dados iniciais entre os aplicativos</span><span class="sxs-lookup"><span data-stu-id="496d5-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="496d5-118">Visualização consolidada de logs de atividades e erros para administradores de dados</span><span class="sxs-lookup"><span data-stu-id="496d5-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="496d5-119">Capacidade de configurar alertas e limites personalizados e assinar notificações</span><span class="sxs-lookup"><span data-stu-id="496d5-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="496d5-120">Interface de usuário (UI) intuitiva para filtragem e transformações</span><span class="sxs-lookup"><span data-stu-id="496d5-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="496d5-121">Capacidade de definir e exibir dependências e relacionamentos da entidade</span><span class="sxs-lookup"><span data-stu-id="496d5-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="496d5-122">Extensibilidade para mapas e entidades padrão e personalizadas</span><span class="sxs-lookup"><span data-stu-id="496d5-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="496d5-123">Gerenciamento confiável do ciclo de vida de aplicativos</span><span class="sxs-lookup"><span data-stu-id="496d5-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="496d5-124">Experiência de configuração pronta para uso para novos clientes</span><span class="sxs-lookup"><span data-stu-id="496d5-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="496d5-125">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="496d5-125">Application</span></span>

<span data-ttu-id="496d5-126">A gravação dupla cria um mapeamento entre conceitos em aplicativos do Finance and Operations e conceitos em aplicativos baseados em modelo no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="496d5-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="496d5-127">Essa integração é compatível com os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="496d5-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="496d5-128">Cliente mestre integrado</span><span class="sxs-lookup"><span data-stu-id="496d5-128">Integrated customer master</span></span>
+ <span data-ttu-id="496d5-129">Acesso a cartões de fidelização de clientes e pontos de recompensa</span><span class="sxs-lookup"><span data-stu-id="496d5-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="496d5-130">Experiência unificada de controle de produtos</span><span class="sxs-lookup"><span data-stu-id="496d5-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="496d5-131">Consciência da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="496d5-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="496d5-132">Fornecedor mestre integrado</span><span class="sxs-lookup"><span data-stu-id="496d5-132">Integrated vendor master</span></span>
+ <span data-ttu-id="496d5-133">Acesso a dados de referência financeira e tributária</span><span class="sxs-lookup"><span data-stu-id="496d5-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="496d5-134">Experiência de mecanismo de definição de preços sob demanda</span><span class="sxs-lookup"><span data-stu-id="496d5-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="496d5-135">Experiência integrada de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="496d5-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="496d5-136">Capacidade de atender ativos internos e clientes por meio de agentes de campo</span><span class="sxs-lookup"><span data-stu-id="496d5-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="496d5-137">Experiência integrada de compra ao pagamento</span><span class="sxs-lookup"><span data-stu-id="496d5-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="496d5-138">Atividades e notas integradas para dados e documentos do cliente</span><span class="sxs-lookup"><span data-stu-id="496d5-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="496d5-139">Capacidade de procurar disponibilidade e detalhes de estoque disponíveis</span><span class="sxs-lookup"><span data-stu-id="496d5-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="496d5-140">Experiência de projeto com pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="496d5-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="496d5-141">Capacidade de lidar com vários endereços e funções por meio do conceito de participante</span><span class="sxs-lookup"><span data-stu-id="496d5-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="496d5-142">Gerenciamento de fonte única para usuários</span><span class="sxs-lookup"><span data-stu-id="496d5-142">Single source management for users</span></span>
+ <span data-ttu-id="496d5-143">Canais integrados de varejo e marketing</span><span class="sxs-lookup"><span data-stu-id="496d5-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="496d5-144">Visibilidade de promoções e descontos</span><span class="sxs-lookup"><span data-stu-id="496d5-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="496d5-145">Funções de solicitação de serviço</span><span class="sxs-lookup"><span data-stu-id="496d5-145">Request-for-service functions</span></span>
+ <span data-ttu-id="496d5-146">Operações de serviço simplificadas</span><span class="sxs-lookup"><span data-stu-id="496d5-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="496d5-147">Principais motivos para usar a gravação dupla</span><span class="sxs-lookup"><span data-stu-id="496d5-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="496d5-148">A gravação dupla fornece integração de dados nos aplicativos do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="496d5-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="496d5-149">Essa estrutura robusta vincula ambientes e permite que diferentes aplicativos comerciais trabalhem juntos.</span><span class="sxs-lookup"><span data-stu-id="496d5-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="496d5-150">Aqui estão os principais motivos pelos quais você deve usar a gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="496d5-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="496d5-151">A gravação dupla fornece integração bidirecional e extremamente interligada, em tempo quase real e bidirecional entre aplicativos do Finance and Operations e aplicativos baseados em modelo no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="496d5-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="496d5-152">Essa integração convertem o Microsoft Dynamics 365 no principal espaço para todas as suas soluções empresariais.</span><span class="sxs-lookup"><span data-stu-id="496d5-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="496d5-153">Os clientes que usam o Dynamics 365 Finance e o Dynamics 365 Supply Chain Management, mas que usam soluções que não são da Microsoft para gerenciamento de relacionamento com o cliente (CRM), estão migrando para o Dynamics 365 para obter suporte para gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="496d5-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="496d5-154">Os dados de clientes, produtos, operações, projetos e a Internet das Coisas (IoT) fluem automaticamente para o Common Data Service por meio de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="496d5-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="496d5-155">Essa conexão é muito útil para empresas interessadas nas expansões do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="496d5-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="496d5-156">A infraestrutura de gravação dupla segue o princípio sem codificação/com pouca codificação.</span><span class="sxs-lookup"><span data-stu-id="496d5-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="496d5-157">É necessário um esforço mínimo de engenharia para estender os mapas tabela a tabela padrão e incluir mapas personalizados.</span><span class="sxs-lookup"><span data-stu-id="496d5-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="496d5-158">A gravação dupla é compatível com os modos online e offline.</span><span class="sxs-lookup"><span data-stu-id="496d5-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="496d5-159">A Microsoft é a única empresa que oferece suporte aos modos online e offline.</span><span class="sxs-lookup"><span data-stu-id="496d5-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="496d5-160">O que a gravação dupla significa para usuários e arquitetos de produtos do CRM?</span><span class="sxs-lookup"><span data-stu-id="496d5-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="496d5-161">A gravação dupla automatiza o fluxo de dados entre os aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="496d5-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="496d5-162">Em versões futuras, os conceitos em aplicativos baseados em modelo no Dynamics 365 (por exemplo, cliente, contato, cotação e ordem) serão dimensionados para clientes de mercados de classe média e média-superior.</span><span class="sxs-lookup"><span data-stu-id="496d5-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="496d5-163">Na primeira versão, a maior parte da automação é manipulada por soluções de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="496d5-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="496d5-164">Em versões futuras, essas soluções se tornarão parte do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="496d5-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="496d5-165">Ao entender as próximas alterações no Common Data Service, você pode poupar esforços em longo prazo.</span><span class="sxs-lookup"><span data-stu-id="496d5-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="496d5-166">Veja algumas das mudanças cruciais:</span><span class="sxs-lookup"><span data-stu-id="496d5-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="496d5-167">O Common Data Service terá novos conceitos, como empresa e participante.</span><span class="sxs-lookup"><span data-stu-id="496d5-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="496d5-168">Esses conceitos afetarão todos os aplicativos criados no Common Data Service, como Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="496d5-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="496d5-169">Atividades e notas são unificadas e expandidas para suportar C1s (usuários do sistema) e C2s (clientes do sistema).</span><span class="sxs-lookup"><span data-stu-id="496d5-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="496d5-170">Veja algumas das próximas mudanças no Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="496d5-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="496d5-171">O tipo de dados decimal substituirá o tipo de dados monetários.</span><span class="sxs-lookup"><span data-stu-id="496d5-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="496d5-172">A efetividade da data oferecerá suporte a dados passados, presentes e futuros no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="496d5-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="496d5-173">Haverá mais suporte para taxas de câmbio e moeda, e a interface de programação de aplicativos (API) **Taxa de Câmbio** será revisada.</span><span class="sxs-lookup"><span data-stu-id="496d5-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="496d5-174">Conversões de unidades serão compatíveis.</span><span class="sxs-lookup"><span data-stu-id="496d5-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="496d5-175">Para obter mais informações sobre as próximas alterações, consulte [Dados no Common Data Service – fase 1 e 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span><span class="sxs-lookup"><span data-stu-id="496d5-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span></span>
