---
title: Configurar códigos de imposto
description: Este tópico explica como configurar códigos de imposto no Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3dad006b486f7cd6714c713a3bd83a95fdf0d2b5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440257"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="25ef6-103">Configurar códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="25ef6-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25ef6-104">Este tópico explica como configurar códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="25ef6-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="25ef6-105">Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="25ef6-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="25ef6-106">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="25ef6-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="25ef6-107">Vá para **Painel de navegação > Imposto > Impostos indiretos > Imposto > Códigos de imposto**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="25ef6-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-108">Select **New**.</span></span>
3. <span data-ttu-id="25ef6-109">No campo **Código de imposto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="25ef6-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="25ef6-110">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="25ef6-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="25ef6-111">Selecione um **Período de liquidação** ao abrir a lista suspensa para especificar em que a autoridade de impostos sobre vendas e em intervalos que esses impostos sobre vendas precisem ser informado e pago.</span><span class="sxs-lookup"><span data-stu-id="25ef6-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="25ef6-112">Selecione um **Grupo de lançamentos contábeis** para especificar as contas principais para lançar impostos sobre vendas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="25ef6-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="25ef6-113">Expanda a Guia Rápida **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="25ef6-114">Isso inclui vários campos que controlam como os valores do imposto sobre vendas será calculado.</span><span class="sxs-lookup"><span data-stu-id="25ef6-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="25ef6-115">Preencha esses campos como necessário.</span><span class="sxs-lookup"><span data-stu-id="25ef6-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="25ef6-116">No **Painel de Ações**, na parte superior de interface, selecione **Código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="25ef6-117">Selecione **Valores**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-117">Select **Values**.</span></span>
10. <span data-ttu-id="25ef6-118">Insira o valor para esse código de imposto na coluna **valor**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="25ef6-119">Na Guia Rápida **Cálculo**, no campo Origem, se Valor por unidade estiver selecionado, o valor será multiplicado pela quantidade da transação para calcular o valor do imposto.</span><span class="sxs-lookup"><span data-stu-id="25ef6-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="25ef6-120">Se o código de imposto não for um imposto baseado na unidade, o valor é uma porcentagem que é aplicada na origem para a qual esse código de imposto calcula o valor do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="25ef6-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="25ef6-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-121">Select **Save**.</span></span>
12. <span data-ttu-id="25ef6-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="25ef6-122">Close the page.</span></span>
13. <span data-ttu-id="25ef6-123">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25ef6-123">Select **Save**.</span></span>

