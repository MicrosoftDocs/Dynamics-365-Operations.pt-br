--- 
title: "Configurar códigos de imposto"
description: "Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c8f1eea5e257ccb8f2e7fe900e2c8c68bdd5148f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="90dd0-103">Configurar códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="90dd0-103">Set up sales tax codes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90dd0-104">Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="90dd0-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="90dd0-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="90dd0-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="90dd0-106">Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Códigos de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="90dd0-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="90dd0-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="90dd0-107">Click New.</span></span>
3. <span data-ttu-id="90dd0-108">No campo Impostos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="90dd0-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="90dd0-109">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="90dd0-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="90dd0-110">Selecione um período de liquidação para especificar em que a autoridade de impostos sobre vendas e em intervalos que esses impostos sobre vendas precisem ser informado e pago.</span><span class="sxs-lookup"><span data-stu-id="90dd0-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="90dd0-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="90dd0-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="90dd0-112">Selecione um grupo de lançamentos contábeis para especificar as contas principais para lançar impostos sobre vendas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="90dd0-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="90dd0-113">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="90dd0-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="90dd0-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="90dd0-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="90dd0-115">Expanda a Guia Rápida Cálculo.</span><span class="sxs-lookup"><span data-stu-id="90dd0-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="90dd0-116">O cálculo FastTab têm vários campos que controlam como os valores do imposto sobre vendas será calculado.</span><span class="sxs-lookup"><span data-stu-id="90dd0-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="90dd0-117">No Painel de Ação, clique em Código de impostos de vendas.</span><span class="sxs-lookup"><span data-stu-id="90dd0-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="90dd0-118">Clique em Valores.</span><span class="sxs-lookup"><span data-stu-id="90dd0-118">Click Values.</span></span>
13. <span data-ttu-id="90dd0-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="90dd0-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="90dd0-120">Insira o valor para este código de imposto.</span><span class="sxs-lookup"><span data-stu-id="90dd0-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="90dd0-121">No cálculo FastTab, no campo de origem, se o valor da unidade for selecionado, o valor será multiplicado pela quantidade da transação para calcular o valor do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="90dd0-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="90dd0-122">Se o código de imposto não for um imposto baseado na unidade, o valor é uma porcentagem que é aplicada na origem para a qual esse código de imposto calcula o valor do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="90dd0-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="90dd0-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="90dd0-123">Click Save.</span></span>
16. <span data-ttu-id="90dd0-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="90dd0-124">Close the page.</span></span>
17. <span data-ttu-id="90dd0-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="90dd0-125">Click Save.</span></span>


