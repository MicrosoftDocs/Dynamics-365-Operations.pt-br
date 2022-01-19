---
title: Criar uma configuração para gerar documentos no formato Excel
description: Este tópico descreve como criar um formato de relatório eletrônico (ER) para preencher um modelo do Excel e gerar documentos no formato Excel de saída.
author: NickSelin
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9b1c83894d93789a270ed4521ba7f80da70285ac
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952643"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Criar uma configuração para gerar documentos no formato Excel

[!include[banner](../includes/banner.md)]

Você pode criar uma configuração de formato de [relatório eletrônico (ER)](general-electronic-reporting.md) que tem um componente de formato de ER que pode ser configurado para gerar um documento de saída em um formato de pasta de trabalho do Microsoft Excel. Componentes de formato ER específicos devem ser usados com essa finalidade.

Para saber mais sobre esse recurso, siga as etapas no tópico, [Criar uma configuração para gerar relatórios no formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Adicionar um novo formato ER

Ao adicionar uma nova configuração de formato ER para gerar um documento de saída em um formato de pasta de trabalho do Excel, você deve selecionar o valor **Excel** para o atributo **Tipo de formato** no formato ou deixar o atributo **Tipo de formato** em branco.

- Se você selecionar **Excel**, poderá configurar o formato para gerar um documento de saída somente no formato Excel.
- Se você deixar o atributo em branco, poderá configurar o formato para gerar um documento de saída em qualquer formato com suporte da estrutura ER.

Para configurar o componente de formato ER da configuração, selecione **Designer** no Painel de Ações e abra o componente de formato ER para edição no designer de operação do ER.

![Página Configurações.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente Arquivo do Excel

### <a name="manual-entry"></a>Entrada manual

Você deve adicionar um componente **Arquivo\\do Excel** ao formato ER configurado para gerar um documento de saída no formato Excel.

![Componente Arquivo\do Excel.](./media/er-excel-format-add-file-component.png)

Para especificar o layout do documento de saída, anexe uma pasta de trabalho do Excel com a extensão .xlsx ao componente **Arquivo\\do Excel** como o modelo para documentos de saída.

> [!NOTE]
> Ao anexar manualmente um modelo, você deve usar um [tipo de documento](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) que tenha sido configurado com essa finalidade nos [parâmetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Adição de um anexo ao componente Arquivo\do Excel.](./media/er-excel-format-add-file-component2.png)

Para especificar como o modelo anexado será preenchido quando você executar o formato ER configurado, adicione componentes aninhados **Planilha**, **Intervalo** e **Célula** ao componente **Arquivo\\do Excel**. Cada componente aninhado deve estar associado a um item nomeado do Excel.

### <a name="template-import"></a>Importação de modelo

Você pode selecionar **Importar do Excel** na guia **Importar** do Painel de Ações para importar um novo modelo para um formato ER em branco. Neste exemplo, um componente **Arquivo\\do Excel** será criado automaticamente e o modelo importado será anexado a ele. Todos os componentes ER obrigatórios também serão criados automaticamente, com base na lista de itens nomeados do Excel que forem descobertos.

![Seleção de Importar do Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Se desejar criar o elemento opcional **Planilha** no formato ER editável, defina a opção **Criar elemento de formato de planilha do Excel** como **Sim**.

## <a name="sheet-component"></a>Componente Planilha

O componente **Planilha** indica uma planilha da pasta de trabalho do Excel anexada que deve ser preenchida. O nome da planilha em um modelo do Excel é definido na propriedade **Planilha** deste componente.

> [!NOTE]
> Esse componente é opcional para pastas de trabalho do Excel que contêm uma única planilha.

Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Planilha** para especificar se o componente deve ser colocado em um documento gerado:

- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, a planilha apropriada será colocada no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução, o documento gerado não conterá uma planilha.

![Exemplo de um componente Planilha.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Componente Intervalo

O componente **Intervalo** indica um intervalo do Excel que deve ser controlado por esse componente ER. O nome do intervalo é definido na propriedade **Intervalo do Excel** deste componente.

### <a name="replication"></a>Replicação

A propriedade **Direção da replicação** especifica se e como o intervalo será repetido em um documento gerado:

- Se a propriedade **Direção da replicação** estiver definida como **Sem replicação**, o intervalo do Excel apropriado não será repetido no documento gerado.
- Se a propriedade **Direção da replicação** estiver definida como **Vertical**, o intervalo do Excel apropriado será repetido no documento gerado. Todo intervalo replicado é colocado abaixo do intervalo original em um modelo do Excel. O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.
- Se a propriedade **Direção da replicação** estiver definida como **Horizontal**, o intervalo do Excel apropriado será repetido no documento gerado. Todo intervalo replicado é colocado à direita do intervalo original em um modelo do Excel. O número de repetições é definido pelo número de registros em uma fonte de dados do tipo **Lista de registros** que está associada a este componente ER.

Para saber mais sobre a replicação horizontal, siga as etapas em [Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente nos relatórios do Excel](tasks/er-horizontal-1.md).

### <a name="nested-components"></a>Componentes aninhados

O componente **Intervalo** pode ter outros componentes ER aninhados que são usados para inserir valores nos intervalos nomeados apropriados do Excel.

- Se qualquer componente do grupo **Texto** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor de texto.

    > [!NOTE]
    > Use este padrão para formatar valores inseridos com base na localidade definida no aplicativo.

- Se o componente **Célula** do grupo **Excel** for usado para inserir valores, o valor será inserido em um intervalo do Excel como um valor do tipo de dados definido pela associação do componente **Célula** (por exemplo, **Cadeia de caracteres**, **Real** ou **Inteiro**).

    > [!NOTE]
    > Use este padrão para permitir que o aplicativo Excel formate valores inseridos com base na localidade do computador local que abre o documento de saída.

### <a name="enabling"></a>Habilitando

Na guia **Mapeamento** do designer de operação do ER, você pode configurar a propriedade **Habilitado** para um componente **Intervalo** para especificar se o componente deve ser colocado em um documento gerado:

- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Verdadeiro** no tempo de execução ou se nenhuma expressão for configurada, o intervalo apropriado será preenchido no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo não representar as linhas ou colunas inteiras, o intervalo apropriado não será preenchido no documento gerado.
- Se uma expressão da propriedade **Habilitado** estiver configurada para retornar **Falso** no tempo de execução e se esse intervalo representar as linhas ou colunas inteiras, o documento gerado conterá essas linhas e colunas como linhas e colunas ocultas.

### <a name="resizing"></a>Alinhamento

Você pode configurar o modelo do Excel para usar células para apresentar dados textuais. Para garantir que todo o texto em uma célula fique visível em um documento gerado, você pode configurar essa célula para quebrar automaticamente o texto dentro dela. Você também poderá configurar a linha que contém essa célula para ajustar automaticamente a altura se o texto disposto não estiver totalmente visível. Para obter mais informações, consulte a seção "Quebrar texto automaticamente em uma célula" em [Corrigir dados cortados em células](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e).

> [!NOTE]
> Por causa de uma [limitação do Excel](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353) conhecida, mesmo se você configurar células para quebrar texto automaticamente e configurar as linhas contendo essas células para ajustar automaticamente a altura de acordo com o texto disposto, talvez não consiga usar os recursos **Autoajuste** e **Quebra automática de texto** do Excel para células mescladas e as linhas que as contêm. 

A partir do Dynamics 365 Finance versão 10.0.23, é possível forçar o ER a calcular, em um documento gerado, a altura de cada linha configurada para ajustar automaticamente a altura ao conteúdo de células aninhadas sempre que essa linha contém pelo menos uma célula mesclada que foi configurada para incluir o texto nela. A altura calculada é usada para redimensionar a linha para garantir que todas as células da linha fiquem visíveis no documento gerado. Para começar a usar essa funcionalidade ao executar formatos ER configurados para usar modelos do Excel para gerar documentos de saída, siga estas etapas.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Runtime**, defina a opção **Autoajuste da altura da linha** como **Sim**.

Quando desejar alterar essa regra para um único formato ER, atualize a versão de rascunho desse formato seguindo essas etapas.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configurações no painel esquerdo, selecione uma configuração ER criada para usar um modelo do Excel para gerar documentos de saída.
4. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
5. No Painel de Ação, selecione **Designer**.
6. Na página **Designer de formato**, na árvore de formatos no painel esquerdo, selecione o componente Excel que está vinculado a um modelo do Excel.
7. Na guia **Formatar**, no campo **Ajustar altura da linha**, selecione um valor para especificar se ER deve ser forçado, no runtime, para alterar a altura de linhas em um documento de saída gerado pelo formato ER editado:

    - **Padrão** – use a configuração geral que está configurada no campo **Autoajuste da altura da linha** na página **Parâmetros de relatório eletrônicos**.
    - **Sim** – substitui a configuração geral e altera a altura da linha no runtime.
    - **Não** – substitui a configuração geral e não altera a altura da linha no runtime.

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

## <a name="page-component"></a><a name="page-component"></a>Componente da página

### <a name="overview"></a>Visão Geral

Você pode usar o componente da **Página** quando quiser que o Excel siga o formato ER e a paginação da estrutura em um documento de saída gerado. Quando um formato ER executa componentes que estão sob o componente da **Página**, as quebras de página necessárias são adicionadas automaticamente. Durante esse processo, o tamanho do conteúdo gerado, a configuração de página do modelo do Excel e o tamanho do papel selecionado no modelo do Excel são considerados.

Se você deve dividir um documento gerado em seções diferentes, cada um deles tem uma paginação diferente, é possível configurar vários componentes da **Página** em cada componente da [Planilha](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Estrutura

Se o primeiro componente no componente da **Página** for um componente do [Intervalo](er-fillable-excel.md#range-component) no qual a propriedade **Direção da replicação** estiver definida como **Sem replicação**, esse intervalo será considerado o cabeçalho da página para paginação baseada nas configurações do componente da **Página** atual. O intervalo do Excel associado a esse componente de formato é repetido na parte superior de cada página gerada usando as configurações do componente da **Página** atual.

> [!NOTE]
> Para paginação correta, se as [Linhas a serem repetidas](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) no intervalo superior forem configuradas no seu modelo do Excel, o endereço desse intervalo do Excel deverá ser igual ao endereço do intervalo do Excel associado ao componente do **Intervalo** descrito anteriormente.

Se o último componente no componente da **Página** for um componente do **Intervalo** no qual a propriedade **Direção da replicação** estiver definida como **Sem replicação**, esse intervalo será considerado o rodapé da página para paginação baseada nas configurações do componente da **Página** atual. O intervalo do Excel associado a esse componente de formato é repetido na parte inferior de cada página gerada usando as configurações do componente da **Página** atual.

> [!NOTE]
> Para a paginação correta, os intervalos do Excel associados aos componentes do **Intervalo** não devem ser redimensionados no tempo de execução. Não é recomendável formatar células deste intervalo usando as [opções](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84) do Excel **Quebra automática de texto em uma célula** e **Ajustar altura da linha**.

Você pode adicionar vários outros componentes do **Intervalo** entre os componentes do **Intervalo** para especificar como um documento gerado é preenchido.

Se o conjunto de componentes do **Intervalo** aninhado no componente da **Página** não estiver de acordo com a estrutura descrita anteriormente, ocorre [erro](er-components-inspections.md#i17) no tempo de design no designer de formato do ER. A mensagem de erro informa que isso pode causar problemas durante o tempo de execução.

> [!NOTE]
> Para gerar a saída correta, não especifique uma associação para qualquer componente do **Intervalo** no componente da **Página**, se a propriedade **Direção da replicação** desse componente do **Intervalo** estiver definida como **Sem replicação** e o intervalo estiver configurado para gerar cabeçalhos de página ou rodapés de página.

Se você desejar que a soma e a contagem relacionados à paginação calculem os totais de execução e totais por página, recomendamos que você configure as fontes de dados necessárias da [Coleta de dados](er-data-collection-data-sources.md). Para aprender a usar o componente da **Página** para paginar um documento do Excel gerado, conclua os procedimentos em [Criar um formato ER para paginar documentos gerados no Excel](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Limitações

Ao usar o componente da **Página** para paginação do Excel, você não saberá o número final de páginas em um documento gerado até que a paginação seja concluída. Portanto, não é possível calcular o número total de páginas usando fórmulas de ER e imprimir o número correto de páginas de um documento gerado em qualquer página antes da última página.

> [!TIP]
> Para obter esse resultado em um cabeçalho ou rodapé do Excel, usando a [formatação](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) especial do Excel para cabeçalhos e rodapés.

Componentes de **Página** configurados não são considerados quando você atualiza um modelo do Excel no formato editável na versão 10.0.22 do Dynamics 365 Finance. Essa funcionalidade é considerada para novas versões de Finanças.

Se você configurar seu modelo do Excel para usar a [formatação condicional](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), talvez ele não funcione como esperado em alguns casos.

### <a name="applicability"></a>Aplicabilidade

O componente da **Página** funciona para o componente de formato do [arquivo do Excel](er-fillable-excel.md#excel-file-component) somente quando esse componente for configurado para usar um modelo no Excel. Se você [substituir](tasks/er-design-configuration-word-2016-11.md) o modelo do Excel por um modelo do Word e executar o formato de ER editável, o componente da **Página** será ignorado.

O componente da **Página** funciona somente quando o recurso **Habilitar uso da biblioteca de EPPlus em estrutura eletrônica de relatórios** estiver habilitado. Uma exceção será lançada no tempo de execução, se o ER tentar processar o componente **Página** enquanto esse recurso estiver desabilitado.

> [!NOTE]
> Uma exceção é lançada no tempo de execução se um formato de ER processar o componente da **Página** para um modelo do Excel que contém pelo menos uma fórmula que se refere a uma célula que não é válida. Para ajudar a evitar erros de tempo de execução, corrija o modelo do Excel conforme descrito em [Como corrigir um erro de #REF!](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Componente do rodapé

O componente **Rodapé** é usado para preencher os rodapés na parte inferior de uma planilha gerada em uma pasta de trabalho do Excel.

> [!NOTE]
> Você pode adicionar esse componente para cada componente de **Planilha** a fim de especificar diferentes rodapés para planilhas diferentes em uma pasta de trabalho do Excel gerada.

Ao configurar um componente **Rodapé** individual , você poderá usar a propriedade de **Aparência de cabeçalho/rodapé** para especificar as páginas para as quais o componente é usado. Os valores a seguir estão disponíveis:

- **Qualquer** – execute o componente **Rodapé** configurado para qualquer página da planilha do Excel pai.
- **Primeira** – execute o componente **Rodapé** configurado somente para a primeira página da planilha do Excel pai.
- **Pares** – execute o componente **Rodapé** configurado somente para as páginas pares da planilha do Excel pai.
- **Ímpares** – execute o componente **Rodapé** configurado somente para as páginas ímpares da planilha do Excel pai.

Para um único componente **Planilha**, você pode adicionar vários componentes **Rodapé**, cada um deles com um valor diferente para a propriedade **Aparência de cabeçalho/rodapé**. Dessa forma, você poderá gerar diferentes rodapés para diferentes tipos de páginas em uma planilha do Excel.

> [!NOTE]
> Certifique-se de que cada componente **Rodapé** adicionado a um único componente **Planilha** tenha um valor diferente para a propriedade **Aparência de cabeçalho/rodapé**. Caso contrário, ocorrerá um [erro de validação](er-components-inspections.md#i16). A mensagem de erro recebida notifica sobre a inconsistência.

No componente **Rodapé** adicionado, adicione os componentes aninhados necessários de **Texto\\Cadeia de Caracteres**, **Texto\\DateTime**, ou outro tipo. Configure as associações para esses componentes para especificar como o rodapé da página será preenchido.

Você também pode usar [códigos de formatação](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) especiais para formatar corretamente o conteúdo de um rodapé gerado. Para saber como usar essa abordagem, siga as etapas no [Exemplo 1](#example-1), posteriormente neste tópico.

> [!NOTE]
> Ao configurar os formatos de ER, certifique-se de considerar o [limite](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) do Excel e o número máximo de caracteres para um único cabeçalho ou rodapé.

## <a name="header-component"></a>Componente do cabeçalho

O componente **Cabeçalho** é usado para preencher os cabeçalhos na parte superior de uma planilha gerada em uma pasta de trabalho do Excel. Ele é usado como o componente **Rodapé**.

## <a name="edit-an-added-er-format"></a>Editar um formato ER adicionado

### <a name="update-a-template"></a>Atualize um modelo

Você pode selecionar **Atualizar do Excel** na guia **Importar** do Painel de Ações para importar um modelo atualizado para um formato ER editável. Durante esse processo, um modelo do componente **Arquivo\\do Excel** selecionado será substituído por um novo modelo. O conteúdo do formato ER editável será sincronizado com o conteúdo do modelo ER atualizado.

- Um novo componente de formato ER será criado automaticamente para todos os nomes do Excel se o componente de formato ER não for encontrado no formato editável.
- Todo componente de formato ER será excluído do formato de ER editável se o nome apropriado do Excel não for encontrado para ele.

> [!NOTE]
> Defina a opção **Criar elemento de formato de planilha do Excel** como **Sim** se desejar criar o elemento **Planilha** opcional no formato ER editável.
>
> Se o formato ER editável originalmente contiver elementos **Planilha**, será recomendável definir a opção **Criar elemento de formato de planilha do Excel** como **Sim** ao importar um modelo atualizado. Caso contrário, todos os elementos aninhados do elemento **Planilha** original serão criados do zero. Portanto, todas as associações dos elementos de formato recriados serão perdidas no formato ER atualizado.

![Opção Criar elemento de formato de planilha do Excel na caixa de diálogo Atualizar do Excel.](./media/er-excel-format-update-template.png)

Para saber mais sobre esse recurso, siga as etapas em [Modificar formatos de relatório eletrônico reaplicando modelos do Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validar um formato ER

Quando você valida um formato ER editável, uma verificação de consistência é realizada para saber se o nome do Excel está presente no modelo do Excel em uso no momento. Você será notificado sobre as inconsistências. Para algumas inconsistências, a opção de correção automática de problemas será oferecida.

![Mensagem de erro de validação.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controlar o cálculo de fórmulas do Excel

Quando um documento de saída é gerado em um formato de pasta de trabalho do Microsoft Excel, algumas células deste documento podem conter fórmulas do Excel. Quando o recurso **Habilitar uso da biblioteca de EPPlus em estrutura eletrônica de relatórios** estiver habilitado, você pode controlar quando as fórmulas são calculadas alterando o valor do [parâmetro](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows)**Opções de cálculo** no modelo do Excel que está sendo usado:

- Selecione **Automático** para recalcular todas as fórmulas dependentes toda vez que um documento gerado for acrescentado por novos intervalos, células etc.

    >[!NOTE]
    > Isso pode causar um problema de desempenho para os modelos do Excel que contêm várias fórmulas relacionadas.

- Selecione **Manual** para evitar o recálculo de fórmulas quando um documento é gerado.

    >[!NOTE]
    > O recálculo da fórmula é forçado manualmente quando um documento gerado é aberto para visualização usando o Excel.
    > Não use esta opção se você configurar um destino ER que suponha o uso de um documento gerado sem sua visualização no Excel (conversão em PDF, email, etc.) como o documento gerado pode não conter valores nas células que contêm fórmulas.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Exemplo 1: Formatar conteúdo de rodapé

1. Use as configurações de ER fornecidas para [gerar](er-generate-printable-fti-forms.md) um documento da fatura de texto livre (FTI) imprimível.
2. Analise o rodapé do documento gerado. Observe que ele contém informações sobre o número de página atual e o número total de páginas no documento.

    ![Analisar o rodapé de um documento gerado no formato do Excel.](./media/er-fillable-excel-footer-1.gif)

3. No designer de formato ER, [abra](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) o formato ER de exemplo para análise.

    O rodapé da planilha **Fatura** é gerado com base nas configurações de dois componentes **Cadeia de Caracteres** que residem no componente **Rodapé**:

    - O primeiro componente **Cadeia de Caracteres** preenche os seguintes códigos de formatação especiais para forçar o Excel a aplicar formatação específica:

        - **&C** – alinha o texto do rodapé no centro.
        - **&"Segoe UI,Regular"&8** – apresenta o texto do rodapé na fonte "Segoe UI Regular" em um tamanho de 8 pontos.

    - O segundo componente **Cadeia de Caracteres** preenche o texto que contém o número de página atual e o número total de páginas no documento atual.

    ![Analisar o componente de formato ER Rodapé na página Designer de formato.](./media/er-fillable-excel-footer-2.png)

4. Personalize o formato ER de exemplo para modificar o rodapé da página atual:

    1. [Crie](er-quick-start2-customize-report.md#DeriveProvidedFormat) um formato ER personalizado de **Fatura de texto livre (Excel)** derivado baseado no formato ER de exemplo.
    2. Adicione o primeiro par novo de componentes **Cadeia de Caracteres** para o componente **Rodapé** da planilha **Fatura**:

        1. Adicione um componente **Cadeia de Caracteres** que alinhe o nome da empresa à esquerda e o apresente na fonte "Segoe UI Regular" de 8 pontos (**"&L&"Segoe UI,Regular"&8"**).
        2. Adicione um componente **Cadeia de Caracteres** que preencha o nome da empresa (**model.InvoiceBase.CompanyInfo.Name**).

    3. Adicione o segundo par novo de componentes **Cadeia de Caracteres** para o componente **Rodapé** da planilha **Fatura**:

        1. Adicione um componente **Cadeia de Caracteres** que alinhe a data de processamento à direita e a apresente na fonte "Segoe UI Regular" de 8 pontos (**"&R&"Segoe UI,Regular"&8"**).
        2. Adicione um componente **Cadeia de Caracteres** que preencha a data de processamento em um formato personalizado (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Análise do componente de formato de ER Rodapé na página Designer de formato.](./media/er-fillable-excel-footer-3.png)

    4. [Preencha](er-quick-start2-customize-report.md#CompleteDerivedFormat) a versão de rascunho do formato ER personalizado da **Fatura de texto livre (Excel)** derivada.

5. [Configure](er-generate-printable-fti-forms.md#configure-print-management) o Gerenciamento de impressão para usar o formato ER personalizado da **Fatura de texto livre (Excel)** derivada em vez do formato ER de exemplo.
6. Gere um documento de impressão FTI e analise o rodapé do documento gerado.

    ![Análise do rodapé de um documento gerado no formato do Excel.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>Exemplo 2: Corrigir o problema de EPPlus de células mescladas

Você pode executar um formato de ER para gerar um documento de saída em um formato de pasta de trabalho do Excel. Quando o recurso **Habilitar uso da biblioteca de EPPlus em estrutura eletrônica de relatórios** estiver habilitado no workspace **Gerenciamento de recursos**, a [biblioteca de EPPlus](https://www.nuget.org/packages/epplus/4.5.2.1) será usada para gerar a saída do Excel. No entanto, devido ao [comportamento do Excel](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9) conhecido e a uma limitação da biblioteca de EPPlus, você pode encontrar a seguinte exceção: "Não é possível excluir/substituir células mescladas. Um intervalo é mesclado parcialmente com o outro intervalo mesclado." Para saber qual tipo de modelos do Excel podem causar essa exceção e como você pode corrigir o problema, conclua o exemplo a seguir.

1. No aplicativo de área de trabalho do Excel, crie uma nova pasta de trabalho do Excel.
2. Na planilha **Sheet1**, adicione o nome **ReportTitle** para a célula **A2**.
3. Mescle as células **A1** e **A2**.

    ![Revisão dos resultados das células de mesclagem A1 e A2 na pasta de trabalho do Excel criada no aplicativo de área de trabalho do Excel.](./media/er-fillable-excel-example2-1.png)

3. Na página **Configurações**, [adicione um novo formato de ER](er-fillable-excel.md#add-a-new-er-format) para gerar um documento de saída em um formato de pasta de trabalho do Excel.
4. Na página **Designer de formato**, [importe](er-fillable-excel.md#template-import) a pasta de trabalho do Excel criada para o formato de ER adicionado como um novo modelo para documentos de saída.
5. Na guia **Mapeamento**, configure a associação para o componente **ReportTitle** do tipo de [célula](er-fillable-excel.md#cell-component).
6. Execute o formato de ER configurado. Observe que a seguinte exceção é lançada: "Não é possível excluir/substituir células mescladas. Um intervalo é mesclado parcialmente com o outro intervalo mesclado."

    ![Revisão dos resultados da execução do formato de ER configurado na página Designer de formato.](./media/er-fillable-excel-example2-2.png)

Você pode corrigir o problema de uma das seguintes maneiras:

- **Mais fácil, mas não recomendado:** no workspace **Gerenciamento de recursos**, desative o recurso **Habilitar uso da biblioteca de EPPlus em estrutura de Relatório eletrônico**. Embora essa abordagem seja mais fácil, você poderá ter outras saídas se usá-la, pois há suporte para algumas funcionalidades de ER somente quando o recurso **Habilitar uso da biblioteca de EPPlus em estrutura de Relatório eletrônico** está habilitado.
- **Recomendado:** siga estas etapas:

    1. No aplicativo de área de trabalho do Excel, modifique a pasta de trabalho do Excel de uma das seguintes maneiras:

        - Na planilha **1**, desfaça a mesclagem das células **A1** e **A2**.
        - Altere a referência do nome **ReportTitle** de **=Sheet1!$A$2** para **=Sheet1!$A$1**.

        ![Revisão dos resultados da alteração da referência na pasta de trabalho do Excel criada no aplicativo de área de trabalho do Excel.](./media/er-fillable-excel-example2-3.png)

    2. Na página **Designer de formato**, [importe](er-fillable-excel.md#template-import) a pasta de trabalho do Excel modificada para o formato de ER editável a fim de atualizar o modelo existente.
    3. Execute o formato de ER modificado.

        ![Revisão do documento gerado no aplicativo de área de trabalho do Excel.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>Limitações

### <a name="known-epplus-library-limitations"></a>Limitações conhecidas da biblioteca EPPlus

#### <a name="external-data-sources"></a>Fontes de dados externas

Se um dos seus modelos contiver uma Tabela Dinâmica baseada em um modelo do PowerPivot que se refere a uma [fonte de dados externa](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b) e o recurso **Habilitar o uso da biblioteca EPPlus na estrutura do Relatório Eletrônico** estiver habilitado, você receberá a seguinte mensagem de erro ao executar um formato de ER que usa esse modelo para gerar um documento de saída no formato Excel: "A fonte de cache não é uma planilha". Para solucionar esse problema, você tem estas opções:

- **Recomendado:** Recrie a solução do Excel que você está usando:

    1. Isole a parte que contém pivôs em uma pasta de trabalho separada do Excel (pasta de trabalho A). 
    2. Use ER para gerar uma segunda pasta de trabalho do Excel (pasta de trabalho B) do Finance com os detalhes necessários. 
    3. Consulte a pasta de trabalho B na pasta de trabalho A assim que a pasta de trabalho B for gerada.

- Desativar o recurso, **Habilitar o uso da biblioteca de EPPlus na estrutura eletrônica de relatórios** para usar uma opção que não seja EPPlus. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Criar uma configuração para gerar relatórios no formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificar formatos de Relatório eletrônico ao reaplicar modelos do Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel](tasks/er-horizontal-1.md)

[Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md)

[Configurar ER (Relatórios eletrônicos) para efetuar pull de dados para o Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
