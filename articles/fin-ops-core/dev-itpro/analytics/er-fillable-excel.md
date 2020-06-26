---
title: Criar uma configuração para gerar documentos no formato Excel
description: Este tópico fornece informações sobre como criar um formato de relatório eletrônico (ER) para preencher um modelo do Excel e gerar documentos no formato Excel de saída.
author: NickSelin
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e889b08f10c5d0c95fed7c9e422340706bdd154a
ms.sourcegitcommit: 67ce81c57194afb26a04ae4c0b7509e0efa32afc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "3375804"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a><span data-ttu-id="e23e2-103">Criar uma configuração para gerar documentos no formato Excel</span><span class="sxs-lookup"><span data-stu-id="e23e2-103">Design a configuration for generating documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e23e2-104">Você pode criar uma configuração de formato de [relatório eletrônico (ER)](general-electronic-reporting.md) que tem um ER [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) que pode ser configurado para gerar um documento de saída em um formato de pasta de trabalho do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) format configuration that has an ER [format component](general-electronic-reporting.md#FormatComponentOutbound) that you can configure to generate an outbound document in a Microsoft Excel workbook format.</span></span> <span data-ttu-id="e23e2-105">Componentes de formato ER específicos devem ser usados com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="e23e2-105">Specific ER format components must be used for this purpose.</span></span>

