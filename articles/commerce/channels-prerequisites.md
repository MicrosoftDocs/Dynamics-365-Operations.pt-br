---
title: Pré-requisitos de configuração de canal
description: Este tópico apresenta uma visão geral dos pré-requisitos de configuração de canais no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0da0457240cf12686fff2fa929c7fb510c11f242
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410148"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="c4c06-103">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="c4c06-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c4c06-104">Este tópico apresenta uma visão geral dos pré-requisitos de configuração de canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4c06-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c4c06-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c4c06-105">Overview</span></span>

<span data-ttu-id="c4c06-106">Para que um canal do Dynamics 365 Commerce possa ser criado, é preciso concluir várias tarefas de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="c4c06-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="c4c06-107">As listas de tarefas de pré-requisito a seguir estão organizadas por tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="c4c06-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="c4c06-108">Uma parte da documentação ainda está sendo escrita, e os links serão atualizados quando novos conteúdos forem publicados.</span><span class="sxs-lookup"><span data-stu-id="c4c06-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="c4c06-109">Inicialização</span><span class="sxs-lookup"><span data-stu-id="c4c06-109">Initialization</span></span>

- [<span data-ttu-id="c4c06-110">Inicializar dados semente</span><span class="sxs-lookup"><span data-stu-id="c4c06-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="c4c06-111">Pré-requisitos globais necessários para todos os tipos de canal</span><span class="sxs-lookup"><span data-stu-id="c4c06-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="c4c06-112">Definir e configurar sua estrutura de entidade legal</span><span class="sxs-lookup"><span data-stu-id="c4c06-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="c4c06-113">Configurar sua hierarquia organizacional</span><span class="sxs-lookup"><span data-stu-id="c4c06-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="c4c06-114">Configurar um depósito</span><span class="sxs-lookup"><span data-stu-id="c4c06-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="c4c06-115">Configurar imposto</span><span class="sxs-lookup"><span data-stu-id="c4c06-115">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="c4c06-116">Configurar um perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="c4c06-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="c4c06-117">Configurar sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="c4c06-117">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="c4c06-118">Configurar um padrão e um catálogo de endereços padrão</span><span class="sxs-lookup"><span data-stu-id="c4c06-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="c4c06-119">Pré-requisitos do canal de varejo</span><span class="sxs-lookup"><span data-stu-id="c4c06-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="c4c06-120">Códigos informativos e grupos de códigos informativos</span><span class="sxs-lookup"><span data-stu-id="c4c06-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="c4c06-121">Configurar um perfil de funcionalidade de varejo</span><span class="sxs-lookup"><span data-stu-id="c4c06-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="c4c06-122">Configurar um catálogo de endereços de funcionário</span><span class="sxs-lookup"><span data-stu-id="c4c06-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="c4c06-123">Configurar um layout de tela</span><span class="sxs-lookup"><span data-stu-id="c4c06-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="c4c06-124">Configurar uma estação de hardware</span><span class="sxs-lookup"><span data-stu-id="c4c06-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="c4c06-125">Pré-requisitos do canal de Call Center</span><span class="sxs-lookup"><span data-stu-id="c4c06-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="c4c06-126">Parâmetros de call center</span><span class="sxs-lookup"><span data-stu-id="c4c06-126">Call center parameters</span></span>
- [<span data-ttu-id="c4c06-127">Formas de pagamento para ordens e reembolsos de call center</span><span class="sxs-lookup"><span data-stu-id="c4c06-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="c4c06-128">Modos de entrega e encargos de call center</span><span class="sxs-lookup"><span data-stu-id="c4c06-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="c4c06-129">Pré-requisitos do canal online</span><span class="sxs-lookup"><span data-stu-id="c4c06-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="c4c06-130">Criar um perfil de funcionalidade online</span><span class="sxs-lookup"><span data-stu-id="c4c06-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="c4c06-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c4c06-131">Additional resources</span></span>

[<span data-ttu-id="c4c06-132">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="c4c06-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c4c06-133">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="c4c06-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c4c06-134">Configurar hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="c4c06-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="c4c06-135">Criar entidades legais</span><span class="sxs-lookup"><span data-stu-id="c4c06-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="c4c06-136">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="c4c06-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="c4c06-137">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="c4c06-137">Set up an online channel</span></span>](channel-setup-online.md)
