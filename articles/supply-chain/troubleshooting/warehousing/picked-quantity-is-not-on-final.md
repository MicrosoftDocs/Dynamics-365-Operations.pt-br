---
title: Não é possível confirmar uma remessa porque os itens não foram separados
description: Não é possível confirmar uma remessa porque os itens não foram separados
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301296"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="85425-103">Não é possível confirmar uma remessa porque os itens não foram separados</span><span class="sxs-lookup"><span data-stu-id="85425-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="85425-104">Código de erro: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="85425-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="85425-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="85425-105">Symptoms</span></span>

<span data-ttu-id="85425-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="85425-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="85425-107">Alguns dos itens necessários para carregar %1 ainda não foram separados e movidos para a localização de remessa final.</span><span class="sxs-lookup"><span data-stu-id="85425-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="85425-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="85425-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="85425-109">Causa</span><span class="sxs-lookup"><span data-stu-id="85425-109">Cause</span></span>

<span data-ttu-id="85425-110">A carga ou a remessa não pode ser confirmada no estado atual porque pode existir uma das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="85425-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="85425-111">O trabalho relacionado ainda não foi separado e movido para o local de remessa final.</span><span class="sxs-lookup"><span data-stu-id="85425-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="85425-112">A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="85425-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="85425-113">A diretiva de localização foi configurada com o local de embalagem como o local final de envio enquanto usa o modelo de conteinerização em ciclo.</span><span class="sxs-lookup"><span data-stu-id="85425-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="85425-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="85425-114">Resolution</span></span>

<span data-ttu-id="85425-115">A carga ou a remessa estão em um estado no qual a confirmação de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="85425-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="85425-116">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="85425-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="85425-117">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="85425-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="85425-118">Cancele os IDs de trabalho que foram criados com a localização de embalagem como o local final de envio, reconfigure a diretiva de localização e libere a carga novamente.</span><span class="sxs-lookup"><span data-stu-id="85425-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="85425-119">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem</span><span class="sxs-lookup"><span data-stu-id="85425-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="85425-120">Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="85425-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="85425-121">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="85425-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="85425-122">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="85425-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="85425-123">Na FastTab **Linhas de carga**, selecione a linha de carga.</span><span class="sxs-lookup"><span data-stu-id="85425-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="85425-124">Anote o valor do campo **Quantidade de trabalho criado**.</span><span class="sxs-lookup"><span data-stu-id="85425-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="85425-125">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="85425-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="85425-126">Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="85425-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="85425-127">Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="85425-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="85425-128">Cancele os IDs de trabalho que foram criados com a localização de embalagem como o local final de envio, reconfigure a diretiva de localização e libere a carga novamente</span><span class="sxs-lookup"><span data-stu-id="85425-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="85425-129">Use o procedimento a seguir para cancelar os IDs de trabalho que possuem o local de embalagem como o local final de colocação com contêiner automatizado no local.</span><span class="sxs-lookup"><span data-stu-id="85425-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="85425-130">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="85425-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="85425-131">A caixa de diálogo **cancelar trabalho** é aberta.</span><span class="sxs-lookup"><span data-stu-id="85425-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="85425-132">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="85425-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="85425-133">O ID de trabalho selecionado deve ter um valor **Status de trabalho** de *Aberto*, *Em andamento* *Cancelado*, *Combinado* ou *Fechado*.</span><span class="sxs-lookup"><span data-stu-id="85425-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="85425-134">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="85425-134">Select **OK**.</span></span>
1. <span data-ttu-id="85425-135">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="85425-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="85425-136">Repita este procedimento para as outras IDs de trabalho conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="85425-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="85425-137">Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="85425-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="85425-138">Use o procedimento a seguir para reconfigurar a diretiva de localização para que ela não use o local de embalagem como local final de envio quando a conteinerização automatizada for configurada para o modelo de ciclo.</span><span class="sxs-lookup"><span data-stu-id="85425-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="85425-139">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="85425-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="85425-140">No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="85425-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="85425-141">Selecione a diretiva de localização que você está usando para a conteinerização automatizada.</span><span class="sxs-lookup"><span data-stu-id="85425-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="85425-142">Na barra de ferramentas da FastTab **Ações de diretiva de localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="85425-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="85425-143">Na caixa de diálogo do editor de consulta, na guia **Intervalo**, encontre a linha em que **Campo** esteja definida para o *Perfil de localização* e verifique se o campo **Critérios** para essa linha não está definido como um perfil de localização que tenha um **Tipo de localização** de *Embalagem*.</span><span class="sxs-lookup"><span data-stu-id="85425-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="85425-144">Ajuste o campo **Critérios** para corrigir o local final da colocação.</span><span class="sxs-lookup"><span data-stu-id="85425-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="85425-145">Use o procedimento a seguir para relançar a carga e criar IDs de trabalho com o local de envio final correto.</span><span class="sxs-lookup"><span data-stu-id="85425-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="85425-146">Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="85425-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="85425-147">Na seção **Cargas**, encontre a carga que precisa ser liberada.</span><span class="sxs-lookup"><span data-stu-id="85425-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="85425-148">Na barra de ferramentas da seção **Cargas**, selecione **Liberar \> Liberar para depósito** para liberar a carga selecionada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="85425-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="85425-149">Repita este procedimento para as outras cargas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="85425-149">Repeat this procedure for the other loads as needed.</span></span>
