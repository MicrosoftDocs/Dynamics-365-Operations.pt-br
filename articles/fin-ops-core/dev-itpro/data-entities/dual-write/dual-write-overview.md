---
title: Visão geral da gravação dupla
description: Este tópico traz uma visão geral da gravação dupla, que fornece interação quase em tempo real entre aplicativos do Customer Engagement e aplicativos do Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6cc02b483a2975dd3be28032ea7e90b540945492
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561269"
---
# <a name="dual-write-overview"></a><span data-ttu-id="56624-103">Visão geral da gravação dupla</span><span class="sxs-lookup"><span data-stu-id="56624-103">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a><span data-ttu-id="56624-104">O que é gravação dupla?</span><span class="sxs-lookup"><span data-stu-id="56624-104">What is dual-write?</span></span>

<span data-ttu-id="56624-105">A gravação dupla é uma infraestrutura pronta para uso que fornece interação quase em tempo real entre aplicativos do Customer Engagement e aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="56624-105">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between customer engagement apps and Finance and Operations apps.</span></span> <span data-ttu-id="56624-106">Quando dados sobre clientes, produtos, pessoas e operações fluem além dos limites dos aplicativos, todos os departamentos de uma organização são capacitados.</span><span class="sxs-lookup"><span data-stu-id="56624-106">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="56624-107">A gravação dupla fornece integração bidirecional extremamente interligada entre aplicativos do Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="56624-107">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="56624-108">Qualquer alteração de dados nos aplicativos do Finance and Operations causa gravações no Dataverse e qualquer alteração de dados no Dataverse causa gravações nos aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="56624-108">Any data change in Finance and Operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="56624-109">Esse fluxo de dados automatizado fornece uma experiência de usuário integrada nos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="56624-109">This automated data flow provides an integrated user experience across the apps.</span></span>

![Relação de dados entre aplicativos](media/dual-write-overview.jpg)

<span data-ttu-id="56624-111">A gravação dupla tem dois aspectos: um *infraestrutura* e um *aplicativo*.</span><span class="sxs-lookup"><span data-stu-id="56624-111">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="56624-112">Infraestrutura</span><span class="sxs-lookup"><span data-stu-id="56624-112">Infrastructure</span></span>

<span data-ttu-id="56624-113">A infraestrutura de gravação dupla é extensível e confiável e inclui os seguintes recursos principais:</span><span class="sxs-lookup"><span data-stu-id="56624-113">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="56624-114">Fluxo de dados síncrono e bidirecional entre aplicativos</span><span class="sxs-lookup"><span data-stu-id="56624-114">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="56624-115">Sincronização, juntamente com os modos de reprodução, pausa e recuperação para oferecer suporte ao sistema durante os modos online e offline/assíncrono.</span><span class="sxs-lookup"><span data-stu-id="56624-115">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="56624-116">Capacidade de sincronizar dados iniciais entre os aplicativos</span><span class="sxs-lookup"><span data-stu-id="56624-116">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="56624-117">Exibição combinada de logs de atividades e erros para administradores de dados</span><span class="sxs-lookup"><span data-stu-id="56624-117">Combined view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="56624-118">Capacidade de configurar alertas e limites personalizados e assinar notificações</span><span class="sxs-lookup"><span data-stu-id="56624-118">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="56624-119">Interface de usuário (UI) intuitiva para filtragem e transformações</span><span class="sxs-lookup"><span data-stu-id="56624-119">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="56624-120">Capacidade de definir e exibir dependências e relacionamentos da tabela</span><span class="sxs-lookup"><span data-stu-id="56624-120">Ability to set and view table dependencies and relationships</span></span>
+ <span data-ttu-id="56624-121">Extensibilidade para mapas e tabelas padrão e personalizadas</span><span class="sxs-lookup"><span data-stu-id="56624-121">Extensibility for both standard and custom tables and maps</span></span>
+ <span data-ttu-id="56624-122">Gerenciamento confiável do ciclo de vida de aplicativos</span><span class="sxs-lookup"><span data-stu-id="56624-122">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="56624-123">Experiência de configuração pronta para uso para novos clientes</span><span class="sxs-lookup"><span data-stu-id="56624-123">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="56624-124">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="56624-124">Application</span></span>

