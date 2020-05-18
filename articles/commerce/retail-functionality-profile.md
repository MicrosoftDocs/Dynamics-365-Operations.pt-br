---
title: Criar um perfil de funcionalidade de varejo
description: Este tópico descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 6bee51eb25b04eb65e588dd4cf54a0cef587aa15
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057339"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="9ab54-103">Criar um perfil de funcionalidade de varejo</span><span class="sxs-lookup"><span data-stu-id="9ab54-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9ab54-104">Este tópico descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ab54-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9ab54-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="9ab54-105">Overview</span></span>

<span data-ttu-id="9ab54-106">O perfil de funcionalidade de comércio fornece várias configurações usadas em canais online.</span><span class="sxs-lookup"><span data-stu-id="9ab54-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="9ab54-107">Cada canal deve especificar um perfil de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9ab54-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="9ab54-108">Criar um perfil de funcionalidade</span><span class="sxs-lookup"><span data-stu-id="9ab54-108">Create a functionality profile</span></span>

<span data-ttu-id="9ab54-109">Para criar um novo perfil de funcionalidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9ab54-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="9ab54-110">No painel de navegação, vá para **Módulos \> Configuração de canal \> Perfis de PDV \> Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="9ab54-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="9ab54-111">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9ab54-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9ab54-112">No campo **Perfil**, insira uma ID para o perfil ("FN006" no exemplo da imagem abaixo).</span><span class="sxs-lookup"><span data-stu-id="9ab54-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="9ab54-113">No campo **Descrição**, insira um valor ("perfil da Adventure Works" no exemplo da imagem abaixo).</span><span class="sxs-lookup"><span data-stu-id="9ab54-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="9ab54-114">Na seção **Geral**, selecione um país/região para a localidade **ISO**.</span><span class="sxs-lookup"><span data-stu-id="9ab54-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="9ab54-115">Na seção **Geral**, modifique outras configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ab54-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="9ab54-116">Na seção **Geral**, selecione uma **ID do perfil de recibo** para o recebimento de emails.</span><span class="sxs-lookup"><span data-stu-id="9ab54-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="9ab54-117">Na seção **Funções**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ab54-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="9ab54-118">Na seção **Valor**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ab54-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="9ab54-119">Na seção **Códigos Informativos**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ab54-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="9ab54-120">Na seção **Numeração de recibo**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ab54-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="9ab54-121">A imagem a seguir mostra um exemplo de perfil de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9ab54-121">The following image shows an example functionality profile.</span></span>
  
![Exemplo de perfil de funcionalidade](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="9ab54-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9ab54-123">Additional resources</span></span>

[<span data-ttu-id="9ab54-124">Códigos informativos e grupos de códigos informativos</span><span class="sxs-lookup"><span data-stu-id="9ab54-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="9ab54-125">Criar novo catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="9ab54-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="9ab54-126">Visão geral do layout da tela</span><span class="sxs-lookup"><span data-stu-id="9ab54-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="9ab54-127">Configurar e instalar Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="9ab54-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 