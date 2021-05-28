---
title: Registrar números de certificados recuperáveis de TDS
description: Este tópico explica como usar a página Certificados recuperáveis para registrar os números e datas dos certificados de Imposto Deduzido na Origem (TDS) recebidos de um fornecedor, cliente ou razão específico.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023014"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="26056-103">Registrar números de certificados recuperáveis de TDS</span><span class="sxs-lookup"><span data-stu-id="26056-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26056-104">Este tópico explica como usar a página **Certificados recuperáveis** para registrar os números e datas dos certificados de Imposto Deduzido na Origem (TDS) recebidos de um fornecedor, cliente ou razão específico.</span><span class="sxs-lookup"><span data-stu-id="26056-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="26056-105">Para atualizar os números e datas dos certificados do TDS que são registrados para transações TDS nesta página, use a página **Atualizar certificado** (**Contabilidade \> Periódico \> Imposto retido na fonte \> Atualizar certificado**).</span><span class="sxs-lookup"><span data-stu-id="26056-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="26056-106">Depois de terminar de atualizar os números dos certificados do TDS, feche-os.</span><span class="sxs-lookup"><span data-stu-id="26056-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="26056-107">Siga estas etapas para registrar os números e datas dos certificados do TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="26056-108">Acesse **Imposto \> Imposto indireto \> Imposto retido na fonte \> Certificados recuperáveis**.</span><span class="sxs-lookup"><span data-stu-id="26056-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="26056-109">[![Página Certificados recuperáveis](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="26056-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="26056-110">Na página **Certificados recuperáveis**, no campo **Tipo de imposto**, selecione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="26056-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="26056-111">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="26056-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="26056-112">No campo **Número do certificado**, insira o número do certificado do TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="26056-113">No campo **Tipo de conta**, selecione o tipo de conta para a qual o certificado do TDS é recebido: **Fornecedor**, **Cliente** ou **Razão**.</span><span class="sxs-lookup"><span data-stu-id="26056-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="26056-114">No campo **Conta**, selecione o fornecedor, cliente ou número da conta contábil, dependendo do tipo de conta que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="26056-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="26056-115">O campo **Nome** mostra o nome do fornecedor, cliente ou conta contábil.</span><span class="sxs-lookup"><span data-stu-id="26056-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="26056-116">No campo **Valor do certificado**, insira o valor do certificado do TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="26056-117">No campo **Data**, insira a data do certificado para o número do certificado.</span><span class="sxs-lookup"><span data-stu-id="26056-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="26056-118">Selecione **Consultas** para abrir a página **Transações de certificado**, em que você pode exibir as transações do TDS para as quais o número e a data do certificado do TDS foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="26056-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="26056-119">Essas informações podem ser atualizadas na página **Atualizar certificado** (**Imposto \> Declarações \> Imposto retido na fonte \> Atualizar certificado**).</span><span class="sxs-lookup"><span data-stu-id="26056-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="26056-120">A página **Atualizar certificado** mostra as seguintes informações para cada transação TDS:</span><span class="sxs-lookup"><span data-stu-id="26056-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="26056-121">**Data** – A data de lançamento da transação TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="26056-122">**Comprovante** – O número do comprovante da transação de TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="26056-123">**Origem** – O módulo em que a transação TDS foi criada.</span><span class="sxs-lookup"><span data-stu-id="26056-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="26056-124">**Conta** – O fornecedor, cliente ou número da conta contábil para o qual a transação TDS foi criada.</span><span class="sxs-lookup"><span data-stu-id="26056-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="26056-125">**Nome** – O nome do fornecedor, cliente ou conta contábil para o qual a transação TDS foi criada.</span><span class="sxs-lookup"><span data-stu-id="26056-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="26056-126">**Valor** – O valor da fatura sobre o qual o TDS foi calculado.</span><span class="sxs-lookup"><span data-stu-id="26056-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="26056-127">**Valor do imposto** – O valor do imposto TDS calculado para a transação.</span><span class="sxs-lookup"><span data-stu-id="26056-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="26056-128">**Data do certificado** – A data do certificado do TDS que foi atualizado para a transação TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="26056-129">**Número do certificado** – Número do certificado TDS que foi atualizado para a transação TDS.</span><span class="sxs-lookup"><span data-stu-id="26056-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="26056-130">Na página **Certificados recuperáveis**, marque a caixa de seleção **Fechado** para fechar o número do certificado do TDS após terminar de atualizá-lo para transações TDS na página **Atualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="26056-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="26056-131">Para marcar a caixa de seleção **Fechado** de todos os registros da página, selecione **Marcar todos**.</span><span class="sxs-lookup"><span data-stu-id="26056-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26056-132">Os números do certificado do TDS para os quais a caixa de seleção **Fechado** está marcada não estão disponíveis na página **Atualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="26056-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
