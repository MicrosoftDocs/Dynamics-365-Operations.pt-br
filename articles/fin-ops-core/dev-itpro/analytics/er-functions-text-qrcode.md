---
title: Função de ER QRCODE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) QRCODE é usada.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: bac0910d213ee05a2a7a7b218a6714d4f935be16
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916743"
---
# <span data-ttu-id="07758-103"><a name="QRCODE">Função de ER QRCODE</a></span><span class="sxs-lookup"><span data-stu-id="07758-103"><a name="QRCODE">QRCODE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07758-104">A função `QRCODE` retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário.</span><span class="sxs-lookup"><span data-stu-id="07758-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="07758-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="07758-105">Syntax</span></span>

```
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="07758-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="07758-106">Arguments</span></span>

<span data-ttu-id="07758-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="07758-107">`text`: *String*</span></span>

<span data-ttu-id="07758-108">Um valor de *Cadeia de caracteres* que representa o texto original.</span><span class="sxs-lookup"><span data-stu-id="07758-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="07758-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="07758-109">Return values</span></span>

<span data-ttu-id="07758-110">*Contêiner*</span><span class="sxs-lookup"><span data-stu-id="07758-110">*Container*</span></span>

<span data-ttu-id="07758-111">O fluxo binário resultante.</span><span class="sxs-lookup"><span data-stu-id="07758-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="07758-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="07758-112">Example</span></span>

<span data-ttu-id="07758-113">Você pode configurar um formato de relatório eletrônico (ER) para gerar um documento de saída em um formato do Microsoft Office (pastas de trabalho do Excel ou documentos do Word) usando um modelo predefinido.</span><span class="sxs-lookup"><span data-stu-id="07758-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="07758-114">Esse modelo pode conter um objeto **Imagem** (pasta de trabalho do Excel) ou um **Controle de Conteúdo de Imagem** (documento do Word) como um espaço reservado para uma imagem de código QR.</span><span class="sxs-lookup"><span data-stu-id="07758-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="07758-115">Você deve adicionar ao formato de ER configurado um elemento **Célula** que será usado para preencher esse espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="07758-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="07758-116">Para especificar quais informações serão armazenadas em um código QR, você precisa definir uma associação para esse elemento **Célula**.</span><span class="sxs-lookup"><span data-stu-id="07758-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="07758-117">Por exemplo, você pode configurar essa associação como contendo a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="07758-117">For example, you can configure such binding as containing the following expression:</span></span>

```
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="07758-118">Ao executar o formato de ER configurado, o valor de texto do campo **LabelText** da fonte de dados **model.ListOfShelfLabels** será usado para gerar uma imagem de código QR.</span><span class="sxs-lookup"><span data-stu-id="07758-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="07758-119">Essa imagem substituirá um espaço reservado de imagem de código QR no modelo de documento usado para gerar um documento de saída.</span><span class="sxs-lookup"><span data-stu-id="07758-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="07758-120">Quando essa imagem do documento gerado for digitalizada, ela retornará o texto obtido do campo **LabelText** da fonte de dados **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="07758-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="07758-121">Para obter mais informações, consulte [Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="07758-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07758-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="07758-122">Additional resources</span></span>

[<span data-ttu-id="07758-123">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="07758-123">Text functions</span></span>](er-functions-category-text.md)