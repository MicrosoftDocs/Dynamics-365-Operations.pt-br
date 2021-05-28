---
title: Funcionalidade de divisão de fatura
description: Este tópico descreve a configuração e a funcionalidade para dividir faturas por endereço de entrega e número de conta de imposto (TAN).
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
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023033"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="46592-103">Funcionalidade de divisão de fatura</span><span class="sxs-lookup"><span data-stu-id="46592-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46592-104">Este tópico descreve a configuração e a funcionalidade para dividir faturas por endereço de entrega e número de conta de imposto (TAN).</span><span class="sxs-lookup"><span data-stu-id="46592-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="46592-105">Na página **Parâmetros de contas a pagar**, na guia **Geral** , marque a caixa de seleção **Recebimento de produtos** ou **Fatura** para lançar e dividir um recibo de produto ou fatura que tenha endereços de entrega e TANs diferentes na página **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="46592-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="46592-106">A fatura lançada será dividida por endereço de entrega e TAN.</span><span class="sxs-lookup"><span data-stu-id="46592-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="46592-107">Na guia **Atualização resumida**, na FastTab **Divisão baseada em**, na linha **Informações de entrega**, defina a opção **Confirmação**, **Lista de separação**, **Guia de remessa** ou **Fatura** como **Sim** para lançar e dividir uma confirmação, lista de separação, guia de remessa ou fatura onde diferentes endereços de entrega e TANs são definidos para diferentes faturas linhas na página **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="46592-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="46592-108">A fatura será dividida primeiro por endereço de entrega e depois por TAN.</span><span class="sxs-lookup"><span data-stu-id="46592-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="46592-109">Se nenhuma opção para **Informações de entrega** for definida como **Sim**, a fatura será lançada como uma única fatura.</span><span class="sxs-lookup"><span data-stu-id="46592-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="46592-110">Nenhuma divisão de fatura ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="46592-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="46592-111">Para dividir e lançar uma guia de remessa onde as linhas da fatura têm endereços de entrega e TANs diferentes, você deve definir a opção **Guia de remessa** de **Informações de entrega** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="46592-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="46592-112">Para dividir e lançar uma fatura onde as linhas da fatura têm endereços de entrega e TANs diferentes, você deve definir a opção **Fatura** de **Informações de entrega** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="46592-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="46592-113">Para lançar uma fatura onde as linhas da fatura têm endereços de entrega diferentes, mas o mesmo TAN, você deve definir a opção **Fatura** de **Informações de entrega** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="46592-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="46592-114">A fatura será dividida por endereço de entrega.</span><span class="sxs-lookup"><span data-stu-id="46592-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="46592-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="46592-115">Example</span></span>

<span data-ttu-id="46592-116">Neste exemplo, a opção **Fatura** de **Informações de entrega** é definida como **Sim** na guia **Atualização resumida** da página **Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="46592-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="46592-117">Uma fatura de compra é lançada com a seguinte configuração para endereços de entrega e TANs nas linhas:</span><span class="sxs-lookup"><span data-stu-id="46592-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="46592-118">**Linha de item 1:** endereço de entrega 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="46592-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="46592-119">**Linha de item 2:** endereço de entrega 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="46592-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="46592-120">**Linha de item 3:** endereço de entrega 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="46592-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="46592-121">**Linha de item 4:** endereço de entrega 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="46592-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="46592-122">Nesse caso, a fatura original é dividida em duas faturas e lançada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="46592-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="46592-123">A fatura 1 é lançada para a linha de item 1 e linha de item 2, porque ambas as linhas têm o mesmo endereço de entrega e TAN.</span><span class="sxs-lookup"><span data-stu-id="46592-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="46592-124">A fatura 2 é lançada para a linha de item 3.</span><span class="sxs-lookup"><span data-stu-id="46592-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="46592-125">A fatura 3 é lançada para a linha de item 4.</span><span class="sxs-lookup"><span data-stu-id="46592-125">Invoice 3 is posted for item line 4.</span></span>
