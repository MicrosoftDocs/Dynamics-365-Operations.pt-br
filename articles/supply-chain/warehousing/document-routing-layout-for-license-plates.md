---
title: Layout de roteiro de documentos para etiquetas de placa de licença
description: Este tópico descreve como usar métodos de formatação para imprimir valores em etiquetas.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 62d4301f9dbe301c2a2573102d911a8d0ec58eb0
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261299"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="d22b0-103">Layout de roteiro de documentos para etiquetas de placa de licença</span><span class="sxs-lookup"><span data-stu-id="d22b0-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d22b0-104">O layout de circulação de documentos define o layout dos rótulos de placa de licença e os dados impressos neles.</span><span class="sxs-lookup"><span data-stu-id="d22b0-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="d22b0-105">Os pontos do disparador de impressão são configurados quando você configura itens de menu e modelos de trabalho de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="d22b0-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="d22b0-106">Em um cenário típico, os auxiliares de recebimento de depósito imprimem etiquetas de placa de licença imediatamente após registrarem o conteúdo dos paletes que chegam na área de recebimento.</span><span class="sxs-lookup"><span data-stu-id="d22b0-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="d22b0-107">As etiquetas físicas são aplicadas aos paletes.</span><span class="sxs-lookup"><span data-stu-id="d22b0-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="d22b0-108">Em seguida, eles podem ser usados para validação como parte do processo de retirada que segue e operações de separação de saída futura.</span><span class="sxs-lookup"><span data-stu-id="d22b0-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="d22b0-109">Você pode imprimir etiquetas altamente complexas, desde que o dispositivo de impressão possa interpretar o texto enviado a ela.</span><span class="sxs-lookup"><span data-stu-id="d22b0-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="d22b0-110">Por exemplo, um layout de linguagem de programação zebra (ZPL) que inclui um código de barras pode ser semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="d22b0-111">Como parte do processo de impressão de etiquetas, o texto `$LicensePlateId$` neste exemplo será substituído por um valor de dados.</span><span class="sxs-lookup"><span data-stu-id="d22b0-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="d22b0-112">Para ver os valores que serão impressos, vá para **Gerenciamento de depósito \> Consultas e relatórios \> Etiquetas de placa de licença**.</span><span class="sxs-lookup"><span data-stu-id="d22b0-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="d22b0-113">Várias ferramentas de geração de etiquetas amplamente disponíveis podem ajudá-lo a formatar o texto para o layout da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d22b0-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="d22b0-114">Muitas dessas ferramentas dão suporte ao formato `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="d22b0-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="d22b0-115">Além disso, o Microsoft Dynamics 365 Supply Chain Management usa lógica de formatação especial como parte do mapeamento de campos para o layout de roteiro de documentos.</span><span class="sxs-lookup"><span data-stu-id="d22b0-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="d22b0-116">Formatos de número personalizados</span><span class="sxs-lookup"><span data-stu-id="d22b0-116">Custom number formats</span></span>

<span data-ttu-id="d22b0-117">Você pode personalizar a formatação de valores de campos numéricos que são impressos usando códigos que têm o seguinte formato.</span><span class="sxs-lookup"><span data-stu-id="d22b0-117">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="d22b0-118">Aqui está uma explicação deste formato:</span><span class="sxs-lookup"><span data-stu-id="d22b0-118">Here is an explanation of this format:</span></span>

