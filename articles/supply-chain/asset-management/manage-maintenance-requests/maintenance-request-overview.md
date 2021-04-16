---
title: Solicitações de manutenção
description: Este tópico fornece uma visão geral sobre o gerenciamento de solicitações de manutenção no Asset Management
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dceb179d0a17d8025d88c5945b9571de65c86449
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838601"
---
# <a name="maintenance-requests"></a><span data-ttu-id="0ae40-103">Solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="0ae40-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0ae40-104">As solicitações de manutenção são anotações ou declarações criadas para notificar um gerente ou planejador de que um ativo pode exigir um trabalho de manutenção ou de reparo, mas sem a criação de uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0ae40-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="0ae40-105">Se o conteúdo de uma solicitação de manutenção for considerado válido, uma ordem de serviço será criada com base na solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="0ae40-106">As solicitações de serviço podem ser criadas para qualquer ativo no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="0ae40-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="0ae40-107">Diversos tipos de solicitações de serviço podem ser criados, dependendo de como sua empresa usa solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="0ae40-108">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="0ae40-108">Here are some examples:</span></span>

- <span data-ttu-id="0ae40-109">Solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="0ae40-109">Maintenance requests</span></span>
- <span data-ttu-id="0ae40-110">Observação</span><span class="sxs-lookup"><span data-stu-id="0ae40-110">Notes</span></span>
- <span data-ttu-id="0ae40-111">Correções ou aprimoramentos</span><span class="sxs-lookup"><span data-stu-id="0ae40-111">Corrections or enhancements</span></span>
- <span data-ttu-id="0ae40-112">Investimentos</span><span class="sxs-lookup"><span data-stu-id="0ae40-112">Investments</span></span>
- <span data-ttu-id="0ae40-113">Reparo de depósito (esse tipo é usado quando você recebe ativos de outro local para efetuar um trabalho de manutenção ou de reparo e então devolve o ativo após a conclusão do trabalho).</span><span class="sxs-lookup"><span data-stu-id="0ae40-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="0ae40-114">Exibir solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="0ae40-114">View maintenance requests</span></span>

<span data-ttu-id="0ae40-115">Para exibir solicitações de manutenção, selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção**, **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**.</span><span class="sxs-lookup"><span data-stu-id="0ae40-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="0ae40-116">Cada página de listagem mostra algumas das informações relacionadas a uma solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Exibir solicitações de manutenção](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="0ae40-118">Use a página de listagem **Minhas solicitações de manutenção de local funcional** para exibir uma lista de solicitações de manutenção que contenham um ou mais locais funcionais aos quais você está relacionado como trabalhador ou ativos instalados em locais funcionais aos quais você está relacionado como trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0ae40-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="0ae40-119">Para obter informações sobre como configurar locais funcionais em funcionários de manutenção, consulte [Funcionários de manutenção e grupos de funcionários](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0ae40-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="0ae40-120">Embora as informações de conta de cliente estejam disponíveis no Asset Service Management (manutenção externa), elas não estão disponíveis no Asset Management (manutenção interna).</span><span class="sxs-lookup"><span data-stu-id="0ae40-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="0ae40-121">Para abrir a exibição de detalhes de um registro, na página de listagem **Todas as solicitações de manutenção**, na exibição de grade, selecione um link na coluna **Solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="0ae40-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Exibição de detalhes da solicitação de manutenção](media/02-manage-maintenance-requests.png)

<span data-ttu-id="0ae40-123">Os botões no Painel de Ação estão organizados em guias.</span><span class="sxs-lookup"><span data-stu-id="0ae40-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="0ae40-124">A tabela a seguir descreve brevemente os botões relacionados ao Asset Management.</span><span class="sxs-lookup"><span data-stu-id="0ae40-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="0ae40-125">Nome do botão</span><span class="sxs-lookup"><span data-stu-id="0ae40-125">Button name</span></span>                      | <span data-ttu-id="0ae40-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ae40-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="0ae40-127">Edição</span><span class="sxs-lookup"><span data-stu-id="0ae40-127">Edit</span></span>                             | <span data-ttu-id="0ae40-128">Edite a solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-129">Novos</span><span class="sxs-lookup"><span data-stu-id="0ae40-129">New</span></span>                              | <span data-ttu-id="0ae40-130">Crie uma nova solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="0ae40-131">Excluir</span><span class="sxs-lookup"><span data-stu-id="0ae40-131">Delete</span></span>                           | <span data-ttu-id="0ae40-132">Exclua a solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-133">Grupo de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="0ae40-133">Work order pool</span></span>                  | <span data-ttu-id="0ae40-134">Conecte a solicitação de manutenção selecionada a um grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="0ae40-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="0ae40-135">Ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="0ae40-135">Work order</span></span>                       | <span data-ttu-id="0ae40-136">Crie uma ordem de serviço com base na solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-137">Falha do ativo</span><span class="sxs-lookup"><span data-stu-id="0ae40-137">Asset fault</span></span>                      | <span data-ttu-id="0ae40-138">Clique em **Falhas de ativo**, onde você poderá criar um registro de falha sobre a solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-139">Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="0ae40-139">Work orders</span></span>                      | <span data-ttu-id="0ae40-140">Mostre uma lista de todas as ordens de serviço conectadas à solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-141">Atualizar o estado da solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="0ae40-141">Update maintenance request state</span></span> | <span data-ttu-id="0ae40-142">Atualize o estado da solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ae40-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="0ae40-143">Log de estados de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="0ae40-143">Lifecycle state log</span></span>              | <span data-ttu-id="0ae40-144">Exiba um log que mostre os estados de ciclo de vida de solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-145">Detalhes da solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="0ae40-145">Maintenance request details</span></span>      | <span data-ttu-id="0ae40-146">Imprima um relatório que mostre detalhes da solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-147">Enviar ativo de empréstimo</span><span class="sxs-lookup"><span data-stu-id="0ae40-147">Send loan asset</span></span>                  | <span data-ttu-id="0ae40-148">Selecione um ativo de empréstimo que deve ser uma substituição temporária para o ativo selecionado na solicitação de manutenção selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ae40-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="0ae40-149">Devolver o ativo de empréstimo</span><span class="sxs-lookup"><span data-stu-id="0ae40-149">Return loan asset</span></span>                | <span data-ttu-id="0ae40-150">Registre o ativo de empréstimo como devolvido.</span><span class="sxs-lookup"><span data-stu-id="0ae40-150">Register the loan asset as returned.</span></span> |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]