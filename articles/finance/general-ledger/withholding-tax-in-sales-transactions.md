---
title: Imposto retido na fonte em transações de venda
description: Este tópico lista as etapas para evitar o cálculo da imposto retido na fonte para clientes selecionados. Para clientes que especificam o imposto retido na fonte em seus pagamentos, você pode atribuir o grupo de retenção de imposto na fonte padrão.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: c50f6df1c63c91107da65f463934565f786d6ccd
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060701"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="b838e-104">Imposto retido na fonte em transações de venda</span><span class="sxs-lookup"><span data-stu-id="b838e-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="b838e-105">Este tópico lista as etapas para evitar o cálculo da imposto retido na fonte para clientes selecionados.</span><span class="sxs-lookup"><span data-stu-id="b838e-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="b838e-106">Para clientes que especificam o imposto retido na fonte em seus pagamentos, você pode atribuir o **Grupo de retenção de imposto na fonte** padrão na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="b838e-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="b838e-107">Vá para **Painel de Navegação > Módulos > Contas a receber > Clientes > Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="b838e-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="b838e-108">Clique na respectiva conta de cliente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b838e-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="b838e-109">Na guia **Fatura e entrega**, defina o campo **Calcular imposto retido na fonte** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b838e-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="b838e-110">O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** não estiver ativado para esse cliente nos dados mestres.</span><span class="sxs-lookup"><span data-stu-id="b838e-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="b838e-111">Selecione um grupo de retenção de imposto na fonte no **Grupo de retenção de imposto na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b838e-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="b838e-112">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b838e-112">Click **Save**.</span></span>

<span data-ttu-id="b838e-113">Para itens/serviços que são responsáveis por retenção de imposto, você pode atribuir o **Grupo de imposto retido na fonte** em **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="b838e-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="b838e-114">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="b838e-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="b838e-115">Clique no respectivo número do item e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b838e-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="b838e-116">Na guia **Vender**, clique em **Calcular imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="b838e-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="b838e-117">O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** estiver definido como **Sim** para esse item na guia **Vender** na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="b838e-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="b838e-118">Selecione um grupo de retenção imposto na fonte do item na lista **Grupos de retenção de imposto na fonte do item**.</span><span class="sxs-lookup"><span data-stu-id="b838e-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="b838e-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b838e-119">Click **Save**.</span></span>

<span data-ttu-id="b838e-120">Os grupos de retenção de imposto na fonte e os grupos de retenção de imposto na fonte do item podem ser atribuídos usando a página **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="b838e-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="b838e-121">O grupo de retenção de imposto na fonte padrão e o grupo de retenção de imposto na fonte do item serão usados como entradas padrão nas linhas da ordem de venda quando você criar uma nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b838e-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="b838e-122">O imposto retido na fonte é calculado e lançado com o **Diário de pagamentos do cliente**.</span><span class="sxs-lookup"><span data-stu-id="b838e-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="b838e-123">Você pode ajustar manualmente o código aplicável de retenção de imposto na fonte, bem como o valor real do imposto retido na fonte na guia **Imposto retido na fonte** na página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="b838e-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="b838e-124">O valor do imposto retido na fonte calculado será deduzido do pagamento do cliente e lançado na conta de **Contrapartida do imposto retido na fonte** em um comprovante relacionado.</span><span class="sxs-lookup"><span data-stu-id="b838e-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>
