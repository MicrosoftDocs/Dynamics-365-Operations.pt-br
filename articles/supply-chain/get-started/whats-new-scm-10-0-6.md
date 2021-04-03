---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.6 (Novembro de 2019)
description: Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 77fdc3ae092fc8f214ae3ba68866244385e32b74
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263413"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="c7af7-103">Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.6 (Novembro de 2019)</span><span class="sxs-lookup"><span data-stu-id="c7af7-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7af7-104">Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="c7af7-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="c7af7-105">Esta versão tem um número de compilação de 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="c7af7-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="c7af7-106">Embora a data de disponibilidade geral seja em novembro, os novos recursos estão disponíveis para o lançamento antecipado em outubro.</span><span class="sxs-lookup"><span data-stu-id="c7af7-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="c7af7-107">Para obter mais informações sobre a versão 10.0.6, consulte [Recursos adicionais](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="c7af7-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="c7af7-108">Entidade de dados V2 de modelos de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="c7af7-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="c7af7-109">Uma segunda versão da entidade de dados de "modelos de configuração de produto" será lançada (chamada "modelos de configuração de produto V2").</span><span class="sxs-lookup"><span data-stu-id="c7af7-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="c7af7-110">O modelo padrão de "modelos de configuração de produto 418" também deve ser para usar a nova entidade de dados "modelos de configuração de produto V2" nos modelos de estrutura de importação/exportação.</span><span class="sxs-lookup"><span data-stu-id="c7af7-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="c7af7-111">O modelo não será atualizado automaticamente para que você tenha que carregar o modelo manualmente a partir do padrão.</span><span class="sxs-lookup"><span data-stu-id="c7af7-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="c7af7-112">A entidade V2 exporta uma linha como arquivo separado em um anexo em vez de embutida, solucionando as limitações de tamanho da entidade V1.</span><span class="sxs-lookup"><span data-stu-id="c7af7-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="c7af7-113">O que você precisa fazer para realizar esta alteração?</span><span class="sxs-lookup"><span data-stu-id="c7af7-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="c7af7-114">Como a entidade V1 foi substituída, você deve iniciar a migração do V1 para o V2.</span><span class="sxs-lookup"><span data-stu-id="c7af7-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="c7af7-115">Se estiver usando o modelo de "modelos de configuração de produto 418", você pode clicar no botão "carregar modelos padrão" e recarregar o modelo de "modelos de configuração de produto – 418"</span><span class="sxs-lookup"><span data-stu-id="c7af7-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="c7af7-116">Se for necessário manter a compatibilidade com sistemas existentes, você pode continuar usando o modelo existente e a entidade V1 (preterida) até mover as integrações para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="c7af7-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="c7af7-117">Aprimoramentos em gerenciamento de recursos</span><span class="sxs-lookup"><span data-stu-id="c7af7-117">Feature management enhancements</span></span>
<span data-ttu-id="c7af7-118">O gerenciamento de recursos agora permite habilitar todos os novos recursos por padrão, exigir a confirmação para habilitar um recurso e habilitar todos os recursos que ainda não foram habilitados.</span><span class="sxs-lookup"><span data-stu-id="c7af7-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="c7af7-119">Participante responsável pelo Contrato de compra</span><span class="sxs-lookup"><span data-stu-id="c7af7-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="c7af7-120">Agora você pode definir as partes primárias e secundárias responsáveis no formulário de classificação do Contrato de compra e os Contratos de compra resultantes.</span><span class="sxs-lookup"><span data-stu-id="c7af7-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="c7af7-121">Isso fornece ao usuário acesso a quem supervisiona os contratos.</span><span class="sxs-lookup"><span data-stu-id="c7af7-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="c7af7-122">Link da RFQ na linha da Ordem de compra</span><span class="sxs-lookup"><span data-stu-id="c7af7-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="c7af7-123">Você pode adicionar um link de referência das linhas da Ordem de compra às linhas da RFQ correspondentes das quais elas foram originadas, permitindo que o usuário receba facilmente o documento da solicitação de cotação de suporte.</span><span class="sxs-lookup"><span data-stu-id="c7af7-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7af7-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c7af7-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="c7af7-125">Correções de bug</span><span class="sxs-lookup"><span data-stu-id="c7af7-125">Bug fixes</span></span>
<span data-ttu-id="c7af7-126">Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.6, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="c7af7-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="c7af7-127">Update 30 para plataforma</span><span class="sxs-lookup"><span data-stu-id="c7af7-127">Platform update 30</span></span>
<span data-ttu-id="c7af7-128">O Microsoft Dynamics 365 Supply Chain Management 10.0.6 inclui a Atualização de plataforma 30.</span><span class="sxs-lookup"><span data-stu-id="c7af7-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="c7af7-129">Para saber mais sobre a Atualização de plataforma 30, consulte [Novidades ou alterações da Atualização de plataforma 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="c7af7-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="c7af7-130">Dynamics 365: plano do ciclo de lançamentos 2 de 2019</span><span class="sxs-lookup"><span data-stu-id="c7af7-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="c7af7-131">Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?</span><span class="sxs-lookup"><span data-stu-id="c7af7-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="c7af7-132">Confira o [Dynamics 365: plano do ciclo de lançamentos 2 de 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="c7af7-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="c7af7-133">Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.</span><span class="sxs-lookup"><span data-stu-id="c7af7-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="c7af7-134">Recursos removidos e preteridos do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c7af7-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="c7af7-135">O tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c7af7-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="c7af7-136">Um recurso *removido* não estará mais disponível no produto.</span><span class="sxs-lookup"><span data-stu-id="c7af7-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="c7af7-137">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="c7af7-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="c7af7-138">Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.</span><span class="sxs-lookup"><span data-stu-id="c7af7-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="c7af7-139">Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses.</span><span class="sxs-lookup"><span data-stu-id="c7af7-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="c7af7-140">Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.</span><span class="sxs-lookup"><span data-stu-id="c7af7-140">Typically, these are functional updates that need to be made to the compiler.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]