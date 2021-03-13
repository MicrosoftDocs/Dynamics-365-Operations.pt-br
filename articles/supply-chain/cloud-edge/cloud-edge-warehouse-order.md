---
title: Ordens de depósito para unidades de escala de nuvem e borda
description: Este tópico fornece informações sobre o recurso de ordem de depósito usado como parte da carga de trabalho da unidade de escala de depósito.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105692"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="a4a9f-103">Ordens de depósito para unidades de escala de nuvem e borda</span><span class="sxs-lookup"><span data-stu-id="a4a9f-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="a4a9f-104">Nem todas as funcionalidades comerciais têm suporte total na versão preliminar pública quando são usadas cargas de trabalho de unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="a4a9f-105">Se você estiver usando unidades de escala, certifique-se de usar somente esses processos descritos explicitamente por este tópico como aceitos.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="a4a9f-106">O que são ordens de depósito?</span><span class="sxs-lookup"><span data-stu-id="a4a9f-106">What are warehouse orders?</span></span>

<span data-ttu-id="a4a9f-107">As *ordens de depósito* são um tipo de ordem que foi criado para oferecer suporte a implantações de depósito e unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="a4a9f-108">Eles permitem que você receba estoque quando estiver executando uma carga de trabalho de depósito em uma unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="a4a9f-109">No momento, eles são usados com ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="a4a9f-110">As ordens de depósito são usadas como parte do processamento de gerenciamento de depósito, por exemplo, quando o aplicativo de depósito é usado para registrar o estoque físico disponível durante o processamento de uma ordem de compra de entrada.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="a4a9f-111">As ordens de depósito são criadas como parte do processo de *Liberação para depósito* que está disponível para ordens de compra que especificam um depósito de unidades de escala e itens habilitados para usar os processos de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4a9f-112">As ordens de depósito estão disponíveis somente em implantações que usam [cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="a4a9f-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="a4a9f-113">Criar uma ordem de depósito</span><span class="sxs-lookup"><span data-stu-id="a4a9f-113">Create a warehouse order</span></span>

<span data-ttu-id="a4a9f-114">Para criar uma ordem de depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="a4a9f-115">Entre na instância do Microsoft Dynamics 365 Supply Chain Management que está em execução no hub.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="a4a9f-116">(É necessário iniciar o processo *Liberar para o depósito* enquanto você estiver conectado no hub.)</span><span class="sxs-lookup"><span data-stu-id="a4a9f-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="a4a9f-117">Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="a4a9f-118">No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="a4a9f-119">Para exibir as linhas de ordem de depósito relacionadas, abra a ordem de compra relevante, selecione uma linha na seção **Linhas da ordem de compra** e, na barra de ferramentas, selecione **Depósito \> Linhas da ordem de depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="a4a9f-120">Para exibir todas as linhas, vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="a4a9f-121">Cancelar uma ordem de depósito</span><span class="sxs-lookup"><span data-stu-id="a4a9f-121">Cancel a warehouse order</span></span>

<span data-ttu-id="a4a9f-122">Como parte do processo *Liberar para o depósito*, as transações de estoque da ordem de compra são vinculadas a ordens de depósito e bloqueadas para serem atualizadas pelo hub.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="a4a9f-123">Se você liberou para o depósito por engano ou se tiver algum outro motivo para reverter a criação de linhas da ordem de depósito, poderá solicitar o cancelamento de linhas da ordem de depósito.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="a4a9f-124">Para cancelar linhas de uma ordem de depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="a4a9f-125">Entre na instância do Supply Chain Management que está em execução no hub.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="a4a9f-126">Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="a4a9f-127">Selecione a linha relevante.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-127">Select the relevant line.</span></span>
1. <span data-ttu-id="a4a9f-128">No painel de ações, selecione **Cancelar linhas da ordem de depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4a9f-129">A solicitação para cancelar linhas será negada para todas as linhas que já estiverem com cancelamento pendente ou que estiverem sendo processadas ativamente em um depósito que está executando sua carga de trabalho em uma unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="a4a9f-130">Monitorar uma ordem de depósito</span><span class="sxs-lookup"><span data-stu-id="a4a9f-130">Monitor a warehouse order</span></span>

<span data-ttu-id="a4a9f-131">Na exibição **Linhas da ordem de depósito**, você pode monitorar o andamento da remessa de entrada, revisando os valores na coluna **Quantidade restante para receber**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="a4a9f-132">Para exibir detalhes relacionados ao trabalho feito usando o aplicativo de depósito, siga uma destas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="a4a9f-133">Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito** e use o filtro para localizar as linhas que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="a4a9f-134">Vá para **Compras e fornecimento \> Ordens de compra \> Todas as ordens de compra** e abra a ordem de compra relevante.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="a4a9f-135">Na seção **Linhas da ordem de compra**, selecione uma ou mais linhas e, em seguida, na barra de ferramentas, selecione **Depósito \> Entradas de recebimento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="a4a9f-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
