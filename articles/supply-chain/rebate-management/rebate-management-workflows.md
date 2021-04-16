---
title: Fluxos de trabalho de acordos de gerenciamento de reembolso
description: Este tópico explica como configurar um fluxo de trabalho de Acordo de gerenciamento de reembolso para aprovar e ativar acordos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831713"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="8f958-103">Fluxos de trabalho de acordos de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="8f958-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8f958-104">Para aprovar acordos de reembolso, o Gerenciamento de reembolso usa a mesma plataforma de fluxo de trabalho que outros aplicativos Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f958-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="8f958-105">Dois processos de trabalho estão associados a cada fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="8f958-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="8f958-106">Um elemento do fluxo de trabalho ativa o acordo para que o usuário ou processo de fluxo de trabalho possa aprovar as transações.</span><span class="sxs-lookup"><span data-stu-id="8f958-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="8f958-107">Um elemento do fluxo de trabalho aprova o acordo.</span><span class="sxs-lookup"><span data-stu-id="8f958-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="8f958-108">Para poder usar um acordo de reembolso, ele deve estar ativo no módulo **Gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="8f958-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="8f958-109">Para ativar um acordo, você deve primeiro criar e configurar um *Fluxo de trabalho de acordo de gerenciamento de reembolso*.</span><span class="sxs-lookup"><span data-stu-id="8f958-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="8f958-110">Após um fluxo de trabalho ser ativado para Gerenciamento de reembolso, os usuários não podem aprovar acordos manualmente.</span><span class="sxs-lookup"><span data-stu-id="8f958-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="8f958-111">O fluxo de trabalho deve ser sempre utilizado.</span><span class="sxs-lookup"><span data-stu-id="8f958-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="8f958-112">Criar e gerenciar fluxos de trabalho de Acordo de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="8f958-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="8f958-113">Para trabalhar com fluxos de trabalho de Acordo de gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração \> Fluxos de trabalho de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="8f958-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="8f958-114">Aqui você pode exibir, criar e atualizar fluxos de trabalho, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8f958-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="8f958-115">Só é possível ativar um fluxo de trabalho deste tipo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="8f958-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="8f958-116">Para obter mais informações sobre fluxos de trabalho, como trabalhar com a página **Fluxos de trabalho de gerenciamento de reembolso** e como criar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e os tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="8f958-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="8f958-117">Use um fluxo de trabalho para ativar um acordo</span><span class="sxs-lookup"><span data-stu-id="8f958-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="8f958-118">Para ativar um acordo por meio de um fluxo de trabalho, abra o acordo (por exemplo, na página **Todos os acordos de gerenciamento de reembolso**).</span><span class="sxs-lookup"><span data-stu-id="8f958-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="8f958-119">No Painel de Ações, selecione **Fluxo de trabalho \> Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8f958-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="8f958-120">Após o processamento e a aprovação do novo acordo pelo fluxo de trabalho, ele ficará ativo e pronto para ser usado.</span><span class="sxs-lookup"><span data-stu-id="8f958-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="8f958-121">Depois que um acordo for ativado, você não poderá alterar a configuração.</span><span class="sxs-lookup"><span data-stu-id="8f958-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="8f958-122">Se for necessário alterar um acordo ativo, desative-o e crie um novo acordo.</span><span class="sxs-lookup"><span data-stu-id="8f958-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="8f958-123">Se o novo acordo for parecido com o antigo, você poderá criá-lo copiando o acordo antigo.</span><span class="sxs-lookup"><span data-stu-id="8f958-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
