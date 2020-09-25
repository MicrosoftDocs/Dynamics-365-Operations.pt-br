---
title: Atualizar processo
description: O Microsoft Dynamics 365 Human Resources é um software como serviço (SaaS) que disponibiliza atualizações de serviço contínuas e touchless para alterações de aplicação e plataforma.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
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
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: be9be5509f933ecbda5bf6d040027a7bac8b666d
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759950"
---
# <a name="update-process"></a><span data-ttu-id="b00d3-103">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="b00d3-103">Update process</span></span>

<span data-ttu-id="b00d3-104">O Microsoft Dynamics 365 Human Resources é um software como serviço (SaaS) que disponibiliza atualizações de serviço contínuas e touchless.</span><span class="sxs-lookup"><span data-stu-id="b00d3-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="b00d3-105">Essas atualizações contêm alterações no aplicativo e na plataforma, que geralmente oferecem melhorias cruciais para o serviço, incluindo atualizações regulatórias.</span><span class="sxs-lookup"><span data-stu-id="b00d3-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="b00d3-106">Política de atualização</span><span class="sxs-lookup"><span data-stu-id="b00d3-106">Update policy</span></span>

<span data-ttu-id="b00d3-107">As atualizações são lançadas regularmente para todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="b00d3-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="b00d3-108">O Human Resources oferecem suporte de acordo com a [política de Ciclo de Vida da Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), que oferece diretrizes consistentes e previsíveis para a disponibilidade de suporte.</span><span class="sxs-lookup"><span data-stu-id="b00d3-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="b00d3-109">Cadência da versão</span><span class="sxs-lookup"><span data-stu-id="b00d3-109">Release cadence</span></span> 

<span data-ttu-id="b00d3-110">As atualizações do Human Resources são aplicadas a todos os ambientes automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b00d3-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="b00d3-111">O Human Resources oferece dois tipos de versão:</span><span class="sxs-lookup"><span data-stu-id="b00d3-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="b00d3-112">**Atualizações de serviço**: atualizações ocorrem a cada duas semanas e incluem correções de bugs e novos recursos.</span><span class="sxs-lookup"><span data-stu-id="b00d3-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="b00d3-113">As atualizações de serviço também incluem atualizações de Plataforma aplicáveis quando são lançadas.</span><span class="sxs-lookup"><span data-stu-id="b00d3-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="b00d3-114">Para ter uma ideia de quando as atualizações de Plataforma serão lançadas, consulte [Tabela 3: versões da plataforma](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="b00d3-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span></span> <span data-ttu-id="b00d3-115">As atualizações quinzenais têm uma distribuição global em etapas entre regiões.</span><span class="sxs-lookup"><span data-stu-id="b00d3-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="b00d3-116">Para obter mais informações sobre atualizações quinzenais, consulte [Novidades ou alterações do Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="b00d3-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="b00d3-117">Todos os data centers compatíveis são atualizados a cada duas semanas, salvo indicação em contrário.</span><span class="sxs-lookup"><span data-stu-id="b00d3-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="b00d3-118">As regiões EUA, Austrália, Europa, Reino Unido, Ásia e Canadá estão inclusas nas atualizações quinzenais.</span><span class="sxs-lookup"><span data-stu-id="b00d3-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="b00d3-119">**Atualizações de soluções do Common Data Service**: essas atualizações ocorrem aproximadamente a cada seis semanas, conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="b00d3-119">**Common Data Service solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="b00d3-120">Elas incluem novas entidades e alterações às entidades existentes no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b00d3-120">They include new entities and changes to existing entities in Common Data Service.</span></span> <span data-ttu-id="b00d3-121">Essas atualizações são lançadas nas mesmas regiões como as atualizações quinzenais, e levam até seis semanas para serem replicadas em todos os data centers.</span><span class="sxs-lookup"><span data-stu-id="b00d3-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="b00d3-122">As atualizações da solução podem ou não estar alinhadas às atualizações de serviço quinzenais.</span><span class="sxs-lookup"><span data-stu-id="b00d3-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="b00d3-123">As atualizações de solução ficam disponíveis em todos os data centers após serem lançadas.</span><span class="sxs-lookup"><span data-stu-id="b00d3-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="b00d3-124">Caso não queira esperar as atualizações serem replicadas automaticamente, você pode aplicá-las manualmente em qualquer ambiente ou data center.</span><span class="sxs-lookup"><span data-stu-id="b00d3-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="b00d3-125">Quando necessário, o Human Resources também oferece os seguintes tipos de correções:</span><span class="sxs-lookup"><span data-stu-id="b00d3-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="b00d3-126">**Revisão (hotfix)**: correções de bugs que podem ocorrer com ou sem o lançamento da atualização de serviço quinzenal</span><span class="sxs-lookup"><span data-stu-id="b00d3-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="b00d3-127">**Correção de emergência**: hotfixes proativos e reativos que são independentes por natureza, podem incluir alterações de código ou somente para configuração para solucionar problemas de sites ativos e podem ocorrer sem um lançamento de atualização de serviço quinzenal</span><span class="sxs-lookup"><span data-stu-id="b00d3-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="b00d3-128">As versões são analisadas, testadas e validadas em um ambiente interno.</span><span class="sxs-lookup"><span data-stu-id="b00d3-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="b00d3-129">Após as compilações serem aprovadas, elas são implementadas na produção.</span><span class="sxs-lookup"><span data-stu-id="b00d3-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2020"></a><span data-ttu-id="b00d3-130">Exceções de cadência da versão em 2020</span><span class="sxs-lookup"><span data-stu-id="b00d3-130">Release cadence exceptions in 2020</span></span>

