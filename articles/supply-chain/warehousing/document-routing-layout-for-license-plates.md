---
title: Layout de roteiro de documentos para etiquetas de placa de licença
description: Este tópico descreve como usar métodos de formatação para imprimir valores em etiquetas.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: faf54fec2885f868c66987a7b481559d0c5615d0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838265"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="9fbeb-103">Layout de roteiro de documentos para etiquetas de placa de licença</span><span class="sxs-lookup"><span data-stu-id="9fbeb-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9fbeb-104">O layout de circulação de documentos define o layout dos rótulos de placa de licença e os dados impressos neles.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="9fbeb-105">Os pontos do disparador de impressão são configurados quando você configura itens de menu e modelos de trabalho de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="9fbeb-106">Em um cenário típico, os auxiliares de recebimento de depósito imprimem etiquetas de placa de licença imediatamente após registrarem o conteúdo dos paletes que chegam na área de recebimento.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="9fbeb-107">As etiquetas físicas são aplicadas aos paletes.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="9fbeb-108">Em seguida, eles podem ser usados para validação como parte do processo de retirada que segue e operações de separação de saída futura.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="9fbeb-109">Você pode imprimir etiquetas altamente complexas, desde que o dispositivo de impressão possa interpretar o texto enviado a ela.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="9fbeb-110">Por exemplo, um layout de linguagem de programação zebra (ZPL) que inclui um código de barras pode ser semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

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

