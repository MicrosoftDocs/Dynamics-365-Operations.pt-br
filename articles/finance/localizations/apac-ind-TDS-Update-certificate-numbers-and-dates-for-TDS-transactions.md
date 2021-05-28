---
title: Atualizar números e datas de certificado para transações de TDS
description: Este tópico explica como atualizar os números e datas do certificado recuperável que foram registrados para contas de fornecedor, cliente e razão para Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023024"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="5b475-103">Atualizar números e datas de certificado para transações de TDS</span><span class="sxs-lookup"><span data-stu-id="5b475-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b475-104">Este tópico explica como atualizar os números e datas do certificado recuperável que foram registrados para contas de fornecedor, cliente e razão para Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="5b475-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="5b475-105">Você pode exibir os certificados para transações de TDS na página **Certificados recuperáveis**.</span><span class="sxs-lookup"><span data-stu-id="5b475-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="5b475-106">Você pode atualizar os certificados usando a página **Atualizar Certificados**.</span><span class="sxs-lookup"><span data-stu-id="5b475-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="5b475-107">Siga estas etapas para atualizar os números e datas dos certificados para transações de TDS.</span><span class="sxs-lookup"><span data-stu-id="5b475-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="5b475-108">Vá para **Imposto \> Declarações \> Imposto retido na fonte \> Atualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="5b475-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="5b475-109">[![Página Atualizar certificado](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="5b475-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="5b475-110">Na página **Atualizar certificado**, na seção **Selecionar** no campo **Tipo de imposto**, selecione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="5b475-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="5b475-111">No campo **Número do certificado**, selecione o número do certificado TDS do cliente ou do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5b475-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b475-112">O campo **Número do certificado** lista somente os números de certificados de TDS para os quais a caixa de seleção **Fechada** está desmarcada na página **Certificados recuperáveis**.</span><span class="sxs-lookup"><span data-stu-id="5b475-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="5b475-113">O campo **Data do certificado**, mostra a data do certificado.</span><span class="sxs-lookup"><span data-stu-id="5b475-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="5b475-114">O campo **Tipo de conta** mostra o tipo de conta para a qual o número do certificado de TDS é recebido e o campo **Nome** mostra o nome da conta.</span><span class="sxs-lookup"><span data-stu-id="5b475-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="5b475-115">Nos campos **Data inicial** e **Data final** selecione as datas inicial e final do período para mostrar as transações TDS.</span><span class="sxs-lookup"><span data-stu-id="5b475-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="5b475-116">Selecione **Mostrar dados** para exibir as transações de TDS que foram lançadas durante o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="5b475-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="5b475-117">Na guia **Visão geral**, a grade no painel superior mostra as seguintes informações sobre cada transação de TDS que foi lançada para o fornecedor ou cliente durante o período selecionado:</span><span class="sxs-lookup"><span data-stu-id="5b475-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="5b475-118">**Comprovante** – O número do comprovante da transação de TDS.</span><span class="sxs-lookup"><span data-stu-id="5b475-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="5b475-119">**Data** – A data da transação de TDS.</span><span class="sxs-lookup"><span data-stu-id="5b475-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="5b475-120">**Valor** – O valor da fatura sobre o qual o TDS foi calculado.</span><span class="sxs-lookup"><span data-stu-id="5b475-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="5b475-121">**Valor do imposto** – O valor do imposto TDS calculado para a transação.</span><span class="sxs-lookup"><span data-stu-id="5b475-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="5b475-122">Para mover transações de TDS específicas da grade superior para a grade inferior, selecione as transações e, em seguida, selecione **Incluir**.</span><span class="sxs-lookup"><span data-stu-id="5b475-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="5b475-123">Como alternativa, selecione **Incluir tudo** para mover todas as transações de TDS da grade superior para a grade inferior.</span><span class="sxs-lookup"><span data-stu-id="5b475-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="5b475-124">Para mover transações de TDS específicas ou todas as transações de TDS da grade inferior para a grade superior, use o botão **Excluir** ou **Excluir tudo**.</span><span class="sxs-lookup"><span data-stu-id="5b475-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="5b475-125">Selecione **Atualizar** para atualizar os campos **Número do certificado** e **Data do certificado** para transações de TDS na grade inferior.</span><span class="sxs-lookup"><span data-stu-id="5b475-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="5b475-126">Vá para **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Certificado recuperável** e selecione **Consulta** para exibir as linhas de transação atualizadas que têm os novos números de certificados na página **Transações do certificado**.</span><span class="sxs-lookup"><span data-stu-id="5b475-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="5b475-127">[![Página Transações do certificado](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="5b475-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
