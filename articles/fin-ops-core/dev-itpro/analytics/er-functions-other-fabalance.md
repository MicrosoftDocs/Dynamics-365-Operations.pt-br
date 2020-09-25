---
title: Função de ER FA_BALANCE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FA_BALANCE é usada.
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
ms.openlocfilehash: 6a969e3a484208388fd82d7a714bee27b7fe64a9
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744158"
---
# <a name="fa_balance-er-function"></a><span data-ttu-id="bbe05-103">Função de ER FA_BALANCE</span><span class="sxs-lookup"><span data-stu-id="bbe05-103">FA_BALANCE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bbe05-104">A função `FA_BALANCE` retorna um valor de *Contêiner (registro)* que consiste em dados do saldo de ativo fixo para o item de ativo fixo, o código do método de depreciação, o ano do relatório e a data do relatório especificados.</span><span class="sxs-lookup"><span data-stu-id="bbe05-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbe05-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bbe05-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="bbe05-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bbe05-106">Arguments</span></span>

<span data-ttu-id="bbe05-107">`fixed asset code`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bbe05-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="bbe05-108">Um valor de *Cadeia de caracteres* que representa o código de um item de ativo fixo para o qual o saldo é calculado.</span><span class="sxs-lookup"><span data-stu-id="bbe05-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="bbe05-109">`value model code`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bbe05-109">`value model code`: *String*</span></span>

<span data-ttu-id="bbe05-110">Um valor de *Cadeia de caracteres* que representa o código de um método de depreciação para o qual o saldo é calculado.</span><span class="sxs-lookup"><span data-stu-id="bbe05-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="bbe05-111">`reporting year`: *Valor de enumeração*</span><span class="sxs-lookup"><span data-stu-id="bbe05-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="bbe05-112">Um valor de enumeração da enumeração de aplicativo **AssetYear** que define um período para o cálculo do saldo.</span><span class="sxs-lookup"><span data-stu-id="bbe05-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="bbe05-113">`reporting date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="bbe05-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="bbe05-114">Um valor de *Data* que define uma data para o cálculo do saldo.</span><span class="sxs-lookup"><span data-stu-id="bbe05-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="bbe05-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bbe05-115">Return values</span></span>

<span data-ttu-id="bbe05-116">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="bbe05-116">*Container (record)*</span></span>

<span data-ttu-id="bbe05-117">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="bbe05-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="bbe05-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bbe05-118">Example</span></span>

<span data-ttu-id="bbe05-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` retorna o contêiner de dados de saldos para o ativo fixo **COMP-000001** que foi preparado para o método de depreciação **Atual** na data atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bbe05-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbe05-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bbe05-120">Additional resources</span></span>

[<span data-ttu-id="bbe05-121">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="bbe05-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
