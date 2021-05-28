---
title: Configurar taxas de pagamento para pagamentos de autoridade TDS
description: Este tópico explica como configurar taxas de pagamento que são cobradas para pagamentos de autoridade de Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023043"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="a53d7-103">Configurar taxas de pagamento para pagamentos de autoridade TDS</span><span class="sxs-lookup"><span data-stu-id="a53d7-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a53d7-104">Este tópico explica como configurar taxas de pagamento que são cobradas para pagamentos de autoridade de Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="a53d7-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="a53d7-105">Vá para **Contas a pagar \> Configurar pagamento \> Taxa de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="a53d7-106">[![Página Taxa de pagamento](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="a53d7-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="a53d7-107">Selecione **Novo** para criar uma taxa de pagamento e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="a53d7-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="a53d7-108">No campo **Tipo de taxa**, selecione o tipo de taxa de pagamento:</span><span class="sxs-lookup"><span data-stu-id="a53d7-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="a53d7-109">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="a53d7-109">**None**</span></span>
    - <span data-ttu-id="a53d7-110">**Juros** – Os juros são cobrados sobre pagamentos atrasados feitos ao fornecedor da autoridade TDS.</span><span class="sxs-lookup"><span data-stu-id="a53d7-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="a53d7-111">**Outros** – Outros encargos são cobrados em pagamentos atrasados feitos ao fornecedor da autoridade TDS.</span><span class="sxs-lookup"><span data-stu-id="a53d7-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="a53d7-112">Se você selecionar **Juros** ou **Outros**, o campo **Encargo** será automaticamente definido como **Razão**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="a53d7-113">Se você selecionou **Juros** ou **Outros** no campo **Tipo de campo**, no campo **Conta principal**, selecione a conta contábil para lançar os juros ou outras cobranças.</span><span class="sxs-lookup"><span data-stu-id="a53d7-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="a53d7-114">Insira os outros detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="a53d7-114">Enter the other required details.</span></span>
6. <span data-ttu-id="a53d7-115">No Painel de Ações, selecione **Configuração de taxa de pagamento** para abrir a página **Configuração de taxa de pagamento**, onde você pode configurar taxas de pagamento para várias combinações de bancos, métodos de pagamento, especificações de pagamento, moedas e intervalos de data.</span><span class="sxs-lookup"><span data-stu-id="a53d7-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="a53d7-116">[![Página Configuração de taxa de pagamento](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="a53d7-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="a53d7-117">Na guia **Visão geral**, no campo **Agrupamentos**, especifique para quais bancos você está configurando a taxa de pagamento:</span><span class="sxs-lookup"><span data-stu-id="a53d7-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="a53d7-118">**Tabela** – A taxa é válida para uma conta bancária específica.</span><span class="sxs-lookup"><span data-stu-id="a53d7-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="a53d7-119">**Grupo** – A taxa é válida para um grupo de bancos específico.</span><span class="sxs-lookup"><span data-stu-id="a53d7-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="a53d7-120">**Tudo** – A taxa é válida para todas as contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="a53d7-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="a53d7-121">Se você selecionou **Tabela** ou **Grupo** no campo **Agrupamentos**, no campo **Relação do banco**, selecione a conta bancária específica ou grupo de bancos para o qual você está definindo a taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a53d7-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="a53d7-122">No campo **Método de pagamento**, selecione a forma de pagamento para o pagamento das taxas.</span><span class="sxs-lookup"><span data-stu-id="a53d7-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="a53d7-123">No campo **Especificação de pagamento**, selecione ou insira o código de especificação de pagamento que foi gerado na página **Especificação de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="a53d7-124">A especificação de pagamento é usada com métodos de transferência de fundo eletrônico de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a53d7-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="a53d7-125">No campo **Moeda do pagamento**, selecione a moeda que ativa a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="a53d7-126">Somente as transações que usam a moeda selecionada podem ativar a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="a53d7-127">Se você deixar esse campo em branco, todas as moedas ativarão a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="a53d7-128">No campo **Porcentagem/valor**, selecione o método de cálculo.</span><span class="sxs-lookup"><span data-stu-id="a53d7-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="a53d7-129">As opções são **Valor**, **Porcentagem** e **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="a53d7-130">No campo **Valor da taxa**, especifique o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.</span><span class="sxs-lookup"><span data-stu-id="a53d7-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="a53d7-131">No campo **Moeda da taxa**, especifique o código da moeda para a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="a53d7-132">Selecione a guia **Geral** para exibir ou modificar os detalhes da conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="a53d7-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="a53d7-133">[![Guia Geral](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="a53d7-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="a53d7-134">No campo **Mínimo**, insira o valor mínimo da transação que ativa a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="a53d7-135">No campo **Máximo**, insira o valor máximo da transação que ativa a taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="a53d7-136">Nos campos **De** e **Até**, defina um intervalo de datas para calcular as taxas.</span><span class="sxs-lookup"><span data-stu-id="a53d7-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="a53d7-137">No campo **Taxa mínima**, especifique o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.</span><span class="sxs-lookup"><span data-stu-id="a53d7-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="a53d7-138">No campo **Grupo de impostos**, selecione o grupo de impostos a ser usado para calcular o imposto para o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="a53d7-139">No campo **Grupo de impostos do item**, selecione o grupo de impostos do item a ser usado para calcular o imposto do item para o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="a53d7-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="a53d7-140">Selecione a guia **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="a53d7-141">[![Guia Intervalo](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="a53d7-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="a53d7-142">No campo **Dias**, insira o número de dias entre a data de lançamento (data de desconto) do pagamento e a data de vencimento da nota promissória.</span><span class="sxs-lookup"><span data-stu-id="a53d7-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="a53d7-143">No campo **Porcentagem/valor**, selecione se a especificação é uma porcentagem ou um valor definido.</span><span class="sxs-lookup"><span data-stu-id="a53d7-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="a53d7-144">No campo **Valor da taxa**, insira o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.</span><span class="sxs-lookup"><span data-stu-id="a53d7-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="a53d7-145">Feche a página **Configuração de taxa de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="a53d7-146">Feche a página **Taxa de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a53d7-146">Close the **Payment fee** page.</span></span>
