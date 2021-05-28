---
title: Cálculo de TDS em faturas da página Fatura de texto livre
description: Este tópico explica como calcular o Imposto Deduzido na Origem (TDS) em faturas usando a página Fatura de texto livre.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023034"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="2277d-103">Cálculo de TDS em faturas da página Fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="2277d-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2277d-104">Este tópico explica como calcular o Imposto Deduzido na Origem (TDS) em faturas usando a página **Fatura de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="2277d-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="2277d-105">Vá para **Contas recebíveis \> Faturas \> Todas faturas de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="2277d-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="2277d-106">[![Página de fatura de texto livre](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="2277d-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="2277d-107">Selecione **Novo** para criar uma fatura de texto livre e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="2277d-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="2277d-108">Selecione a guia **Fatura**. Na seção **Grupo de impostos retidos na fonte**, o campo **Natureza do avaliado** mostra a natureza da categoria do avaliado do cliente.</span><span class="sxs-lookup"><span data-stu-id="2277d-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="2277d-109">No campo **Grupo de TDS**, revise ou altere o grupo de TDS padrão definido para o cliente.</span><span class="sxs-lookup"><span data-stu-id="2277d-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2277d-110">Quando você seleciona um valor no campo **Grupo de TDS**, o campo **Grupo de TCS** fica indisponível.</span><span class="sxs-lookup"><span data-stu-id="2277d-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="2277d-111">O TDS é calculado apenas se a opção **Calcular imposto retido na fonte** for definida como **Sim** para o cliente na página **Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="2277d-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="2277d-112">Na guia **Informações sobre impostos**, na **Informações sobre a empresa**, no campo **Nome**, selecione o nome da empresa para um endereço alternativo configurado para a empresa.</span><span class="sxs-lookup"><span data-stu-id="2277d-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="2277d-113">Na seção **Imposto retido na fonte**, o campo **Número da Conta de Imposto (TAN)** mostra o número da conta de imposto (TAN) para a empresa selecionada.</span><span class="sxs-lookup"><span data-stu-id="2277d-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="2277d-114">Na guia **Linhas da fatura**, crie linhas da fatura e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="2277d-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="2277d-115">Na seção **Grupo de impostos retidos na fonte**, o campo **Número da Conta de Imposto (TAN)** mostra o TAN e o campo **Grupo de TDS** mostra o grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="2277d-116">Selecione **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**.</span><span class="sxs-lookup"><span data-stu-id="2277d-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="2277d-117">A parte superior desta página tem os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="2277d-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="2277d-118">**Valor do imposto retido na fonte no total** - O TDS total que foi calculado para a transação do grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="2277d-119">**Valor** - A porcentagem total que foi usada para calcular o TDS para a transação.</span><span class="sxs-lookup"><span data-stu-id="2277d-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="2277d-120">A porcentagem total é baseada na fórmula definida para os códigos de imposto de TDS e anexados ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="2277d-121">**Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="2277d-122">**TDS** – uma caixa de seleção marcada indica que um grupo de TDS está associado à transação.</span><span class="sxs-lookup"><span data-stu-id="2277d-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="2277d-123">Os campos nas guias **Visão geral**, **Geral** e **Ajuste** mostram o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="2277d-124">Selecione **Limite** para abrir a página **Limite**, na qual é possível revisar o limite definido para o componente de imposto TDS anexado a um código de imposto TDS específico.</span><span class="sxs-lookup"><span data-stu-id="2277d-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="2277d-125">Selecione **Designer de fórmulas** para abrir a página **Designer de fórmulas**, na qual você pode revisar a fórmula definida para um código de imposto TDS específico.</span><span class="sxs-lookup"><span data-stu-id="2277d-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="2277d-126">Lançar a fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="2277d-126">Post the free text invoice.</span></span> <span data-ttu-id="2277d-127">O valor de TDS que é calculado para a fatura de texto livre é lançado na conta a receber definida para cada código de imposto de TDS no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="2277d-128">As contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="2277d-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="2277d-129">Selecione **Imposto retido na fonte lançado** para abrir a página **Transações de retenção de imposto**.</span><span class="sxs-lookup"><span data-stu-id="2277d-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="2277d-130">O campo **Valor** mostra a porcentagem total que foi usada para calcular o TDS para a transação.</span><span class="sxs-lookup"><span data-stu-id="2277d-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="2277d-131">Os campos nas guias **Visão geral**, **Geral** e **Valor** mostram os valores de TDS que foram calculados nas linhas da fatura.</span><span class="sxs-lookup"><span data-stu-id="2277d-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="2277d-132">Revise as informações de cálculo do TDS para cada código de imposto de TDS que foi anexado ao grupo do TDS.</span><span class="sxs-lookup"><span data-stu-id="2277d-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