<span data-ttu-id="56624-125">A gravação dupla cria um mapeamento entre conceitos em aplicativos do Finance and Operations e conceitos em aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="56624-125">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in customer engagement apps.</span></span> <span data-ttu-id="56624-126">Essa integração é compatível com os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="56624-126">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="56624-127">Cliente mestre integrado</span><span class="sxs-lookup"><span data-stu-id="56624-127">Integrated customer master</span></span>
+ <span data-ttu-id="56624-128">Acesso a cartões de fidelização de clientes e pontos de recompensa</span><span class="sxs-lookup"><span data-stu-id="56624-128">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="56624-129">Experiência unificada de controle de produtos</span><span class="sxs-lookup"><span data-stu-id="56624-129">Unified product mastering experience</span></span>
+ <span data-ttu-id="56624-130">Consciência da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="56624-130">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="56624-131">Fornecedor mestre integrado</span><span class="sxs-lookup"><span data-stu-id="56624-131">Integrated vendor master</span></span>
+ <span data-ttu-id="56624-132">Acesso a dados de referência financeira e tributária</span><span class="sxs-lookup"><span data-stu-id="56624-132">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="56624-133">Experiência de mecanismo de definição de preços sob demanda</span><span class="sxs-lookup"><span data-stu-id="56624-133">On-demand price engine experience</span></span>
+ <span data-ttu-id="56624-134">Experiência integrada de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="56624-134">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="56624-135">Capacidade de atender ativos internos e clientes por meio de agentes de campo</span><span class="sxs-lookup"><span data-stu-id="56624-135">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="56624-136">Experiência integrada de compra ao pagamento</span><span class="sxs-lookup"><span data-stu-id="56624-136">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="56624-137">Atividades e notas integradas para dados e documentos do cliente</span><span class="sxs-lookup"><span data-stu-id="56624-137">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="56624-138">Capacidade de procurar disponibilidade e detalhes de estoque disponíveis</span><span class="sxs-lookup"><span data-stu-id="56624-138">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="56624-139">Experiência de projeto com pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="56624-139">Project-to-cash experience</span></span>
+ <span data-ttu-id="56624-140">Capacidade de lidar com vários endereços e funções por meio do conceito de participante</span><span class="sxs-lookup"><span data-stu-id="56624-140">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="56624-141">Gerenciamento de fonte única para usuários</span><span class="sxs-lookup"><span data-stu-id="56624-141">Single source management for users</span></span>
+ <span data-ttu-id="56624-142">Canais integrados de varejo e marketing</span><span class="sxs-lookup"><span data-stu-id="56624-142">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="56624-143">Visibilidade de promoções e descontos</span><span class="sxs-lookup"><span data-stu-id="56624-143">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="56624-144">Funções de solicitação de serviço</span><span class="sxs-lookup"><span data-stu-id="56624-144">Request-for-service functions</span></span>
+ <span data-ttu-id="56624-145">Operações de serviço simplificadas</span><span class="sxs-lookup"><span data-stu-id="56624-145">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="56624-146">Principais motivos para usar a gravação dupla</span><span class="sxs-lookup"><span data-stu-id="56624-146">Top reasons to use dual-write</span></span>

<span data-ttu-id="56624-147">A gravação dupla fornece integração de dados nos aplicativos do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="56624-147">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="56624-148">Essa estrutura robusta vincula ambientes e permite que diferentes aplicativos comerciais trabalhem juntos.</span><span class="sxs-lookup"><span data-stu-id="56624-148">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="56624-149">Aqui estão os principais motivos pelos quais você deve usar a gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="56624-149">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="56624-150">A gravação dupla fornece integração bidirecional e extremamente interligada, em tempo quase real e bidirecional entre aplicativos do Finance and Operations e aplicativos baseados em modelo no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="56624-150">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="56624-151">Essa integração convertem o Microsoft Dynamics 365 no principal espaço para todas as suas soluções empresariais.</span><span class="sxs-lookup"><span data-stu-id="56624-151">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="56624-152">Os clientes que usam o Dynamics 365 Finance e o Dynamics 365 Supply Chain Management, mas que usam soluções que não são da Microsoft para gerenciamento de relacionamento com o cliente (CRM), estão migrando para o Dynamics 365 para obter suporte para gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="56624-152">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="56624-153">Os dados de clientes, produtos, operações, projetos e a Internet das Coisas (IoT) fluem automaticamente para o Dataverse por meio de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="56624-153">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Dataverse through dual-write.</span></span> <span data-ttu-id="56624-154">Essa conexão é útil para empresas interessadas em expansões do Power Platform.</span><span class="sxs-lookup"><span data-stu-id="56624-154">This connection is useful for businesses that are interested in Power Platform expansions.</span></span>
+ <span data-ttu-id="56624-155">A infraestrutura de gravação dupla segue o princípio sem codificação/com pouca codificação.</span><span class="sxs-lookup"><span data-stu-id="56624-155">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="56624-156">É necessário um esforço mínimo de engenharia para estender os mapas tabela a tabela padrão e incluir mapas personalizados.</span><span class="sxs-lookup"><span data-stu-id="56624-156">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="56624-157">A gravação dupla é compatível com os modos online e offline.</span><span class="sxs-lookup"><span data-stu-id="56624-157">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="56624-158">A Microsoft é a única empresa que oferece suporte aos modos online e offline.</span><span class="sxs-lookup"><span data-stu-id="56624-158">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a><span data-ttu-id="56624-159">O que significa a gravação dupla para desenvolvedores e arquitetos de aplicativos do Customer Engagement?</span><span class="sxs-lookup"><span data-stu-id="56624-159">What does dual-write mean for developers and architects of customer engagement apps?</span></span>