- <span data-ttu-id="d22b0-119">`FieldName` é o nome do campo de dados (por exemplo**Qtd.**).</span><span class="sxs-lookup"><span data-stu-id="d22b0-119">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="d22b0-120">`FormatString` define como os dados devem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="d22b0-120">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="d22b0-121">Os exemplos a seguir mostram como é possível personalizar o campo (**Qtd.**) de quantidade de trabalho:</span><span class="sxs-lookup"><span data-stu-id="d22b0-121">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="d22b0-122">Para mostrar sempre quatro dígitos (usando zeros como espaços reservados), use `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="d22b0-122">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="d22b0-123">Por exemplo, se a quantidade for 10, o rótulo mostrará "0010".</span><span class="sxs-lookup"><span data-stu-id="d22b0-123">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="d22b0-124">Para mostrar sempre duas casas decimais, use `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="d22b0-124">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="d22b0-125">Por exemplo, se a quantidade for 10, o rótulo mostrará "10,00".</span><span class="sxs-lookup"><span data-stu-id="d22b0-125">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="d22b0-126">Para obter uma lista completa das cadeias de caracteres de formato de número disponíveis, consulte [Strings de formato numérico personalizado](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d22b0-126">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="d22b0-127">Formatos de sequência de caracteres personalizados</span><span class="sxs-lookup"><span data-stu-id="d22b0-127">Custom string formats</span></span>

<span data-ttu-id="d22b0-128">Você pode remover os primeiros caracteres de uma sequência usando o campo a seguir e código de formatação.</span><span class="sxs-lookup"><span data-stu-id="d22b0-128">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="d22b0-129">Aqui, `#` especifica o número de caracteres a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="d22b0-129">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="d22b0-130">Por exemplo, para imprimir um número de placa de licença de SSCC (código série do contêiner de remessa) que não inclua os dois primeiros caracteres, use `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="d22b0-130">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="d22b0-131">Nesse caso, o número da placa de licença 0011111111111222221 será impresso como "11111111111222221."</span><span class="sxs-lookup"><span data-stu-id="d22b0-131">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="d22b0-132">Formatos de data/hora personalizados</span><span class="sxs-lookup"><span data-stu-id="d22b0-132">Custom date/time formats</span></span>

<span data-ttu-id="d22b0-133">O exemplo a seguir mostra como você pode controlar o formato usado para imprimir datas.</span><span class="sxs-lookup"><span data-stu-id="d22b0-133">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="d22b0-134">Neste exemplo, a data 30 de abril 2020 será impressa como "30-04-2020".</span><span class="sxs-lookup"><span data-stu-id="d22b0-134">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="d22b0-135">Para obter uma lista completa dos formatos de data/hora disponíveis, consulte [Strings de formato de data e hora personalizados](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d22b0-135">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="d22b0-136">Imprimir linhas individuais de dados de várias linhas</span><span class="sxs-lookup"><span data-stu-id="d22b0-136">Print individual lines from multiline data</span></span>

<span data-ttu-id="d22b0-137">Se um campo de dados contiver várias linhas (ou seja, linhas separadas por quebras de linha), você poderá imprimir uma linha individual usando o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-137">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="d22b0-138">Aqui, `#` é o número da linha que você deseja imprimir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-138">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="d22b0-139">(Use 1 para a primeira linha.)</span><span class="sxs-lookup"><span data-stu-id="d22b0-139">(Use 1 for the first line.)</span></span>

<span data-ttu-id="d22b0-140">Por exemplo, seu sistema tem um campo `AdditionalAddress` que armazena o seguinte endereço de várias linhas:</span><span class="sxs-lookup"><span data-stu-id="d22b0-140">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="d22b0-141">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="d22b0-141">Contoso Inc.</span></span>  
<span data-ttu-id="d22b0-142">123 Nome da rua</span><span class="sxs-lookup"><span data-stu-id="d22b0-142">123 Street Name</span></span>  
<span data-ttu-id="d22b0-143">Cidade, Estado</span><span class="sxs-lookup"><span data-stu-id="d22b0-143">Some City, Some State</span></span>

<span data-ttu-id="d22b0-144">Você pode imprimir este endereço, uma linha de cada vez, usando os códigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-144">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="d22b0-145">Código</span><span class="sxs-lookup"><span data-stu-id="d22b0-145">Code</span></span> | <span data-ttu-id="d22b0-146">Texto impresso</span><span class="sxs-lookup"><span data-stu-id="d22b0-146">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="d22b0-147">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="d22b0-147">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="d22b0-148">123 Nome da rua</span><span class="sxs-lookup"><span data-stu-id="d22b0-148">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="d22b0-149">Cidade, Estado</span><span class="sxs-lookup"><span data-stu-id="d22b0-149">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="d22b0-150">Imprimir e formatar de um método de exibição</span><span class="sxs-lookup"><span data-stu-id="d22b0-150">Print and format from a display method</span></span>

<span data-ttu-id="d22b0-151">Você pode imprimir de um método de exibição usando o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-151">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="d22b0-152">Você pode combinar esse formato com outros tipos que foram descritos anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d22b0-152">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="d22b0-153">Por exemplo, você tem um método de exibição denominado `DisplayListOfItemsNumbers()` e deseja imprimir o primeiro número de item desse método.</span><span class="sxs-lookup"><span data-stu-id="d22b0-153">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="d22b0-154">Nesse caso, você pode usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="d22b0-154">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="d22b0-155">Mais informações sobre como imprimir etiquetas</span><span class="sxs-lookup"><span data-stu-id="d22b0-155">More information about how to print labels</span></span>

<span data-ttu-id="d22b0-156">Para obter mais informações sobre como configurar e imprimir etiquetas, consulte [Habilitar impressão de etiqueta de placa de licença](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="d22b0-156">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>
