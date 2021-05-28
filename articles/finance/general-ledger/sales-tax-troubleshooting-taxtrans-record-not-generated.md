---
title: O registro TaxTrans não é gerado
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando um registro TaxTrans não é gerado.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 74987506699834d86703702106e5abf87bfa45da
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018772"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="dd56c-103">O registro TaxTrans não é gerado</span><span class="sxs-lookup"><span data-stu-id="dd56c-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd56c-104">Se você selecionar **Imposto lançado** para uma transação, mas a página **Imposto lançado** não mostrar linhas de imposto ou uma linha de imposto estiver ausente, talvez o registro **TaxTrans** não tenha sido gerado.</span><span class="sxs-lookup"><span data-stu-id="dd56c-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="dd56c-105">[![Página Imposto lançado sem itens de linha](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="dd56c-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="dd56c-106">Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dd56c-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="dd56c-107">Verificar o imposto antes de lançar a transação</span><span class="sxs-lookup"><span data-stu-id="dd56c-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="dd56c-108">Antes de lançar a transação, na página **Lançar fatura**, selecione **Imposto** para verificar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="dd56c-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="dd56c-109">[![Botão Imposto na página Lançar fatura](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="dd56c-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="dd56c-110">Na página **Transações temporárias de imposto**, revise o resultado do cálculo.</span><span class="sxs-lookup"><span data-stu-id="dd56c-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="dd56c-111">Se nenhum imposto for calculado, consulte [O imposto não é calculado ou o valor do imposto é zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="dd56c-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="dd56c-112">Localizar o registro TaxTrans em todos os impostos lançados</span><span class="sxs-lookup"><span data-stu-id="dd56c-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="dd56c-113">Vá para **Imposto** \> **Consultas e relatórios** \> **Consultas de imposto** > **Imposto lançado**.</span><span class="sxs-lookup"><span data-stu-id="dd56c-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="dd56c-114">No título da coluna **Comprovante**, selecione o símbolo de filtro para localizar o registro **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="dd56c-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="dd56c-115">Se você encontrar os registros de impostos que está procurando, verifique a data.</span><span class="sxs-lookup"><span data-stu-id="dd56c-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="dd56c-116">Se a data for diferente da data do cabeçalho do diário, crie uma solicitação de serviço da Microsoft para obter suporte adicional.</span><span class="sxs-lookup"><span data-stu-id="dd56c-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="dd56c-117">[![Página Imposto lançado](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="dd56c-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="dd56c-118">Depurar para verificar detalhes</span><span class="sxs-lookup"><span data-stu-id="dd56c-118">Debug to check details</span></span>

1. <span data-ttu-id="dd56c-119">Para obter informações sobre como depurar e determinar se **TmpTaxWorkTrans** e **TaxUncommitted** são gerados corretamente, consulte [O valor de campo em TaxTrans está incorreto](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="dd56c-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="dd56c-120">Se **TaxTmpWorkTrans** ou **TaxUncommitted** for gerado corretamente, adicione um ponto de interrupção em **TaxPost::SaveAndPost()** e **Tax::SaveAndPost** para depurar o motivo pelo qual **TaxTrans** não é inserido.</span><span class="sxs-lookup"><span data-stu-id="dd56c-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="dd56c-121">[![Pontos de interrupção adicionados no código](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="dd56c-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="dd56c-122">[![Resultados de pontos de interrupção adicionados](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="dd56c-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="dd56c-123">Determinar se há personalização</span><span class="sxs-lookup"><span data-stu-id="dd56c-123">Determine whether customization exists</span></span>

<span data-ttu-id="dd56c-124">Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização.</span><span class="sxs-lookup"><span data-stu-id="dd56c-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="dd56c-125">Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.</span><span class="sxs-lookup"><span data-stu-id="dd56c-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
