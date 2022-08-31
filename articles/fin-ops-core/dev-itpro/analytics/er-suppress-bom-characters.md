---
title: Criar configurações de ER para suprimir caracteres da BOM nos arquivos gerados
description: Este artigo explica como configurar um formato de relatório eletrônico (ER) para gerar relatórios que suprimem caracteres de marca de ordem de byte (BOM).
author: kfend
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EROperationDesigner
ms.openlocfilehash: a2ea132b51f2f451fbe81a9c7869bea84bf4017a
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324009"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Criar configurações de ER para suprimir caracteres da BOM nos arquivos gerados

[!include [banner](../includes/banner.md)]

Você pode criar uma [solução](er-quick-start1-new-solution.md) de [relatórios eletrônicos (ER)](general-electronic-reporting.md) para gerar documentos de saída no formato XML. Para gerar os documentos como arquivos de texto ou XML, a solução deve incluir uma [configuração](general-electronic-reporting.md#Configuration) de ER que contenha um componente de formato de ER. Para especificar a [codificação de caracteres](/windows/win32/intl/character-sets) que representa o conjunto de caracteres em arquivos gerados, o formato de ER deve conter o formato de elemento **Comum\\File**. Para configurar o componente de formato de ER, abra a versão de rascunho da configuração de ER no designer de formato de ER e adicione o elemento **Common\\File**. No campo **Codificação**, especifique a codificação de arquivos de saída que são gerados no tempo de execução usando esse componente.

> [!NOTE]
> Se o formato tiver um nome de codificação incorreto, um erro será exibido quando você salvar as alterações nas configurações do formato.

![Adicionar um elemento raiz na página Designer de formato.](./media/er-suppress-bom-characters-image1.gif)

Se você especificar **UTF-8**, **UTF-16** ou **UTF-32** como a codificação, a opção **Suprimir caracteres de BOM** ficará disponível. Defina esta opção como **Sim** para suprimir [caracteres de marca de ordem de bytes (BOM)](/globalization/encoding/byte-order-mark) em arquivos de saída que são gerados no tempo de execução quando o formato de ER editável é executado.

> [!NOTE]
> Se o campo **Codificação** ficar em branco, a codificação **UTF-8** padrão será usada.

![Configurar a opção Suprimir caracteres de BOM na página Designer de formato.](./media/er-suppress-bom-characters-image2.gif)

Para analisar a funcionalidade no tempo de execução, conclua o procedimento apropriado. Por exemplo, conclua as etapas do artigo [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md). Depois de concluir as etapas na seção [Modificar o formato para que o cálculo se baseie na saída gerada](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) deste artigo, siga mais estas etapas.

1. Especifique a codificação UTF:

    1. Selecione o elemento de **Relatório** do tipo **Common\\File**.
    2. No campo **Codificação**, especifique a codificação **UTF-8**.

2. Gerar um arquivo XML que inclui um caractere de BOM:

    1. Defina a opção **Suprimir caracteres de BOM** como **Não** para incluir caracteres de BOM em arquivos XML gerados.
    2. Conclua as etapas na seção [Adiar a execução do elemento XML de resumo para que o total calculado seja usado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) do artigo [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md) e salve o arquivo gerado como **SampleXmlReport.xml**.

3. Gerar um arquivo XML que não inclua um caractere de BOM:

    1. Defina a opção **Suprimir caracteres de BOM** como **Sim** para suprimir caracteres de BOM em arquivos XML gerados.
    2. Conclua as etapas na seção [Adiar a execução do elemento XML de resumo para que o total calculado seja usado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) do artigo [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md) e salve o arquivo gerado como **SampleXmlReport (1).xml**.

4. Em um utilitário de comparação de arquivos, compare os arquivos gerados.

    A primeira diferença que você observará está no cabeçalho do arquivo. O arquivo SampleXmlReport.xml contém um caractere de BOM, enquanto o arquivo SampleXmlReport (1).xml não.

    ![Comparar os arquivos gerados usando um utilitário de comparação de arquivos.](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Consulte também

- [Adiar a execução de elementos XML nos formatos ER](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
