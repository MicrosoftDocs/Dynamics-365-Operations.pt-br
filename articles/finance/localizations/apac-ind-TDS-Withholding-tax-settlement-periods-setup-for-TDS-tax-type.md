---
title: Configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS
description: Este tópico explica como configurar períodos de liquidação do Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023015"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="184b5-103">Configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS</span><span class="sxs-lookup"><span data-stu-id="184b5-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="184b5-104">Este tópico explica como configurar períodos de liquidação do Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="184b5-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="184b5-105">Vá para **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Períodos de liquidação de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="184b5-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="184b5-106">[![Página Períodos de liquidação de imposto retido na fonte](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="184b5-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="184b5-107">No campo **Tipo de imposto**, selecione **TDS** para configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS.</span><span class="sxs-lookup"><span data-stu-id="184b5-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="184b5-108">Selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="184b5-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="184b5-109">No campo **Período de liquidação**, informe um nome para o período de liquidação de TDS.</span><span class="sxs-lookup"><span data-stu-id="184b5-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="184b5-110">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="184b5-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="184b5-111">No campo **Autoridade do imposto retido na fonte**, selecione a autoridade de TDS para a qual você está definindo o período de liquidação de TDS.</span><span class="sxs-lookup"><span data-stu-id="184b5-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="184b5-112">Na FastTAb **Geral**, no campo **Intervalo do período**, selecione o tipo de intervalo do período para o período de liquidação de TDS.</span><span class="sxs-lookup"><span data-stu-id="184b5-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="184b5-113">No campo **Número de unidades**, especifique o número de unidades para o tipo de intervalo do período.</span><span class="sxs-lookup"><span data-stu-id="184b5-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="184b5-114">Na FastTab **Períodos**, no campo **Data inicial**, selecione a data inicial para o período de liquidação de TDS.</span><span class="sxs-lookup"><span data-stu-id="184b5-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="184b5-115">No campo de **Data final**, selecione a data final.</span><span class="sxs-lookup"><span data-stu-id="184b5-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="184b5-116">Para criar um período de liquidação de TDS subsequente para um período existente, com base nas unidades de intervalo e de período, selecione **Novo período**.</span><span class="sxs-lookup"><span data-stu-id="184b5-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="184b5-117">Para exibir os detalhes da liquidação de TDS durante a execução para um período de liquidação específico, selecione **Pagamentos de imposto retido na fonte** para abrir a página **Pagamento de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="184b5-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="184b5-118">Para executar o processo de liquidação de TDS periódico, vá para **Contabilidade \> Periódico \> Imposto retido na fonte \> Pagamento de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="184b5-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="184b5-119">[![Página Pagamento do imposto retido na fonte](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="184b5-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="184b5-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="184b5-120">Close the page.</span></span>
