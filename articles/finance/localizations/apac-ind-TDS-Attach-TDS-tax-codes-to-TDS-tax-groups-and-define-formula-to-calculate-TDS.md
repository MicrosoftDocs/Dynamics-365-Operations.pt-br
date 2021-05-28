---
title: Anexar os códigos de imposto TDS aos grupos de impostos TDS e definir a fórmula para calcular o TDS
description: Este tópico explica como configurar grupos de impostos TDS (Imposto Deduzido na Fonte) e anexar códigos de imposto TDS aos grupos de impostos TDS. Para calcular o TDS para um grupo de impostos TDS, você deve definir a fórmula para os códigos de impostos TDS que estão anexados a ele.
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
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023037"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="63033-104">Anexar os códigos de imposto TDS aos grupos de impostos TDS e definir a fórmula para calcular o TDS</span><span class="sxs-lookup"><span data-stu-id="63033-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63033-105">Este tópico explica como configurar grupos de impostos TDS (Imposto Deduzido na Fonte) e anexar códigos de imposto TDS aos grupos de impostos TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="63033-106">Para calcular o TDS para um grupo de impostos TDS, você deve definir a fórmula para os códigos de impostos TDS que estão anexados a ele.</span><span class="sxs-lookup"><span data-stu-id="63033-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="63033-107">Siga estas etapas para configurar um grupo de impostos TDS, anexar códigos de impostos TDS a ele e definir a fórmula para calcular o TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="63033-108">Acesse **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Grupos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="63033-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="63033-109">[![Página Grupos de impostos retidos na fonte](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="63033-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="63033-110">No Painel de Ações, selecione **Novo** para criar um grupo de imposto retido na fonte para TDS e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="63033-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="63033-111">No campo **Tipo de imposto**, selecione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="63033-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="63033-112">Na Guia Rápida **Configuração**, selecione **Adicionar** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="63033-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="63033-113">No campo **Código de imposto retido na fonte**, selecione o código de imposto TDS para o grupo de impostos TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="63033-114">O campo **Nome do imposto retido na fonte** mostra o nome do código de imposto TDS e o campo **Valor** mostra o valor.</span><span class="sxs-lookup"><span data-stu-id="63033-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="63033-115">Para ignorar o limite e o limite de exceção definidos para o componente de imposto TDS anexado ao código de imposto TDS em transações TDS, marque a caixa de seleção **Esquecer limite**.</span><span class="sxs-lookup"><span data-stu-id="63033-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="63033-116">Para evitar que o grupo de impostos seja calculado nas transações, marque a caixa de seleção **Isento**.</span><span class="sxs-lookup"><span data-stu-id="63033-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="63033-117">No Painel de Ações, selecione **Designer** para abrir o designer de fórmulas, para que você possa definir a fórmula para calcular o TDS para o grupo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="63033-118">Na página **Designer**, a guia **Impostos** mostra os códigos de imposto TDS que foram selecionados para o grupo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="63033-119">[![Página Designer](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="63033-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="63033-120">Na guia **Cálculo**, selecione **Alt+N** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="63033-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="63033-121">O campo **ID** mostra a ID de prioridade gerada automaticamente para o cálculo de TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="63033-122">No campo **Código do imposto**, selecione o código de imposto TDS para o qual definir a fórmula.</span><span class="sxs-lookup"><span data-stu-id="63033-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="63033-123">Todos os códigos de imposto TDS que foram selecionados para o grupo de imposto TDS estão disponíveis para seleção neste campo.</span><span class="sxs-lookup"><span data-stu-id="63033-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="63033-124">No campo **Base de tributação**, selecione a base para o cálculo do TDS:</span><span class="sxs-lookup"><span data-stu-id="63033-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="63033-125">**Valor bruto** – Calcule o TDS com base no valor bruto da transação (ou seja, o valor da fatura) usando a expressão de cálculo definida para o código de imposto.</span><span class="sxs-lookup"><span data-stu-id="63033-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="63033-126">**Valor bruto excluído** – Calcule o TDS com base na expressão de cálculo definida para o código de imposto.</span><span class="sxs-lookup"><span data-stu-id="63033-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63033-127">O campo **Base de tributação** não pode ser definido como **Valor bruto excluído** para o código de imposto TDS que tem uma ID de prioridade **1**.</span><span class="sxs-lookup"><span data-stu-id="63033-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="63033-128">O cálculo do TDS é baseado na fórmula definida no campo **Expressão de cálculo** para cada código de imposto anexado ao grupo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="63033-129">Selecione o sinal de mais (**+**), sinal de menos (**-**), sinal de multiplicação (**\**_) ou sinal de divisão (_*/**) para inserir a expressão de cálculo para o código de imposto TDS selecionado no campo **Expressão de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="63033-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63033-130">Nenhuma expressão de cálculo pode ser definida para o código de imposto TDS que tem uma ID de prioridade de **1**.</span><span class="sxs-lookup"><span data-stu-id="63033-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="63033-131">Para definir a expressão de cálculo para o código de imposto TDS no campo **Expressão de cálculo**, adicione os códigos de imposto TDS que estão disponíveis na guia **Impostos**. Para adicionar códigos de imposto TDS no campo **Expressão de cálculo**, você pode usar qualquer um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="63033-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="63033-132">Arraste o código de imposto necessário da guia **Impostos** para o campo **Expressão de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="63033-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="63033-133">Toque duas vezes (ou clique duas vezes) no código de imposto necessário na guia **Impostos**.</span><span class="sxs-lookup"><span data-stu-id="63033-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="63033-134">Selecione e mantenha pressionado (ou clique com o botão direito) o código de imposto necessário na guia **Impostos** e, em seguida, selecione **Adicionar código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="63033-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63033-135">Insira uma expressão de cálculo antes de cada código de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="63033-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="63033-136">Os códigos de imposto TDS que foram adicionados à expressão de cálculo aparecem entre colchetes (\[...\]).</span><span class="sxs-lookup"><span data-stu-id="63033-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="63033-137">Para limpar a expressão de cálculo definida para um código de imposto no campo **Expressão de cálculo**, selecione o botão **C**.</span><span class="sxs-lookup"><span data-stu-id="63033-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="63033-138">Para excluir um registro na guia **Cálculo**, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="63033-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="63033-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="63033-139">Close the page.</span></span>
