---
title: Cálculo do TDS em transações entre empresas
description: Este tópico descreve o processo usado para calcular o Imposto Deduzido na Origem (TDS) em transações entre empresas em fases.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023031"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="c5409-103">Cálculo do TDS em transações entre empresas</span><span class="sxs-lookup"><span data-stu-id="c5409-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5409-104">Este tópico descreve o processo usado para calcular o Imposto Deduzido na Origem (TDS) em transações entre empresas em fases.</span><span class="sxs-lookup"><span data-stu-id="c5409-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="c5409-105">Quando uma ordem de compra ou venda entre empresas é criada, o grupo de TDS padrão definido para o cliente ou fornecedor é usado para calcular o valor do TDS.</span><span class="sxs-lookup"><span data-stu-id="c5409-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="c5409-106">O valor do TDS é lançado nas contas a recuperar ou a pagar após o lançamento da fatura.</span><span class="sxs-lookup"><span data-stu-id="c5409-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="c5409-107">Uma ordem de venda ou compra entre empresas é criada automaticamente para a ordem de compra ou venda original.</span><span class="sxs-lookup"><span data-stu-id="c5409-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="c5409-108">O grupo de TDS padrão é mostrado na ordem entre empresas para que o TDS possa ser calculado.</span><span class="sxs-lookup"><span data-stu-id="c5409-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="c5409-109">Você pode alterar o grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="c5409-109">You can change the TDS group.</span></span> <span data-ttu-id="c5409-110">A fatura pode ser lançada apenas se o valor líquido da fatura no pedido entre companhias criado automaticamente corresponder ao valor líquido da fatura na ordem original.</span><span class="sxs-lookup"><span data-stu-id="c5409-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="c5409-111">(O valor líquido é o valor da fatura após a dedução do TDS.)</span><span class="sxs-lookup"><span data-stu-id="c5409-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="c5409-112">Por exemplo, uma fatura de venda é criada para 50.000 e o grupo de TDS de **10%** é anexado a ela.</span><span class="sxs-lookup"><span data-stu-id="c5409-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="c5409-113">O valor da fatura lançada é 45.000 e o valor do TDS lançado para a nota fiscal de venda é 5.000.</span><span class="sxs-lookup"><span data-stu-id="c5409-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="c5409-114">Uma ordem de compra é criada automaticamente para a ordem de venda entre empresas e o grupo de TDS de **10%** é anexado a ela.</span><span class="sxs-lookup"><span data-stu-id="c5409-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="c5409-115">Se você alterar o grupo de TDS para **15%**, não poderá lançar a fatura, porque o valor líquido da fatura da ordem de venda entre empresas que foi criado automaticamente não corresponde ao valor líquido da fatura da ordem de venda original.</span><span class="sxs-lookup"><span data-stu-id="c5409-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="c5409-116">Um diário de pagamento criado para uma fatura entre empresas é lançado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c5409-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="c5409-117">Esse diário de pagamentos pode ser lançado apenas se o valor do pagamento líquido nele corresponder ao valor do pagamento líquido no diário de pagamentos original.</span><span class="sxs-lookup"><span data-stu-id="c5409-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
