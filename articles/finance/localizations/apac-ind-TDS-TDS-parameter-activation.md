---
title: Definir os parâmetros de TDS
description: Este tópico explica como definir parâmetros para ativar a funcionalidade de Imposto Deduzido na Origem (TDS) nas transações especificadas. Esta é uma etapa necessária para usar o recurso Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023026"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="0dea3-104">Definir os parâmetros de TDS</span><span class="sxs-lookup"><span data-stu-id="0dea3-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dea3-105">Este tópico explica como definir parâmetros para ativar a funcionalidade de Imposto Deduzido na Origem (TDS) nas transações especificadas.</span><span class="sxs-lookup"><span data-stu-id="0dea3-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="0dea3-106">Esta é uma etapa necessária para usar o recurso Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="0dea3-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="0dea3-107">Vá para **Contabilidade \> Configuração do razão \> Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="0dea3-108">Na guia **Impostos diretos**, na seção **Imposto Deduzido na Origem**, defina a opção **Ativar TDS** como **Sim** para ativar a funcionalidade de TDS e as páginas e campos que são usados para ela.</span><span class="sxs-lookup"><span data-stu-id="0dea3-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="0dea3-109">Defina a opção **Fatura** como **Sim** para ativar os campos que são usados para calcular e deduzir TDS no nível da fatura.</span><span class="sxs-lookup"><span data-stu-id="0dea3-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="0dea3-110">Defina a opção **Pagamento** como **Sim** para ativar os campos que são usados para calcular e deduzir TDS no nível do pagamento.</span><span class="sxs-lookup"><span data-stu-id="0dea3-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="0dea3-111">[![Guia Impostos diretos](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="0dea3-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="0dea3-112">Na guia **Sequências de número**, localize a linha onde o campo **Referência** foi definido como **Pagamento de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="0dea3-113">No campo **Código de sequência numérica** da linha, selecione o código de sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="0dea3-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="0dea3-114">O código de sequência numérica é usado para gerar números do comprovante para o processo de liquidação TDS periódico.</span><span class="sxs-lookup"><span data-stu-id="0dea3-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0dea3-115">Para executar o processo de liquidação de TDS periódico, vá para **Imposto \> Declarações \> Imposto retido na fonte \> Pagamento de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="0dea3-116">[![Guia Sequências numéricas](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="0dea3-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="0dea3-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0dea3-117">Close the page.</span></span>
