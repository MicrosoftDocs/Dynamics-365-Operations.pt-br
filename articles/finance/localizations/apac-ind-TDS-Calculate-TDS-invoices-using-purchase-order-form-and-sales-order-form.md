---
title: Calcular faturas de TDS usando formulário de ordem de compra e formulário de ordem de venda
description: Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) em vários tipos de faturas.
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
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023018"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="b6f88-103">Calcular faturas de TDS usando formulário de ordem de compra e formulário de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b6f88-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6f88-104">Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) em vários tipos de faturas usando as páginas **Ordem de compra**, **Diário de compras**, **Ordem ampla** e **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="b6f88-105">Crie uma ordem de compra, diário de compras, ordem de compra ampla ou ordem de venda usando a página listada.</span><span class="sxs-lookup"><span data-stu-id="b6f88-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="b6f88-106">Insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="b6f88-106">Enter the required details.</span></span>

2. <span data-ttu-id="b6f88-107">Selecione a guia **Configuração** para ver a natureza do avaliado do fornecedor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="b6f88-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="b6f88-108">Essas informações estão listadas no campo **Natureza do avaliado**, no grupo do campo **Grupo de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="b6f88-109">No campo **Grupo de TDS**, exibe ou modifique o grupo de TDS padrão definido para o fornecedor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="b6f88-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b6f88-110">O campo **Grupo de TCS** não está disponível quando você seleciona um grupo de TDS no campo **Grupo de TDS**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="b6f88-111">O TDS é calculado apenas se a caixa de seleção **Calcular imposto retido na fonte** estiver marcada para o fornecedor ou cliente na página **Todos os fornecedores** ou **Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="b6f88-112">Crie linhas de itens na guia **Linhas** e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="b6f88-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="b6f88-113">Selecione a guia **Configuração** (nível de linha) para exibir ou alterar o grupo de TDS definido no nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b6f88-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="b6f88-114">O grupo de TDS é exibido no campo **Grupo de TDS**, que está no grupo do campo **Grupo de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="b6f88-115">Selecione a guia **Informações sobre impostos** e selecione endereços alternativos que são configurados para o nome da empresa que é exibido neste campo.</span><span class="sxs-lookup"><span data-stu-id="b6f88-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="b6f88-116">O nome da empresa é exibido no campo **Nome**, que está no grupo do campo **Informações sobre a empresa**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="b6f88-117">O TAN do nome da empresa selecionada é exibido no campo **Número da Conta de Imposto** (**TAN**), no grupo do campo **Imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="b6f88-118">Selecione **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="b6f88-119">Exiba os seguintes campos no painel superior da página **Transações de retenção temporária de impostos**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="b6f88-120">**Valor** **do imposto retido** **na fonte** **no** **total** - O TDS total calculado para a transação do grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="b6f88-121">**Valor** - A porcentagem total usada para calcular o TDS para a transação.</span><span class="sxs-lookup"><span data-stu-id="b6f88-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="b6f88-122">A porcentagem total é baseada na fórmula definida para os códigos de imposto TDS anexados ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="b6f88-123">**Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="b6f88-124">**TDS** - Se selecionado, um grupo de TDS é anexado à transação.</span><span class="sxs-lookup"><span data-stu-id="b6f88-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="b6f88-125">Os campos nas guias **Visão geral**, **Geral** e **Ajuste** na página **Transações de retenção temporária de impostos** exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="b6f88-126">Selecione **Limite** para abrir a página **Limite**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="b6f88-127">Exiba o limite definido para o componente de imposto TDS anexado a um código de imposto TDS específico nesta página.</span><span class="sxs-lookup"><span data-stu-id="b6f88-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="b6f88-128">Selecione **Designer de fórmulas** para abrir a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="b6f88-129">Exiba a fórmula definida para um código de imposto TDS específico nesta página.</span><span class="sxs-lookup"><span data-stu-id="b6f88-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="b6f88-130">Lance a fatura.</span><span class="sxs-lookup"><span data-stu-id="b6f88-130">Post the invoice.</span></span> <span data-ttu-id="b6f88-131">O valor do TDS calculado nas notas fiscais de compra é lançado na conta a pagar e o valor do TDS calculado nas notas fiscais de vendas é lançado na conta a receber que é definida para cada código de imposto TDS no grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="b6f88-132">As contas a pagar ou contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="b6f88-133">Selecione o botão **Consulta** e o botão **> Fatura > Imposto retido na fonte lançado** para abrir a página **Transações de retenção de imposto**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="b6f88-134">Você pode ver a porcentagem total usada para calcular o TDS para a transação no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="b6f88-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="b6f88-135">Os campos nas guias **Visão geral**, **Geral** e **Valor** na página **Transações de retenção de imposto** exibem as informações do TDS calculado para a transação.</span><span class="sxs-lookup"><span data-stu-id="b6f88-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="b6f88-136">Exiba as informações de cálculo do TDS para cada código de imposto TDS anexado ao grupo do TDS.</span><span class="sxs-lookup"><span data-stu-id="b6f88-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
