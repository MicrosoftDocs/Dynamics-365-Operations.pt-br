---
title: Imposto retido na fonte em transações de compra
description: Para fornecedores que são responsáveis por retenção de imposto na fonte, você pode atribuir o **Grupo de imposto retido na fonte** padrão na página **Todos os fornecedores**.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: faeaf0746532875d3517a208c9c338c112bf2c77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816874"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="50913-103">Imposto retido na fonte em transações de compra</span><span class="sxs-lookup"><span data-stu-id="50913-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="50913-104">Para fornecedores que são responsáveis por retenção de imposto na fonte, você pode atribuir o **Grupo de imposto retido na fonte** padrão na página **Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="50913-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="50913-105">Vá para **Painel de navegação > Módulos > Contas a pagar > Fornecedores > Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="50913-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="50913-106">Clique na respectiva conta de fornecedor e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="50913-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="50913-107">Na guia **Fatura e entrega**, defina o campo **Calcular imposto retido na fonte** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="50913-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="50913-108">O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** não estiver ativado para esse fornecedor nos dados.</span><span class="sxs-lookup"><span data-stu-id="50913-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="50913-109">Selecione um grupo de retenção de imposto na fonte no **Grupo de retenção de imposto na fonte**.</span><span class="sxs-lookup"><span data-stu-id="50913-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="50913-110">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="50913-110">Click **Save**.</span></span>

<span data-ttu-id="50913-111">Para itens/serviços que são responsáveis por retenção de imposto, você pode atribuir o **Grupo de imposto retido na fonte** em **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="50913-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="50913-112">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="50913-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="50913-113">Clique no respectivo número do item e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="50913-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="50913-114">Na guia **Compra**, clique em **Calcular imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="50913-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="50913-115">O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** estiver definido como **Sim** para esse item na guia **Compra** na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="50913-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="50913-116">Selecione um grupo de retenção imposto na fonte do item na lista **Grupos de retenção de imposto na fonte do item**.</span><span class="sxs-lookup"><span data-stu-id="50913-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="50913-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="50913-117">Click **Save**.</span></span>

<span data-ttu-id="50913-118">Os grupos de retenção de imposto na fonte e os grupos de retenção de imposto na fonte do item podem ser atribuídos em páginas:</span><span class="sxs-lookup"><span data-stu-id="50913-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="50913-119">**Ordem de compra**</span><span class="sxs-lookup"><span data-stu-id="50913-119">**Purchase order**</span></span>
- <span data-ttu-id="50913-120">**Fatura de fornecedor**</span><span class="sxs-lookup"><span data-stu-id="50913-120">**Vendor invoice**</span></span>
- <span data-ttu-id="50913-121">**Diário de faturas**</span><span class="sxs-lookup"><span data-stu-id="50913-121">**Invoice journal**</span></span>

<span data-ttu-id="50913-122">O grupo de retenção de imposto na fonte padrão e o grupo de retenção de imposto na fonte do item serão transportados para as linhas ao criar **Ordens de compra** e/ou **Faturas de fornecedor pendentes**.</span><span class="sxs-lookup"><span data-stu-id="50913-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="50913-123">Para o **Diário de faturas de fornecedores**, você pode alternar para **Calcular imposto retido na fonte** e selecionar **Grupo de retenção de imposto na fonte do item** na guia **Geral** do diário.</span><span class="sxs-lookup"><span data-stu-id="50913-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="50913-124">O valor temporário do imposto retido na fonte está disponível no campo **Imposto retido na fonte ajustado** da guia **Totais** na página **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="50913-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![O imposto retido na fonte está incluído na ordem de compra](media/withholding-tax-adjusted.png)

<span data-ttu-id="50913-126">O imposto retido na fonte é calculado no **Diário de pagamentos do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="50913-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="50913-127">Você pode ajustar manualmente os códigos aplicáveis de retenção de imposto na fonte, bem como os valores reais do imposto retido na fonte na guia **Imposto retido na fonte** na página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="50913-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![A retenção pode ser ajustada manualmente na página Liquidar transações](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="50913-129">O valor do imposto retido na fonte derivado será deduzido do pagamento do fornecedor e lançado na **Conta do imposto retido na fonte** em um comprovante relacionado.</span><span class="sxs-lookup"><span data-stu-id="50913-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Conta do imposto retido na fonte mostrando um comprovante relacionado](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]