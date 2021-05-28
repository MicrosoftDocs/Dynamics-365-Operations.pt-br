---
title: Configurar os componentes de imposto para o tipo de imposto TDS
description: Este tópico explica como configurar os componentes do imposto retido na fonte para o tipo de Imposto Deduzido na Origem (TDS). Também explica como definir o limite que é usado para calcular o TDS para cada componente do TDS.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023023"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="7e22e-104">Configurar os componentes de imposto para o tipo de imposto TDS</span><span class="sxs-lookup"><span data-stu-id="7e22e-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e22e-105">Este tópico explica como configurar os componentes do imposto retido na fonte para o tipo de Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="7e22e-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="7e22e-106">Os componentes do TDS são TDS, sobretaxa, PE-Cess e SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="7e22e-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="7e22e-107">Este tópico também explica como definir o limite usado para calcular o TDS para cada componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="7e22e-108">Além disso, você pode definir um limite de exceção que é usado para calcular o TDS para cada componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="7e22e-109">Siga estas etapas para configurar os componentes do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="7e22e-110">Vá para **Imposto \> Configuração \> Imposto retido na fonte \> Componentes de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="7e22e-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="7e22e-111">[![Página Componentes de imposto retido na fonte](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="7e22e-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="7e22e-112">No campo **Tipo de imposto**, selecione **TDS** para configurar componentes de imposto retido na fonte para o tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="7e22e-113">No Painel de Ações, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="7e22e-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="7e22e-114">No campo **Componente do imposto retido na fonte**, insira um nome para o componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="7e22e-115">No campo **Grupo de componentes do imposto retido na fonte**, selecione o grupo de componente de imposto retido na fonte de TDS ao qual anexar o componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="7e22e-116">Na FastTab **Geral**, no campo **Descrição**, insira uma descrição do componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="7e22e-117">No Painel de Ações, selecione **Limite** para abrir a página **Limite**, para que você possa definir o limite que é usado para calcular o TDS para o componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="7e22e-118">Use os campos **Data inicial** e **Data final** para definir o período ao qual o limite é aplicável.</span><span class="sxs-lookup"><span data-stu-id="7e22e-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="7e22e-119">Na FastTab **Geral**, no campo **Limite**, insira o valor limite que é usado para calcular o TDS para o componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="7e22e-120">O imposto será deduzido na fonte somente quando o valor cumulativo da fatura ultrapassar o limite.</span><span class="sxs-lookup"><span data-stu-id="7e22e-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="7e22e-121">Por exemplo, se o valor limite for 10.000, o TDS será calculado depois que o valor cumulativo da fatura exceder 10.000 (em outras palavras, quando for 10.001 ou mais).</span><span class="sxs-lookup"><span data-stu-id="7e22e-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="7e22e-122">No campo **Limite de exceção**, insira o valor do limite de exceção que é usado para calcular o TDS para o componente do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="7e22e-123">O imposto em uma linha da fatura será deduzido na fonte somente quando o valor ultrapassar o limite de exceção.</span><span class="sxs-lookup"><span data-stu-id="7e22e-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="7e22e-124">Por exemplo, se o valor do limite de exceção for 5.000, o TDS será calculado em uma linha de fatura específica se o valor da linha da fatura exceder 5.000 (em outras palavras, se for 5.001 ou mais).</span><span class="sxs-lookup"><span data-stu-id="7e22e-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="7e22e-125">[![Página Limite](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="7e22e-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e22e-126">O valor do limite de exceção deve ser menor ou igual ao valor do limite.</span><span class="sxs-lookup"><span data-stu-id="7e22e-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="7e22e-127">O imposto é deduzido para uma transação se o valor da transação ultrapassar o limite de exceção, mesmo se o valor da fatura cumulativa não ultrapassar o limite especificado no campo **Limite**.</span><span class="sxs-lookup"><span data-stu-id="7e22e-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="7e22e-128">Feche a página **Limite** para retornar à página **Componentes de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="7e22e-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="7e22e-129">No Painel de Ações, selecione **Copiar** para abrir a caixa de diálogo **Copiar componentes de imposto retido na fonte**, para que você possa copiar os componentes do TDS que foram configurados para um grupo de componentes do TDS para outro grupo de componentes do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="7e22e-130">No campo **De**, selecione o grupo de componentes do TDS do qual copiar os componentes do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="7e22e-131">No campo **Até**, selecione o grupo de componentes de imposto retido na fonte para o qual copiar os componentes do TDS.</span><span class="sxs-lookup"><span data-stu-id="7e22e-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e22e-132">Os componentes do TDS comuns que estão anexados a ambos os grupos de componentes do TDS não são copiados.</span><span class="sxs-lookup"><span data-stu-id="7e22e-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="7e22e-133">Selecione **OK** para copiar e criar componentes do TDS para o outro grupo de componentes do TDS na página **Componentes de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="7e22e-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="7e22e-134">[![Caixa de diálogo Copiar componentes de imposto retido na fonte](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="7e22e-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="7e22e-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e22e-135">Close the page.</span></span>
