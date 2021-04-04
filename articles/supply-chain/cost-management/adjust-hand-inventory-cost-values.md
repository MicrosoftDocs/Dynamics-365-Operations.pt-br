---
title: Ajustar valores de custo de estoque disponível
description: Use a página Ajuste de estoque disponível para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66323e99c04a141aa5dc5ab828e0e261c61b83ce
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254326"
---
# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="3b0e0-103">Ajustar valores de custo de estoque disponível</span><span class="sxs-lookup"><span data-stu-id="3b0e0-103">Adjust on-hand inventory cost values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b0e0-104">Use a página Ajuste de estoque disponível para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="3b0e0-105">Você pode usar a página **Ajuste de estoque disponível** para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="3b0e0-106">**Observação:** para abrir a página **Ajuste de estoque disponível**, na página **Fechamento e ajuste**, selecione o registro de um processo de fechamento de estoque concluído e clique em **Ajuste** &gt; **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="3b0e0-107">**Exemplo:** você tem estas transações em fevereiro:</span><span class="sxs-lookup"><span data-stu-id="3b0e0-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="3b0e0-108">1º de fevereiro: um recebimento financeiro de estoque para uma quantidade de 2 a um custo de BRL 10,00</span><span class="sxs-lookup"><span data-stu-id="3b0e0-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="3b0e0-109">5 de fevereiro: um recebimento financeiro de estoque para uma quantidade de 1 a um custo de BRL 13,00</span><span class="sxs-lookup"><span data-stu-id="3b0e0-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="3b0e0-110">19 fevereiro: uma saída financeira de estoque para uma quantidade igual a 1 a um custo médio em execução de R$ 11,00</span><span class="sxs-lookup"><span data-stu-id="3b0e0-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="3b0e0-111">Esse item foi configurado com o modelo de estoque PEPS (primeiro a entrar, primeiro a sair), e o fechamento do estoque foi feito em 28 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="3b0e0-112">A transação de saída financeira de R$ 11,00 será liquidada no recebimento financeiro datado de 1º de fevereiro e será feito um ajuste de R$ 1,00.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="3b0e0-113">Os seguintes recebimentos de estoque conterão, assim, quantidades de estoque em aberto:</span><span class="sxs-lookup"><span data-stu-id="3b0e0-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="3b0e0-114">1º de fevereiro: uma quantidade igual a 1 a um custo de R$ 10,00</span><span class="sxs-lookup"><span data-stu-id="3b0e0-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="3b0e0-115">5 de fevereiro: uma quantidade igual a 1 a um custo de R$ 13,00</span><span class="sxs-lookup"><span data-stu-id="3b0e0-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="3b0e0-116">Para definir o custo desses dois itens como BRL 15,00, use a opção de ajuste disponível para ajustar as quantidades disponíveis em aberto no último período de fechamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="3b0e0-117">**Observação:** a data de lançamento da transação de ajuste disponível será a data do último fechamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="3b0e0-118">Essa data não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="3b0e0-118">This date can't be modified.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]