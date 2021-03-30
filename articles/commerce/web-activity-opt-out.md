---
title: Cancelar a coleta de eventos da atividade Web
description: Este tópico explica como você pode permitir que os visitantes do seu site recusem a coleta de eventos de atividade da Web no Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 244d612fa01529df4fff250df50a06526632fcf1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210914"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="d232c-103">Cancelar a coleta de eventos da atividade Web</span><span class="sxs-lookup"><span data-stu-id="d232c-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="d232c-104">Este tópico explica como você pode permitir que os clientes optem por cancelar a coleção de evento de atividade da Web no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d232c-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d232c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d232c-105">Overview</span></span>

<span data-ttu-id="d232c-106">O Dynamics 365 Commerce permite que os administradores de sites analisem a atividade da Web de usuários de seus sites de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d232c-106">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="d232c-107">Dessa forma, eles podem compreender melhor como os sites são usados e podem otimizar os sites para proporcionar uma experiência de usuário aprimorada e atender a objetivos comerciais.</span><span class="sxs-lookup"><span data-stu-id="d232c-107">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="d232c-108">Maneiras de os administradores implementarem uma experiência de recusa</span><span class="sxs-lookup"><span data-stu-id="d232c-108">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="d232c-109">Os administradores podem implementar uma experiência de recusa de três maneiras.</span><span class="sxs-lookup"><span data-stu-id="d232c-109">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="d232c-110">Recusar em nome de usuários</span><span class="sxs-lookup"><span data-stu-id="d232c-110">Opt out on behalf of users</span></span>

<span data-ttu-id="d232c-111">No gerenciamento de contas no Commerce headquarters (HQ), os administradores podem recusar em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="d232c-111">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="d232c-112">Nos cliente das sedes (HQ), na página **Todos os clientes**, procure e selecione um cliente.</span><span class="sxs-lookup"><span data-stu-id="d232c-112">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="d232c-113">Na página de detalhes do cliente, na Guia Rápida **Varejo**, na seção **Privacidade**, defina a opção **Não rastrear atividade da Web** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d232c-113">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Configurações de privacidade](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="d232c-115">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="d232c-115">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="d232c-116">Experiência de recusa baseada em módulo</span><span class="sxs-lookup"><span data-stu-id="d232c-116">Module-based opt-out experience</span></span>

<span data-ttu-id="d232c-117">Os administradores podem permitir que os usuários autenticados cancelem a coleta de eventos de atividade da Web sozinhos.</span><span class="sxs-lookup"><span data-stu-id="d232c-117">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="d232c-118">Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="d232c-118">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="d232c-119">Extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="d232c-119">Custom extensions</span></span>

<span data-ttu-id="d232c-120">Os administradores podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d232c-120">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="d232c-121">Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="d232c-121">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]