<span data-ttu-id="e23e2-106">Para saber mais sobre esse recurso, siga as etapas no tópico, [Criar uma configuração para gerar relatórios no formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e23e2-106">To learn more about this feature, follow the steps in the topic, [Design a configuration for generating reports in OPENXML format](tasks/er-design-reports-openxml-2016-11.md).</span></span>

## <a name="add-a-new-er-format"></a><span data-ttu-id="e23e2-107">Adicionar um novo formato ER</span><span class="sxs-lookup"><span data-stu-id="e23e2-107">Add a new ER format</span></span>

<span data-ttu-id="e23e2-108">Ao adicionar uma nova configuração de formato ER para gerar um documento de saída em um formato de pasta de trabalho do Excel, você deve selecionar o valor **Excel** para o atributo **Tipo de formato** no formato ou deixar o atributo **Tipo de formato** em branco.</span><span class="sxs-lookup"><span data-stu-id="e23e2-108">When you add a new ER format configuration to generate an outbound document in an Excel workbook format, you must either select the **Excel** value for the **Format type** attribute of the format or leave the **Format type** attribute blank.</span></span>

- <span data-ttu-id="e23e2-109">Se você selecionar **Excel**, poderá configurar o formato para gerar um documento de saída somente no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-109">If you select **Excel**, you can configure the format to generate an outbound document only in Excel format.</span></span>
- <span data-ttu-id="e23e2-110">Se você deixar o atributo em branco, poderá configurar o formato para gerar um documento de saída em qualquer formato com suporte da estrutura ER.</span><span class="sxs-lookup"><span data-stu-id="e23e2-110">If you leave the attribute blank, you can configure the format to generate an outbound document in any format that is supported by the ER framework.</span></span>

<span data-ttu-id="e23e2-111">Para configurar o componente de formato ER da configuração, selecione **Designer** no Painel de Ações e abra o componente de formato ER para edição no designer de operação do ER.</span><span class="sxs-lookup"><span data-stu-id="e23e2-111">To configure the ER format component of the configuration, select **Designer** on the Action Pane, and open the ER format component for editing in the ER Operation designer.</span></span>

![Página Configurações](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a><span data-ttu-id="e23e2-113">Componente Arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="e23e2-113">Excel file component</span></span>

### <a name="manual-entry"></a><span data-ttu-id="e23e2-114">Entrada manual</span><span class="sxs-lookup"><span data-stu-id="e23e2-114">Manual entry</span></span>

<span data-ttu-id="e23e2-115">Você deve adicionar um componente **Arquivo\\do Excel** ao formato ER configurado para gerar um documento de saída no formato Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-115">You must add an **Excel\\File** component to the configured ER format to generate an outbound document in Excel format.</span></span>

![Componente Arquivo\do Excel](./media/er-excel-format-add-file-component.png)

<span data-ttu-id="e23e2-117">Para especificar o layout do documento de saída, anexe uma pasta de trabalho do Excel com a extensão .xlsx ao componente **Arquivo\\do Excel** como o modelo para documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="e23e2-117">To specify the layout of the outbound document, attach an Excel workbook that has the .xlsx extension to the **Excel\\File** component as the template for outbound documents.</span></span>

> [!NOTE]
> <span data-ttu-id="e23e2-118">Ao anexar manualmente um modelo, você deve usar um [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) que tenha sido configurado com essa finalidade nos [parâmetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span><span class="sxs-lookup"><span data-stu-id="e23e2-118">When you manually attach a template, you must use a [document type](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) that has been configured for that purpose in the [ER parameters](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span></span>

![Adição de um anexo ao componente Arquivo\do Excel](./media/er-excel-format-add-file-component2.png)

<span data-ttu-id="e23e2-120">Para especificar como o modelo anexado será preenchido quando você executar o formato ER configurado, adicione componentes aninhados **Planilha**, **Intervalo** e **Célula** ao componente **Arquivo\\do Excel**.</span><span class="sxs-lookup"><span data-stu-id="e23e2-120">To specify how the attached template will be filled in when you run the configured ER format, you must add nested **Sheet**, **Range**, and **Cell** components to the **Excel\\File** component.</span></span> <span data-ttu-id="e23e2-121">Cada componente aninhado deve estar associado a um item nomeado do Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-121">Each nested component must be associated with an Excel named item.</span></span>

### <a name="template-import"></a><span data-ttu-id="e23e2-122">Importação de modelo</span><span class="sxs-lookup"><span data-stu-id="e23e2-122">Template import</span></span>

<span data-ttu-id="e23e2-123">Você pode selecionar **Importar do Excel** na guia **Importar** do Painel de Ações para importar um novo modelo para um formato ER em branco.</span><span class="sxs-lookup"><span data-stu-id="e23e2-123">You can select **Import from Excel** on the **Import** tab of the Action Pane to import a new template into a blank ER format.</span></span> <span data-ttu-id="e23e2-124">Neste exemplo, um componente **Arquivo\\do Excel** será criado automaticamente e o modelo importado será anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="e23e2-124">In this example, an **Excel\\File** component will be created automatically, and the imported template will be attached to it.</span></span> <span data-ttu-id="e23e2-125">Todos os componentes ER obrigatórios também serão criados automaticamente, com base na lista de itens nomeados do Excel que forem descobertos.</span><span class="sxs-lookup"><span data-stu-id="e23e2-125">All required ER components will also be created automatically, based on the list of Excel named items that are discovered.</span></span>

![Seleção de Importar do Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> <span data-ttu-id="e23e2-127">Se desejar criar o elemento opcional **Planilha** no formato ER editável, defina a opção **Criar elemento de formato de planilha do Excel** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e23e2-127">If you want to create the optional **Sheet** element in the editable ER format, set the **Create Excel Sheet format element** option to **Yes**.</span></span>

## <a name="sheet-component"></a><span data-ttu-id="e23e2-128">Componente Planilha</span><span class="sxs-lookup"><span data-stu-id="e23e2-128">Sheet component</span></span>

<span data-ttu-id="e23e2-129">O componente **Planilha** indica uma planilha da pasta de trabalho do Excel anexada que deve ser preenchida.</span><span class="sxs-lookup"><span data-stu-id="e23e2-129">The **Sheet** component indicates a worksheet of the attached Excel workbook that must be filled in.</span></span> <span data-ttu-id="e23e2-130">O nome da planilha em um modelo do Excel é definido na propriedade **Planilha** deste componente.</span><span class="sxs-lookup"><span data-stu-id="e23e2-130">The name of the worksheet in an Excel template is defined in the **Sheet** property of this component.</span></span>

> [!NOTE]
> <span data-ttu-id="e23e2-131">Esse componente é opcional para pastas de trabalho do Excel que contêm uma única planilha.</span><span class="sxs-lookup"><span data-stu-id="e23e2-131">This component is optional for Excel workbooks that contain a single worksheet.</span></span>

<span data-ttu-id="e23e2-132">Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Planilha** para especificar se o componente deve ser colocado em um documento gerado:</span><span class="sxs-lookup"><span data-stu-id="e23e2-132">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Sheet** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="e23e2-133">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, a planilha apropriada será colocada no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-133">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate worksheet will be put in the generated document.</span></span>
- <span data-ttu-id="e23e2-134">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução, o documento gerado não conterá uma planilha.</span><span class="sxs-lookup"><span data-stu-id="e23e2-134">If an expression of the **Enabled** property is configured to return **False** at runtime, the generated document won't contain a worksheet.</span></span>

![Exemplo de um componente Planilha](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a><span data-ttu-id="e23e2-136">Componente Intervalo</span><span class="sxs-lookup"><span data-stu-id="e23e2-136">Range component</span></span>

<span data-ttu-id="e23e2-137">O componente **Intervalo** indica um intervalo do Excel que deve ser controlado por esse componente ER.</span><span class="sxs-lookup"><span data-stu-id="e23e2-137">The **Range** component indicates an Excel range that must be controlled by this ER component.</span></span> <span data-ttu-id="e23e2-138">O nome do intervalo é definido na propriedade **Intervalo do Excel** deste componente.</span><span class="sxs-lookup"><span data-stu-id="e23e2-138">The name of the range is defined in the **Excel range** property of this component.</span></span>

<span data-ttu-id="e23e2-139">A propriedade **Direção da replicação** especifica se e como o intervalo será repetido em um documento gerado:</span><span class="sxs-lookup"><span data-stu-id="e23e2-139">The **Replication direction** property specifies whether and how the range will be repeated in a generated document:</span></span>

- <span data-ttu-id="e23e2-140">Se a propriedade **Direção da replicação** estiver definida como **Sem replicação**, o intervalo do Excel apropriado não será repetido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-140">If the **Replication direction** property is set to **No replication**, the appropriate Excel range won't be repeated in the generated document.</span></span>
- <span data-ttu-id="e23e2-141">Se a propriedade **Direção da replicação** estiver definida como **Vertical**, o intervalo do Excel apropriado será repetido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-141">If the **Replication direction** property is set to **Vertical**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="e23e2-142">Todo intervalo replicado é colocado abaixo do intervalo original em um modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-142">Every replicated range is put below the original range in an Excel template.</span></span> <span data-ttu-id="e23e2-143">O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.</span><span class="sxs-lookup"><span data-stu-id="e23e2-143">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>
- <span data-ttu-id="e23e2-144">Se a propriedade **Direção da replicação** estiver definida como **Horizontal**, o intervalo do Excel apropriado será repetido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-144">If the **Replication direction** property is set to **Horizontal**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="e23e2-145">Todo intervalo replicado é colocado à direita do intervalo original em um modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-145">Every replicated range is put to the right of the original range in an Excel template.</span></span> <span data-ttu-id="e23e2-146">O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.</span><span class="sxs-lookup"><span data-stu-id="e23e2-146">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>

<span data-ttu-id="e23e2-147">Para saber mais sobre a replicação horizontal, siga as etapas em [Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente nos relatórios do Excel](tasks/er-horizontal-1.md).</span><span class="sxs-lookup"><span data-stu-id="e23e2-147">To learn more about horizontal replication, follow the steps in [Use horizontally expandable ranges to dynamically add columns in Excel reports](tasks/er-horizontal-1.md).</span></span>

<span data-ttu-id="e23e2-148">O componente **Intervalo** pode ter outros componentes ER aninhados que são usados para inserir valores nos intervalos nomeados apropriados do Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-148">The **Range** component can have other nested ER components that are used to enter values in the appropriate Excel named ranges.</span></span>

- <span data-ttu-id="e23e2-149">Se qualquer componente do grupo **Texto** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor de texto.</span><span class="sxs-lookup"><span data-stu-id="e23e2-149">If any component of the **Text** group is used to enter values, the value is entered in an Excel range as a text value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e23e2-150">Use este padrão para formatar valores inseridos com base na localidade definida no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e23e2-150">Use this pattern to format entered values based on the locale that is defined in the application.</span></span>

- <span data-ttu-id="e23e2-151">Se o componente **Célula** do grupo **Excel** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor do tipo de dados definido pela associação do componente **Célula** (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**).</span><span class="sxs-lookup"><span data-stu-id="e23e2-151">If the **Cell** component of the **Excel** group is used to enter values, the value is entered in an Excel range as a value of the data type that is defined by the binding of that **Cell** component (for example, **String**, **Real**, or **Integer**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e23e2-152">Use este padrão para permitir que o aplicativo Excel formate valores inseridos com base na localidade do computador local que abre o documento de saída.</span><span class="sxs-lookup"><span data-stu-id="e23e2-152">Use this pattern to enable the Excel application to format entered values based on the locale of the local computer that opens the outbound document.</span></span>

<span data-ttu-id="e23e2-153">Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Intervalo** para especificar se o componente deve ser colocado em um documento gerado:</span><span class="sxs-lookup"><span data-stu-id="e23e2-153">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Range** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="e23e2-154">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, o intervalo apropriado será preenchido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-154">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate range will be filled in in the generated document.</span></span>
- <span data-ttu-id="e23e2-155">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo não representar as linhas ou colunas inteiras, o intervalo apropriado não será preenchido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-155">If an expression of the **Enabled** property is configured to return **False** at runtime, and if this range doesn't represent the entire rows or columns, the appropriate range won't be filled in in the generated document.</span></span>
- <span data-ttu-id="e23e2-156">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo representar as linhas ou colunas inteiras, o documento gerado conterá essas linhas e colunas como linhas e colunas ocultas.</span><span class="sxs-lookup"><span data-stu-id="e23e2-156">If an expression of the **Enabled** property is configured to return **False** at runtime, and this range represents the entire rows or columns, the generated document will contain those rows and columns as hidden rows and columns.</span></span>

## <a name="cell-component"></a><span data-ttu-id="e23e2-157">Componente Célula</span><span class="sxs-lookup"><span data-stu-id="e23e2-157">Cell component</span></span>

<span data-ttu-id="e23e2-158">O componente **Célula** é usado para preencher células, formas e imagens nomeadas no Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-158">The **Cell** component is used to fill in Excel named cells, shapes, and pictures.</span></span> <span data-ttu-id="e23e2-159">Para indicar um objeto nomeado do Excel que deva ser preenchido por um componente ER **Célula**, você deve especificar o nome desse objeto na propriedade **Intervalo do Excel** do componente **Célula**.</span><span class="sxs-lookup"><span data-stu-id="e23e2-159">To indicate an Excel named object that must be filled in by a **Cell** ER component, you must specify the name of that object in the **Excel range** property of the **Cell** component.</span></span>

<span data-ttu-id="e23e2-160">Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Célula** para especificar se o objeto deve ser preenchido em um documento gerado:</span><span class="sxs-lookup"><span data-stu-id="e23e2-160">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Cell** component to specify whether the object must be filled in in a generated document:</span></span>

- <span data-ttu-id="e23e2-161">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, o objeto apropriado será preenchido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-161">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate object will be filled in in the generated document.</span></span> <span data-ttu-id="e23e2-162">A associação deste componente **Célula** especifica um valor que é inserido no objeto apropriado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-162">The binding of this **Cell** component specifies a value that is put in the appropriate object.</span></span>
- <span data-ttu-id="e23e2-163">Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução, o objeto apropriado não será preenchido no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-163">If an expression of the **Enabled** property is configured to return **False** at runtime, the appropriate object won't be filled in in the generated document.</span></span>

<span data-ttu-id="e23e2-164">Quando um componente **Célula** estiver configurado para inserir um valor em uma célula, ele poderá ser associado a uma fonte de dados que retorne o valor de um tipo de dados primitivo (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**).</span><span class="sxs-lookup"><span data-stu-id="e23e2-164">When a **Cell** component is configured to enter a value in a cell, it can be bound with a data source that returns the value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="e23e2-165">Nesse caso, o valor é inserido na célula como um valor do mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="e23e2-165">In this case, the value is entered in the cell as a value of the same data type.</span></span>

<span data-ttu-id="e23e2-166">Quando um componente **Célula** estiver configurado para inserir um valor em um formato Excel, ele poderá ser associado a uma fonte de dados que retorne um valor de um tipo de dados primitivo (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**).</span><span class="sxs-lookup"><span data-stu-id="e23e2-166">When a **Cell** component is configured to enter a value in an Excel shape, it can be bound with a data source that returns a value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="e23e2-167">Nesse caso, o valor é inserido no formato Excel como o texto desse formato.</span><span class="sxs-lookup"><span data-stu-id="e23e2-167">In this case, the value is entered in the Excel shape as the text of that shape.</span></span> <span data-ttu-id="e23e2-168">Para valores de tipos de dados que não são **Cadeia de caracteres**, a conversão em texto é feita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e23e2-168">For values of data types that aren't **String**, the conversion to text is done automatically.</span></span>

> [!NOTE]
> <span data-ttu-id="e23e2-169">Você pode configurar um componente **Célula** para preencher um formato somente quando há suporte a uma propriedade texto de formato.</span><span class="sxs-lookup"><span data-stu-id="e23e2-169">You can configure a **Cell** component to fill in a shape only in cases where a shape text property is supported.</span></span>

<span data-ttu-id="e23e2-170">Quando um componente **Célula** estiver configurado para inserir um valor em uma imagem do Excel, ele poderá ser associado a uma fonte de dados que retorne um valor do tipo de dados **Contêiner** que represente uma imagem em formato binário.</span><span class="sxs-lookup"><span data-stu-id="e23e2-170">When a **Cell** component is configured to enter a value in an Excel picture, it can be bound with a data source that returns a value of the **Container** data type that represents an image in binary format.</span></span> <span data-ttu-id="e23e2-171">Nesse caso, o valor é inserido na imagem do Excel como uma imagem.</span><span class="sxs-lookup"><span data-stu-id="e23e2-171">In this case, the value is entered in the Excel picture as an image.</span></span>

> [!NOTE]
> <span data-ttu-id="e23e2-172">Cada imagem e forma do Excel é considerada ancorada pelo canto superior esquerdo a uma célula ou um intervalo específico do Excel.</span><span class="sxs-lookup"><span data-stu-id="e23e2-172">Every Excel picture and shape is considered to be anchored by its upper-left corner to a specific Excel cell or range.</span></span> <span data-ttu-id="e23e2-173">Se desejar replicar uma imagem ou uma forma do Excel, você deverá configurar a célula ou o intervalo ao qual ela está ancorada como uma célula ou um intervalo replicado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-173">If you want to replicate an Excel picture or shape, you must configure the cell or range that it's anchored to as a replicated cell or range.</span></span>

<span data-ttu-id="e23e2-174">Para saber mais sobre como incorporar imagens e formas, consulte [Incorporar imagens e formas em documentos que você gera usando ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="e23e2-174">To learn more about how to embed images and shapes, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="page-break-component"></a><span data-ttu-id="e23e2-175">Componente Quebra de página</span><span class="sxs-lookup"><span data-stu-id="e23e2-175">Page break component</span></span>

<span data-ttu-id="e23e2-176">O componente **PageBreak** força o Excel a iniciar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="e23e2-176">The **PageBreak** component forces Excel to start a new page.</span></span> <span data-ttu-id="e23e2-177">Esse componente não é necessário quando você deseja usar a paginação padrão do Excel, mas você deve usá-lo quando deseja que o Excel siga o formato ER para a paginação da estrutura.</span><span class="sxs-lookup"><span data-stu-id="e23e2-177">This component isn't required when you want to use Excel's default paging, but you should use it when you want Excel to follow your ER format to structure paging.</span></span>

## <a name="edit-an-added-er-format"></a><span data-ttu-id="e23e2-178">Editar um formato ER adicionado</span><span class="sxs-lookup"><span data-stu-id="e23e2-178">Edit an added ER format</span></span>

### <a name="update-a-template"></a><span data-ttu-id="e23e2-179">Atualize um modelo</span><span class="sxs-lookup"><span data-stu-id="e23e2-179">Update a template</span></span>

<span data-ttu-id="e23e2-180">Você pode selecionar **Atualizar do Excel** na guia **Importar** do Painel de Ações para importar um modelo atualizado para um formato ER editável.</span><span class="sxs-lookup"><span data-stu-id="e23e2-180">You can select **Update from Excel** on the **Import** tab of the Action Pane to import an updated template into an editable ER format.</span></span> <span data-ttu-id="e23e2-181">Durante esse processo, um modelo do componente **Arquivo\\do Excel** selecionado será substituído por um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="e23e2-181">During this process, a template of the selected **Excel\\File** component will be replaced by a new template.</span></span> <span data-ttu-id="e23e2-182">O conteúdo do formato ER editável será sincronizado com o conteúdo do modelo ER atualizado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-182">The content of the editable ER format will be synced with the content of the updated ER template.</span></span>

- <span data-ttu-id="e23e2-183">Um novo componente de formato ER será criado automaticamente para todos os nomes do Excel se o componente de formato ER não for encontrado no formato editável.</span><span class="sxs-lookup"><span data-stu-id="e23e2-183">A new ER format component will automatically be created for every Excel name if the ER format component isn't found in the editable format.</span></span>
- <span data-ttu-id="e23e2-184">Todo componente de formato ER será excluído do formato de ER editável se o nome apropriado do Excel não for encontrado para ele.</span><span class="sxs-lookup"><span data-stu-id="e23e2-184">Every ER format component will be deleted from the editable ER format if the appropriate Excel name isn't found for it.</span></span>

> [!NOTE]
> <span data-ttu-id="e23e2-185">Defina a opção **Criar elemento de formato de planilha do Excel** como **Sim** se desejar criar o elemento **Planilha** opcional no formato ER editável.</span><span class="sxs-lookup"><span data-stu-id="e23e2-185">Set the **Create Excel Sheet format element** option to **Yes** if you want to create the optional **Sheet** element in the editable ER format.</span></span>
>
> <span data-ttu-id="e23e2-186">Se o formato ER editável originalmente contiver elementos **Planilha**, será recomendável definir a opção **Criar elemento de formato de planilha do Excel** como **Sim** ao importar um modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-186">If the editable ER format originally contained **Sheet** elements, we recommend that you set the **Create Excel Sheet format element** option to **Yes** when you import an updated template.</span></span> <span data-ttu-id="e23e2-187">Caso contrário, todos os elementos aninhados do elemento **Planilha** original serão criados do zero.</span><span class="sxs-lookup"><span data-stu-id="e23e2-187">Otherwise, all nested elements of the original **Sheet** element will be created from scratch.</span></span> <span data-ttu-id="e23e2-188">Portanto, todas as associações dos elementos de formato recriados serão perdidas no formato ER atualizado.</span><span class="sxs-lookup"><span data-stu-id="e23e2-188">Therefore, all bindings of the re-created format elements will be lost in the updated ER format.</span></span>

![Opção Criar elemento de formato de planilha do Excel na caixa de diálogo Atualizar do Excel](./media/er-excel-format-update-template.png)

<span data-ttu-id="e23e2-190">Para saber mais sobre esse recurso, siga as etapas em [Modificar formatos de relatório eletrônico reaplicando modelos do Excel](modify-electronic-reporting-format-reapply-excel-template.md).</span><span class="sxs-lookup"><span data-stu-id="e23e2-190">To learn more about this feature, follow the steps in [Modify Electronic reporting formats by reapplying Excel templates](modify-electronic-reporting-format-reapply-excel-template.md).</span></span>

## <a name="validate-an-er-format"></a><span data-ttu-id="e23e2-191">Validar um formato ER</span><span class="sxs-lookup"><span data-stu-id="e23e2-191">Validate an ER format</span></span>

<span data-ttu-id="e23e2-192">Quando você valida um formato ER editável, uma verificação de consistência é realizada para saber se o nome do Excel está presente no modelo do Excel em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="e23e2-192">When you validate an ER format that can be edited, a consistency check is done to make sure that the Excel name is present in the Excel template that is currently used.</span></span> <span data-ttu-id="e23e2-193">Você será notificado sobre as inconsistências.</span><span class="sxs-lookup"><span data-stu-id="e23e2-193">You will be notified about any inconsistencies.</span></span> <span data-ttu-id="e23e2-194">Para algumas inconsistências, a opção de correção automática de problemas será oferecida.</span><span class="sxs-lookup"><span data-stu-id="e23e2-194">For some inconsistencies, the option to automatically fix issues will be offered.</span></span>

![Mensagem de erro de validação](./media/er-excel-format-validate.png)


## <a name="additional-resources"></a><span data-ttu-id="e23e2-196">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e23e2-196">Additional resources</span></span>

[<span data-ttu-id="e23e2-197">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="e23e2-197">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="e23e2-198">Criar uma configuração para gerar relatórios no formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="e23e2-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks\er-design-reports-openxml-2016-11.md)

[<span data-ttu-id="e23e2-199">Modificar formatos de Relatório eletrônico ao reaplicar modelos do Excel</span><span class="sxs-lookup"><span data-stu-id="e23e2-199">Modify Electronic reporting formats by reapplying Excel templates</span></span>](modify-electronic-reporting-format-reapply-excel-template.md)

[<span data-ttu-id="e23e2-200">Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel</span><span class="sxs-lookup"><span data-stu-id="e23e2-200">Use horizontally expandable ranges to dynamically add columns in Excel reports</span></span>](tasks/er-horizontal-1.md)

[<span data-ttu-id="e23e2-201">Inserir imagens e formas em documentos que você gerar usando ER</span><span class="sxs-lookup"><span data-stu-id="e23e2-201">Embed images and shapes in documents that you generate by using ER</span></span>](electronic-reporting-embed-images-shapes.md)

[<span data-ttu-id="e23e2-202">Configurar ER (Relatórios eletrônicos) para efetuar pull de dados para o Power BI</span><span class="sxs-lookup"><span data-stu-id="e23e2-202">Configure Electronic reporting (ER) to pull data into Power BI</span></span>](general-electronic-reporting-report-configuration-get-data-powerbi.md)