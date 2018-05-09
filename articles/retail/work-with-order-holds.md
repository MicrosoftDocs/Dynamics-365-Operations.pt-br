---
title: Bloqueios da ordem
description: "Este tópico descreve os bloqueios de ordens usando o Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 106ce40f93704e67e53db2e62ae481d271aed755
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="order-holds"></a><span data-ttu-id="1b335-103">Bloqueios da ordem</span><span class="sxs-lookup"><span data-stu-id="1b335-103">Order holds</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1b335-104">Este tópico descreve os bloqueios de ordens usando o Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="1b335-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="1b335-105">Uma ordem pode ser colocada em espera por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="1b335-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="1b335-106">Por exemplo, você pode colocar uma ordem em espera até que o endereço do cliente ou o método de pagamento seja verificado ou até que um gerente possa revisar o limite de crédito do cliente.</span><span class="sxs-lookup"><span data-stu-id="1b335-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="1b335-107">Durante o processo de vendas, há momentos em que as ordens de venda devem ser colocadas em espera.</span><span class="sxs-lookup"><span data-stu-id="1b335-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="1b335-108">Por exemplo, uma ordem de venda pode ser colocada em espera devido a problemas com o pagamento do cliente, por suspeita de fraude ou porque um gerente deve analisar a ordem.</span><span class="sxs-lookup"><span data-stu-id="1b335-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="1b335-109">Quando uma ordem de venda é colocada em espera, um código de bloqueio da ordem é atribuído à ordem de venda para indicar o motivo do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="1b335-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="1b335-110">Os códigos de bloqueio da ordem de venda são configurados em **Vendas e marketing** &gt; **Configuração** &gt; **Ordens de venda** &gt; **Códigos de bloqueio de ordem**.</span><span class="sxs-lookup"><span data-stu-id="1b335-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="1b335-111">Uma ordem de venda pode ser colocada em espera manualmente no momento da criação da ordem ou posteriormente.</span><span class="sxs-lookup"><span data-stu-id="1b335-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="1b335-112">Além disso, uma ordem pode ser colocada em espera automaticamente, com base nas regras de fraude.</span><span class="sxs-lookup"><span data-stu-id="1b335-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="1b335-113">Enquanto uma ordem de venda estiver em espera, você possivelmente precisará atualizá-la com mais informações.</span><span class="sxs-lookup"><span data-stu-id="1b335-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="1b335-114">Se desejar, você poderá fazer o check-out da ordem de venda enquanto trabalha nela.</span><span class="sxs-lookup"><span data-stu-id="1b335-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="1b335-115">Você pode fazer o check-out de uma ordem de venda, fazer o check-in novamente e até mesmo substituir o check-out de outro usuário usando a bancada de bloqueio da ordem (**Varejo** &gt; **Clientes** &gt; **Bloqueios de ordem**).</span><span class="sxs-lookup"><span data-stu-id="1b335-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="1b335-116">Quando uma ordem estiver pronta para ser concluída, você deverá remover o bloqueio antes de poder concluir o processo da ordem.</span><span class="sxs-lookup"><span data-stu-id="1b335-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




