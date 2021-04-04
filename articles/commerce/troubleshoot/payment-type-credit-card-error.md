---
title: Erro O tipo de pagamento deve ser cartão de crédito na página ordem de venda
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585196"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="67b75-103">O erro "O tipo de pagamento deve ser cartão de crédito" na página ordem de venda</span><span class="sxs-lookup"><span data-stu-id="67b75-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="67b75-104">Este tópico fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.</span><span class="sxs-lookup"><span data-stu-id="67b75-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="67b75-105">descrição</span><span class="sxs-lookup"><span data-stu-id="67b75-105">Description</span></span>

<span data-ttu-id="67b75-106">Ao abrir a página ordem de venda após a sincronização de uma ordem, você recebe a seguinte mensagem de erro: "O tipo de pagamento deve ser cartão de crédito, pois o número do cartão de crédito foi especificado".</span><span class="sxs-lookup"><span data-stu-id="67b75-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Erro O tipo de pagamento deve ser cartão de crédito](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="67b75-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="67b75-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="67b75-109">Definir o tipo de pagamento no Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="67b75-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="67b75-110">Vá para **Contas a receber \> Configuração de pagamento \> Termos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="67b75-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="67b75-111">Na navegação à esquerda, selecione as condições de pagamento.</span><span class="sxs-lookup"><span data-stu-id="67b75-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="67b75-112">No campo **Tipo de pagamento**, verifique se **Cartão de crédito** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="67b75-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67b75-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="67b75-113">Additional resources</span></span>

[<span data-ttu-id="67b75-114">Lançamento de vendas e pagamentos online</span><span class="sxs-lookup"><span data-stu-id="67b75-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
