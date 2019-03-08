---
title: Adicionar produtos de variante a ordens de compra usando pesos de variante
description: Este procedimento mostra as etapas para usar pesos de variante para preencher automaticamente as linhas da ordem de compra para cada variante de um produto.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 446260a09bd5177877637ac8a288ad584dfa2b2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "345481"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="50a37-103">Adicionar produtos de variante a ordens de compra usando pesos de variante</span><span class="sxs-lookup"><span data-stu-id="50a37-103">Add variant products to purchase orders using variant weights</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50a37-104">Este procedimento mostra as etapas para usar pesos de variante para preencher automaticamente as linhas da ordem de compra para cada variante de um produto.</span><span class="sxs-lookup"><span data-stu-id="50a37-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="50a37-105">Quando você seleciona a quantidade do produto que você deseja comprar, as linhas da ordem de compra são criadas para todas as variantes do produto com as quantidades sugeridas com base nos pesos configurados nas variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="50a37-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="50a37-106">Este procedimento não inclui etapas para configurar valores de peso nas dimensões do produto e nas variantes de produto.</span><span class="sxs-lookup"><span data-stu-id="50a37-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="50a37-107">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="50a37-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="50a37-108">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="50a37-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="50a37-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="50a37-109">Click New.</span></span>
3. <span data-ttu-id="50a37-110">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="50a37-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="50a37-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="50a37-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="50a37-112">Alternar a expansão da seção Geral.</span><span class="sxs-lookup"><span data-stu-id="50a37-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="50a37-113">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="50a37-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="50a37-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="50a37-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="50a37-115">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="50a37-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="50a37-116">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="50a37-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="50a37-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="50a37-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="50a37-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="50a37-118">Click OK.</span></span>
12. <span data-ttu-id="50a37-119">Ative a expansão da seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="50a37-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="50a37-120">Clique na guia Variantes.</span><span class="sxs-lookup"><span data-stu-id="50a37-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="50a37-121">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="50a37-121">Click Add line.</span></span>
15. <span data-ttu-id="50a37-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="50a37-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="50a37-123">No campo Número de item, digite '0140'.</span><span class="sxs-lookup"><span data-stu-id="50a37-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="50a37-124">Defina a quantidade como '1000'.</span><span class="sxs-lookup"><span data-stu-id="50a37-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="50a37-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="50a37-125">Click Save.</span></span>

