---
title: "Executar atualizações de fatura para devoluções"
description: "Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa."
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
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---


# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="13a3e-103">Executar atualizações de fatura para devoluções</span><span class="sxs-lookup"><span data-stu-id="13a3e-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="13a3e-104">Uma ordem de devolução é um tipo de ordem de venda marcada como um Item Devolvido.</span><span class="sxs-lookup"><span data-stu-id="13a3e-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="13a3e-105">Portanto, a página de listagem de **Todas as ordens de venda** é usada para gerar faturas para ordens de devolução em vez do formulário de **Ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="13a3e-106">Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="13a3e-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="13a3e-107">Porque a fatura para um item devolvido é para um valor negativo, é chamada uma nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="13a3e-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="13a3e-108">Ao configurar a atualização da nota fiscal para processamento em lotes, a ordem de venda do tipo **Ordem devolvida** deve ter o status de linha de devolução **Recebido**, que indica que a guia de remessa da ordem foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="13a3e-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="13a3e-109">Lançar uma fatura para uma ordem de devolução</span><span class="sxs-lookup"><span data-stu-id="13a3e-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="13a3e-110">Clique em **Contas a receber** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="13a3e-111">Selecione uma ordem de venda para a qual **Ordem devolvida** é exibido no campo de **Tipo de ordem**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="13a3e-112">No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="13a3e-113">Na guia **Parâmetros**, marque a caixa de seleção **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="13a3e-114">Reveja as informações no formulário e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="13a3e-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="13a3e-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a3e-115">Click **OK**.</span></span> <span data-ttu-id="13a3e-116">Uma nota de crédito é lançada.</span><span class="sxs-lookup"><span data-stu-id="13a3e-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="13a3e-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="13a3e-117">See also</span></span>

[<span data-ttu-id="13a3e-118">Atualizações de guia de remessa para devoluções</span><span class="sxs-lookup"><span data-stu-id="13a3e-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  



