---
title: Configurar códigos de impostos retidos na fonte para o tipo de imposto TDS
description: Este tópico explica como configurar códigos de impostos para Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023040"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="bd0a1-103">Configurar códigos de impostos retidos na fonte para o tipo de imposto TDS</span><span class="sxs-lookup"><span data-stu-id="bd0a1-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd0a1-104">Este tópico explica como configurar códigos de impostos para Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="bd0a1-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="bd0a1-105">Vá para **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Códigos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="bd0a1-106">[![Página Códigos de impostos retidos na fonte](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="bd0a1-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="bd0a1-107">No Painel de Ações, selecione **Novo** para criar um código de imposto retido na fonte para TDS e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="bd0a1-108">Na FastTab **Geral**, no campo **Tipo de imposto**, selecione **TDS** para categorizar o código de imposto como um código de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="bd0a1-109">No campo **Período de liquidação**, selecione o período de liquidação de TDS para o código do imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="bd0a1-110">No campo **Conta principal**, selecione a conta contábil na qual o valor de TDS deve ser lançado.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="bd0a1-111">No campo **Conta a receber**, selecione a conta a receber para a qual o valor TDS deduzido nas transações de vendas deve ser lançado.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="bd0a1-112">O campo **Origem** é definido automaticamente como **Porcentagem do valor bruto** e o valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd0a1-113">Não é possível definir a origem para a **Porcentagem do valor líquido** dos códigos de imposto do tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="bd0a1-114">No campo **Componente do imposto retido na fonte**, selecione o componente do imposto TDS para o código do imposto de TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="bd0a1-115">No Painel de Ações, selecione **Valores** para abrir a página **Valores da retenção de imposto**.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="bd0a1-116">No campo **Data inicial**, informe a data inicial para o valor de TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="bd0a1-117">No campo **Data final**, informe a data final.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd0a1-118">Os campos **Limite mínimo**, **Limite superior** e **Excluir %** não estão disponíveis para códigos de imposto do tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="bd0a1-119">No campo **Valor**, insira a porcentagem de TDS para o código do imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="bd0a1-120">Feche a página **Valores da retenção de imposto** para retornar à página **Códigos de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd0a1-121">O botão **Limites** na página **Códigos de impostos retidos na fonte** não está disponível para códigos de imposto do tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="bd0a1-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd0a1-122">Close the page.</span></span>
