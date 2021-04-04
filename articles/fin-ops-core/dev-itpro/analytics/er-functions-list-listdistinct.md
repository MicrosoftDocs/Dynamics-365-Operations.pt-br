---
title: Função LISTDISTINCT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTDISTINCT é usada.
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: f20565d73cea8d0cc1361bd03cda86a79a97955e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563815"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="23fff-103">Função LISTDISTINCT ER</span><span class="sxs-lookup"><span data-stu-id="23fff-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="23fff-104">A função `LISTDISTINCT` calcula a expressão especificada como um seletor para cada registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23fff-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="23fff-105">Ela retorna um novo valor *Lista de registros* que contém um único registro para cada valor de seletor único.</span><span class="sxs-lookup"><span data-stu-id="23fff-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="23fff-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="23fff-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="23fff-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="23fff-107">Arguments</span></span>

<span data-ttu-id="23fff-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="23fff-108">`list`: *Record list*</span></span>

<span data-ttu-id="23fff-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="23fff-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="23fff-110">`selector`: *tipo de dados primitivos*</span><span class="sxs-lookup"><span data-stu-id="23fff-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="23fff-111">Uma expressão válida que é usada para calcular um valor de seletor para cada registro na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23fff-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="23fff-112">Os seguintes tipos de dados têm suporte para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="23fff-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="23fff-113">Booleano</span><span class="sxs-lookup"><span data-stu-id="23fff-113">Boolean</span></span>
- <span data-ttu-id="23fff-114">Data </span><span class="sxs-lookup"><span data-stu-id="23fff-114">Date</span></span>
- <span data-ttu-id="23fff-115">Data e Hora</span><span class="sxs-lookup"><span data-stu-id="23fff-115">DateTime</span></span>
- <span data-ttu-id="23fff-116">Guid</span><span class="sxs-lookup"><span data-stu-id="23fff-116">GUID</span></span>
- <span data-ttu-id="23fff-117">Inteiro</span><span class="sxs-lookup"><span data-stu-id="23fff-117">Integer</span></span>
- <span data-ttu-id="23fff-118">Int64</span><span class="sxs-lookup"><span data-stu-id="23fff-118">Int64</span></span>
- <span data-ttu-id="23fff-119">Real</span><span class="sxs-lookup"><span data-stu-id="23fff-119">Real</span></span>
- <span data-ttu-id="23fff-120">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="23fff-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="23fff-121">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="23fff-121">Return values</span></span>

<span data-ttu-id="23fff-122">*Registrar lista*</span><span class="sxs-lookup"><span data-stu-id="23fff-122">*Record list*</span></span>

<span data-ttu-id="23fff-123">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="23fff-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="23fff-124">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="23fff-124">Usage notes</span></span>

<span data-ttu-id="23fff-125">A estrutura da lista criada corresponde à estrutura da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23fff-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="23fff-126">O mesmo valor do seletor pode ser calculado para vários registros na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23fff-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="23fff-127">Nesse caso, os valores de campo do registro correspondente na lista criada são iguais aos valores do primeiro registro da lista especificada para as quais o valor do seletor é calculado.</span><span class="sxs-lookup"><span data-stu-id="23fff-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="23fff-128">A execução dessa função é feita em qualquer fonte de dados de [relatório eletrônico (ER)](general-electronic-reporting.md) do tipo de *Lista de registros* presente na memória.</span><span class="sxs-lookup"><span data-stu-id="23fff-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="23fff-129">A fonte de dados **GROUPBY** também pode ser usada para gerar a lista de registros para a qual é calculado o seletor que tem valores distintos.</span><span class="sxs-lookup"><span data-stu-id="23fff-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="23fff-130">No entanto, de uma perspectiva de desempenho e de consumo de memória, convém usar a função `LISTDISTINCT` do que a fonte de de dados **GROUPBY**, pois a execução da função é realizada na memória.</span><span class="sxs-lookup"><span data-stu-id="23fff-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="23fff-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="23fff-131">Example</span></span>

<span data-ttu-id="23fff-132">O exemplo a seguir mostra como é possível obter a lista de números de conta de cliente únicos para os quais pelo menos uma fatura de venda ou de projeto foi emitida durante um período específico.</span><span class="sxs-lookup"><span data-stu-id="23fff-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="23fff-133">Insira a fonte de dados **SalesInvoice** do tipo `Record list` que se refere à tabela do aplicativo **CustInvoiceJour** e filtre as faturas de venda para períodos específicos.</span><span class="sxs-lookup"><span data-stu-id="23fff-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="23fff-134">O campo `InvoiceAccount` dessa fonte de dados retorna o número da conta de um cliente faturado.</span><span class="sxs-lookup"><span data-stu-id="23fff-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="23fff-135">Insira a fonte de dados **ProjectInvoice** do tipo `Record list` que se refere à tabela do aplicativo **ProjInvoiceJour** e filtre as faturas do projeto para períodos específicos.</span><span class="sxs-lookup"><span data-stu-id="23fff-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="23fff-136">O campo `InvoiceAccount` dessa fonte de dados retorna o número da conta de um cliente faturado.</span><span class="sxs-lookup"><span data-stu-id="23fff-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="23fff-137">Configura a fonte de dados **AllInvoices** do tipo `Calculated field` que contém a expressão `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="23fff-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="23fff-138">Essa fonte de dados retorna a lista unida de faturas de venda e de projeto.</span><span class="sxs-lookup"><span data-stu-id="23fff-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="23fff-139">Configure a fonte de dados **InvoicedCustomer** do tipo `Record list` que contém a expressão `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="23fff-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="23fff-140">Essa fonte de dados retorna uma nova lista que contém um único registro para cada cliente único que foi faturado durante o período definido.</span><span class="sxs-lookup"><span data-stu-id="23fff-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="23fff-141">O campo `InvoiceAccount` desta lista contém um número de conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="23fff-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23fff-142">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="23fff-142">Additional resources</span></span>

[<span data-ttu-id="23fff-143">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="23fff-143">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]