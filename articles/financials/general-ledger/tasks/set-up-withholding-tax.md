--- 
title: Configurar imposto retido na fonte
description: "Imposto retido na fonte é um imposto sobre os fornecedores, o que não cria transações de imposto."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 39ebd6a1a326b0ff2943957c9606e91852d524ce
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="33cd1-103">Configurar imposto retido na fonte</span><span class="sxs-lookup"><span data-stu-id="33cd1-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="33cd1-104">Imposto retido na fonte é um imposto sobre os fornecedores, o que não cria transações de imposto.</span><span class="sxs-lookup"><span data-stu-id="33cd1-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="33cd1-105">O imposto retido na fonte calculado sobre os pagamentos do fornecedor é um passivo.</span><span class="sxs-lookup"><span data-stu-id="33cd1-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="33cd1-106">Por isso, apenas contas de balanço ou de passivos são contas válidas para o lançamento do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="33cd1-107">Essa guia da tarefa demonstra como definir a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="33cd1-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="33cd1-108">Vá para Imposto > Impostos indiretos > Impostos retidos na fonte > Códigos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="33cd1-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="33cd1-109">Click New.</span></span>
3. <span data-ttu-id="33cd1-110">No campo Impostos retidos na fonte, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33cd1-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="33cd1-111">No campo Nome de impostos retidos na fonte, insira o nome do código de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="33cd1-112">No campo de conta principal, selecione a conta principal para lançar a responsabilidade da retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="33cd1-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="33cd1-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33cd1-113">Click Save.</span></span>
7. <span data-ttu-id="33cd1-114">Clique em Valores.</span><span class="sxs-lookup"><span data-stu-id="33cd1-114">Click Values.</span></span>
8. <span data-ttu-id="33cd1-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33cd1-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="33cd1-116">No campo Valor, insira uma porcentagem usada para o cálculo do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="33cd1-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33cd1-117">Click Save.</span></span>
11. <span data-ttu-id="33cd1-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="33cd1-118">Close the page.</span></span>
12. <span data-ttu-id="33cd1-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33cd1-119">Click Save.</span></span>
13. <span data-ttu-id="33cd1-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="33cd1-120">Close the page.</span></span>
14. <span data-ttu-id="33cd1-121">Vá para Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="33cd1-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="33cd1-122">Click New.</span></span>
16. <span data-ttu-id="33cd1-123">No campo Grupo de impostos retidos na fonte, insira o identificador do grupo de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="33cd1-124">No campo Descrição, insira o nome do grupo de impostos retidos na fonte do item.</span><span class="sxs-lookup"><span data-stu-id="33cd1-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="33cd1-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33cd1-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="33cd1-126">No campo de código de Imposto retido na fonte, selecione o código do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="33cd1-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="33cd1-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33cd1-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="33cd1-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="33cd1-128">Click Save.</span></span>


