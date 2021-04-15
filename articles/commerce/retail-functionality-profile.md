---
title: Criar um perfil de funcionalidade de varejo
description: Este tópico descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b8d481597485775796290f61de19ef7682cb9f43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791988"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="c48e3-103">Criar um perfil de funcionalidade de varejo</span><span class="sxs-lookup"><span data-stu-id="c48e3-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c48e3-104">Este tópico descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c48e3-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c48e3-105">O perfil de funcionalidade de comércio fornece várias configurações usadas em canais online.</span><span class="sxs-lookup"><span data-stu-id="c48e3-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="c48e3-106">Cada canal deve especificar um perfil de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c48e3-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="c48e3-107">Criar um perfil de funcionalidade</span><span class="sxs-lookup"><span data-stu-id="c48e3-107">Create a functionality profile</span></span>

<span data-ttu-id="c48e3-108">Para criar um novo perfil de funcionalidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c48e3-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="c48e3-109">No painel de navegação, vá para **Módulos \> Configuração de canal \> Perfis de PDV \> Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="c48e3-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="c48e3-110">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c48e3-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c48e3-111">No campo **Perfil**, insira uma ID para o perfil ("FN006" no exemplo da imagem abaixo).</span><span class="sxs-lookup"><span data-stu-id="c48e3-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="c48e3-112">No campo **Descrição**, insira um valor ("perfil da Adventure Works" no exemplo da imagem abaixo).</span><span class="sxs-lookup"><span data-stu-id="c48e3-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="c48e3-113">Na seção **Geral**, selecione um país/região para a localidade **ISO**.</span><span class="sxs-lookup"><span data-stu-id="c48e3-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="c48e3-114">Na seção **Geral**, modifique outras configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c48e3-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="c48e3-115">Na seção **Geral**, selecione uma **ID do perfil de recibo** para o recebimento de emails.</span><span class="sxs-lookup"><span data-stu-id="c48e3-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="c48e3-116">Na seção **Funções**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c48e3-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="c48e3-117">Na seção **Valor**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c48e3-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="c48e3-118">Na seção **Códigos Informativos**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c48e3-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="c48e3-119">Na seção **Numeração de recibo**, modifique as configurações, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c48e3-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="c48e3-120">A imagem a seguir mostra um exemplo de perfil de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c48e3-120">The following image shows an example functionality profile.</span></span>
  
![Exemplo de perfil de funcionalidade](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="c48e3-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c48e3-122">Additional resources</span></span>

[<span data-ttu-id="c48e3-123">Códigos informativos e grupos de códigos informativos</span><span class="sxs-lookup"><span data-stu-id="c48e3-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="c48e3-124">Criar novo catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="c48e3-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="c48e3-125">Visão geral do layout da tela</span><span class="sxs-lookup"><span data-stu-id="c48e3-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="c48e3-126">Configurar e instalar Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="c48e3-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
