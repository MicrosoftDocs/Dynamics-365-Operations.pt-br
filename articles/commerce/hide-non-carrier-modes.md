---
title: Ocultar modos de entrega sem transportadora das opções de remessa no PDV
description: Este tópico descreve uma opção de configuração que pode impedir a exibição de modos de entrega sem transportadora para seleção quando ordens de remessa são criadas no aplicativo do ponto de venda (POS).
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 38d57ed5f8d2b8725cd11156f0135988bb76e047
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410276"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="fc86c-103">Ocultar modos de entrega sem transportadora das opções de remessa no PDV</span><span class="sxs-lookup"><span data-stu-id="fc86c-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fc86c-104">Este tópico descreve uma opção de configuração disponível para o aplicativo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="fc86c-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="fc86c-105">Esta opção de configuração alterará o comportamento da seleção de um modo de entrega quando ordens de remessa são criadas no PDV.</span><span class="sxs-lookup"><span data-stu-id="fc86c-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="fc86c-106">Quando os usuários criam ordens de remessa de clientes no PDV, eles podem selecionar um modo de entrega para a remessa.</span><span class="sxs-lookup"><span data-stu-id="fc86c-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="fc86c-107">Essa funcionalidade está disponível independentemente da ordem inteira sendo enviada ou de apenas linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="fc86c-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="fc86c-108">Por padrão, a caixa de diálogo em que um modo de entrega é selecionado mostra todos os modos de entrega válidos para a combinação de um canal, um item e um endereço de entrega.</span><span class="sxs-lookup"><span data-stu-id="fc86c-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="fc86c-109">Esses modos de entrega são definidos na página **Modos de entrega** em Headquarters (**Vendas e marketing \> Configurar \> Distribuição \> Modos de entrega**).</span><span class="sxs-lookup"><span data-stu-id="fc86c-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="fc86c-110">Modos de entrega "sem transportadora", como **Execução** ou **Retirada**, também podem aparecer para seleção na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fc86c-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="fc86c-111">Contudo, foi adicionado um recurso que permite ocultar modos de entrega sem transportadora na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fc86c-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="fc86c-112">Para ativar esse recurso, na página **Parâmetros do Commerce**, na guia **Ordens do cliente**, defina a opção **Mostrar apenas opções de modo de transportadora para ordens de remessa** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc86c-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="fc86c-113">Depois de ativar esse recurso e executar os trabalhos de distribuição apropriados para sincronizar as informações com o banco de dados do canal, os modos de entrega sem transportadora não aparecerão para seleção durante o processo de criação de ordens de remessa no PDV.</span><span class="sxs-lookup"><span data-stu-id="fc86c-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