<span data-ttu-id="9fbeb-111">Como parte do processo de impressão de etiquetas, o texto `$LicensePlateId$` neste exemplo será substituído por um valor de dados.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="9fbeb-112">Para ver os valores que serão impressos, vá para **Gerenciamento de depósito \> Consultas e relatórios \> Etiquetas de placa de licença**.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="9fbeb-113">Várias ferramentas de geração de etiquetas amplamente disponíveis podem ajudá-lo a formatar o texto para o layout da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="9fbeb-114">Muitas dessas ferramentas dão suporte ao formato `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="9fbeb-115">Além disso, o Microsoft Dynamics 365 Supply Chain Management usa lógica de formatação especial como parte do mapeamento de campos para o layout de roteiro de documentos.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="9fbeb-116">Ative este recurso para o seu sistema</span><span class="sxs-lookup"><span data-stu-id="9fbeb-116">Turn on this feature for your system</span></span>

<span data-ttu-id="9fbeb-117">Se o sistema ainda não incluir os recursos descritos neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Layouts de etiqueta da placa de licença aprimorados*.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Enhanced license plate label layouts* feature.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="9fbeb-118">Formatos de número personalizados</span><span class="sxs-lookup"><span data-stu-id="9fbeb-118">Custom number formats</span></span>

<span data-ttu-id="9fbeb-119">Você pode personalizar a formatação de valores de campos numéricos que são impressos usando códigos que têm o seguinte formato.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-119">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="9fbeb-120">Aqui está uma explicação deste formato:</span><span class="sxs-lookup"><span data-stu-id="9fbeb-120">Here is an explanation of this format:</span></span>

- <span data-ttu-id="9fbeb-121">`FieldName` é o nome do campo de dados (por exemplo **Qtd.**).</span><span class="sxs-lookup"><span data-stu-id="9fbeb-121">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="9fbeb-122">`FormatString` define como os dados devem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-122">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="9fbeb-123">Os exemplos a seguir mostram como é possível personalizar o campo (**Qtd.**) de quantidade de trabalho:</span><span class="sxs-lookup"><span data-stu-id="9fbeb-123">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="9fbeb-124">Para mostrar sempre quatro dígitos (usando zeros como espaços reservados), use `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-124">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="9fbeb-125">Por exemplo, se a quantidade for 10, o rótulo mostrará "0010".</span><span class="sxs-lookup"><span data-stu-id="9fbeb-125">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="9fbeb-126">Para mostrar sempre duas casas decimais, use `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-126">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="9fbeb-127">Por exemplo, se a quantidade for 10, o rótulo mostrará "10,00".</span><span class="sxs-lookup"><span data-stu-id="9fbeb-127">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="9fbeb-128">Para obter uma lista completa das cadeias de caracteres de formato de número disponíveis, consulte [Strings de formato numérico personalizado](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="9fbeb-128">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="9fbeb-129">Formatos de sequência de caracteres personalizados</span><span class="sxs-lookup"><span data-stu-id="9fbeb-129">Custom string formats</span></span>

<span data-ttu-id="9fbeb-130">Você pode remover os primeiros caracteres de uma sequência usando o campo a seguir e código de formatação.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-130">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="9fbeb-131">Aqui, `#` especifica o número de caracteres a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-131">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="9fbeb-132">Por exemplo, para imprimir um número de placa de licença de SSCC (código série do contêiner de remessa) que não inclua os dois primeiros caracteres, use `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-132">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="9fbeb-133">Nesse caso, o número da placa de licença 0011111111111222221 será impresso como "11111111111222221."</span><span class="sxs-lookup"><span data-stu-id="9fbeb-133">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="9fbeb-134">Formatos de data/hora personalizados</span><span class="sxs-lookup"><span data-stu-id="9fbeb-134">Custom date/time formats</span></span>

<span data-ttu-id="9fbeb-135">O exemplo a seguir mostra como você pode controlar o formato usado para imprimir datas.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-135">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="9fbeb-136">Neste exemplo, a data 30 de abril 2020 será impressa como "30-04-2020".</span><span class="sxs-lookup"><span data-stu-id="9fbeb-136">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="9fbeb-137">Para obter uma lista completa dos formatos de data/hora disponíveis, consulte [Strings de formato de data e hora personalizados](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="9fbeb-137">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="9fbeb-138">Imprimir linhas individuais de dados de várias linhas</span><span class="sxs-lookup"><span data-stu-id="9fbeb-138">Print individual lines from multiline data</span></span>

<span data-ttu-id="9fbeb-139">Se um campo de dados contiver várias linhas (ou seja, linhas separadas por quebras de linha), você poderá imprimir uma linha individual usando o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-139">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="9fbeb-140">Aqui, `#` é o número da linha que você deseja imprimir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-140">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="9fbeb-141">(Use 1 para a primeira linha.)</span><span class="sxs-lookup"><span data-stu-id="9fbeb-141">(Use 1 for the first line.)</span></span>

<span data-ttu-id="9fbeb-142">Por exemplo, seu sistema tem um campo `AdditionalAddress` que armazena o seguinte endereço de várias linhas:</span><span class="sxs-lookup"><span data-stu-id="9fbeb-142">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="9fbeb-143">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-143">Contoso Inc.</span></span>  
<span data-ttu-id="9fbeb-144">123 Nome da rua</span><span class="sxs-lookup"><span data-stu-id="9fbeb-144">123 Street Name</span></span>  
<span data-ttu-id="9fbeb-145">Cidade, Estado</span><span class="sxs-lookup"><span data-stu-id="9fbeb-145">Some City, Some State</span></span>

<span data-ttu-id="9fbeb-146">Você pode imprimir este endereço, uma linha de cada vez, usando os códigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-146">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="9fbeb-147">Código</span><span class="sxs-lookup"><span data-stu-id="9fbeb-147">Code</span></span> | <span data-ttu-id="9fbeb-148">Texto impresso</span><span class="sxs-lookup"><span data-stu-id="9fbeb-148">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="9fbeb-149">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-149">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="9fbeb-150">123 Nome da rua</span><span class="sxs-lookup"><span data-stu-id="9fbeb-150">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="9fbeb-151">Cidade, Estado</span><span class="sxs-lookup"><span data-stu-id="9fbeb-151">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="9fbeb-152">Imprimir e formatar de um método de exibição</span><span class="sxs-lookup"><span data-stu-id="9fbeb-152">Print and format from a display method</span></span>

<span data-ttu-id="9fbeb-153">Você pode imprimir de um método de exibição usando o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-153">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="9fbeb-154">Você pode combinar esse formato com outros tipos que foram descritos anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-154">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="9fbeb-155">Por exemplo, você tem um método de exibição denominado `DisplayListOfItemsNumbers()` e deseja imprimir o primeiro número de item desse método.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-155">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="9fbeb-156">Nesse caso, você pode usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fbeb-156">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="9fbeb-157">Mais informações sobre como imprimir etiquetas</span><span class="sxs-lookup"><span data-stu-id="9fbeb-157">More information about how to print labels</span></span>

<span data-ttu-id="9fbeb-158">Para obter mais informações sobre como configurar e imprimir etiquetas, consulte [Habilitar impressão de etiqueta de placa de licença](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="9fbeb-158">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]