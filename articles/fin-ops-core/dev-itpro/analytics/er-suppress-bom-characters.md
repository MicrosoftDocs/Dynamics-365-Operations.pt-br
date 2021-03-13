---
title: Criar configurações de ER para suprimir caracteres da BOM nos arquivos gerados
description: Este tópico explica como configurar um formato de relatório eletrônico (ER) para gerar relatórios que suprimem caracteres de marca de ordem de byte (BOM).
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19fbbdea4bfdf30b1313a47e65056b536ed73dbe
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060810"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="f9ce4-103">Criar configurações de ER para suprimir caracteres da BOM nos arquivos gerados</span><span class="sxs-lookup"><span data-stu-id="f9ce4-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9ce4-104">Você pode criar uma [solução](er-quick-start1-new-solution.md) de [relatórios eletrônicos (ER)](general-electronic-reporting.md) para gerar documentos de saída no formato XML.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="f9ce4-105">Para gerar os documentos como arquivos de texto ou XML, a solução deve incluir uma [configuração](general-electronic-reporting.md#Configuration) de ER que contém um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="f9ce4-106">Para especificar a [codificação de caracteres](https://docs.microsoft.com/windows/win32/intl/character-sets) que representa o conjunto de caracteres em arquivos gerados, o formato de ER deve conter o formato de elemento **Comum\\File**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="f9ce4-107">Para configurar o componente de formato de ER, abra de versão de [rascunho](general-electronic-reporting.md#component-versioning) da configuração de ER no designer de formato de ER e adicione o elemento **Common\\File**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="f9ce4-108">No campo **Codificação**, especifique a codificação de arquivos de saída que são gerados no tempo de execução usando esse componente.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ce4-109">Se o formato tiver um nome de codificação incorreto, um erro será exibido quando você salvar as alterações nas configurações do formato.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Adicionar um elemento raiz na página Designer de formato](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="f9ce4-111">Se você especificar **UTF-8**, **UTF-16** ou **UTF-32** como a codificação, a opção **Suprimir caracteres de BOM** ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="f9ce4-112">Defina esta opção como **Sim** para suprimir [caracteres de marca de ordem de bytes (BOM)](https://docs.microsoft.com/globalization/encoding/byte-order-mark) em arquivos de saída que são gerados no tempo de execução quando o formato de ER editável é executado.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ce4-113">Se o campo **Codificação** ficar em branco, a codificação **UTF-8** padrão será usada.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Configurar a opção Suprimir caracteres de BOM na página Designer de formato](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="f9ce4-115">Para analisar a funcionalidade no tempo de execução, conclua o procedimento apropriado.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="f9ce4-116">Por exemplo, conclua as etapas do tópico [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="f9ce4-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="f9ce4-117">Depois de concluir as etapas na seção [Modificar o formato para que o cálculo se baseie na saída gerada](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) deste tópico, siga mais estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="f9ce4-118">Especifique a codificação UTF:</span><span class="sxs-lookup"><span data-stu-id="f9ce4-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="f9ce4-119">Selecione o elemento de **Relatório** do tipo **Common\\File**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="f9ce4-120">No campo **Codificação**, especifique a codificação **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="f9ce4-121">Gerar um arquivo XML que inclui um caractere de BOM:</span><span class="sxs-lookup"><span data-stu-id="f9ce4-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="f9ce4-122">Defina a opção **Suprimir caracteres de BOM** como **Não** para incluir caracteres de BOM em arquivos XML gerados.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="f9ce4-123">Conclua as etapas na seção [Adiar a execução do elemento XML de resumo para que o total calculado seja usado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) do tópico [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md) e salve o arquivo gerado como **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="f9ce4-124">Gerar um arquivo XML que não inclua um caractere de BOM:</span><span class="sxs-lookup"><span data-stu-id="f9ce4-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="f9ce4-125">Defina a opção **Suprimir caracteres de BOM** como **Sim** para suprimir caracteres de BOM em arquivos XML gerados.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="f9ce4-126">Conclua as etapas na seção [Adiar a execução do elemento XML de resumo para que o total calculado seja usado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) do tópico [Adiar a execução de elementos XML em formatos de ER](er-defer-xml-element.md) e salve o arquivo gerado como **SampleXmlReport.(1).xml**.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="f9ce4-127">Em um utilitário de comparação de arquivos, compare os arquivos gerados.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="f9ce4-128">A primeira diferença que você observará está no cabeçalho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="f9ce4-129">O arquivo SampleXmlReport.xml contém um caractere de BOM, enquanto o arquivo SampleXmlReport (1).xml não.</span><span class="sxs-lookup"><span data-stu-id="f9ce4-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Comparar os arquivos gerados usando um utilitário de comparação de arquivos](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="f9ce4-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f9ce4-131">See also</span></span>

- [<span data-ttu-id="f9ce4-132">Adiar a execução de elementos XML nos formatos ER</span><span class="sxs-lookup"><span data-stu-id="f9ce4-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)
