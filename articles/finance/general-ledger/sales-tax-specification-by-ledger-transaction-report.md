---
title: Relatório Especificação de imposto por transação do razão
description: Este tópico explica como usar o relatório Especificação de imposto por transação do razão para exibir e imprimir informações sobre transações do razão para as quais o imposto é calculado.
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b90ae491605bf59b93137936a2804c4b84c6e1b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204873"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="c0447-103">Relatório Especificação de imposto por transação do razão</span><span class="sxs-lookup"><span data-stu-id="c0447-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0447-104">Este tópico explica como usar o relatório **Especificação de imposto por transação do razão** para exibir e imprimir informações sobre transações do razão para as quais o imposto é calculado.</span><span class="sxs-lookup"><span data-stu-id="c0447-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="c0447-105">Contas fiscais vs. não fiscais</span><span class="sxs-lookup"><span data-stu-id="c0447-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="c0447-106">O relatório **Especificação de imposto por transação do razão** mostra transações de imposto para contas fiscais e não fiscais.</span><span class="sxs-lookup"><span data-stu-id="c0447-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="c0447-107">Essas contas são categorizadas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c0447-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="c0447-108">**Conta fiscal** – Uma conta é considerada fiscal quando uma transação de imposto é lançada, e a conta principal na linha de diário **Imposto** é uma conta fiscal, como uma conta de imposto a pagar ou uma conta de imposto a receber.</span><span class="sxs-lookup"><span data-stu-id="c0447-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="c0447-109">**Conta não fiscal** – Uma conta é considerada não fiscal quando uma transação de imposto é lançada, e a conta principal na transação original é uma conta não fiscal, como uma conta de receita ou uma conta de despesa.</span><span class="sxs-lookup"><span data-stu-id="c0447-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="c0447-110">Para contas fiscais, as colunas **Origem**, **Imposto a receber** e **Imposto a pagar** no relatório mostram **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="c0447-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="c0447-111">Para contas não fiscais, essas colunas mostram valores.</span><span class="sxs-lookup"><span data-stu-id="c0447-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="c0447-112">Filtrando os dados no relatório</span><span class="sxs-lookup"><span data-stu-id="c0447-112">Filtering the data on the report</span></span>

<span data-ttu-id="c0447-113">Quando você gera o relatório, os seguintes campos padrão são disponibilizados.</span><span class="sxs-lookup"><span data-stu-id="c0447-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="c0447-114">Você pode usar esses campos para filtrar os dados que são mostrados no relatório.</span><span class="sxs-lookup"><span data-stu-id="c0447-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="c0447-115">Campo</span><span class="sxs-lookup"><span data-stu-id="c0447-115">Field</span></span>                      | <span data-ttu-id="c0447-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0447-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="c0447-117">Data </span><span class="sxs-lookup"><span data-stu-id="c0447-117">Date</span></span>                       | <span data-ttu-id="c0447-118">Use os campos nas seções **De** e **Para** a fim de definir um intervalo de datas para as transações de imposto.</span><span class="sxs-lookup"><span data-stu-id="c0447-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="c0447-119">Conta principal</span><span class="sxs-lookup"><span data-stu-id="c0447-119">Main account</span></span>               | <span data-ttu-id="c0447-120">Use os campos nas seções **De** e **Para** a fim de definir um intervalo de contas principais.</span><span class="sxs-lookup"><span data-stu-id="c0447-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="c0447-121">Código do imposto</span><span class="sxs-lookup"><span data-stu-id="c0447-121">Sales tax code</span></span>             | <span data-ttu-id="c0447-122">Use os campos nas seções **De** e **Para** a fim de definir um intervalo de códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="c0447-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="c0447-123">Agrupamento</span><span class="sxs-lookup"><span data-stu-id="c0447-123">Grouping</span></span>                   | <span data-ttu-id="c0447-124">Selecione se o relatório deverá ser agrupado pela conta contábil ou pelo código de imposto.</span><span class="sxs-lookup"><span data-stu-id="c0447-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="c0447-125">Subtotal por código de imposto sobre vendas</span><span class="sxs-lookup"><span data-stu-id="c0447-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="c0447-126">Defina essa opção como **Sim** para mostrar subtotais por código de imposto.</span><span class="sxs-lookup"><span data-stu-id="c0447-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="c0447-127">Apenas totais</span><span class="sxs-lookup"><span data-stu-id="c0447-127">Totals only</span></span>                | <span data-ttu-id="c0447-128">Defina essa opção como **Sim** para mostrar apenas totais.</span><span class="sxs-lookup"><span data-stu-id="c0447-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="c0447-129">Somente contas principais</span><span class="sxs-lookup"><span data-stu-id="c0447-129">Main accounts only</span></span>         | <span data-ttu-id="c0447-130">Defina essa opção como **Sim** para incluir apenas contas principais no relatório.</span><span class="sxs-lookup"><span data-stu-id="c0447-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="c0447-131">Mostrando apenas contas não fiscais no relatório</span><span class="sxs-lookup"><span data-stu-id="c0447-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="c0447-132">Para mostrar apenas contas não fiscais no relatório, configure uma condição de filtro, como um asterisco (\*), conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0447-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Relatório mostrando contas não fiscais](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]