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
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 9af077022ab0759534d2c1da5f39997712e6a354
ms.sourcegitcommit: 965fa733be068dc37f482d02ebbcd77f2c3d0a45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763446"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>Layout de roteiro de documentos para etiquetas de placa de licença

[!include [banner](../includes/banner.md)]

O layout de circulação de documentos define o layout dos rótulos de placa de licença e os dados impressos neles. Os pontos do disparador de impressão são configurados quando você configura itens de menu e modelos de trabalho de dispositivo móvel.

Em um cenário típico, os auxiliares de recebimento de depósito imprimem etiquetas de placa de licença imediatamente após registrarem o conteúdo dos paletes que chegam na área de recebimento. As etiquetas físicas são aplicadas aos paletes. Em seguida, eles podem ser usados para validação como parte do processo de retirada que segue e operações de separação de saída futura.

Você pode imprimir etiquetas altamente complexas, desde que o dispositivo de impressão possa interpretar o texto enviado a ela. Por exemplo, um layout de linguagem de programação zebra (ZPL) que inclui um código de barras pode ser semelhante ao exemplo a seguir.

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

Como parte do processo de impressão de etiquetas, o texto `$LicensePlateId$` neste exemplo será substituído por um valor de dados.

Para ver os valores que serão impressos, vá para **Gerenciamento de depósito \> Consultas e relatórios \> Etiquetas de placa de licença**.

Várias ferramentas de geração de etiquetas amplamente disponíveis podem ajudá-lo a formatar o texto para o layout da etiqueta. Muitas dessas ferramentas dão suporte ao formato `$FieldName$`. Além disso, o Microsoft Dynamics 365 Supply Chain Management usa lógica de formatação especial como parte do mapeamento de campos para o layout de roteiro de documentos.

## <a name="custom-number-formats"></a>Formatos de número personalizados

Você pode personalizar a formatação de valores de campos numéricos que são impressos usando códigos que têm o seguinte formato.

```dos
$FieldName:FormatString$
```

Aqui está uma explicação deste formato:

- `FieldName` é o nome do campo de dados (por exemplo**Qtd.**).
- `FormatString` define como os dados devem ser impressos.

Os exemplos a seguir mostram como é possível personalizar o campo (**Qtd.**) de quantidade de trabalho:

- Para mostrar sempre quatro dígitos (usando zeros como espaços reservados), use `$Qty:0000$`. Por exemplo, se a quantidade for 10, o rótulo mostrará "0010".
- Para mostrar sempre duas casas decimais, use `$Qty:0.00$`. Por exemplo, se a quantidade for 10, o rótulo mostrará "10,00".

Para obter uma lista completa das cadeias de caracteres de formato de número disponíveis, consulte [Strings de formato numérico personalizado](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Formatos de sequência de caracteres personalizados

Você pode remover os primeiros caracteres de uma sequência usando o campo a seguir e código de formatação.

```dos
$FieldName:#..$
```

Aqui, `#` especifica o número de caracteres a serem ignorados. Por exemplo, para imprimir um número de placa de licença de SSCC (código série do contêiner de remessa) que não inclua os dois primeiros caracteres, use `$LicensePlateId:2..$`. Nesse caso, o número da placa de licença 0011111111111222221 será impresso como "11111111111222221."

## <a name="custom-datetime-formats"></a>Formatos de data/hora personalizados

O exemplo a seguir mostra como você pode controlar o formato usado para imprimir datas.

```dos
$PrintedDate:dd-MM-yyyy$
```

Neste exemplo, a data 30 de abril 2020 será impressa como "30-04-2020".

Para obter uma lista completa dos formatos de data/hora disponíveis, consulte [Strings de formato de data e hora personalizados](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Imprimir linhas individuais de dados de várias linhas

Se um campo de dados contiver várias linhas (ou seja, linhas separadas por quebras de linha), você poderá imprimir uma linha individual usando o formato a seguir.

```dos
$FieldName[#]$
```

Aqui, `#` é o número da linha que você deseja imprimir. (Use 1 para a primeira linha.)

Por exemplo, seu sistema tem um campo `AdditionalAddress` que armazena o seguinte endereço de várias linhas:

Contoso Inc.  
123 Nome da rua  
Cidade, Estado

Você pode imprimir este endereço, uma linha de cada vez, usando os códigos a seguir.

| Código | Texto impresso |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Nome da rua |
| `$AdditionalAddress[3]$` | Cidade, Estado |

## <a name="print-and-format-from-a-display-method"></a>Imprimir e formatar de um método de exibição

Você pode imprimir de um método de exibição usando o formato a seguir.

```dos
$DisplayMethod()$
```

Você pode combinar esse formato com outros tipos que foram descritos anteriormente neste tópico. Por exemplo, você tem um método de exibição denominado `DisplayListOfItemsNumbers()` e deseja imprimir o primeiro número de item desse método. Nesse caso, você pode usar o código a seguir.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Mais informações sobre como imprimir etiquetas

Para obter mais informações sobre como configurar e imprimir etiquetas, consulte [Habilitar impressão de etiqueta de placa de licença](tasks/license-plate-label-printing.md).
