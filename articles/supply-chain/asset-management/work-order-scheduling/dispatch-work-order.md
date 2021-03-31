---
title: Expedir ordem de serviço
description: Este tópico explica como expedir uma ordem de serviço no Gerenciamento de Ativo.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cd9965ec8f3c3ff58f16b53abc8b9b114444946d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215001"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="aa5a7-103">Expedir ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="aa5a7-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="aa5a7-104">Você pode agendar uma ordem de serviço ou trabalhos de ordem de serviço para um trabalhador usando a funcionalidade **Expedir**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="aa5a7-105">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="aa5a7-106">Selecione a ordem de serviço na lista.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="aa5a7-107">Na guia **Geral**, clique em **Expedir**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="aa5a7-108">No diálogo **Agendar ordem de serviço**, selecione o trabalhador no campo **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="aa5a7-109">No campo **Agendar horas**, é possível inserir as horas de trabalho esperadas caso estas sejam diferentes das horas previstas.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="aa5a7-110">No campo **Início programado**, é possível editar a data e hora de início, se necessário.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="aa5a7-111">Se o processo de agendamento respeitar as limitações de capacidade em relação aos recursos já agendados em outros trabalhos, verifique se os botões de alternância **Ativo**, **Ferramenta** e **Trabalhador** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="aa5a7-112">Se você quiser ver informações detalhadas sobre o processo de agendamento, selecione **Sim** no botão de alternância **Detalhado**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="aa5a7-113">Isso significa que informações detalhadas sobre as pontuações calculadas na ordem de serviço são mostradas no Log de Informações.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="aa5a7-114">Selecione **Sim** no botão de alternância **Ignorar agendamento** para ignorar os dias fechados no calendário (aplica-se a ativos, trabalhadores e ferramentas).</span><span class="sxs-lookup"><span data-stu-id="aa5a7-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="aa5a7-115">Selecione **Sim** no botão de alternância **Ignorar execução agendada** para ignorar as limitações que podem ter sido selecionadas na ordem de serviço referente ao agendamento.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="aa5a7-116">Para obter informações sobre a configuração da execução agendada, consulte a seção [Execução agendada](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="aa5a7-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="aa5a7-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-117">Click **OK**.</span></span> <span data-ttu-id="aa5a7-118">O estado de ciclo de vida da ordem de serviço é atualizado automaticamente para o estado de ciclo de vida **Agendado** especificado em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Modelos de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="aa5a7-119">A figura abaixo mostra um exemplo de seleções de expedição na caixa de diálogo **Agendar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Figura 1](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="aa5a7-121">Se você deseja excluir o agendamento de uma ordem de serviço, selecione a ordem de serviço em **Todas as ordens de serviço** e, em seguida, clique em **Excluir agenda** na guia **Geral**. Lembre-se de atualizar manualmente o estado de ciclo de vida da ordem de serviço se você excluir o agendamento.</span><span class="sxs-lookup"><span data-stu-id="aa5a7-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]