---
title: Criar um formato de ER para paginar documentos gerados no Excel
description: Este tópico explica como criar um formato de Relatório eletrônico (ER) que pagina um documento gerado no Microsoft Excel.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.openlocfilehash: ce29225c4bce24adc2abefc3d3d6f20774852af4
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488330"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Criar um formato de ER para paginar documentos gerados no Excel

[!include [banner](../includes/banner.md)]

Este tópico explica como um usuário na função de Administrador do Sistema ou de Consultor Funcional de Relatório Eletrônico pode configurar um formato de [Relatório eletrônico (ER)](general-electronic-reporting.md) para gerar documentos de saída no Microsoft Excel e gerenciar a paginação de documentos.

Neste exemplo, você modificará o formato de ER fornecido pela Microsoft, que é usado para imprimir o relatório de controle quando a declaração de Intrastat é [gerada](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Este relatório permite observar transações Intrastat relatadas. Suas modificações permitirão que você gerencie a paginação dos relatórios de controle que são gerados.

Os procedimentos deste tópico podem ser concluídos na empresa **DEMF**. Nenhum código é necessário. Antes de começar, baixe e salve os seguintes arquivos.

| descrição       | Nome do arquivo |
|-------------------|-----------| 
| Modelo de relatório 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Modelo de relatório 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para criar uma versão personalizada de um formato de ER padrão.

## <a name="import-the-standard-er-format-configuration"></a>Importar a configuração do formato de ER padrão

Siga as etapas em [Importar a configuração do formato de ER padrão](er-quick-start2-customize-report.md#ImportERSolution1) para adicionar as configurações de ER padrão à sua instância atual do Dynamics 365 Finance. Importe a versão **1.9** da configuração de formato do **relatório Intrastat**. A versão base 1 da configuração base do **modelo Intrastat** é importada automaticamente do repositório.

## <a name="customize-the-standard-er-format"></a>Personalizar o formato de ER padrão

### <a name="create-the-custom-er-format"></a>Criar o formato de ER personalizado

Neste cenário, você é o representante da Litware, Inc., que está selecionado no momento como o provedor de configuração de ER ativo. Você deve criar uma nova configuração de formato de ER usando a configuração do **Relatório Intrastat** como base.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo Intrastat** e selecione **Relatório Intrastat**. A Litware, Ltda. usará a versão 1.9 dessa configuração do formato de ER como base para a versão personalizada.
3. Selecione **Criar configuração** para abrir a caixa de diálogo suspensa. Você pode usar essa caixa de diálogo para criar uma nova configuração para um formato de pagamento personalizado.
4. No grupo de campos **Novo**, selecione **Derivar do Nome: relatório Intrastat, Microsoft**.
5. No campo **Nome**, insira **Relatório intrastat Litware**.
6. Selecione **Criar configuração** para criar o novo formato.

A versão 1.9.1 da configuração do formato de ER **Relatório Intrastat Litware** foi criada. Essa versão tem um [status](general-electronic-reporting.md#component-versioning) de **Rascunho** e pode ser editada. O conteúdo atual do formato de ER personalizado corresponde ao conteúdo do formato fornecido pela Microsoft.

### <a name="make-the-custom-format-runnable"></a>Torna o formato personalizado executável

Agora que a primeira versão do formato personalizado foi criada e tem o status de **Rascunho**, você pode executar o formato para fins de teste. Para executar o relatório, processe um pagamento de fornecedor usando o método de pagamento que se refere ao seu formato de ER personalizado. Por padrão, quando você chama um formato de ER no aplicativo, somente as versões que têm o status **Concluída** ou **Compartilhada** são [consideradas](general-electronic-reporting.md#component-versioning). Esse comportamento ajuda a impedir que formatos de ER com designs não concluídos sejam utilizados. No entanto, para as execuções de teste, você pode forçar o aplicativo a usar a versão do seu formato de ER que tem o status de **Rascunho**. Dessa forma, é possível ajustar a versão do formato atual se modificações forem necessárias. Para obter mais informações, consulte [Aplicabilidade](electronic-reporting-destinations.md#applicability).

Para usar a versão de rascunho de um formato de ER, você deve marcar o formato de ER explicitamente.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.
4. Selecione **Editar** para tornar a página atual editável, conforme necessário.
5. Na árvore de configuração no painel esquerdo, selecione **Relatório Intrastat Litware**.
6. Defina a opção **Executar Rascunho** como **Sim** e selecione **Salvar**.

    ![Opção Executar Rascunho na página Configurações.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Configurar parâmetros de Comércio exterior para usar o formato de ER personalizado

Siga estas etapas para configurar parâmetros de Comércio exterior para que você possa usar o formato personalizado.

1. Vá para **Imposto** \> **Configuração** \> **Comércio exterior** \> **Parâmetros de comércio exterior**.
2. Na página **Parâmetros de comércio exterior**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato do arquivo**, selecione **Relatório Intrastat Litware**.
3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat Litware**.
4. Selecione **Salvar**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Configurar o formato personalizado para usar o modelo de relatório baixado

### <a name="review-the-first-downloaded-excel-template"></a>Revisar o primeiro modelo baixado do Excel

1. No aplicativo da área de trabalho Excel, abra o arquivo de modelo **ERIntrastatReportDemo1.xlsx** baixado anteriormente.
2. Verifique se o modelo contém intervalos nomeados para criar cabeçalho do relatório, detalhes do relatório e seções de rodapé de relatório em documentos gerados.

    ![O layout de modelo do Excel 1 no aplicativo da área de trabalho.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Substituir o modelo atual do Excel no formato de ER personalizado

Você deve adicionar um novo modelo do Excel ao formato de ER personalizado.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo Intrastat** \> **Relatório Intrastat** e selecione a configuração **Relatório Intrastat Litware**.
3. Selecione **Designer**.
4. Na página **Designer de formato**, no Painel de Ações, selecione **Mostrar detalhes**.
5. Certifique-se de que o componente de formato raiz **Intrastat: Excel** está selecionado e, no Painel de Ações, na guia **Importar**, no grupo **Importar** selecione **Atualizar do Excel**.
6. Na caixa de diálogo **Atualizar do Excel**, selecione **Atualizar modelo**.
7. Na caixa de diálogo **Abrir**, navegue e selecione o arquivo **ERIntrastatReportDemo1.xlsx** que você baixou anteriormente e selecione **Abrir**.
8. Selecione **OK**.
9. Selecione **Salvar**.

![Formate a estrutura no designer de formato de ER após o novo modelo do Excel ser adicionado.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Alterar a associação de dados para mostrar a descrição do item em um relatório gerado

1. Na página **Designer de formato**, selecione a guia **Mapeamento**.
2. Expanda **Intrastat** \> **Linhas do relatório** e selecione o componente **Código da mercadoria**.
3. Selecione **Editar fórmula**.
4. Altere a fórmula de associação de `@.CommodityCode` para `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Selecione **Salvar**.

![Associação configurada para mostrar a descrição do item no designer de formato de ER.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Gerar um relatório de controle da declaração de Intrastat

Primeiro, verifique se você tem transações do Intrastat para relatar na página **Intrastat**.

![Transações na página Intrastat.](./media/er-paginate-excel-reports-transactions1.gif)

Em seguida, use o formato de ER personalizado para gerar o relatório de controle da declaração Intrastat.

1. Acesse **Imposto** \> **Declarações** \> **Comércio exterior** \> **Intrastat**.
2. Na página **Intrastat**, no Painel de Ações, selecione **Saída** \> **Relatório**.
3. Na caixa de diálogo **Relatório Intrastat**, siga estas etapas para executar o relatório:

    1. Defina os campos **Data inicial** e **Data final** para incluir transações Intrastat específicas para o relatório.
    2. Defina a opção **Gerar arquivo** como **Não**.
    3. Defina a opção **Gerar relatório** como **Sim**.
    4. Selecione **OK**.

4. Baixe e salve o documento gerado.
5. Abra o documento no Excel e revise-o.

    ![Documento do Excel gerado no aplicativo de desktop.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Configurar o formato personalizado para paginar os documentos gerados

### <a name="review-the-second-downloaded-excel-template"></a>Revisar o segundo modelo baixado do Excel

1. No Excel, abra o arquivo do modelo **ERIntrastatReportDemo2.xlsx** baixado anteriormente.
2. Compare este modelo com o modelo **ERIntrastatReportDemo1.xlsx** e verifique se ele contém vários novos nomes do Excel para criar e preencher seções específicas de página em documentos gerados:

    - O intervalo **ReportPageHeader** é adicionado para criar cabeçalhos de página.
    - O intervalo **ReportPageHeader** é adicionado para criar rodapés de página.
    - A célula **\_ReportPageFooter PageLines** é configurada para mostrar o número de transações por página.
    - A célula **ReportPageFooter\_PageAmount** é configurada para mostrar o valor total de transações por página.
    - A célula **ReportPageFooter\_PageWeight** é configurada para mostrar o peso total de transações por página.
    - A célula **\_ReportPageFooter RunningCounterLines** é configurada para mostrar o contador de execução de transações desde o início do relatório até a página atual.
    - A célula **ReportPageFooter\_RunningTotalAmount** é configurada para mostrar o valor total de execução de todas as transações desde o início do relatório até a página atual.
    - A célula **ReportPageFooter\_RunningTotalWeight** é configurada para mostrar o peso total de execução de todas as transações desde o início do relatório até a página atual.

    ![O layout de modelo do Excel 2 no aplicativo da área de trabalho.](./media/er-paginate-excel-reports-template2a.gif)

    A célula **CommodityCode** deste modelo está configurada para quebrar o texto da célula. Como a linha de detalhes da transação está configurada de forma que ela caiba automaticamente na altura de uma linha, a altura da linha inteira deve ser alterada automaticamente quando o texto na célula **CommodityCode** for quebrado.

    ![Célula CommodityCode configurada para quebra de texto da célula.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Repita a substituição do modelo atual do Excel no formato de ER personalizado

1. Siga as etapas na seção [Substituir o modelo do Excel atual formato de ER personalizado](#replace-template) deste tópico. No entanto, na etapa 7, selecione o arquivo **ERIntrastatReportDemo2. xlsx**.
2. Na página **Designer de formato**, expanda **Intrastat**.
3. Nomeie os componentes de formato do [Intervalo](er-fillable-excel.md#range-component) que foram adicionados ao formato de ER editável para sincronizar a estrutura com a estrutura do modelo do Excel aplicado:

    1. Selecione o componente do **Intervalo** associado ao nome do Excel **ReportPageHeader**.
    2. Na guia **Formatar**, no campo **Nome**, insira o **Cabeçalho da página do relatório**.
    3. Selecione o componente do **Intervalo** associado ao nome do Excel **ReportPageFooter**.
    4. Na guia **Formatar**, no campo **Nome**, insira o **Rodapé da página do relatório**.

4. Selecione **Salvar**.

![Formate a estrutura no designer de formato de ER após o novo modelo do Excel ser substituído.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Alterar a estrutura de formatação para implementar a paginação de documento

1. Na página **Designer de formato**, na árvore de formatação no painel esquerdo, selecione o componente raiz **Intrastat**.
2. Selecione **Adicionar**.
3. Na caixa de diálogo **Adicionar**, selecione o componente [Página](er-fillable-excel.md#page-component) no grupo de componentes do **Excel**.
4. Na caixa de diálogo **Propriedade do componente**, no campo **Nome**, insira **Página do relatório**. Em seguida, selecione **OK**.
5. Para usar o componente **Cabeçalho da página do relatório** como um cabeçalho de página em cada página gerada, siga estas etapas:

    1. Selecione o componente **Cabeçalho da página do relatório** e, em seguida, selecione **Recortar**.
    2. Selecione o componente **Página do relatório** e, em seguida, selecione **Colar**.
    3. Expanda a **página do Relatório**.
    4. Para forçar o componente da **Página** a [considerar](er-fillable-excel.md#page-component-structure) esse intervalo um cabeçalho de página, selecione o **Cabeçalho da página do relatório** e, na guia **Formato**, no campo **Direção da replicação**, selecione **Sem replicação**.

6. Para paginar um documento gerado para que o conteúdo nas linhas do relatório seja considerado, siga estas etapas:

    1. Selecione o componente **Linhas do relatório** e, em seguida, selecione **Recortar**.
    2. Selecione o componente **Página do relatório** e, em seguida, selecione **Colar**.

7. Para incluir o rodapé do relatório após as linhas do relatório, mas antes do rodapé da página final, siga estas etapas:

    1. Selecione o componente **Rodapé do relatório** e, em seguida, selecione **Recortar**.
    2. Selecione o componente **Página do relatório** e, em seguida, selecione **Colar**.

8. Para usar o componente **Rodapé da página do relatório** como um rodapé de página em cada página gerada, siga estas etapas:

    1. Selecione o componente **Rodapé da página do relatório** e, em seguida, selecione **Recortar**.
    2. Selecione o componente **Página do relatório** e, em seguida, selecione **Colar**.
    3. Para forçar o componente da **Página** a [considerar](er-fillable-excel.md#page-component-structure) esse intervalo um rodapé de página, selecione o **Rodapé da página do relatório** e, na guia **Formato**, no campo **Direção da replicação**, selecione **Sem replicação**.

![Formate a estrutura no designer de formato de ER após a paginação do documento ser implementada.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Adicionar fontes de dados para calcular totais de rodapés de página

Você deve configurar novas fontes de dados para calcular o total da página, o contador em execução e os valores totais em execução, e mostrá-los na seção rodapé da página. Recomendamos que você use fontes de dados de [Coleta de dados](er-data-collection-data-sources.md) para essa finalidade.

1. Na página **Designer de formato**, selecione a guia **Mapeamento**.
2. Selecione **Adicionar raiz** e, em seguida, siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Geral**, selecione **Contêiner vazio**.
    2. Na caixa de diálogo **Propriedades da fonte de dados do contêiner vazio**, no campo **Nome** digite **Total**.
    3. Selecione **OK**.

3. Selecione a fonte de dados **Total**, selecione **Adicionar** e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Geral**, selecione **Contêiner vazio**.
    2. Na caixa de diálogo **Propriedades da fonte de dados do contêiner vazio**, no campo **Nome** digite **Página**.
    3. Selecione **OK**.

4. Selecione **Adicionar** novamente e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Geral**, selecione **Contêiner vazio**.
    2. Na caixa de diálogo **Propriedades da fonte de dados do contêiner vazio**, no campo **Nome** digite **Execução**.
    3. Selecione **OK**.

5. Selecione a fonte de dados **Total.Page**, selecione **Adicionar** e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
    2. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Valor**.
    3. No campo **Tipo de item**, selecione **Real**.
    4. Defina a opção **Coletar todos os valores** como **Sim**.
    5. Selecione **OK**.

6. Selecione **Adicionar** novamente e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
    2. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Peso**.
    3. No campo **Tipo de item**, selecione **Real**.
    4. Defina a opção **Coletar todos os valores** como **Sim**.
    5. Selecione **OK**.

7. Selecione a fonte de dados **Total.Running**, selecione **Adicionar** e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
    2. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Valor**.
    3. No campo **Tipo de item**, selecione **Real**.
    4. Defina o campo **Coletar todos os valores** como **Sim**.
    5. Selecione **OK**.

8. Selecione **Adicionar** novamente e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
    2. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Peso**.
    3. No campo **Tipo de item**, selecione **Real**.
    4. Defina o campo **Coletar todos os valores** como **Sim**.
    5. Selecione **OK**.

9. Selecione **Adicionar** novamente e siga estas etapas:

    1. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
    2. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Linhas**.
    3. No campo **Tipo de item**, selecione **Inteiro**.
    4. Defina o campo **Coletar todos os valores** como **Sim**.
    5. Selecione **OK**.

10. Selecione **Salvar**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Adicionar fontes de dados para controlar a visibilidade do rodapé da página

Se você planeja controlar a visibilidade do rodapé da página e não pretenda incluir o rodapé na página final, se ele contiver transações, configure uma nova fonte de dados para calcular o contador de execução necessário.

1. Na página **Designer de formato**, selecione a guia **Mapeamento**.
2. Selecione a fonte de dados **Total.Running**, selecione **Adicionar**.
3. Na caixa de diálogo **Adicionar fonte de dados**, na seção **Funções**, selecione **Coleta de dados**.
4. Na caixa de diálogo **Propriedades da fonte de dados da coleta de dados**, no campo **Nome** digite **Linhas2**.
5. No campo **Tipo de item**, selecione **Inteiro**.
6. Defina a opção **Coletar todos os valores** como **Sim**.
7. Selecione **OK**.
8. Selecione **Salvar**.

![Adicionadas fontes de dados no designer de formato de ER.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Configurar associações para coletar valores totais

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Linhas do relatório** e selecione o componente aninhado **Valor da fatura**.
2. Selecione **Editar fórmula**.
3. Altere a fórmula de associação de `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` para `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > Além de colocar o valor em uma célula do Excel para cada transação iterada, essa associação coleta o valor no na fonte de dados **Total.Page.Amount** da coleta de dados.

4. Selecione o componente aninhado **Peso**.
5. Selecione **Editar fórmula**.
6. Altere a fórmula de associação de `@.'$RoundedWeight'` para `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > Além de colocar o valor do peso em uma célula do Excel para cada transação iterada, essa associação coleta o valor no na fonte de dados **Total.Page.Weight** da coleta de dados.

![Associações configuradas para coletar valores totais no designer de formato de ER.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Configurar associações para preencher totais do rodapé da página

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Rodapé de página do relatório**, selecione o componente **Intervalo** aninhado que se refere à célula **ReportPageFooter\_PageAmount** e siga estas etapas:

    1. Na árvore de fontes de dados no painel à direita, selecione o item **Total.Page.Amount.Sum()**.
    2. Selecione **Associar**.
    3. Selecione **Editar fórmula**.
    4. Atualize a fórmula para `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Você deve especificar o argumento dessa função como **Falso** para manter os dados coletados para a página atual, porque esses dados são necessários para calcular o valor total de execução, o número total de linhas por página e a execução do contador de linhas.

2. Na árvore de formatação, selecione o componente **Intervalo** que se refere à célula do Excel **ReportPageFooter\_PageWeight** e siga estas etapas:

    1. Na árvore de fontes de dados no painel à direita, selecione o item **Total.Page.Weight.Sum()**.
    2. Selecione **Associar**.
    3. Selecione **Editar fórmula**.
    4. Atualize a fórmula para `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Configurar associações para preencher totais de execução da página

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Rodapé de página do relatório**, selecione o componente **Intervalo** aninhado que se refere à célula **ReportPageFooter\_RunningTotalAmount** e siga estas etapas:

    1. Na árvore de fontes de dados no painel à direita, selecione o item **Total.Running.Amount.Collect()**.
    2. Selecione **Associar**.
    3. Selecione **Editar fórmula**.
    4. Atualize a fórmula para `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > O operando `Total.Running.Amount.Sum(false)` retorna o valor total de execução coletado anteriormente. O operando `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` retorna o valor total da página atual. Você deve especificar o argumento da função aninhada do segundo operando como **Verdadeiro** para redefinir a coleta de dados `Total.Page.Amount`, assim que esse valor for colocado na coleção total somada `Total.Running.Amount`. O argumento especificado deve começar a coletar o total da próxima página a partir de um valor 0 (zero).
    >
    > A função `Total.Running.Amount.Sum(false)` é chamada para inserir o valor total de execução na célula **ReportPageFooter\_RunningTotalAmount** do Excel na página atual.

2. Na árvore de formatação, selecione o componente **Intervalo** aninhado que se refere à célula do Excel **ReportPageFooter\_RunningTotalWeight** e siga estas etapas:

    1. Na árvore de fontes de dados no painel à direita, selecione o item **Total.Running.Weight.Collect()**.
    2. Selecione **Associar**.
    3. Selecione **Editar fórmula**.
    4. Atualize a fórmula para `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Configurar associações para preencher o contador de execução da página

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Rodapé de página do relatório**, e selecione o componente **Intervalo** aninhado que se refere à célula **ReportPageFooter\_RunningCounterLines**:
2. Selecione **Editar fórmula**.
3. Adicione a fórmula `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Essa fórmula retorna o número de valores de valor coletados para todo o relatório. Esse número é igual ao número de transações que foram iteradas no momento atual. Ao mesmo tempo, a fórmula coleta o valor devolvido na coleção **Total.Running.Lines**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Configurar associações para preencher o contador do rodapé da página

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Rodapé de página do relatório**, e selecione o componente **Intervalo** aninhado que se refere à célula **ReportPageFooter\_PageLines**:
2. Selecione **Editar fórmula**.
3. Adicione a fórmula `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Essa fórmula calcula o número de transações na página atual como a diferença entre o número de transações que foi coletado no **Total.Page.Amount.Result** para o relatório inteiro e o número de transações armazenadas nessa fase em **Total.Running.Lines.Sum**. Como o número de transações para a página atual é armazenado no **Total.Running.Lines** na associação do componente do **Intervalo** que se refere à célula **ReportPageFooter\_RunningCounterLines** do Excel, o número de transações na página atual ainda não foi incluído. Portanto, essa diferença é igual ao número de transações na página atual.

![Associações configuradas para preencher o contador de rodapé de página no designer de formato de ER.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Configurar visibilidade de estoque

Você pode alterar a visibilidade do cabeçalho e do rodapé de página em uma página específica de um documento gerado para ocultar os seguintes elementos:

- O cabeçalho da página na primeira página porque o cabeçalho do relatório já contém títulos das colunas
- O cabeçalho da página em qualquer página que não tenha transações que possam ocorrer na última página
- O rodapé da página em qualquer página que não tenha transações que possam ocorrer na última página

Para alterar a visibilidade, atualize a propriedade **Habilitada** do **Cabeçalho da página do relatório** e do componentes do **Rodapé de página do relatório**.

1. Na página **Designer de formato**, na árvore de formatação, expanda o componente **Página do relatório**, selecione o componente aninhado **Cabeçalho da página do relatório** e siga estas etapas.

    1. Selecione **Editar** para o campo **Habilitado**.
    2. Na página **Designer de fórmula**, no campo **Fórmula**, informe a seguinte expressão:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. Na árvore de formatação, selecione o componente aninhado **Rodapé de página do relatório** e siga estas etapas:

    1. Selecione **Editar** para o campo **Habilitado**.
    2. Na página **Designer de fórmula**, no campo **Fórmula**, informe a seguinte expressão:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > A construção `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` é usada para calcular o número de transações na página atual. A construção `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` é usada para adicionar o número de transações na página atual à coleção, para tratar corretamente a visibilidade do rodapé da próxima página.
    >
    > A coleção `Total.Running.Lines` não pode ser reutilizada aqui porque a propriedade **Habilitada** de um componente base é processada **depois** que as associações de componentes aninhados são processadas. Quando a propriedade **Habilitada** é processada, a coleção `Total.Running.Lines` já é incrementada pelo número de transações na página atual.

3. Selecione **Salvar**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Gerar um relatório de controle da declaração de Intrastat (atualizado)

1. Certifique-se de que você tem 24 transações na página **Intrastat**. Repita as etapas na seção [Gerar relatório de controle de declaração Intrastat](#generate-intrastat-control-report) deste tópico para gerar e revisar o relatório de controle.

    Todas as transações são apresentadas na primeira página. Os totais de página e os contadores são iguais aos totais e contadores do relatório. O intervalo do cabeçalho da página na primeira página porque o cabeçalho do relatório já contém títulos das colunas. O cabeçalho e o rodapé da página estão ocultos na segunda página porque essa página não contém transações.

    ![Documento do Excel gerado no aplicativo de desktop.](./media/er-paginate-excel-reports-document2.gif)

2. Atualize duas transações na página **Intrastat** alterando o código **Número do item** de **D00006** para **L0010**. Observe que o nome do produto do novo item, **Par de alto-falante estéreo ativo**, é mais longo do que o nome de produto do item original, **Alto-falante padrão**. Essa situação força a quebra do texto na célula correspondente do documento gerado. A paginação de documento e a soma e a contagem relacionadas à página devem ser atualizadas agora. Repita as etapas na seção [Gerar relatório de controle de declaração Intrastat](#generate-intrastat-control-report) deste tópico para gerar e revisar o relatório de controle.

    No momento, as transações são apresentadas em duas páginas, e os totais de página e os contadores são calculados corretamente. O intervalo do cabeçalho da página é ocultado corretamente na primeira página e fica visível na segunda página. O rodapé da página está visível nas duas páginas porque contêm transações.

    ![Documento do Excel atualizado gerado no aplicativo de desktop.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>Existe alguma forma de reconhecer quando a página final é processada pelo componente de formato de Página?

O componente **Página** [não expõe](er-fillable-excel.md#page-component-limitations) informações sobre o número da página processada e o número total de páginas em um documento gerado. No entanto, você pode configurar as [fórmulas](er-formula-language.md) de ER para reconhecer a página final. Este é um exemplo:

- Calcule o número total de transações que já foram processadas usando o componente **Página do relatório**. Você pode fazer esse cálculo usando a fórmula `COUNT(Total.Page.Amount.Result)`. 
- Calcule o número total de transações que devem ser processadas com base na associação `model.CommodityRecord` configurada para o componente **Linhas do relatório**. Você pode fazer esse cálculo usando a fórmula `COUNT(model.CommodityRecord)`.
- Compare dois números para reconhecer a página final. Quando ambos os valores são iguais, a página final é gerada.

> [!NOTE]
> É recomendável que você use essa abordagem somente quando propriedade **Habilitada** do componente **Linhas do relatório** não contiver fórmula que possa retornar [Falso](er-formula-supported-data-types-primitive.md#boolean) no tempo de execução para alguns [registros](er-formula-supported-data-types-composite.md#record) iterados da [Lista de registros](er-formula-supported-data-types-composite.md#record-list) vinculada.

## <a name="additional-resources"></a>Recursos adicionais

- [Criar uma configuração para gerar documentos no formato Excel](er-fillable-excel.md)
- [Usar fontes de dados de COLETA DE DADOS em formatos de relatório eletrônico (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
