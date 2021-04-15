---
title: A loja de varejo não aparece na lista de lojas para retirada
description: Este tópico fornece orientação de solução de problemas que pode ajudar quando uma loja de varejo não aparece na lista de lojas de onde os itens podem ser retirados.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801594"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="848d1-103">A loja de varejo não aparece na lista de lojas para retirada</span><span class="sxs-lookup"><span data-stu-id="848d1-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="848d1-104">Este tópico fornece orientação de solução de problemas que pode ajudar quando uma loja de varejo não aparece na lista de lojas de onde os itens podem ser retirados.</span><span class="sxs-lookup"><span data-stu-id="848d1-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="848d1-105">descrição</span><span class="sxs-lookup"><span data-stu-id="848d1-105">Description</span></span>

<span data-ttu-id="848d1-106">Uma loja de varejo não aparece na lista de lojas onde os itens podem ser retirados.</span><span class="sxs-lookup"><span data-stu-id="848d1-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="848d1-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="848d1-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="848d1-108">Configurar longitude e latitude do endereço da loja na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="848d1-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="848d1-109">Para configurar longitude e latitude do endereço da loja na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="848d1-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="848d1-110">Vá para **Varejo e Comércio \> Canais \> Lojas \> Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="848d1-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="848d1-111">Localize a loja que você deseja que apareça entre as opções de retirada no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="848d1-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="848d1-112">Anote o valor de seu **Número da unidade operacional**.</span><span class="sxs-lookup"><span data-stu-id="848d1-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="848d1-113">Vá para **Administração da organização \> Organizações \> Unidades operacionais**.</span><span class="sxs-lookup"><span data-stu-id="848d1-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="848d1-114">Procure o número da unidade operacional que você anotou anteriormente e selecione a unidade operacional nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="848d1-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="848d1-115">Na guia rápida **Endereços**, selecione **Mais opções** e, em seguida, **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="848d1-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="848d1-116">Na guia rápida **Geral**, verifique se os campos **Longitude** e **Latitude** estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="848d1-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="848d1-117">Como parte dessa etapa, certifique-se de que os valores estão corretamente especificados como números positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="848d1-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="848d1-118">Configurar grupos de atendimento na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="848d1-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="848d1-119">Para configurar grupos de atendimento na matriz do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="848d1-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="848d1-120">Acesse **Varejo e Comércio \> Canais \> Lojas online**.</span><span class="sxs-lookup"><span data-stu-id="848d1-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="848d1-121">Selecione a loja online a ser configurada.</span><span class="sxs-lookup"><span data-stu-id="848d1-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="848d1-122">No Painel de Ação, selecione **Configurar** e, depois, **Atribuição do grupo de atendimento**.</span><span class="sxs-lookup"><span data-stu-id="848d1-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="848d1-123">Na página **Atribuição do grupo de atendimento**, selecione o grupo de atendimento da loja online.</span><span class="sxs-lookup"><span data-stu-id="848d1-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="848d1-124">Em **Configuração**, verifique se a loja de varejo está configurada corretamente para o grupo de atendimento.</span><span class="sxs-lookup"><span data-stu-id="848d1-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="848d1-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="848d1-125">Additional resources</span></span> 

[<span data-ttu-id="848d1-126">Criar uma unidade operacional</span><span class="sxs-lookup"><span data-stu-id="848d1-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="848d1-127">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="848d1-127">Set up an online channel</span></span>](../channel-setup-online.md)
