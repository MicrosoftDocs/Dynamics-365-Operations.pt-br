---
title: Configurar agendas de pagamento com alocação de TDS
description: Este tópico explica como configurar planos de pagamento com alocação de Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023036"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="4ac6f-103">Configurar agendas de pagamento com alocação de TDS</span><span class="sxs-lookup"><span data-stu-id="4ac6f-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ac6f-104">Este tópico explica como configurar planos de pagamento com alocação de Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="4ac6f-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="4ac6f-105">Vá para **Contas a pagar \> Configurar pagamento \> Planos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="4ac6f-106">[![Página Planos de pagamento](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="4ac6f-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="4ac6f-107">No Painel de Ações, selecione **Novo** para criar um plano de pagamento e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="4ac6f-108">No campo **Alocação**, selecione o método a ser usado para alocar o pagamento para o plano de pagamentos:</span><span class="sxs-lookup"><span data-stu-id="4ac6f-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="4ac6f-109">Total</span><span class="sxs-lookup"><span data-stu-id="4ac6f-109">Total</span></span>
    - <span data-ttu-id="4ac6f-110">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="4ac6f-110">Fixed amount</span></span>
    - <span data-ttu-id="4ac6f-111">Quantidade fixa</span><span class="sxs-lookup"><span data-stu-id="4ac6f-111">Fixed quantity</span></span>
    - <span data-ttu-id="4ac6f-112">Especificado</span><span class="sxs-lookup"><span data-stu-id="4ac6f-112">Specified</span></span>

    <span data-ttu-id="4ac6f-113">O campo **Alocação de imposto retido na fonte** mostra o método de alocação de TDS para o plano de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="4ac6f-114">Se você selecionar **Total** no campo **Alocação**, o campo **Alocação de imposto retido na fonte** será automaticamente definido como **Total**.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="4ac6f-115">Se você selecionar **Valor fixo**, **Quantidade fixa** ou **Especificado** no campo **Alocação**, o campo **Alocação de imposto retido na fonte** é automaticamente definido como **Proporcionalmente**.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ac6f-116">Se o campo **Alocação de imposto retido na fonte** for definido como **Total**, as prestações de pagamento são calculadas com base no valor bruto, que inclui o valor do TDS.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="4ac6f-117">Se o campo **Alocação de imposto retido na fonte** for definido como **Proporcionalmente**, as prestações de pagamento são calculadas com base no valor líquido da fatura após a dedução do valor do TDS.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="4ac6f-118">Insira os outros detalhes necessários e feche a página.</span><span class="sxs-lookup"><span data-stu-id="4ac6f-118">Enter the other required details, and then close the page.</span></span>
