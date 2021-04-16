---
title: Configurar grupos de impostos e grupos de impostos do item
description: Esta tarefa de registro mostra a instalação do imposto sobre vendas e grupos de impostos sobre vendas do item.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 844eee7f81c64eb50ada44cbc151c8aa00c5ae98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815059"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="163e1-103">Configurar grupos de impostos e grupos de impostos do item</span><span class="sxs-lookup"><span data-stu-id="163e1-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="163e1-104">Esta tarefa de registro mostra a instalação do imposto sobre vendas e grupos de impostos sobre vendas do item.</span><span class="sxs-lookup"><span data-stu-id="163e1-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="163e1-105">Os grupos de imposto são grupos de códigos de imposto associados a clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="163e1-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="163e1-106">Eles também são associados a contas contábeis para transações que não são lançadas para um fornecedor ou cliente específico.</span><span class="sxs-lookup"><span data-stu-id="163e1-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="163e1-107">Os grupos de impostos sobre vendas do item são grupos de códigos de impostos sobre vendas associados aos recursos de produtos.</span><span class="sxs-lookup"><span data-stu-id="163e1-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="163e1-108">Os impostos aplicáveis a uma transação específica são determinados pelos códigos de imposto incluídos no grupo de impostos e no grupo de impostos do item da transação.</span><span class="sxs-lookup"><span data-stu-id="163e1-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="163e1-109">Os impostos poderão ser calculados somente se um grupo de impostos e um grupo de impostos do item estiverem selecionados para cada transação cujo imposto precisar ser calculado ou registrado.</span><span class="sxs-lookup"><span data-stu-id="163e1-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="163e1-110">Vá para **Painel de navegação > Módulos > Imposto > Impostos indiretos > Imposto > Grupos de imposto**.</span><span class="sxs-lookup"><span data-stu-id="163e1-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="163e1-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="163e1-111">Click **New**.</span></span>
3. <span data-ttu-id="163e1-112">No campo **Grupo de Impostos**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="163e1-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="163e1-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="163e1-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="163e1-114">Alternar a expansão da seção **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="163e1-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="163e1-115">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="163e1-115">Click **Add**.</span></span>
7. <span data-ttu-id="163e1-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="163e1-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="163e1-117">No campo **Código de imposto**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="163e1-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="163e1-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="163e1-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="163e1-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="163e1-119">Click **Save**.</span></span>
11. <span data-ttu-id="163e1-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="163e1-120">Close the page.</span></span>
12. <span data-ttu-id="163e1-121">Vá para **Imposto > Impostos indiretos > Impostos > Grupos de impostos**.</span><span class="sxs-lookup"><span data-stu-id="163e1-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="163e1-122">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="163e1-122">Click **New**.</span></span>
14. <span data-ttu-id="163e1-123">No campo **Grupo de Impostos de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="163e1-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="163e1-124">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="163e1-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="163e1-125">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="163e1-125">Click **Add**.</span></span>
17. <span data-ttu-id="163e1-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="163e1-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="163e1-127">No campo **Código de imposto**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="163e1-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="163e1-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="163e1-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="163e1-129">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="163e1-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]