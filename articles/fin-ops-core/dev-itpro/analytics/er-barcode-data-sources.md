---
title: Usar fontes de dados de Códigos de Barras para gerar imagens de código de barras
description: Este tópico explica como usar fontes de dados de Códigos de Barras para gerar imagens de código de barras.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: 72c79c37ca5b5f98637ba5069e25465bb1391306
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343254"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Usar fontes de dados de Códigos de Barras para gerar imagens de código de barras

[!include[banner](../includes/banner.md)]

Você pode usar a estrutura de [Relatório eletrônico (ER)](general-electronic-reporting.md) para projetar [componentes de formato de ER](general-electronic-reporting.md#FormatComponentOutbound) que podem ser executados para gerar documentos de saída eletrônicos e imprimíveis necessários. Para gerar um documento de saída no formato do Microsoft Office, você deverá especificar o layout do relatório usando um documento do Microsoft Excel ou um documento do Microsoft Word como modelo de relatório. O [designer de Operações de ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) permite anexar um documento do Excel ou do Word como um modelo para um formato de ER. Os seguintes elementos nomeados no modelo anexado estão associados aos elementos do componente de formato configurado:

- Controles de conteúdo no Word
- Planilhas, intervalos, células, formas e imagens nomeados no Excel

Esses elementos nomeados são usados como espaços reservados para dados inseridos em um documento gerado quando um formato de ER é executado. Os elementos do formato de ER são limitados a fontes de dados. Essas fontes de dados especificam os dados que serão inseridos nos documentos gerados em runtime. Para obter mais informações, consulte [Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md).

Agora, o ER oferece suporte ao tipo de fonte de dados **Código de Barras**. Portanto, agora é possível gerar uma imagem que representa o código de barras para o texto especificado. Ao configurar um formato de ER, você pode especificar fontes de dados do tipo **Código de Barras** para gerar imagens de códigos de barras. Em seguida, você poderá adicionar essas imagens a documentos comerciais gerados, como ordens, faturas, guias de remessa e recebimentos. Você também pode adicioná-los a vários tipos de etiquetas, como etiquetas para produtos e prateleiras e etiquetas de embalagem e remessa.

Os espaços reservados a seguir podem ser usados em modelos de relatório para inserir imagens de código de barras:

- Controle de conteúdo [Imagem](/office/client-developer/word/content-controls-in-word) para Word
- Objeto [Imagem](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) no Excel

Usando uma fonte de dados do tipo **Código de Barras**, você pode gerar códigos de barras nos seguintes formatos:

- Códigos de barras unidimensionais:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligent Mail
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Códigos de barras bidimensionais:

    - Aztec
    - Data Matrix
    - Código QR

Ao configurar uma fonte de dados de **Código de barras**, você poderá definir parâmetros de renderização específicos que são usados para gerar uma imagem:

- **Largura** – especifique a largura do código de barras em pixels. Um valor **0** (zero) indica que a largura padrão é usada. O significado pode variar para diferentes formatos.
- **Altura** – especifique a altura do código de barras em pixels. Um valor **0** (zero) indica que a altura padrão é usada. O significado pode variar para diferentes formatos.
- **Margem** – especifique o tamanho da margem do código de barras em pixels. A margem é a área em cada lado de um código de barras que deve ser mantida limpa (zona silenciosa). Um valor **0** (zero) indica que a margem padrão é usada. O significado pode variar para diferentes formatos.
- **Conteúdo de saída** – defina o valor como **Sim** para gerar uma imagem de código de barras que contém as informações codificadas como texto. O valor padrão é **Não**.
- **Codificação** – especifique o tipo de caracteres que são codificados na imagem de código de barras gerada. Por padrão, a codificação **UTF-8** é usada.

> [!IMPORTANT]
> Ao adicionar uma nova fonte de dados de **Código de Barras**, você deve colocá-la em outro item (contêiner) como um elemento aninhado.
>
> Ao associar uma fonte de dados de **Código de Barras** a um elemento de célula em um formato, e o elemento de célula representa um controle de conteúdo do Word ou uma imagem do Excel, a fonte de dados é apresentada na associação como uma função que tem um único parâmetro do tipo **Cadeia de Caracteres**. Você deve usar esse parâmetro para especificar o texto que deve ser transformado em uma imagem de código de barras e ler quando um código de barras gerado é verificado.

Para obter mais informações sobre esse recurso, conclua os exemplos neste tópico.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Exemplo: gerar um cheque de pagamento que contenha um código de barras que codifique o valor a pagar

Este exemplo mostra como um usuário na função **Administrador do sistema** ou **Consultor eletrônico funcional de relatório eletrônico** pode configurar um formato de ER que contém um modelo usado para gerar um documento de saída no formato Excel que contém um código de barras. Esta é uma visão geral das etapas envolvidas.

1. [Concluir os pré-requisitos](#ExamplePrerequisites).
2. [Ativar um provedor de configuração](#ExampleProvider).
3. [Importar a solução de ER fornecida](#ExampleImportSolution).
4. [Gerar um cheque de pagamento](#ExampleGenerateCheque).
5. [Analisar o cheque de pagamento gerado](#ExampleReviewGeneratedCheque).
6. [Modificar o formato da solução de ER fornecida](#ExampleModifyFormat).

    1. [Aplicar um novo modelo de verificação](#ExampleModifyFormatApplyTemplate).
    2. [Adicionar uma nova fonte de dados Código de Barras](#ExampleModifyFormatAddDataSource).
    3. [Associar um novo elemento de formato](#ExampleModifyFormatBindFormatElement).
    4. [Disponibilizar a versão modificada para execuções de teste](#ExampleModifyFormatMakeVersionAvailable).

        1. [Concluir a versão de formato modificada](#CompleteToRun).
        2. [Disponibilizar a versão de rascunho para uso](#MarkToRun).

7. [Gerar um cheque de pagamento](#ExampleGenerateCheque2).
8. [Converter o cheque gerado em um PDF](#ExampleConvertToPDF).

Neste exemplo, você usará a solução de ER fornecida que foi configurada para gerar cheques de pagamento. Essa solução gera cheques de pagamento nos quais o valor a pagar é gravado como um número e como texto. Você modificará essa solução de ER para que o cheque também inclua um código de barras gerado no qual o valor a pagar é codificado e possa ser lido usando um scanner de código de barras.

As etapas podem ser concluídas na empresa **USMF** no Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Concluir os pré-requisitos

Para concluir este exemplo, você deve ter acesso à empresa USMF no Finance para uma das seguintes funções:

- Consultor funcional de relatório eletrônico
- Administrador do sistema

Se você ainda não tiver concluído o exemplo no tópico [Inserir imagens e formas em documentos gerados usando o ER](electronic-reporting-embed-images-shapes.md), baixe as configurações a seguir do exemplo da solução ER.

| Descrição do conteúdo         | Nome do arquivo                   |
|-----------------------------|-----------------------------|
| Configuração do modelo de dados de ER | [Modelo para cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)      |
| Configuração de formato ER     | [Formato de impressão de cheques.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |

Além disso, baixe o seguinte arquivo do Excel que contém o modelo modificado para a solução de ER fornecida.

| Descrição do conteúdo | Nome do arquivo                 |
|---------------------|---------------------------|
| Modelo de relatório     | [Modelo de cheque do Excel.xlsx](https://download.microsoft.com/download/3/b/d/3bd3b944-da8f-43b4-8533-3c1292a4c3ef/CheckTemplateExcel.xlsx) |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Ativar um provedor de configuração

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, verifique se o [provedor de configuração](general-electronic-reporting.md#Provider) para a empresa de exemplo **Litware, Inc.** está listado e marcado como ativo. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como ativo, siga as etapas no tópico [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Configuração da empresa de exemplo a ser ativada na página Configurações de localização.](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importar a solução de ER fornecida

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, se a configuração **Modelo para cheques** não estiver disponível na árvore de configuração, siga estas etapas para importar a configuração do modelo de dados de ER:

    1. No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.
    2. Na caixa de diálogo, selecione **Procurar**, localize e selecione o arquivo **Modelo para cheques.xml** e selecione **OK**.

4. Na configuração **Formato de impressão de cheques** não está disponível na árvore de configuração, siga estas etapas para importar a configuração do formato de ER:

    1. No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.
    2. Na caixa de diálogo, selecione **Procurar**, localize e selecione o arquivo **Formato de impressão de cheques.xml** e selecione **OK**.

5. Na árvore de configuração, expanda o **Modelo para cheques**.
6. Revise a lista de configurações de ER importadas na árvore de configuração.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Gerar um cheque de pagamento

1. Acesse **Gerenciamento de caixa e bancos** \> **Contas bancárias** \> **Contas bancárias**.
2. Na página **Contas bancárias**, selecione a conta **USMF OPER**.
3. Na página de detalhes da conta bancária, no Painel de Ação, na guia **Configurar**, no grupo **Layout**, selecione **Cheque**.
4. Na página **Layout do cheque**, selecione **Editar**.
5. Na Guia Rápida **Geral**, defina a opção **Formato de exportação eletrônico genérico** como **Sim**.
6. No campo **Configuração de formato de exportação**, selecione o formato de ER **Formato de impressão de cheques** que você importou anteriormente.
7. No Painel de Ação, selecione **Teste de impressão**.
8. Na caixa de diálogo, defina a opção **Formato de cheque negociável** como **Sim** e, em seguida, selecione **OK**.

    ![Caixa de diálogo Layout de cheque - Imprimir teste.](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Analisar o cheque de pagamento gerado

- Abra o cheque gerado no Excel.
2. Analise o cheque gerado.

    ![Cheque de pagamento gerado no Excel.](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Modificar o formato da solução de ER fornecida

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Aplicar um novo modelo de cheque

Você pode usar o aplicativo de área de trabalho do Excel para abrir o arquivo **Modelo de cheque do Excel.xlsx** que você importou anteriormente. Observe que esse modelo é diferente do modelo que você usou para gerar um cheque de pagamento na solução de ER fornecida. Além disso, inclui um elemento **AmountBarcode** para a imagem de código de barras.

![Elemento AmountBarcode no modelo do Excel.](./media/er-barcode-data-source-cheque2.png)

Agora, você deve modificar a solução de ER e [reaplicar](modify-electronic-reporting-format-reapply-excel-template.md) o modelo modificado.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo para cheques** e selecione **Formato de impressão de cheques**.
4. No Painel de Ação, selecione **Designer**.
5. No designer de Operação do ER, selecione a guia **Mapeamento**, no lado direito da página e, em seguida, no painel de árvore de formatos à esquerda, selecione **Expandir/recolher**.
6. Observe que todos os elementos de formato de célula estão associados às fontes de dados apropriadas.

    ![Associação de elementos de formato de célula a fontes de dados no designer de Operação do ER.](./media/er-barcode-data-source-cells-bound.png)

7. Selecione a guia **Formato**, no lado direito da página.
8. No Painel de Ação, selecione as reticências (**...**) e, em seguida, selecione **Importar**.
9. No grupo **Importar** , selecione **Atualizar do Excel** e, em seguida, selecione **Atualizar modelo**.
10. Na caixa de diálogo, navegue até o arquivo **Modelo de cheque do Excel.xlsx** salvo no computador, selecione-o e, em seguida, selecione **OK** para confirmar que o modelo selecionado deve ser aplicado.
11. Selecione a guia **Mapeamento**, no lado direito da página e, em seguida, no painel de árvore de formatos à esquerda, selecione **Expandir/recolher**.
12. Observe que o elemento de célula **AmountBarcode** foi adicionado ao formato. Esse elemento está associado ao elemento **AmountBarcode** que foi adicionado ao modelo modificado do Excel como um espaço reservado para uma imagem de código de barras.

    ![Elemento de célula AmountBarcode adicionado ao formato no designer de Operações do ER.](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Adicionar uma nova fonte de dados Código de Barras

Em seguida, você deverá adicionar uma nova fonte de dados do tipo **Código de Barras**.

1. No designer de Operações do ER, na guia **Mapeamento**, no lado direito da página, selecione a fonte de dados de **impressão**.
2. Selecione **Adicionar** e, em seguida, no grupo **Funções**, selecione o tipo de fonte de dados **Código de Barras**.

    ![Como selecionar o tipo de fonte de dados Código de Barras.](./media/er-barcode-data-source-add.png)

3. Na caixa de diálogo, no campo **Nome** , digite **código de barras**.
4. No **Formato de código de barras**, selecione **Código 128**.
5. No campo **Largura**, insira **500**.
6. Selecione **OK**.

    ![Caixa de diálogo Propriedades da fonte de dados.](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Associar um novo elemento de formato

Em seguida, você deve associar o novo elemento formato à fonte de dados que acabou de adicionar.

1. No designer de Operações do ER, na guia **Mapeamento**, no lado direito da página, selecione a fonte de dados **print\\barcode**.
2. No painel de árvore de formatos à esquerda, selecione o elemento de célula **AmountBarcode** e selecione **Associar**.
3. No Painel de Ação, selecione **Mostrar detalhes**.
4. Observe que, como a fonte de dados **Código de Barras** é representada na associação como uma função que contém um único parâmetro, o nome do elemento de formato associado foi automaticamente levado como o argumento desse parâmetro.

    ![Detalhes da fonte de dados Código de Barras no designer de Operações do ER.](./media/er-barcode-data-source-bind1.png)

5. Selecione **Editar fórmula** para ajustar a associação.

    Você não deseja que o nome do elemento da célula seja retornado. Portanto, você deve configurar uma expressão que retorne texto que contenha o valor a pagar do cheque atual. Porque o intervalo **ChequeLines** pai está associado à fonte de dados **model.cheques**, o valor a pagar do cheque atual está disponível no campo **model.cheques.attributes.amount** do tipo de dados **Real**.

6. No campo **Fórmula** , insira **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Selecione **Salvar** e então feche o [designer de Fórmula do ER](general-electronic-reporting-formula-designer.md).
8. Observe que a associação foi ajustada.

    ![Associação ajustada no designer de Operações do ER.](./media/er-barcode-data-source-bind2.png)

9. Selecione **Salvar** e então feche o designer de Operações do ER.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Disponibilizar a versão modificada para execuções de teste

Por padrão, as únicas versões que têm o status **Concluído** e **Compartilhado** são usadas quando você executa um formato de ER.

Se tiver finalizado suas alterações, você poderá concluir o trabalho com a versão de rascunho atual e disponibilizar suas alterações para uso. Para obter instruções, consulte a seção [Concluir a versão do formato modificado](#CompleteToRun) a seguir.

Se você deseja continuar a trabalhar com a versão de rascunho atual, mas precisa usá-la para gerar cheques, especifique explicitamente que deseja usar a versão de rascunho do formato para execução. Para obter instruções, consulte a seção [Disponibilizar a versão de rascunho para uso](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Concluir a versão de formato modificada

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo para cheques** e selecione **Formato de impressão de cheques**.
4. Na Guia Rápida **Versões**, selecione o registro com o status **Concluído**.
5. Selecione **Alterar status** e selecione **Concluir**.
6. Na caixa de diálogo , selecione **OK**.

O status da versão atual é alterado de **Rascunho** para **Concluído**, e uma nova versão com o status **Rascunho** é criada. Você pode usar essa nova versão de rascunho para aplicar alterações adicionais.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Disponibilizar a versão de rascunho para uso

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione **Configurações de relatórios**.
3. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
4. Na caixa de diálogo, defina a opção **Executar configuração** como **Sim** e, em seguida, selecione **OK**.
5. Na árvore de configuração, expanda **Modelo para cheques** e selecione **Formato de impressão de cheques**.
6. Defina a opção **Executar rascunho** como **Sim**.
7. Selecione **Salvar**.

A versão de rascunho do formato selecionado é marcada como disponível para uso quando o formato selecionado é executado.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Gerar um cheque de pagamento

1. Acesse **Gerenciamento de caixa e bancos** \> **Contas bancárias** \> **Contas bancárias**.
2. Na página **Contas bancárias**, selecione a conta **USMF OPER**.
3. Na página de detalhes da conta bancária, no Painel de Ação, na guia **Configurar**, no grupo **Layout**, selecione **Cheque**.
4. Na página **Layout do cheque**, no Painel de Ação, selecione **Imprimir teste**.
5. Na caixa de diálogo, defina a opção **Formato de cheque negociável** como **Sim**.
6. Selecione **OK**.
7. Analise o cheque gerado. Observe que um código de barras foi gerado para codificar o valor a pagar do cheque.

    ![Cheque de pagamento gerado com código de barras no Excel.](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Uma exceção é lançada se o argumento de uma fonte de dados **Código de Barras** não estiver em conformidade com as necessidades apropriadas específicas ao formato do código de barras. Por exemplo, quando a fonte de dados **Código de Barras** é chamada para gerar um código de barras [EAN-8](https://wikipedia.org/wiki/EAN-8) para o texto fornecido, uma exceção será lançada se o comprimento do texto exceder sete caracteres.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Converter o cheque gerado em um PDF

Conforme descrito no tópico [Gerar formulários de impressão FTI](er-generate-printable-fti-forms.md#finland), você pode usar uma fonte especial para produzir códigos de barras em um documento gerado. Nesse caso, as transformações adicionais do documento gerado podem depender da disponibilidade dessa fonte no ambiente de transformação. Por exemplo, se você tentar converter um documento em formato PDF ou visualizá-lo em um ambiente onde a fonte está faltando, os códigos de barras não serão renderizados corretamente.

No entanto, quando você usa a fonte de dado **Código de Barras** para produzir códigos de barras, a renderização desses códigos de barras não dependerá de nenhuma fonte. Portanto, você pode converter facilmente documentos que contêm os códigos de barras no formato PDF. A ilustração a seguir mostra a visualização de um cheque de pagamento gerado que foi [convertido](electronic-reporting-destinations.md#OutputConversionToPDF) em PDF, com base na configuração do [destino](electronic-reporting-destinations.md) de ER configurado.

![Visualização do PDF de um cheque de pagamento.](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Limitações

> [!NOTE]
> Alguns tipos de códigos de barras gerados têm uma taxa de proporção fixa. Esse comportamento fará sentido se você tiver ativado o recurso **Habilitar uso da biblioteca EPPlus na estrutura de Relatório eletrônico** para trabalhar com documentos do Excel em ER. Nesse caso, uma imagem é inserida em um espaço reservado com uma taxa de proporção bloqueada. Portanto, quando as dimensões de um espaço reservado em um modelo correspondem à proporção de uma imagem inserida, uma imagem real em um documento gerado pode ser redimensionada para manter a taxa de proporção necessária. Para evitar o redimensionamento de imagem, use um espaço reservado com uma taxa de proporção esperada.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico](electronic-reporting-destinations.md)
- [Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
- [Função NUMBERFORMAT](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
