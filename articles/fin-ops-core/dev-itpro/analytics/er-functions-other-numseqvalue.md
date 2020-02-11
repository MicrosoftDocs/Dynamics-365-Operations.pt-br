---
title: Função de ER NUMSEQVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMSEQVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d68784524a5639d8d447daa2cda940680d795542
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915823"
---
# <span data-ttu-id="91cfa-103"><a name="NUMSEQVALUE">Função de ER NUMSEQVALUE</a></span><span class="sxs-lookup"><span data-stu-id="91cfa-103"><a name="NUMSEQVALUE">NUMSEQVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91cfa-104">A função `NUMSEQVALUE` retorna um valor de *Cadeia de caracteres* que representa o novo valor gerado de uma sequência numérica, com base na sequência numérica, no escopo e na ID do escopo especificados.</span><span class="sxs-lookup"><span data-stu-id="91cfa-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="91cfa-105">A ID do escopo é igual ao código da empresa que é fornecido pelo contexto no qual o formato de relatório eletrônico (ER) é executado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="91cfa-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="91cfa-106">Syntax 1</span></span>

```
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="91cfa-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="91cfa-107">Syntax 2</span></span>

```
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="91cfa-108">Sintaxe 3</span><span class="sxs-lookup"><span data-stu-id="91cfa-108">Syntax 3</span></span>

```
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="91cfa-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="91cfa-109">Arguments</span></span>

<span data-ttu-id="91cfa-110">`number sequence code`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="91cfa-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="91cfa-111">Um valor de texto que representa o código da sequência numérica em que um novo valor é necessário.</span><span class="sxs-lookup"><span data-stu-id="91cfa-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="91cfa-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="91cfa-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="91cfa-113">Um valor *Int64* que representa a ID de registro de um registro na tabela NumberSequenceTable que contém a definição da sequência numérica em que um novo valor é necessário.</span><span class="sxs-lookup"><span data-stu-id="91cfa-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="91cfa-114">`scope type`: *Valor de enumeração*</span><span class="sxs-lookup"><span data-stu-id="91cfa-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="91cfa-115">Um valor de enumeração da enumeração **ERExpressionNumberSequenceScopeType** que define o escopo da sequência numérica em que um novo valor é necessário.</span><span class="sxs-lookup"><span data-stu-id="91cfa-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="91cfa-116">Os tipos de escopo disponíveis são **Compartilhado**, **Entidade legal** e **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="91cfa-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="91cfa-117">`scope ID`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="91cfa-117">`scope ID`: *String*</span></span>

<span data-ttu-id="91cfa-118">Um valor de *Cadeia de caracteres* que identifica o escopo, com base no tipo de escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="91cfa-119">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="91cfa-119">Return values</span></span>

<span data-ttu-id="91cfa-120">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="91cfa-120">*String*</span></span>

<span data-ttu-id="91cfa-121">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="91cfa-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="91cfa-122">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="91cfa-122">Usage notes</span></span>

<span data-ttu-id="91cfa-123">Para o tipo de escopo **Compartilhado**, especifique uma cadeia de caracteres vazia como a ID do escopo.</span><span class="sxs-lookup"><span data-stu-id="91cfa-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="91cfa-124">Para os tipos de escopo **Empresa** e **Entidade legal**, especifique o código da empresa como a ID do escopo.</span><span class="sxs-lookup"><span data-stu-id="91cfa-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="91cfa-125">Se você especificar uma cadeia de caracteres vazia como a ID do escopo para esses tipos de escopo, o código atual da empresa será usado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="91cfa-126">Quando a sintaxe 1 é usada, a sequência numérica é solicitada para o tipo de escopo **Empresa** e o código da empresa é fornecido pelo contexto no qual o formato de ER é executado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="91cfa-127">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="91cfa-127">Example 1</span></span>

<span data-ttu-id="91cfa-128">No formato de ER, você define a fonte de dados **AskNumSeq** do tipo *Parâmetro de entrada de usuário*.</span><span class="sxs-lookup"><span data-stu-id="91cfa-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="91cfa-129">Essa fonte de dados se refere ao tipo de dados estendido (EDT) da **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="91cfa-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="91cfa-130">Em seguida, você define a fonte de dados **NumSeq** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="91cfa-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="91cfa-131">Essa fonte de dados contém a expressão `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="91cfa-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="91cfa-132">Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica especificada no tempo de execução inserindo seu código na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91cfa-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="91cfa-133">A sequência numérica é solicitada para o tipo de escopo **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="91cfa-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="91cfa-134">O código da empresa é fornecido pelo contexto no qual o formato de ER é executado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="91cfa-135">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="91cfa-135">Example 2</span></span>

<span data-ttu-id="91cfa-136">As seguintes fontes de dados são definidas no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="91cfa-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="91cfa-137">A fonte de dados **LedgerParms** do tipo *Tabela*.</span><span class="sxs-lookup"><span data-stu-id="91cfa-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="91cfa-138">Essa fonte de dados se refere à tabela LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="91cfa-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="91cfa-139">A fonte de dados **NumSeq** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="91cfa-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="91cfa-140">Essa fonte de dados contém a expressão `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="91cfa-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="91cfa-141">Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica que foi configurado em parâmetros de contabilidade para a empresa que fornece o contexto no qual o formato ER é executado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="91cfa-142">Esta sequência numérica identifica exclusivamente diários e funciona como o número de lote que vincula as transações juntas.</span><span class="sxs-lookup"><span data-stu-id="91cfa-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="91cfa-143">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="91cfa-143">Example 3</span></span>

<span data-ttu-id="91cfa-144">As seguintes fontes de dados são definidas no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="91cfa-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="91cfa-145">A fonte de dados **enumScope** do tipo *enumeração* do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="91cfa-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="91cfa-146">Essa fonte de dados se refere à enumeração **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="91cfa-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="91cfa-147">A fonte de dados **NumSeq** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="91cfa-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="91cfa-148">Essa fonte de dados contém a expressão `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="91cfa-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="91cfa-149">Quando a fonte de dados **NumSeq** é chamada, ela retorna o novo valor gerado da sequência numérica **Gene\_1** que foi configurado para a empresa que fornece o contexto no qual o formato ER é executado.</span><span class="sxs-lookup"><span data-stu-id="91cfa-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="91cfa-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="91cfa-150">Additional resources</span></span>

[<span data-ttu-id="91cfa-151">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="91cfa-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)