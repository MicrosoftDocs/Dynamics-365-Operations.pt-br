---
title: Configurar denominações de pagamento à vista para o PDV (ponto de venda)
description: Denominações de pagamento à vista para moedas e notas podem ser definidas no back office que será usado pelos caixas, vendedores e gerentes da loja no PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a34ae8084c0ad55221f4ab93eb8c6481fa8c4771
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606747"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="49b38-103">Configurar denominações de pagamento à vista para o PDV (ponto de venda)</span><span class="sxs-lookup"><span data-stu-id="49b38-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="49b38-104">Denominações de pagamento à vista para moedas e notas podem ser definidas no back office que será usado pelos caixas, vendedores e gerentes da loja no PDV.</span><span class="sxs-lookup"><span data-stu-id="49b38-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="49b38-105">Essas denominações podem ser usadas para ajudar na contagem de dinheiro para declarações de meios de pagamento no fim do dia ou para finalizar uma venda rapidamente.</span><span class="sxs-lookup"><span data-stu-id="49b38-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="49b38-106">Definir denominações</span><span class="sxs-lookup"><span data-stu-id="49b38-106">Define denominations</span></span>

<span data-ttu-id="49b38-107">As denominações são configuradas por loja na página **Configurar** \> **Declaração de caixa** da propriedade da loja.</span><span class="sxs-lookup"><span data-stu-id="49b38-107">The denominations are set up per store on the **Set up** \> **Cash declaration** option from the store property page.</span></span>

![Opção Declaração de caixa](./media/image1-denomination.png)

<span data-ttu-id="49b38-109">Para definir uma denominação:</span><span class="sxs-lookup"><span data-stu-id="49b38-109">To define a denomination:</span></span>

1. <span data-ttu-id="49b38-110">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="49b38-110">Click **New**.</span></span>
1. <span data-ttu-id="49b38-111">Especifique o tipo (moeda ou nota).</span><span class="sxs-lookup"><span data-stu-id="49b38-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="49b38-112">Especifique o valor.</span><span class="sxs-lookup"><span data-stu-id="49b38-112">Specify the amount (value).</span></span>

![Página Cédulas de declaração de valores em caixa](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="49b38-114">Configurar o perfil de funcionalidade</span><span class="sxs-lookup"><span data-stu-id="49b38-114">Configure the functionality profile</span></span>

<span data-ttu-id="49b38-115">Ao pagar em dinheiro no PDV, o usuário pode usar as denominações de nota para inserir rapidamente o valor pago pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="49b38-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="49b38-116">No perfil da funcionalidade, você pode configurar as duas opções para mostrar a denominação no PDV.</span><span class="sxs-lookup"><span data-stu-id="49b38-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="49b38-117">**Maior ou igual ao valor devido** – Por padrão, o PDV só mostrará as denominações de notas maiores do que o valor devido, permitindo o pagamento com um toque.</span><span class="sxs-lookup"><span data-stu-id="49b38-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="49b38-118">Por exemplo, se o valor devido fosse de US$ 7,50, o PDV mostraria as seguintes denominações: US$ 10, US$ 20, US$ 50 e US$ 100.</span><span class="sxs-lookup"><span data-stu-id="49b38-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="49b38-119">Ao tocar em qualquer um desses valores, o pagamento será feito automaticamente para esse valor.</span><span class="sxs-lookup"><span data-stu-id="49b38-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="49b38-120">As notas de US$ 1 e US$ 5 não são mostradas, pois esses valores são menores que o valor devido.</span><span class="sxs-lookup"><span data-stu-id="49b38-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="49b38-121">**Todas as denominações** – Selecione esta opção para sempre mostrar todas as denominações de notas em PDV, seja qual for o valor devido.</span><span class="sxs-lookup"><span data-stu-id="49b38-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="49b38-122">Isso significa que o usuário poderá usar uma combinação de notas para atingir o valor devido.</span><span class="sxs-lookup"><span data-stu-id="49b38-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="49b38-123">Por exemplo, se o valor devido for US$ 25,00, o usuário poderá usar notas de US$ 20 e US$ 5 para concluir a venda.</span><span class="sxs-lookup"><span data-stu-id="49b38-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
