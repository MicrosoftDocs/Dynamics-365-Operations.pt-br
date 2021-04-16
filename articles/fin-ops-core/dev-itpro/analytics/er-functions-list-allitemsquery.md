---
title: Função de ER ALLITEMSQUERY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ALLITEMSQUERY é usada.
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7995b497a2bd95d4aec9ae6d5f1c3cb790823ea0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746690"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="45559-103">Função de ER ALLITEMSQUERY</span><span class="sxs-lookup"><span data-stu-id="45559-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45559-104">A função `ALLITEMSQUERY` é executada como uma consulta SQL associada.</span><span class="sxs-lookup"><span data-stu-id="45559-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="45559-105">Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="45559-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="45559-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45559-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="45559-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45559-107">Arguments</span></span>

<span data-ttu-id="45559-108">`path`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45559-108">`path`: *Record list*</span></span>

<span data-ttu-id="45559-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45559-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="45559-110">Ele deve conter pelo menos uma relação.</span><span class="sxs-lookup"><span data-stu-id="45559-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="45559-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="45559-111">Return values</span></span>

<span data-ttu-id="45559-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45559-112">*Record list*</span></span>

<span data-ttu-id="45559-113">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="45559-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="45559-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="45559-114">Usage notes</span></span>

<span data-ttu-id="45559-115">O caminho especificado deve ser definido como um caminho de fonte de dados válido de um elemento da fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45559-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="45559-116">Ele também deve conter pelo menos uma relação.</span><span class="sxs-lookup"><span data-stu-id="45559-116">It must also contain at least one relation.</span></span> <span data-ttu-id="45559-117">Os elementos de dados, como a *Cadeia de caracteres* e a *Data* do caminho, devem gerar um erro no construtor de expressões de relatório eletrônico (ER) no momento do design.</span><span class="sxs-lookup"><span data-stu-id="45559-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="45559-118">Quando esta função é aplicada a fontes de dados do tipo *Lista de registros* que se referem a um objeto de aplicativo que pode ser chamado diretamente usando o SQL (por exemplo, uma tabela, entidade ou consulta), ela é executada como uma consulta SQL associada.</span><span class="sxs-lookup"><span data-stu-id="45559-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="45559-119">Caso contrário, ela é executada na memória como a função [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="45559-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="45559-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="45559-120">Example</span></span>

<span data-ttu-id="45559-121">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="45559-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="45559-122">Uma fonte de dados **CustInv** do tipo *Registros de tabela* que se refere à tabela CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="45559-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="45559-123">Uma fonte de dados **FilteredInv** do tipo *Campo calculado* que contém a expressão `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="45559-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="45559-124">Uma **JourLines** do tipo *Campo calculado* que contém a expressão `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="45559-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="45559-125">Ao executar o mapeamento de modelo para chamar a fonte de dados **JourLines**, a seguinte instrução SQL é executada:</span><span class="sxs-lookup"><span data-stu-id="45559-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="45559-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="45559-126">Additional resources</span></span>

[<span data-ttu-id="45559-127">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="45559-127">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]