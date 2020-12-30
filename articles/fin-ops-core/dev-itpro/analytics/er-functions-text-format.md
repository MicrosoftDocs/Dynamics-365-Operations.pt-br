---
title: Função de ER FORMAT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FORMAT é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 8b347a7209ee543f6bd687c2864203eb632d6a4a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688404"
---
# <a name="format-er-function"></a><span data-ttu-id="82f44-103">Função de ER FORMAT</span><span class="sxs-lookup"><span data-stu-id="82f44-103">FORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82f44-104">A função `FORMAT` retorna a cadeia de caracteres especificada como um valor de *Cadeia de caracteres* após ela ser formatada, substituindo todas as ocorrências de **%N** pelo *N* º argumento.</span><span class="sxs-lookup"><span data-stu-id="82f44-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N* th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="82f44-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82f44-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="82f44-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="82f44-106">Arguments</span></span>

<span data-ttu-id="82f44-107">`string`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="82f44-107">`string`: *String*</span></span>

<span data-ttu-id="82f44-108">Uma referência a uma fonte de dados do tipo *Cadeia de caracteres* que deve ser formatada.</span><span class="sxs-lookup"><span data-stu-id="82f44-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="82f44-109">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="82f44-109">This argument is required.</span></span>

<span data-ttu-id="82f44-110">`argument 1`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="82f44-110">`argument 1`: *String*</span></span>

<span data-ttu-id="82f44-111">O primeiro argumento, que é usado para substituir as ocorrências de **%1**.</span><span class="sxs-lookup"><span data-stu-id="82f44-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="82f44-112">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="82f44-112">This argument is required.</span></span>

<span data-ttu-id="82f44-113">`argument N`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="82f44-113">`argument N`: *String*</span></span>

<span data-ttu-id="82f44-114">O *N* º argumento, que é usado para substituir as ocorrências de **%2**, **%3** etc.</span><span class="sxs-lookup"><span data-stu-id="82f44-114">The *N* th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="82f44-115">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="82f44-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="82f44-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="82f44-116">Return values</span></span>

<span data-ttu-id="82f44-117">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="82f44-117">*String*</span></span>

<span data-ttu-id="82f44-118">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="82f44-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="82f44-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="82f44-119">Usage notes</span></span>

<span data-ttu-id="82f44-120">Se o argumento não é fornecido para um parâmetro, o parâmetro será devolvido como **"%N"** na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="82f44-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="82f44-121">Para valores do tipo *Real*, a conversão de cadeia de caracteres padrão é limitada a duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="82f44-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="82f44-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="82f44-122">Example</span></span>

<span data-ttu-id="82f44-123">Na ilustração a seguir, a fonte de dados **PaymentModel** retorna uma lista de registros de clientes usando o componente **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="82f44-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="82f44-124">Ela retorna o valor de data de processamento usando o campo **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="82f44-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="82f44-125">No formato de relatório eletrônico (ER) que foi projetado para gerar um arquivo eletrônico para clientes selecionados, **PaymentModel** é selecionada como uma fonte de dados e controla o fluxo do processo.</span><span class="sxs-lookup"><span data-stu-id="82f44-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="82f44-126">Se um cliente selecionado for interrompido na data em que o relatório é processado, uma exceção será gerada para informar o usuário.</span><span class="sxs-lookup"><span data-stu-id="82f44-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="82f44-127">A fórmula que é criada para este tipo de controle de processamento pode usar os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="82f44-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="82f44-128">Rótulo SYS70894, que tem o texto a seguir:</span><span class="sxs-lookup"><span data-stu-id="82f44-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="82f44-129">**Para o idioma EN-US:** "Nothing to print"</span><span class="sxs-lookup"><span data-stu-id="82f44-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="82f44-130">**Para o idioma DE** "Nichts zu drucken"</span><span class="sxs-lookup"><span data-stu-id="82f44-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="82f44-131">Rótulo SYS18389, que tem o texto a seguir:</span><span class="sxs-lookup"><span data-stu-id="82f44-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="82f44-132">**Para o idioma EN-US**: "Customer %1 is stopped for %2".</span><span class="sxs-lookup"><span data-stu-id="82f44-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="82f44-133">**Para o idioma DE**: "Debitor '%1' wird für %2 gesperrt".</span><span class="sxs-lookup"><span data-stu-id="82f44-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="82f44-134">Veja a expressão que pode ser criada.</span><span class="sxs-lookup"><span data-stu-id="82f44-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="82f44-135">Se um relatório for processado para o cliente **Litware Retail** em 17 de dezembro de 2015, na cultura **EN-US** e no idioma **EN-US**, esta fórmula retornará o seguinte texto, que pode ser apresentado ao usuário como uma mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="82f44-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="82f44-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="82f44-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="82f44-137">Se o mesmo relatório for processado para o cliente **Litware Retail** em 17 de dezembro de 2015, na cultura **DE** e no idioma **DE**, esta fórmula retornará o seguinte texto, que usa um formato de data diferente:</span><span class="sxs-lookup"><span data-stu-id="82f44-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="82f44-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="82f44-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="82f44-139">A seguinte sintaxe será aplicada em fórmulas de ER para rótulos:</span><span class="sxs-lookup"><span data-stu-id="82f44-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="82f44-140">**Para rótulos de recursos no aplicativo Microsoft Dynamics 365 Finance:** **\@X**, onde **X** é a ID do rótulo na AOT (Árvore de Objetos de Aplicativo)</span><span class="sxs-lookup"><span data-stu-id="82f44-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="82f44-141">**Para rótulos que residem nas configurações de ER:** **@"GER_LABEL:X"**, onde **X** é a ID do rótulo na configuração de ER</span><span class="sxs-lookup"><span data-stu-id="82f44-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82f44-142">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="82f44-142">Additional resources</span></span>

[<span data-ttu-id="82f44-143">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="82f44-143">Text functions</span></span>](er-functions-category-text.md)
