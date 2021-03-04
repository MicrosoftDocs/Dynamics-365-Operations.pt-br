---
title: Criar uma configuração para gerar documentos no formato Excel
description: Este tópico fornece informações sobre como criar um formato de relatório eletrônico (ER) para preencher um modelo do Excel e gerar documentos no formato Excel de saída.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5733e40c67f9c97b04f126f7c3cfea9d4f8f5b5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686529"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Criar uma configuração para gerar documentos no formato Excel

[!include[banner](../includes/banner.md)]

Você pode criar uma configuração de formato de [relatório eletrônico (ER)](general-electronic-reporting.md) que tem um ER [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) que pode ser configurado para gerar um documento de saída em um formato de pasta de trabalho do Microsoft Excel. Componentes de formato ER específicos devem ser usados com essa finalidade.

Para saber mais sobre esse recurso, siga as etapas no tópico, [Criar uma configuração para gerar relatórios no formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Adicionar um novo formato ER

Ao adicionar uma nova configuração de formato ER para gerar um documento de saída em um formato de pasta de trabalho do Excel, você deve selecionar o valor **Excel** para o atributo **Tipo de formato** no formato ou deixar o atributo **Tipo de formato** em branco.

- Se você selecionar **Excel**, poderá configurar o formato para gerar um documento de saída somente no formato Excel.
- Se você deixar o atributo em branco, poderá configurar o formato para gerar um documento de saída em qualquer formato com suporte da estrutura ER.

Para configurar o componente de formato ER da configuração, selecione **Designer** no Painel de Ações e abra o componente de formato ER para edição no designer de operação do ER.

![Página Configurações](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente Arquivo do Excel

### <a name="manual-entry"></a>Entrada manual

Você deve adicionar um componente **Arquivo\\do Excel** ao formato ER configurado para gerar um documento de saída no formato Excel.

![Componente Arquivo\do Excel](./media/er-excel-format-add-file-component.png)

Para especificar o layout do documento de saída, anexe uma pasta de trabalho do Excel com a extensão .xlsx ao componente **Arquivo\\do Excel** como o modelo para documentos de saída.

> [!NOTE]
> Ao anexar manualmente um modelo, você deve usar um [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) que tenha sido configurado com essa finalidade nos [parâmetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Adição de um anexo ao componente Arquivo\do Excel](./media/er-excel-format-add-file-component2.png)

Para especificar como o modelo anexado será preenchido quando você executar o formato ER configurado, adicione componentes aninhados **Planilha**, **Intervalo** e **Célula** ao componente **Arquivo\\do Excel**. Cada componente aninhado deve estar associado a um item nomeado do Excel.

### <a name="template-import"></a>Importação de modelo

Você pode selecionar **Importar do Excel** na guia **Importar** do Painel de Ações para importar um novo modelo para um formato ER em branco. Neste exemplo, um componente **Arquivo\\do Excel** será criado automaticamente e o modelo importado será anexado a ele. Todos os componentes ER obrigatórios também serão criados automaticamente, com base na lista de itens nomeados do Excel que forem descobertos.

![Seleção de Importar do Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Se desejar criar o elemento opcional **Planilha** no formato ER editável, defina a opção **Criar elemento de formato de planilha do Excel** como **Sim**.

## <a name="sheet-component"></a>Componente Planilha

O componente **Planilha** indica uma planilha da pasta de trabalho do Excel anexada que deve ser preenchida. O nome da planilha em um modelo do Excel é definido na propriedade **Planilha** deste componente.

> [!NOTE]
> Esse componente é opcional para pastas de trabalho do Excel que contêm uma única planilha.

Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Planilha** para especificar se o componente deve ser colocado em um documento gerado:

- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, a planilha apropriada será colocada no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução, o documento gerado não conterá uma planilha.

![Exemplo de um componente Planilha](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Componente Intervalo

O componente **Intervalo** indica um intervalo do Excel que deve ser controlado por esse componente ER. O nome do intervalo é definido na propriedade **Intervalo do Excel** deste componente.

A propriedade **Direção da replicação** especifica se e como o intervalo será repetido em um documento gerado:

- Se a propriedade **Direção da replicação** estiver definida como **Sem replicação**, o intervalo do Excel apropriado não será repetido no documento gerado.
- Se a propriedade **Direção da replicação** estiver definida como **Vertical**, o intervalo do Excel apropriado será repetido no documento gerado. Todo intervalo replicado é colocado abaixo do intervalo original em um modelo do Excel. O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.
- Se a propriedade **Direção da replicação** estiver definida como **Horizontal**, o intervalo do Excel apropriado será repetido no documento gerado. Todo intervalo replicado é colocado à direita do intervalo original em um modelo do Excel. O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.

Para saber mais sobre a replicação horizontal, siga as etapas em [Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente nos relatórios do Excel](tasks/er-horizontal-1.md).

O componente **Intervalo** pode ter outros componentes ER aninhados que são usados para inserir valores nos intervalos nomeados apropriados do Excel.

- Se qualquer componente do grupo **Texto** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor de texto.

    > [!NOTE]
    > Use este padrão para formatar valores inseridos com base na localidade definida no aplicativo.

- Se o componente **Célula** do grupo **Excel** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor do tipo de dados definido pela associação do componente **Célula** (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**).

    > [!NOTE]
    > Use este padrão para permitir que o aplicativo Excel formate valores inseridos com base na localidade do computador local que abre o documento de saída.

Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Intervalo** para especificar se o componente deve ser colocado em um documento gerado:

- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, o intervalo apropriado será preenchido no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo não representar as linhas ou colunas inteiras, o intervalo apropriado não será preenchido no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo representar as linhas ou colunas inteiras, o documento gerado conterá essas linhas e colunas como linhas e colunas ocultas.

## <a name="cell-component"></a>Componente Célula

O componente **Célula** é usado para preencher células, formas e imagens nomeadas no Excel. Para indicar um objeto nomeado do Excel que deva ser preenchido por um componente ER **Célula**, você deve especificar o nome desse objeto na propriedade **Intervalo do Excel** do componente **Célula**.

Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Célula** para especificar se o objeto deve ser preenchido em um documento gerado:

- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, o objeto apropriado será preenchido no documento gerado. A associação deste componente **Célula** especifica um valor que é inserido no objeto apropriado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução, o objeto apropriado não será preenchido no documento gerado.

Quando um componente **Célula** estiver configurado para inserir um valor em uma célula, ele poderá ser associado a uma fonte de dados que retorne o valor de um tipo de dados primitivo (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**). Nesse caso, o valor é inserido na célula como um valor do mesmo tipo de dados.

Quando um componente **Célula** estiver configurado para inserir um valor em um formato Excel, ele poderá ser associado a uma fonte de dados que retorne um valor de um tipo de dados primitivo (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**). Nesse caso, o valor é inserido no formato Excel como o texto desse formato. Para valores de tipos de dados que não são **Cadeia de caracteres**, a conversão em texto é feita automaticamente.

> [!NOTE]
> Você pode configurar um componente **Célula** para preencher um formato somente quando há suporte a uma propriedade texto de formato.

Quando um componente **Célula** estiver configurado para inserir um valor em uma imagem do Excel, ele poderá ser associado a uma fonte de dados que retorne um valor do tipo de dados **Contêiner** que represente uma imagem em formato binário. Nesse caso, o valor é inserido na imagem do Excel como uma imagem.

> [!NOTE]
> Cada imagem e forma do Excel é considerada ancorada pelo canto superior esquerdo a uma célula ou um intervalo específico do Excel. Se desejar replicar uma imagem ou uma forma do Excel, você deverá configurar a célula ou o intervalo ao qual ela está ancorada como uma célula ou um intervalo replicado.

Para saber mais sobre como incorporar imagens e formas, consulte [Incorporar imagens e formas em documentos que você gera usando ER](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Componente Quebra de página

O componente **PageBreak** força o Excel a iniciar uma nova página. Esse componente não é necessário quando você deseja usar a paginação padrão do Excel, mas você deve usá-lo quando deseja que o Excel siga o formato ER para a paginação da estrutura.

## <a name="edit-an-added-er-format"></a>Editar um formato ER adicionado

### <a name="update-a-template"></a>Atualize um modelo

Você pode selecionar **Atualizar do Excel** na guia **Importar** do Painel de Ações para importar um modelo atualizado para um formato ER editável. Durante esse processo, um modelo do componente **Arquivo\\do Excel** selecionado será substituído por um novo modelo. O conteúdo do formato ER editável será sincronizado com o conteúdo do modelo ER atualizado.

- Um novo componente de formato ER será criado automaticamente para todos os nomes do Excel se o componente de formato ER não for encontrado no formato editável.
- Todo componente de formato ER será excluído do formato de ER editável se o nome apropriado do Excel não for encontrado para ele.

> [!NOTE]
> Defina a opção **Criar elemento de formato de planilha do Excel** como **Sim** se desejar criar o elemento **Planilha** opcional no formato ER editável.
>
> Se o formato ER editável originalmente contiver elementos **Planilha**, será recomendável definir a opção **Criar elemento de formato de planilha do Excel** como **Sim** ao importar um modelo atualizado. Caso contrário, todos os elementos aninhados do elemento **Planilha** original serão criados do zero. Portanto, todas as associações dos elementos de formato recriados serão perdidas no formato ER atualizado.

![Opção Criar elemento de formato de planilha do Excel na caixa de diálogo Atualizar do Excel](./media/er-excel-format-update-template.png)

Para saber mais sobre esse recurso, siga as etapas em [Modificar formatos de relatório eletrônico reaplicando modelos do Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validar um formato ER

Quando você valida um formato ER editável, uma verificação de consistência é realizada para saber se o nome do Excel está presente no modelo do Excel em uso no momento. Você será notificado sobre as inconsistências. Para algumas inconsistências, a opção de correção automática de problemas será oferecida.

![Mensagem de erro de validação](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controlar o cálculo de fórmulas do Excel

Quando um documento de saída é gerado em um formato de pasta de trabalho do Microsoft Excel, algumas células deste documento podem conter fórmulas do Excel. Quando o recurso **Habilitar uso da biblioteca de EPPlus em estrutura eletrônica de relatórios** estiver habilitado, você pode controlar quando as fórmulas são calculadas alterando o valor do [parâmetro](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows)**Opções de cálculo** no modelo do Excel que está sendo usado:

- Selecione **Automático** para recalcular todas as fórmulas dependentes toda vez que um documento gerado for acrescentado por novos intervalos, células etc.
    >[!NOTE]
    > Isso pode causar um problema de desempenho para os modelos do Excel que contêm várias fórmulas relacionadas.
- Selecione **Manual** para evitar o recálculo de fórmulas quando um documento é gerado.
    >[!NOTE]
    > O recálculo da fórmula é forçado manualmente quando um documento gerado é aberto para visualização usando o Excel.
    > Não use esta opção se você configurar um destino ER que suponha o uso de um documento gerado sem sua visualização no Excel (conversão em PDF, email, etc.) como o documento gerado pode não conter valores nas células que contêm fórmulas.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Criar uma configuração para gerar relatórios no formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificar formatos de Relatório eletrônico ao reaplicar modelos do Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel](tasks/er-horizontal-1.md)

[Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md)

[Configurar ER (Relatórios eletrônicos) para efetuar pull de dados para o Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]