---
title: Layouts de etiquetas de roteamento de documentos
description: Este artigo descreve como usar métodos de formatação para imprimir valores em etiquetas.
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
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a4e0c16b71c257cae832870ca58679884047ea16
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708635"
---
# <a name="document-routing-label-layout"></a>Layout de etiquetas de roteamento de documentos

[!include [banner](../includes/banner.md)]

Este artigo descreve como criar layouts para etiquetas de placas de veículos, contêineres e ciclos. Ele inclui diretrizes para usar a Linguagem de Programação Zebra (ZPL) na criação dos layouts.

Os layouts de etiquetas de roteamento de documentos definem a forma como elas serão aplicadas e os dados impressos nelas. Os pontos do disparador de impressão são configurados quando você configura itens de menu e modelos de trabalho de dispositivo móvel.

As informações deste artigo se aplicam a todos os layouts de etiquetas de roteamento de documentos, incluindo para [placas de veículos](tasks/license-plate-label-printing.md), [contêineres](print-container-labels.md) e [ciclos](configure-wave-label-printing.md).

Você pode imprimir etiquetas altamente complexas, desde que o dispositivo de impressão possa interpretar o texto enviado a ela. Por exemplo, um layout ZPL que inclui um código de barras pode ser semelhante ao exemplo a seguir.

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

Como parte do processo de impressão de etiquetas, o texto `$LicensePlateId$` neste exemplo será substituído por um valor de dados. Várias ferramentas de geração de etiquetas amplamente disponíveis podem ajudá-lo a formatar o texto para o layout da etiqueta. Muitas dessas ferramentas dão suporte ao formato `$FieldName$`. Além disso, o Microsoft Dynamics 365 Supply Chain Management usa lógica de formatação especial como parte do mapeamento de campos para o layout de roteiro de documentos.

Para ver os valores que serão impressos, Acesse **Gerenciamento de depósito \> Consultas e relatórios \> Etiquetas de placa de licença**.

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Se o sistema ainda não incluir os recursos descritos neste artigo, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Layouts de etiqueta da placa de licença aprimorados*. (A partir do Supply Chain Management versão 10.0.21, este recurso está ativado por padrão. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado.)

## <a name="custom-number-formats"></a>Formatos de número personalizados

Você pode personalizar a formatação de valores de campos numéricos que são impressos usando códigos que têm o seguinte formato.

```dos
$FieldName:FormatString$
```

Aqui está uma explicação deste formato:

- `FieldName` é o nome do campo de dados (por exemplo **Qtd.**).
- `FormatString` define como os dados devem ser impressos.

Os exemplos a seguir mostram como é possível personalizar o campo (**Qtd.**) de quantidade de trabalho:

- Para mostrar sempre quatro dígitos (usando zeros como espaços reservados), use `$Qty:0000$`. Por exemplo, se a quantidade for 10, o rótulo mostrará "0010".
- Para mostrar sempre duas casas decimais, use `$Qty:0.00$`. Por exemplo, se a quantidade for 10, o rótulo mostrará "10,00".

Para obter uma lista completa das cadeias de caracteres de formato de número disponíveis, consulte [Strings de formato numérico personalizado](/dotnet/standard/base-types/custom-numeric-format-strings).

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

Para obter uma lista completa dos formatos de data/hora disponíveis, consulte [Strings de formato de data e hora personalizados](/dotnet/standard/base-types/custom-date-and-time-format-strings).

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

Você pode combinar esse formato com outros tipos que foram descritos anteriormente neste artigo. Por exemplo, você tem um método de exibição denominado `DisplayListOfItemsNumbers()` e deseja imprimir o primeiro número de item desse método. Nesse caso, você pode usar o código a seguir.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Mais informações sobre como imprimir etiquetas

Para mais informações sobre como configurar e imprimir as etiquetas, confira estes artigos:

- [Impressão de etiqueta de placa de veículo](tasks/license-plate-label-printing.md)
- [Impressão de etiqueta de contêiner](print-container-labels.md)
- [Impressão de etiqueta do ciclo](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