<span data-ttu-id="56624-160">A gravação dupla automatiza o fluxo de dados entre aplicativos do Finance and Operations e aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="56624-160">Dual-write automates the data flow between Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="56624-161">A gravação dupla consiste em duas soluções AppSource instaladas no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="56624-161">Dual-write consists of two AppSource solutions that are installed on Dataverse.</span></span> <span data-ttu-id="56624-162">As soluções expandem o esquema da tabela, os plugins e os fluxos de trabalho no Dataverse para que possam ser escalados para o tamanho do ERP.</span><span class="sxs-lookup"><span data-stu-id="56624-162">The solutions expand the table schema, plugins, and workflows on Dataverse so that they can scale to ERP size.</span></span> <span data-ttu-id="56624-163">Para uma implementação bem-sucedida, os desenvolvedores e arquitetos de aplicativos do Customer Engagement devem compreender essas alterações e colaborar com as contrapartes em aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="56624-163">For a successful implementation, developers and architects of customer engagement apps must understand these changes and collaborate with their counterparts on Finance and Operations apps.</span></span>

<span data-ttu-id="56624-164">Para criar paridade com aplicativos do Finance and Operations, a gravação dupla faz algumas alterações cruciais no esquema do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="56624-164">To create parity with Finance and Operations applications, dual-write makes some crucial changes in the Dataverse schema.</span></span> <span data-ttu-id="56624-165">Se você entender o plano, poderá evitar retrabalho de design e desenvolvimento no futuro.</span><span class="sxs-lookup"><span data-stu-id="56624-165">If you understand the plan, you can avoid some design and development rework in the future.</span></span>

+ <span data-ttu-id="56624-166">Quando o pacote de gravação dupla do AppSource for instalado, o Dataverse terá novos conceitos, como empresa e participante.</span><span class="sxs-lookup"><span data-stu-id="56624-166">When the dual-write AppSource package is installed, Dataverse will have new concepts such as company and party.</span></span> <span data-ttu-id="56624-167">Esses conceitos ajudam aplicativos criados no Dataverse, incluindo Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service, a interagir perfeitamente com aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="56624-167">These concepts help applications built on Dataverse, including Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service, to interact seamlessly with Finance and Operations apps.</span></span>

+ <span data-ttu-id="56624-168">Atividades e notas são unificadas e expandidas para suportar C1s (usuários do sistema) e C2s (clientes do sistema).</span><span class="sxs-lookup"><span data-stu-id="56624-168">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>

+ <span data-ttu-id="56624-169">Para evitar a perda de dados durante a transmissão de moeda entre aplicativos do Finance and Operations e o Dataverse, você poderá estender o número de casas decimais no tipo de dados de moeda de aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="56624-169">To prevent data loss during currency transmission between Finance and Operations apps and the Dataverse, you'll be able to extend the number of decimal places in the currency data type of customers engagement apps.</span></span> <span data-ttu-id="56624-170">O recurso converte automaticamente as linhas existentes no novo estado estendido na camada de metadados.</span><span class="sxs-lookup"><span data-stu-id="56624-170">The feature autotranslates existing rows to the new extended state at the metadata layer.</span></span> <span data-ttu-id="56624-171">Durante esse processo, o valor da moeda é convertido em dados decimais em vez de dados monetários, e o valor da moeda oferece suporte a 10 casas decimais.</span><span class="sxs-lookup"><span data-stu-id="56624-171">During this process, the currency value is translated to decimal data rather than money data, and the currency value supports 10 decimal places.</span></span> <span data-ttu-id="56624-172">Este recurso é opcional e apenas organizações que requeiram acima de 4 casas decimais de precisão deverão aceitá-lo.</span><span class="sxs-lookup"><span data-stu-id="56624-172">This feature is opt-in, and organizations that don't need more than 4 decimal places of precision do not need to opt in.</span></span> <span data-ttu-id="56624-173">Para obter mais informações, consulte [Migração de tipo de dados de moeda para gravação dupla](currrency-decimal-places.md).</span><span class="sxs-lookup"><span data-stu-id="56624-173">For more information, see [Currency data-type migration for dual-write](currrency-decimal-places.md).</span></span>

+ <span data-ttu-id="56624-174">[Efetividade de data](../../dev-tools/date-effectivity.md) será adicionada ao Dataverse.</span><span class="sxs-lookup"><span data-stu-id="56624-174">[Date effectivity](../../dev-tools/date-effectivity.md) will be added to Dataverse.</span></span> <span data-ttu-id="56624-175">Ela dará suporte a dados passados, presentes e futuros na mesma tabela.</span><span class="sxs-lookup"><span data-stu-id="56624-175">It will support past, present, and future data on the same table.</span></span>

+ <span data-ttu-id="56624-176">As [conversões de unidades](../../../../supply-chain/pim/tasks/manage-unit-measure.md) de produto têm suporte para produtos, cotações, ordens e faturas.</span><span class="sxs-lookup"><span data-stu-id="56624-176">Product [unit conversions](../../../../supply-chain/pim/tasks/manage-unit-measure.md) are supported for products, quotes, orders, and invoices.</span></span>

<span data-ttu-id="56624-177">Para obter mais informações sobre as alterações futuras, consulte [Novidades ou alterações em gravação dupla](whats-new-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="56624-177">For more information about upcoming changes, see [What's new or changed in dual-write](whats-new-dual-write.md).</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]