<span data-ttu-id="b00d3-131">Para contabilizar feriados, a agenda de lançamentos para novembro e dezembro de 2020 é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="b00d3-131">To account for holidays, the release schedule for November and December 2020 is as follows:</span></span>

- <span data-ttu-id="b00d3-132">Lançamento de novembro: 2 de novembro - 13 de novembro</span><span class="sxs-lookup"><span data-stu-id="b00d3-132">November release: November 2 - November 13</span></span>
- <span data-ttu-id="b00d3-133">Lançamento de dezembro: 30 de novembro - 11 de dezembro</span><span class="sxs-lookup"><span data-stu-id="b00d3-133">December release: November 30 - December 11</span></span>
 
<span data-ttu-id="b00d3-134">A cadência de lançamentos de duas semanas será retomada normalmente em 11 de janeiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="b00d3-134">The two-week release cadence will resume as usual on January 11, 2021.</span></span>

## <a name="communications"></a><span data-ttu-id="b00d3-135">Comunicações</span><span class="sxs-lookup"><span data-stu-id="b00d3-135">Communications</span></span>

<span data-ttu-id="b00d3-136">Descubra as novidades do Human Resources e o que já foi lançado em:</span><span class="sxs-lookup"><span data-stu-id="b00d3-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="b00d3-137">Dynamics 365 Human Resources roteiro</span><span class="sxs-lookup"><span data-stu-id="b00d3-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="b00d3-138">Planos de Versão do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b00d3-138">Dynamics 365 Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans/)

- [<span data-ttu-id="b00d3-139">Novidades ou alterações no Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="b00d3-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="b00d3-140">[Pesquisa de problemas no Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (somente para bugs relacionados à Plataforma)</span><span class="sxs-lookup"><span data-stu-id="b00d3-140">[Issue search in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="b00d3-141">Blog do Human Resources</span><span class="sxs-lookup"><span data-stu-id="b00d3-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="b00d3-142">Comunidade do Human Resources no Yammer</span><span class="sxs-lookup"><span data-stu-id="b00d3-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="b00d3-143">Versões prévias do recurso em um ambiente de área restrita</span><span class="sxs-lookup"><span data-stu-id="b00d3-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="b00d3-144">Você pode validar as versões prévias do recurso em um ambiente de área restrita antes de habilitá-las no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="b00d3-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="b00d3-145">Para obter mais informações sobre como habilitar os recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="b00d3-145">For more information about enabling features, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

<span data-ttu-id="b00d3-146">Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias.</span><span class="sxs-lookup"><span data-stu-id="b00d3-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="b00d3-147">Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="b00d3-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="b00d3-148">Assim que vir novos recursos no espaço de trabalho Gerenciamento de recursos, você poderá ativá-los.</span><span class="sxs-lookup"><span data-stu-id="b00d3-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="b00d3-149">Alguns recursos podem ser ativados por padrão.</span><span class="sxs-lookup"><span data-stu-id="b00d3-149">Some features may be on by default.</span></span>

<span data-ttu-id="b00d3-150">Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho Gerenciamento de recursos).</span><span class="sxs-lookup"><span data-stu-id="b00d3-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="b00d3-151">Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="b00d3-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="b00d3-152">O espaço de trabalho Gerenciamento de recursos indica quando a versão prévia do recurso se tornará obrigatória.</span><span class="sxs-lookup"><span data-stu-id="b00d3-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="b00d3-153">Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais.</span><span class="sxs-lookup"><span data-stu-id="b00d3-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="b00d3-154">Você não pode desativar recursos obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b00d3-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="b00d3-155">Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="b00d3-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="b00d3-156">É altamente recomendado visualizar os recursos em uma área restrita ou um ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="b00d3-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="b00d3-157">É melhor criar uma cópia do ambiente de produção atual ou do banco de dados em um ambiente de área restrita para obter a experiência completa dos novos recursos com seus dados.</span><span class="sxs-lookup"><span data-stu-id="b00d3-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="b00d3-158">Para obter mais informações sobre como provisionar um ambiente de área restrita, consulte [Provisionar um projeto do Human Resources](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="b00d3-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="b00d3-159">Para remover um ambiente de teste, consulte [Remover uma instância](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="b00d3-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="b00d3-160">Relatar bugs</span><span class="sxs-lookup"><span data-stu-id="b00d3-160">Report bugs</span></span>

<span data-ttu-id="b00d3-161">Enquanto estiver testando as versões prévias do recurso ou experimentando novas funcionalidades, poderá encontrar itens que não funcionam como deveriam.</span><span class="sxs-lookup"><span data-stu-id="b00d3-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="b00d3-162">Relate os bugs no [suporte do Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="b00d3-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="b00d3-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b00d3-163">See also</span></span>

[<span data-ttu-id="b00d3-164">Planos de Versão do Dynamics 365 e Power Platform</span><span class="sxs-lookup"><span data-stu-id="b00d3-164">Dynamics 365 and Power Platform Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans)</br>
[<span data-ttu-id="b00d3-165">Novidades ou alterações no Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="b00d3-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="b00d3-166">Política de ciclo de vida do software - Nuvem</span><span class="sxs-lookup"><span data-stu-id="b00d3-166">Software lifecycle policy</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

