---
title: Visão geral do gerenciamento de alterações de engenharia
description: Este tópico fornece uma visão geral do gerenciamento de alterações de engenharia, que ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947511"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="ae24e-103">Visão geral do gerenciamento de alterações de engenharia</span><span class="sxs-lookup"><span data-stu-id="ae24e-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="ae24e-104">Resumo do recurso</span><span class="sxs-lookup"><span data-stu-id="ae24e-104">Feature summary</span></span>

<span data-ttu-id="ae24e-105">Os fabricantes de hoje precisam de um forte gerenciamento de dados de produtos, controle de versão e gerenciamento de alterações de engenharia para serem bem-sucedidos em um mundo com ciclos de vida de produtos cada vez menores, requisitos de qualidade e confiabilidade maiores e um foco maior na segurança dos produtos.</span><span class="sxs-lookup"><span data-stu-id="ae24e-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="ae24e-106">O gerenciamento de alterações de engenharia traz estrutura e disciplina para o processo de gerenciamento de dados de produtos e permite que os produtos sejam definidos, liberados e revisados de forma controlada com suporte dos fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ae24e-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="ae24e-107"> Por meio de versões do produto e do gerenciamento de alterações de engenharia, você pode documentar, avaliar o impacto e aplicar alterações de engenharia durante todo o ciclo de vida de um produto.</span><span class="sxs-lookup"><span data-stu-id="ae24e-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="ae24e-108">O gerenciamento de alterações de engenharia ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia.</span><span class="sxs-lookup"><span data-stu-id="ae24e-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="ae24e-109">Veja uma lista dos principais recursos:</span><span class="sxs-lookup"><span data-stu-id="ae24e-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="ae24e-110">Controle de versão de produtos</span><span class="sxs-lookup"><span data-stu-id="ae24e-110">Product versioning</span></span>
- <span data-ttu-id="ae24e-111">Funcionalidade aprimorada de liberação de produtos que permite manter os dados mestres dos produtos em uma entidade legal (a empresa de engenharia) e publicar o produto liberado totalmente configurado em outras entidades legais</span><span class="sxs-lookup"><span data-stu-id="ae24e-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="ae24e-112">Regras para validar que as informações necessárias foram inseridas antes de uma versão de produto ser ativada (verificações de preparação)</span><span class="sxs-lookup"><span data-stu-id="ae24e-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="ae24e-113">Gerenciamento aprimorado do ciclo de vida de produtos por meio de um controle refinado sobre quando um produto liberado pode ser usado em processos empresariais específicos</span><span class="sxs-lookup"><span data-stu-id="ae24e-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="ae24e-114">Solicitações de alterações de engenharia com suporte dos fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="ae24e-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="ae24e-115">Ordens de alterações de engenharia com suporte dos fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="ae24e-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="ae24e-116">O vídeo anterior ([Recursos de gerenciamento de alterações no Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.</span><span class="sxs-lookup"><span data-stu-id="ae24e-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="ae24e-117">Ativar os recursos de gerenciamento de alterações de engenharia e dimensão de versão para o seu sistema</span><span class="sxs-lookup"><span data-stu-id="ae24e-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="ae24e-118">Para poder usar o gerenciamento de alterações de engenharia, você deve habilitar o recurso *Gerenciamento de Alterações de Engenharia* e sua chave de configuração.</span><span class="sxs-lookup"><span data-stu-id="ae24e-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="ae24e-119">Se você quiser rastrear a dimensão de versão dos produtos nas transações (opcional), também deverá habilitar o recurso *Dimensão de versão do produto* e sua chave de configuração.</span><span class="sxs-lookup"><span data-stu-id="ae24e-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="ae24e-120">Primeiro, ative os recursos seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae24e-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="ae24e-121">Acesse o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ae24e-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="ae24e-122">Verifique se há atualizações.</span><span class="sxs-lookup"><span data-stu-id="ae24e-122">Check for updates.</span></span>
1. <span data-ttu-id="ae24e-123">Ative o recurso denominado **Gerenciamento de Alterações de Engenharia**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="ae24e-124">Se quiser usá-lo, ative também o recurso denominado **Versão de dimensão do produto**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="ae24e-125">Em seguida, ative as chaves de configuração seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae24e-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="ae24e-126">Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ae24e-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="ae24e-127">Vá para **Administração de sistema \> Configurar \> Configuração de licença**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="ae24e-128">Expanda o nó **Comércio**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="ae24e-129">Habilite a chave de configuração para o recurso principal, marcando a caixa de seleção **Gerenciamento de Alterações de Engenharia**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** check box.</span></span> <span data-ttu-id="ae24e-130">(Não é necessário expandir o nó, a menos que você também deseje desabilitar um ou ambos os sub-recursos.)</span><span class="sxs-lookup"><span data-stu-id="ae24e-130">(It isn't necessary to expand the node unless you also want to disable one or both of its sub-features.)</span></span>
1. <span data-ttu-id="ae24e-131">Se também quiser usar a dimensão de versão, marque a caixa de seleção **Dimensão do produto - Versão**.</span><span class="sxs-lookup"><span data-stu-id="ae24e-131">If you also want to use the version dimension, then select the **Product dimension - Version** check box.</span></span> <span data-ttu-id="ae24e-132">(Esta caixa de seleção está mais abaixo na lista, não aninhada no nó **Gerenciamento de Alterações de Engenharia**.)</span><span class="sxs-lookup"><span data-stu-id="ae24e-132">(This check box is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="ae24e-133">Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ae24e-133">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae24e-134">A partir de abril de 2022, as chaves de licença de **Gerenciamento de Alterações de Engenharia** e **Dimensão do produto - Versão** serão habilitadas por padrão para todas as novas instalações, mas você ainda poderá desabilitá-las, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ae24e-134">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
