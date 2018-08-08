---
title: "Cancelar ordens de serviço"
description: "É possível cancelar uma ordem de serviço ou uma linha de ordem de serviço na própria ordem, ou cancelar várias ordens de serviço executando um trabalho periódico."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1495fa139ea2c3cb7f2450b402126822f5549f60
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="cancel-service-orders"></a><span data-ttu-id="eb7f4-103">Cancelar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="eb7f4-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="eb7f4-104">É possível cancelar uma ordem de serviço ou uma linha de ordem de serviço na própria ordem, ou cancelar várias ordens de serviço executando um trabalho periódico.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="eb7f4-105">As ordens de serviço não podem ser canceladas se sua fase não permitir o cancelamento, se a ordem de serviço possuir requisitos de item ou se já tiver sido lançada.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="eb7f4-106">Cancelar uma ordem de serviço no formulário Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="eb7f4-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="eb7f4-107">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="eb7f4-108">Selecione a ordem de serviço e, no Painel de Ação, clique em **Cancelar ordem**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="eb7f4-109">Cancelar uma linha de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="eb7f4-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="eb7f4-110">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="eb7f4-111">Clique duas vezes na ordem de serviço que contém a linha que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="eb7f4-112">Selecione a linha da ordem de serviço que deseja cancelar e, em seguida, clique em **Cancelar linha de ordem** para alterar o status da linha para **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="eb7f4-113">Para reverter o cancelamento de uma linha de ordem de serviço e alterar o status novamente para <STRONG>Criado</STRONG>, clique em <STRONG>Revogar cancelamento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="eb7f4-114">Cancelar várias ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="eb7f4-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="eb7f4-115">Clique em **Gerenciamento de serviço** \> **Periódico** \> **Ordens de serviço** \> **Cancelar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="eb7f4-116">Clique no botão **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="eb7f4-117">No formulário **Consulta**, na coluna **Critérios**, selecione as ordens de serviço que deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="eb7f4-118">Clique em **OK** para fechar o formulário de **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="eb7f4-119">Marque a caixa de seleção **Mostrar Log de Informações** para gerar um Log de informações que lista as ordens de serviço canceladas.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="eb7f4-120">Marque a caixa de seleção **Revogar cancelamento** se quiser reverter o status **Cancelado** de uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="eb7f4-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-121">Click **OK**.</span></span>

<span data-ttu-id="eb7f4-122">As ordens de serviço selecionadas são canceladas ou seu status de progresso de **Cancelado** é revertido para **Em processo**.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="eb7f4-123">Se você marcar a caixa de seleção <STRONG>Revogar cancelamento</STRONG>, as ordens de serviço com um status de progresso de <STRONG>Cancelado</STRONG> são revertidas e as ordens de serviço com um status de progresso de <STRONG>Em processo</STRONG> não são canceladas.</span><span class="sxs-lookup"><span data-stu-id="eb7f4-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  



