---
title: Configurar depósitos para ordens de transferência
description: Este tópico descreve como você pode configurar depósitos para ordens de transferência.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8111601cb2948c66097b0f5b2f261b7462b279f9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "337454"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="83a35-103">Configurar depósitos para ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="83a35-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83a35-104">Você pode usar níveis de depósito para criar uma hierarquia que ofereça suporte a ordens de transferência entre depósitos.</span><span class="sxs-lookup"><span data-stu-id="83a35-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="83a35-105">Com base nesta configuração, o planejamento mestre calculará as requisições de itens em cada nível de depósito e gerará ordens de transferência planejadas a partir de um depósito de origem atribuído para abastecê-lo.</span><span class="sxs-lookup"><span data-stu-id="83a35-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="83a35-106">Clique em **Gerenciamento do estoque > Configuração > Divisão do estoque > Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="83a35-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="83a35-107">Selecione o depósito que desejar reabastecer.</span><span class="sxs-lookup"><span data-stu-id="83a35-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="83a35-108">Na FastTab **Planejamento mestre**, marque a caixa de seleção **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="83a35-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="83a35-109">No campo **Depósito principal**, selecione o depósito que deseja atribuir como o depósito de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="83a35-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="83a35-110">O agendamento do planejamento mestre calculará uma solicitação de transferência para o depósito selecionado e gerará uma ordem de transferência planejada a partir do **Depósito principal**atribuído.</span><span class="sxs-lookup"><span data-stu-id="83a35-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="83a35-111">Se você desmarcar a caixa de seleção <STRONG>Reabastecimento</STRONG>, o depósito selecionado será atribuído a um nível de depósito em relação ao <STRONG>Depósito principal</STRONG>, mas o <STRONG>Depósito principal</STRONG> não está configurado como um depósito de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="83a35-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="83a35-112">Feche a página para aplicar a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="83a35-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="83a35-113">Se desejar atribuir um depósito para reabastecimento, você precisará primeiro configurar o depósito como uma dimensão de armazenamento na página <STRONG>Grupos de dimensão de armazenamento</STRONG></span><span class="sxs-lookup"><span data-stu-id="83a35-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="83a35-114">Nesta página, selecione o campo <STRONG>Ativar</STRONG> e o campo <STRONG>Plano de cobertura por dimensão</STRONG> para o depósito.</span><span class="sxs-lookup"><span data-stu-id="83a35-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="83a35-115">Configurar o prazo de entrega de transporte</span><span class="sxs-lookup"><span data-stu-id="83a35-115">Set up transport lead time</span></span>

<span data-ttu-id="83a35-116">Você também deve configurar o prazo de entrega de transporte entre os depósitos na página **Dias de transporte** .</span><span class="sxs-lookup"><span data-stu-id="83a35-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="83a35-117">Vá para **Gerenciamento de estoque > Configuração > Distribuição > Dias de transporte**.</span><span class="sxs-lookup"><span data-stu-id="83a35-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="83a35-118">No campo **Ponto de recebimento**, selecione **depósito**.</span><span class="sxs-lookup"><span data-stu-id="83a35-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="83a35-119">Selecione **Depósito da remessa**, **Depósito de recebimento** e **Dias de transporte**.</span><span class="sxs-lookup"><span data-stu-id="83a35-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="83a35-120">(Opcional) você também pode definir o tempo de transporte, dependendo do modo de entrega, na guia **Dias de transporte por modo de entrega** .</span><span class="sxs-lookup"><span data-stu-id="83a35-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
