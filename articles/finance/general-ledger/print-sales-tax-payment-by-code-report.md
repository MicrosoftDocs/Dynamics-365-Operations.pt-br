---
title: Imprimir o relatório Pagamento de imposto sobre vendas por código
description: Este tópico fornece informações sobre as configurações e as ações necessárias para imprimir o relatório Pagamento de imposto sobre vendas por código na contabilidade ou na moeda do código do imposto.
author: anasyash
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 3c3b251aadfa997f453e60b0842f89a6f09eb9cb
ms.sourcegitcommit: 88347d0f0ac862a77f269a05f1801d30dc93586e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "3260246"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="f02ff-103">Imprimir o relatório Pagamento de imposto sobre vendas por código</span><span class="sxs-lookup"><span data-stu-id="f02ff-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="f02ff-104">Para imprimir o **Pagamento de imposto sobre vendas por código**, vá para **Imposto** \> **Consultas e relatórios** \> **Relatórios de imposto sobre vendas** \> **Pagamento de imposto sobre vendas por código**.</span><span class="sxs-lookup"><span data-stu-id="f02ff-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="f02ff-105">Por padrão, os valores do relatório são gerados na moeda contábil da entidade legal para todos os códigos do relatório definidos na página **Códigos de relatório de imposto sobre vendas**.</span><span class="sxs-lookup"><span data-stu-id="f02ff-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="f02ff-106">Também é possível gerar esse relatório para mostrar os valores do pagamento de imposto sobre vendas nas moedas dos códigos de imposto sobre venda de todos os códigos de relatório atribuídos aos códigos de impostos sobre vendas na página **Códigos de imposto sobre vendas**.</span><span class="sxs-lookup"><span data-stu-id="f02ff-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="f02ff-107">Ativar o recurso</span><span class="sxs-lookup"><span data-stu-id="f02ff-107">Turn on the feature</span></span>

<span data-ttu-id="f02ff-108">No espaço de trabalho **Gerenciamento de recursos**, ative o seguinte recurso: **Gerar relatório de pagamento de imposto sobre vendas por código na moeda do código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="f02ff-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="f02ff-109">Executar o relatório</span><span class="sxs-lookup"><span data-stu-id="f02ff-109">Run the report</span></span>

1. <span data-ttu-id="f02ff-110">Vá para **Imposto** \> **Consultas e relatórios** \> **Relatórios de imposto** \> **Pagamento de imposto sobre vendas por código**.</span><span class="sxs-lookup"><span data-stu-id="f02ff-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="f02ff-111">No campo **Moeda do relatório**, selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f02ff-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="f02ff-112">**Moeda contábil** – Imprima os valores do relatório na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="f02ff-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="f02ff-113">**Moeda do código de imposto** – Imprima os valores do relatório nas moedas dos códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="f02ff-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Caixa de diálogo Pagamento de imposto sobre vendas por código](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="f02ff-115">A ilustração a seguir mostra um exemplo do relatório que é gerado.</span><span class="sxs-lookup"><span data-stu-id="f02ff-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="f02ff-116">O relatório mostra que o código de relatório **101** tem a moeda **EUR** se o campo **Moeda do imposto** estiver definido como **EUR** para o código do imposto ao qual o código de relatório está atribuído.</span><span class="sxs-lookup"><span data-stu-id="f02ff-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Exemplo do relatório Pagamento de imposto sobre vendas por código](media/Sales-tax-payment-by-code-2.png)