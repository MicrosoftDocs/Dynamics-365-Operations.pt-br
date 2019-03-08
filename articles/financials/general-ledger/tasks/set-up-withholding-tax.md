---
title: Configurar imposto retido na fonte
description: Imposto retido na fonte é um imposto sobre os fornecedores, o que não cria transações de imposto.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "337224"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="b0cd2-103">Configurar imposto retido na fonte</span><span class="sxs-lookup"><span data-stu-id="b0cd2-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b0cd2-104">Imposto retido na fonte é um imposto sobre os fornecedores, o que não cria transações de imposto.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="b0cd2-105">O imposto retido na fonte calculado sobre os pagamentos do fornecedor é um passivo.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="b0cd2-106">Por isso, apenas contas de balanço ou de passivos são contas válidas para o lançamento do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="b0cd2-107">Essa guia da tarefa demonstra como definir a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="b0cd2-108">Vá para Imposto > Impostos indiretos > Impostos retidos na fonte > Códigos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="b0cd2-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-109">Click New.</span></span>
3. <span data-ttu-id="b0cd2-110">No campo Impostos retidos na fonte, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="b0cd2-111">No campo Nome de impostos retidos na fonte, insira o nome do código de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="b0cd2-112">No campo de conta principal, selecione a conta principal para lançar a responsabilidade da retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="b0cd2-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-113">Click Save.</span></span>
7. <span data-ttu-id="b0cd2-114">Clique em Valores.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-114">Click Values.</span></span>
8. <span data-ttu-id="b0cd2-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="b0cd2-116">No campo Valor, insira uma porcentagem usada para o cálculo do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="b0cd2-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-117">Click Save.</span></span>
11. <span data-ttu-id="b0cd2-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-118">Close the page.</span></span>
12. <span data-ttu-id="b0cd2-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-119">Click Save.</span></span>
13. <span data-ttu-id="b0cd2-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-120">Close the page.</span></span>
14. <span data-ttu-id="b0cd2-121">Vá para Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="b0cd2-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-122">Click New.</span></span>
16. <span data-ttu-id="b0cd2-123">No campo Grupo de impostos retidos na fonte, insira o identificador do grupo de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="b0cd2-124">No campo Descrição, insira o nome do grupo de impostos retidos na fonte do item.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="b0cd2-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="b0cd2-126">No campo de código de Imposto retido na fonte, selecione o código do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="b0cd2-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="b0cd2-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0cd2-128">Click Save.</span></span>

