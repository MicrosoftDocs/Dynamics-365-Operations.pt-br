---
title: Marcação de estoque com a Otimização de Planejamento
description: Este tópico fornece informações sobre as opções disponíveis para marcar estoque em ordens confirmadas ao usar a Otimização de Planejamento.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 3b139673ddf17e13d6687db485208e1aeb3908dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809485"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="bd1b3-103">Marcação de estoque com a Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="bd1b3-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd1b3-104">Este tópico fornece informações sobre as opções disponíveis para marcar estoque em ordens confirmadas ao usar a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="bd1b3-105">A *marcação* é usada para vincular fornecimento e demanda.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="bd1b3-106">Ela é semelhante à *vinculação*, que indica como o planejamento mestre espera cobrir a demanda.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="bd1b3-107">Do ponto de vista de planejamento, a principal diferença é que a marcação é mais permanente do que a vinculação.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="bd1b3-108">A marcação foi introduzida para oferecer suporte a cenários de avaliação de custo especiais para PEPS (primeiro a entrar, primeiro a sair) e UEPS (último a entrar, primeiro a sair).</span><span class="sxs-lookup"><span data-stu-id="bd1b3-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="bd1b3-109">No entanto, agora também é usada para alguns cenários não relacionados à avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="bd1b3-110">A marcação entre fornecimento e demanda é opcional e quase permanente.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="bd1b3-111">Ela pode ser removida manualmente por um usuário ou pode ser removida executando um detalhamento de linha da ordem de venda em que a opção **Remover marcação** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="bd1b3-112">A vinculação é controlada pelo planejamento mestre durante a cobertura para vincular a demanda ao fornecimento necessário.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="bd1b3-113">Ela pode ser atualizada para cada execução de planejamento a fim de otimizar o fornecimento necessário para cobrir a demanda.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="bd1b3-114">Quando o planejamento mestre atualiza as informações de vinculação, ele respeita todas as marcações existentes.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="bd1b3-115">A vinculação começa incluindo marcação relevante, reservas disponíveis e reservas sob encomenda, na seguinte sequência:</span><span class="sxs-lookup"><span data-stu-id="bd1b3-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="bd1b3-116">Marcação entre demanda e fornecimento</span><span class="sxs-lookup"><span data-stu-id="bd1b3-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="bd1b3-117">Reservas disponíveis</span><span class="sxs-lookup"><span data-stu-id="bd1b3-117">On-hand reservations</span></span>
1. <span data-ttu-id="bd1b3-118">Reservas sob encomenda</span><span class="sxs-lookup"><span data-stu-id="bd1b3-118">On-order reservations</span></span>

<span data-ttu-id="bd1b3-119">Quando você confirma uma ordem planejada, a caixa de diálogo **Confirmação** fornece um campo **Atualizar marcação** que é usado para definir as opções de marcação para as ordens criadas durante a confirmação.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="bd1b3-120">Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bd1b3-120">Select one of the following values:</span></span>

- <span data-ttu-id="bd1b3-121">**Não** – Nenhuma marcação de estoque é aplicada.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="bd1b3-122">**Padrão** – A marcação de estoque é atualizada de acordo com a vinculação.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="bd1b3-123">Uma ordem de necessidade (demanda) é marcada em relação a uma ordem de atendimento (fornecimento).</span><span class="sxs-lookup"><span data-stu-id="bd1b3-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="bd1b3-124">Se alguma quantidade permanecer na ordem de atendimento, ela não será marcada, e as informações de referência serão deixadas em branco.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="bd1b3-125">Por exemplo, se uma ordem de venda para 100 ea for vinculada a uma ordem de compra para 150 ea, as informações de referência serão atribuídas somente à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="bd1b3-126">**Estendido** – Tanto a ordem de necessidade (demanda) quanto a de atendimento (fornecimento) são marcadas, independentemente de qualquer quantidade restante na ordem de atendimento.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="bd1b3-127">Por exemplo, se uma ordem de venda para 100 ea for vinculada a uma ordem de compra para 150 ea, as informações de referência serão atribuídas à ordem de venda e à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="bd1b3-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]