---
title: Configurar imposto retido na fonte
description: Este tópico explica como configurar o imposto retido na fonte.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e7018c79e54841d0729636b08ad475a94d20d5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185948"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="b6879-103">Configurar imposto retido na fonte</span><span class="sxs-lookup"><span data-stu-id="b6879-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6879-104">Este tópico explica como configurar o imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="b6879-105">O *imposto retido na fonte* é um imposto cobrado dos fornecedores, o que não cria transações de imposto.</span><span class="sxs-lookup"><span data-stu-id="b6879-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="b6879-106">O imposto retido na fonte calculado sobre os pagamentos do fornecedor é um passivo.</span><span class="sxs-lookup"><span data-stu-id="b6879-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="b6879-107">Por isso, apenas contas de balanço ou de passivos são contas válidas para o lançamento do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="b6879-108">Essa guia da tarefa demonstra como definir a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="b6879-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="b6879-109">Vá para **Painel de navegação > Módulos > Imposto > Impostos indiretos > Imposto retido na fonte > Códigos de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6879-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="b6879-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b6879-110">Select **New**.</span></span>
3. <span data-ttu-id="b6879-111">No campo **Código de imposto retido na fonte**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6879-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="b6879-112">No campo **Nome de imposto retido na fonte**, insira o nome do código de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="b6879-113">No campo **Conta principal**, selecione a conta principal para lançamento da obrigação da retenção de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="b6879-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6879-114">Select **Save**.</span></span>
7. <span data-ttu-id="b6879-115">Selecione **Valores** e marque o registro desejado na lista.</span><span class="sxs-lookup"><span data-stu-id="b6879-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="b6879-116">No campo **Valor**, insira uma porcentagem usada para o cálculo do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="b6879-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6879-117">Select **Save**.</span></span>
10. <span data-ttu-id="b6879-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b6879-118">Close the page.</span></span>
11. <span data-ttu-id="b6879-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6879-119">Select **Save**.</span></span>
12. <span data-ttu-id="b6879-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b6879-120">Close the page.</span></span>
13. <span data-ttu-id="b6879-121">Vá para **Painel de navegação > Módulos > Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6879-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="b6879-122">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b6879-122">Select **New**.</span></span>
15. <span data-ttu-id="b6879-123">No campo **Grupo de impostos retidos na fonte**, insira o identificador do grupo de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="b6879-124">No campo **Descrição**, insira o nome do grupo de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="b6879-125">No campo **Código de imposto retido na fonte**, selecione o código do imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b6879-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="b6879-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6879-126">Select **Save**.</span></span>
19. <span data-ttu-id="b6879-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b6879-127">Close the page.</span></span>

