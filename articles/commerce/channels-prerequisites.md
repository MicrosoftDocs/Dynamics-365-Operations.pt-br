---
title: Pré-requisitos de configuração de canal
description: Este tópico apresenta uma visão geral dos pré-requisitos de configuração de canais no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: b861d90f1333c8f6e61a83602ed74e30b65f3dc1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002280"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="48c31-103">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="48c31-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="48c31-104">Este tópico apresenta uma visão geral dos pré-requisitos de configuração de canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="48c31-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="48c31-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="48c31-105">Overview</span></span>

<span data-ttu-id="48c31-106">Para que um canal do Dynamics 365 Commerce possa ser criado, é preciso concluir várias tarefas de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="48c31-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="48c31-107">As listas de tarefas de pré-requisito a seguir estão organizadas por tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="48c31-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="48c31-108">Uma parte da documentação ainda está sendo escrita, e os links serão atualizados quando novos conteúdos forem publicados.</span><span class="sxs-lookup"><span data-stu-id="48c31-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="48c31-109">Inicialização</span><span class="sxs-lookup"><span data-stu-id="48c31-109">Initialization</span></span>

- [<span data-ttu-id="48c31-110">Inicializar dados semente</span><span class="sxs-lookup"><span data-stu-id="48c31-110">Initialize seed data</span></span>](../retail/enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="48c31-111">Pré-requisitos globais necessários para todos os tipos de canal</span><span class="sxs-lookup"><span data-stu-id="48c31-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="48c31-112">Definir e configurar sua estrutura de entidade legal</span><span class="sxs-lookup"><span data-stu-id="48c31-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="48c31-113">Configurar sua hierarquia organizacional</span><span class="sxs-lookup"><span data-stu-id="48c31-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="48c31-114">Configurar um depósito</span><span class="sxs-lookup"><span data-stu-id="48c31-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="48c31-115">Configurar imposto</span><span class="sxs-lookup"><span data-stu-id="48c31-115">Configure sales tax</span></span>](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="48c31-116">Configurar um perfil de notificação por email</span><span class="sxs-lookup"><span data-stu-id="48c31-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="48c31-117">Configurar sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="48c31-117">Set up number sequences</span></span>](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="48c31-118">Configurar um padrão e um catálogo de endereços padrão</span><span class="sxs-lookup"><span data-stu-id="48c31-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="48c31-119">Pré-requisitos do canal de varejo</span><span class="sxs-lookup"><span data-stu-id="48c31-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="48c31-120">Códigos informativos e grupos de códigos informativos</span><span class="sxs-lookup"><span data-stu-id="48c31-120">Info codes and info code groups</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/info-codes-retail?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="48c31-121">Configurar um perfil de funcionalidade de varejo</span><span class="sxs-lookup"><span data-stu-id="48c31-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="48c31-122">Configurar um catálogo de endereços de funcionário</span><span class="sxs-lookup"><span data-stu-id="48c31-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="48c31-123">Configurar um layout de tela</span><span class="sxs-lookup"><span data-stu-id="48c31-123">Set up a screen layout</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="48c31-124">Configurar uma estação de hardware</span><span class="sxs-lookup"><span data-stu-id="48c31-124">Set up a hardware station</span></span>](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation?toc=/dynamics365/commerce/toc.json)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="48c31-125">Pré-requisitos do canal de Call Center</span><span class="sxs-lookup"><span data-stu-id="48c31-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="48c31-126">Parâmetros de call center</span><span class="sxs-lookup"><span data-stu-id="48c31-126">Call center parameters</span></span>
- <span data-ttu-id="48c31-127">Métodos de reembolso de call center</span><span class="sxs-lookup"><span data-stu-id="48c31-127">Call center refund methods</span></span>
- <span data-ttu-id="48c31-128">Tipos de aluguel</span><span class="sxs-lookup"><span data-stu-id="48c31-128">Rental types</span></span>
- <span data-ttu-id="48c31-129">Serviços de pagamento</span><span class="sxs-lookup"><span data-stu-id="48c31-129">Payment services</span></span>
- <span data-ttu-id="48c31-130">Códigos de bloqueio de ordem</span><span class="sxs-lookup"><span data-stu-id="48c31-130">Order hold codes</span></span>

## <a name="online-channel-prerequisites"></a><span data-ttu-id="48c31-131">Pré-requisitos do canal online</span><span class="sxs-lookup"><span data-stu-id="48c31-131">Online channel prerequisites</span></span>

- [<span data-ttu-id="48c31-132">Criar um perfil de funcionalidade online</span><span class="sxs-lookup"><span data-stu-id="48c31-132">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="48c31-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="48c31-133">Additional resources</span></span>

[<span data-ttu-id="48c31-134">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="48c31-134">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="48c31-135">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="48c31-135">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="48c31-136">Configurar hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="48c31-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="48c31-137">Criar entidades legais</span><span class="sxs-lookup"><span data-stu-id="48c31-137">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="48c31-138">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="48c31-138">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="48c31-139">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="48c31-139">Set up an online channel</span></span>](channel-setup-online.md)
