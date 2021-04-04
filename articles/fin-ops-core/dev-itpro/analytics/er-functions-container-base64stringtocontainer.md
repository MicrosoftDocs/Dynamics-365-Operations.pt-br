---
title: Função de ER Base64StringToContainer
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) Base64StringToContainer é usada.
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 612590dacc1887b87677c12eddaef42660a7a154
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561533"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="56fea-103">Função de ER Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="56fea-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56fea-104">A [função](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *[Contêiner](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="56fea-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="56fea-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="56fea-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="56fea-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="56fea-106">Arguments</span></span>

<span data-ttu-id="56fea-107">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="56fea-107">`input`: *String*</span></span>

<span data-ttu-id="56fea-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="56fea-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="56fea-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="56fea-109">Return values</span></span>

<span data-ttu-id="56fea-110">*Contêiner*</span><span class="sxs-lookup"><span data-stu-id="56fea-110">*Container*</span></span>

<span data-ttu-id="56fea-111">O valor binário resultante no formato binário grande de objeto (BLOB).</span><span class="sxs-lookup"><span data-stu-id="56fea-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="56fea-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="56fea-112">Usage notes</span></span>

<span data-ttu-id="56fea-113">A exceção "Parâmetro não válido" será lançada se a cadeia de caracteres de entrada não fornecer um grupo Base64 correto de esquemas de codificação de binário para texto.</span><span class="sxs-lookup"><span data-stu-id="56fea-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="56fea-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="56fea-114">Example</span></span>

<span data-ttu-id="56fea-115">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="56fea-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="56fea-116">A fonte de dados **DocuTypeGroupEnum** raiz do tipo *Dynamics 365 for Operations / Enumeração* que se refere à enumeração de aplicativo **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="56fea-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="56fea-117">A fonte de dados **Cliente** raiz do tipo *Dynamics 365 for Operations / Registros de tabela* que se refere ao aplicativo de tabela **CustTable**</span><span class="sxs-lookup"><span data-stu-id="56fea-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="56fea-118">A fonte de dados **\#Media** do tipo *Campo calculado* que é configurada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="56fea-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="56fea-119">Ela é adicionado como uma fonte de dados filho da fonte de dados **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="56fea-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="56fea-120">Ela contém a expressão `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="56fea-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="56fea-121">A fonte de dados **\#MediaAsBase64String** do tipo *Campo calculado* que é configurada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="56fea-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="56fea-122">Ela é adicionado como uma fonte de dados filho da fonte de dados **Customer.'\#Media'**.</span><span class="sxs-lookup"><span data-stu-id="56fea-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="56fea-123">Ela contém a expressão `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="56fea-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="56fea-124">A fonte de dados **\#BlobFomBase64** do tipo *Campo calculado* que é configurada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="56fea-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="56fea-125">Ela é adicionado como uma fonte de dados filho da fonte de dados **Customer.'\#Media'**.</span><span class="sxs-lookup"><span data-stu-id="56fea-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="56fea-126">Ela contém a expressão `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="56fea-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="56fea-127">Neste exemplo, a fonte de dados **\#MediaAsBase64String** codifica o conteúdo binário do anexo de mídia atual como texto que representa um grupo Base64 de esquemas de codificação de binário para texto.</span><span class="sxs-lookup"><span data-stu-id="56fea-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="56fea-128">A fonte de dados **\#BlobFomBase64** decodifica a cadeia de caracteres Base64 e retorna um valor binário no formato BLOB.</span><span class="sxs-lookup"><span data-stu-id="56fea-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Exemplo de fonte de dados na página Designer de mapeamento do modelo de ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="56fea-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="56fea-130">Additional resources</span></span>

[<span data-ttu-id="56fea-131">Funções de contêiner</span><span class="sxs-lookup"><span data-stu-id="56fea-131">Container functions</span></span>](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]