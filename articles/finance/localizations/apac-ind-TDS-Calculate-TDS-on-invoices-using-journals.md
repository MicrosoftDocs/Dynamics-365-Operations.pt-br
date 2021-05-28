---
title: Calcular TDS em faturas usando diários
description: Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) nos diários.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023042"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="74f8b-103">Calcular TDS em faturas usando diários</span><span class="sxs-lookup"><span data-stu-id="74f8b-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74f8b-104">Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) nos diários.</span><span class="sxs-lookup"><span data-stu-id="74f8b-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="74f8b-105">Comece abrindo a página **Diários gerais** (**Contabilidade > Entradas de diário > Diários gerais**).</span><span class="sxs-lookup"><span data-stu-id="74f8b-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="74f8b-106">[![Diários Gerais](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="74f8b-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="74f8b-107">Crie linhas de diário usando os formulários de diário listados na tabela.</span><span class="sxs-lookup"><span data-stu-id="74f8b-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="74f8b-108">Selecione o tipo de conta e o tipo de contrapartida e insira o valor da transação.</span><span class="sxs-lookup"><span data-stu-id="74f8b-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="74f8b-109">Na página **Diário de aprovações de fatura**, selecione **Localizar comprovantes** e selecione as faturas para calcular o TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="74f8b-110">Exiba as faturas criadas na página **Registro de fatura** ou na página **Localizar comprovantes**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="74f8b-111">Na guia **Geral** da página **Comprovante de diário**, exiba ou modifique o grupo do TDS padrão definido para o fornecedor ou cliente, no campo **Grupo de TDS**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="74f8b-112">O valor de TDS que é calculado nas linhas do diário é baseado na fórmula definida para os códigos de imposto TDS listados no campo **Grupo de TDS**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="74f8b-113">O campo **Grupo de impostos retidos na fonte** e o campo **Grupo de TCS** tornam-se indisponíveis quando você seleciona um grupo de TDS no campo **Grupo de TDS**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="74f8b-114">O campo **Grupo de impostos retidos na fonte** está disponível apenas na página **Diário geral**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="74f8b-115">O TDS é calculado apenas se a caixa de seleção **Calcular imposto retido na fonte** estiver marcada para o fornecedor ou cliente nas páginas **Todos os fornecedores** ou **Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="74f8b-116">Selecione a guia **Informações sobre impostos**. Selecione os endereços alternativos de uma empresa configurada para a empresa neste campo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="74f8b-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="74f8b-117">Você pode ver o nome da empresa no campo **Nome**, que está no grupo do campo **Informações sobre a empresa**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="74f8b-118">Exiba a categoria da natureza do avaliado do fornecedor ou cliente no campo **Natureza do avaliado**, que está no grupo de campos **Imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="74f8b-119">No campo **Número da Conta de Imposto** (**TAN**), exiba o TAN do nome da empresa selecionada que é exibido.</span><span class="sxs-lookup"><span data-stu-id="74f8b-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="74f8b-120">Selecione **Imposto retido na fonte** no menu **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="74f8b-121">Os seguintes campos são exibidos no painel superior da página **Transações de retenção temporária de impostos**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="74f8b-122">**Valor do imposto retido na fonte no total** - O TDS total calculado para a transação do grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="74f8b-123">**Valor** - A porcentagem total usada para calcular o TDS para a transação.</span><span class="sxs-lookup"><span data-stu-id="74f8b-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="74f8b-124">A porcentagem total é baseada na fórmula definida para os códigos de imposto TDS anexados ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="74f8b-125">**Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="74f8b-126">**TDS** - Se selecionado, um grupo de TDS é anexado à transação.</span><span class="sxs-lookup"><span data-stu-id="74f8b-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="74f8b-127">Os campos nas guias **Visão geral**, **Geral** e **Ajuste** na página **Transações de retenção temporária de impostos** exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="74f8b-128">Selecione **Limite** para abrir a página **Limite**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="74f8b-129">Exiba o limite e o limite de exceção definidos para o componente de imposto TDS anexado a um código de imposto TDS específico nesta página.</span><span class="sxs-lookup"><span data-stu-id="74f8b-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="74f8b-130">Selecione **Designer de fórmulas** para abrir o formulário **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="74f8b-131">Exiba a fórmula definida para um código de imposto TDS específico nesta página.</span><span class="sxs-lookup"><span data-stu-id="74f8b-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="74f8b-132">Feche as páginas **Designer de fórmula** e **Transações de imposto retido na fonte temporárias** para retornar à página **Comprovante de diário**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="74f8b-133">Insira os outros detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="74f8b-133">Enter the other required details.</span></span> <span data-ttu-id="74f8b-134">Valide e lance o diário.</span><span class="sxs-lookup"><span data-stu-id="74f8b-134">Validate and post the journal.</span></span> <span data-ttu-id="74f8b-135">O valor do TDS que é calculado nas faturas de compra é lançado na conta a pagar.</span><span class="sxs-lookup"><span data-stu-id="74f8b-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="74f8b-136">O valor do TDS que é calculado nas faturas de vendas é lançado na conta a receber definida para cada código de imposto de TDS no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="74f8b-137">As contas a pagar ou contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="74f8b-138">Selecione **Imposto retido na fonte lançado** para abrir a página **Transações** **de retenção** **de imposto**.</span><span class="sxs-lookup"><span data-stu-id="74f8b-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="74f8b-139">No campo **Valor**, a porcentagem total usada para calcular o TDS para a transação é exibida.</span><span class="sxs-lookup"><span data-stu-id="74f8b-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="74f8b-140">Os campos nas guias **Visão geral**, **Geral** e **Valor** na página de transações de imposto retido na fonte exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="74f8b-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
