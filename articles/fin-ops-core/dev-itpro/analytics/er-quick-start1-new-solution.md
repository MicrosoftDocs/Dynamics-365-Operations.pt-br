---
title: Criar uma nova solução ER para imprimir um relatório personalizado
description: Este tópico explica como criar uma solução de relatório eletrônico (ER) para imprimir um relatório personalizado.
author: NickSelin
manager: AnnBe
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cd0d8e7aa9595e705416798772f52956ef609da
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680233"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Criar uma nova solução ER para imprimir um relatório personalizado

[!include[banner](../includes/banner.md)]

As etapas a seguir explicam como um usuário no administrador do sistema, no desenvolvedor de relatórios eletrônicos ou na função consultor funcional de relatórios eletrônicos pode configurar parâmetros da estrutura ER, criar as configurações de ER necessárias de uma nova solução ER para acessar os dados de um domínio comercial específico e gerar um relatório personalizado no formato do Microsoft Office. Essas etapas podem ser concluídas na empresa **USMF**.

- [Configurar a estrutura de ER](#ConfigureFramework)

    - [Configurar parâmetros de ER](#ConfigureParameters)
    - [Ativar um provedor de configuração de ER](#ActivateProvider)

        - [Examinar a lista de provedores de configuração de ER](#ReviewProvidersList)
        - [Adicionar um novo provedor de configuração de ER](#AddProvider)
        - [Ativar um provedor de configuração de ER](#ActivateAddedProvider)

- [Criar um modelo de dados de domínio específico](#DesignModel)

    - [Importar uma nova configuração de modelo de dados](#ImportDataModel)
    - [Criar uma nova configuração de modelo de dados](#DesignDataModel)

        - [Nomear o modelo de dados](#NameDataModel)
        - [Adicionar campos de modelo de dados](#FieldsEntry)
        - [Concluir o design do modelo de dados](#CompleteDataModel)

- [Criar um mapeamento de modelo para o modelo de dados configurado](#DesignMapping)

    - [Importar uma nova configuração de mapeamento de modelo](#ImportModelMapping)
    - [Crie uma nova configuração de mapeamento de modelo](#CreateModelMapping)

        - [Criar um novo componente de mapeamento de modelos](#DesignMappingComponent)
        - [Adicionar fontes de dados para acessar tabelas de aplicativos](#AddMmDataSource1)
        - [Adicionar fontes de dados para acessar enumerações de aplicativos](#AddMmDataSource2)
        - [Adicionar rótulos de ER para gerar um relatório em um idioma especificado](#AddMmLabels)
        - [Adicionar uma fonte de dados para transformar os resultados da comparação de valores de enumeração em um valor de texto](#AddMmDataSource3)
        - [Associar fontes de dados a campos do modelo de dados](#AddMmBindings1)
        - [Concluir o design de mapeamento do modelo](#CompleteModelMapping)

- [Criar um modelo para um relatório personalizado](#DesignReportTemplate)
- [Criar um formato](#DesignFormat)

    - [Importar uma configuração de formato criado](#FormatImport)
    - [Criar uma nova configuração de formato](#FormatCreate)

        - [Importar um modelo do relatório](#ImportReportTemplate)
        - [Configurar um formato](#ConfigureFormat)
        - [Definir a associação de dados para um título de relatório](#DefineFormatBindings)
        - [Analisar a fonte de dados do modelo](#ReviewModelDataSource)
        - [Associar elementos a campos da fonte de dados](#BindFormatElements)

    - [Executar um formato criado a partir de ER](#RunFormatFromER)

- [Ajustar um formato criado](#TuneFormat)

    - [Modificar um formato para alterar o nome de um documento gerado](#ModifyToChangeName)
    - [Modificar um formato para alterar a ordem das perguntas](#ModifyToOrder)
    - [Executar um formato modificado a partir de ER](#RunFormatFromER2)
    - [Concluir a criação do formato](#CompleteFormat)

- [Desenvolver artefatos de aplicativos para chamar o relatório criado](#DevelopCustomCode)

    - [Modificar o código-fonte](#ModifySourceCode)

        - [Adicionar uma classe de contrato de dados](#DataContractClass)
        - [Adicionar uma classe do construtor de interface de usuário](#UIBuilderClass)
        - [Adicionar uma classe de provedor de dados](#DataProviderClass)
        - [Adicionar um arquivo de rótulos](#LabelsFile)
        - [Adicionar uma classe de serviço de relatório](#ServiceClass)
        - [Adicionar uma classe de controlador de relatório](#ControllerClass)
        - [Adicionar um item de menu](#MenuItem)
        - [Adicionar um item de menu a um menu](#Menu)
        - [Criar um projeto do Visual Studio](#BuildVSProject)

    - [Executar um formato do aplicativo](#RunFormatFromApp)

- [Ajustar uma solução de ER criada](#TuneSolution)

    - [Modifique um mapeamento de modelo](#ModifyModelMapping)

        - [Adicionar fontes de dados para acessar um objeto de contrato de dados](#AddDataSource1)
        - [Adicionar uma fonte de dados para acessar registros de mapeamento de formato ER](#AddDataSource2)
        - [Adicionar uma fonte de dados para acessar um registro de mapeamento de formato de um formato de ER em execução](#AddDataSource3)
        - [Inserir o nome do formato de ER em execução no modelo de dados](#AddBinding)
        - [Concluir o design de mapeamento do modelo](#CompleteModelMapping2)

    - [Modificar um formato](#ModifyFormat)

        - [Adicionar um novo elemento de formato](#AddFormatElement)
        - [Vincular o elemento de formato adicionado](#BindAddedFormatElement)
        - [Concluir a criação do formato](#CompleteFormat2)

    - [Executar um formato do aplicativo](#RunFormatFromApp2)
    - [Executar um formato de ER](#RunFormatFromER3)
    - [Configurar um destino de formato para versão prévia na tela](#ConfigureDestination)
    - [Executar um formato do aplicativo para visualizá-lo como um documento PDF](#RunFormatFromApp3)

- [Recursos adicionais](#References)

Neste exemplo, você criará uma nova solução ER para o módulo [Questionário](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires). Essa nova solução ER permite criar um relatório usando uma planilha do Microsoft Excel como modelo. Em seguida, você pode gerar o relatório **Questionário** no formato Excel ou PDF, além de gerar o relatório Serviços de Relatório do SQL Server (SSRS) existente. Você também pode modificar o novo relatório posteriormente, quando solicitado. Nenhum código é necessário.

1. Para executar o relatório existente, vá para **Questionário** \> **Design** \> **Relatório Questionários**.

    ![Seleção do item de menu do relatório Questionários no módulo Questionário para executar o relatório SSRS existente](./media/er-quick-start1-application-menu-origin.png)

2. Na caixa de diálogo **Relatório Questionários**, especifique os critérios de seleção. Aplique um filtro para que o relatório inclua somente o questionário **SBCCrsExam**.

    ![Como especificar critérios de seleção na caixa de diálogo Relatório Questionários](./media/er-quick-start1-ssrs-report-dialog.png)

A ilustração a seguir mostra a versão gerada do relatório SSRS para o questionário **SBCCrsExam**.

![Relatório SSRS gerado](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Configurar a estrutura de ER

Como usuário na função de Desenvolvedor de Relatório Eletrônico, você deve configurar o conjunto mínimo de parâmetros de ER antes de começar a usar a estrutura de ER para criar uma nova solução ER.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Configurar parâmetros de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. No espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.
4. Na guia **Anexos**, defina os seguintes parâmetros:

    - Defina o campo **Configurações** como **Arquivo** para a empresa **USMF**.
    - Defina os campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros** como **Arquivo**.

Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Ativar um provedor de configuração de ER

Toda configuração de ER é marcada como pertencente a um provedor de configuração de ER. Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.

> [!NOTE]
> Somente o proprietário de uma configuração de ER pode editá-la. Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Examinar a lista de provedores de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Provedores de configuração**, cada registro de provedor de configuração tem um nome e uma URL únicos. Examine o conteúdo dessa página. Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Adicionar um novo provedor de configuração de ER

1. Na página **Provedores de configuração**, selecione **Novo**.
2. No campo **Nome**, insira **Litware, Ltda.**
3. No campo **Endereço na Internet**, insira `https://www.litware.com`.
4. Selecione **Salvar**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Ativar um provedor de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. No espaço de trabalho **Relatório eletrônico**, selecione o provedor de configuração **Litware, Inc.**.
3. Selecione **Definir como ativo**.

Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Criar um modelo de dados de domínio específico

Você deve criar uma nova configuração ER contendo um componente de [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) para o domínio comercial do **Questionário**. Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar um formato ER para gerar o relatório **Questionário**.

Ao concluir as etapas na seção [Importar uma nova configuração do modelo de dados](#ImportDataModel), você pode importar o modelo de dados necessário do arquivo XML fornecido. Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração do modelo de dados](#DesignDataModel) para criar esse modelo de dados desde o início.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importar uma nova configuração de modelo de dados

1. Baixe o arquivo [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.
2. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires model.version.1.xml**.
6. Selecione **OK** para importar a configuração.

Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de modelo de dados](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Criar uma nova configuração de modelo de dados

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
3. Selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, no campo **Nome**, insira **Modelo de questionário**.
5. Selecione **Criar configuração** para criar a configuração.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Nomear o modelo de dados

1. Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.
2. Selecione **Designer**.
3. Na página **Designer de modelo de dados**, na FastTab **Geral**, no campo **Nome**, insira <a name="DataModeName"></a>**Questionários**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Adicionar novos campos de modelo de dados

1. Na página **Designer de modelo de dados**, selecione **Novo**.
2. Na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. Selecione **Raiz do modelo** como o tipo do novo nó.
    2. No campo **Nome**, insira <a name="RootDefinitionName"></a>**Raiz**.
    3. Selecione **Adicionar** para adicionar o novo nó.

    Esse descritor raiz será usado para fornecer dados para o relatório **Questionário**. Um único modelo de dados pode ter vários descritores. Cada descritor pode ser especificado para um único formato ER, a fim de identificar os dados necessários para gerar o relatório.

3. Selecione **Novo** novamente e, na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. Selecione **Filho de um nó ativo** como o tipo do novo nó.
    2. No campo **Nome**, insira **CompanyName**.
    3. No campo **Tipo de item**, selecione **String**.
    4. Selecione **Adicionar** para adicionar o novo campo.

    Este campo é necessário para passar o nome da empresa atual para um relatório ER que consome esse modelo de dados como uma fonte de dados.

4. Selecione **Novo** novamente e, na caixa de diálogo suspensa para adicionar um nó de modelo de dados, siga estas etapas:

    1. Selecione **Filho de um nó ativo** como o tipo do novo nó.
    2. No campo **Nome**, insira **Questionário**.
    3. No campo **Tipo de item**, selecione **Lista de registros**.
    4. Selecione **Adicionar** para adicionar o novo campo.

    Este campo será usado para passar a lista de questionários para um relatório ER que consome esse modelo de dados como uma fonte de dados.

5. Selecione o nó **Questionário**.
6. Continue a adicionar os campos obrigatórios do modelo de dados editável da mesma forma até concluir a estrutura de modelo de dados a seguir.

    | Caminho do campo                                                    | Tipo de dados   | Designação de campo/valor retornado |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Raiz                                                          |             | O ponto de referência para solicitar dados de questionário. |
    | Raiz\\CompanyName                                             | Sequência de caracteres      | O nome da empresa atual. |
    | Raiz\\ExecutionContext                                        | Registrar      | Detalhes da execução de formato. |
    | Raiz\\ExecutionContext\\FormatName                            | Sequência de caracteres      | O nome do formato ER que está sendo executado. |
    | Raiz\\Questionário                                           | Registrar lista | A lista de questionários |
    | Raiz\\Questionário\\Ativo                                   | Sequência de caracteres      | O status do questionário atual. |
    | Raiz\\Questionário\\Código                                     | Sequência de caracteres      | O código do questionário atual. |
    | Raiz\\Questionário\\Descrição                              | Sequência de caracteres      | A descrição do questionário atual. |
    | Raiz\\Questionário\\QuestionnaireType                        | Sequência de caracteres      | O tipo do questionário atual. |
    | Raiz\\Questionário\\QuestionOrder                            | Sequência de caracteres      | A ordem numérica do questionário atual. |
    | Raiz\\Questionário\\ResultsGroup                             | Registrar      | As parâmetros de resultado do questionário atual. |
    | Raiz\\Questionário\\ResultsGroup\\Código                       | Sequência de caracteres      | O código de identificação do grupo de resultados atual. |
    | Raiz\\Questionário\\ResultsGroup\\Descrição                | Sequência de caracteres      | A descrição do grupo de resultados atual. |
    | Raiz\\Questionário\\ResultsGroup\\MaxNumberOfPoints          | Real        | O número máximo de pontos a ser obtido. |
    | Raiz\\Questionário\\Pergunta                                 | Registrar lista | A lista de perguntas do questionário atual. |
    | Raiz\\Questionário\\Pergunta\\CollectionSequenceNumber       | Inteiro     | O número de sequência da coleção de respostas atual. |
    | Raiz\\Questionário\\Pergunta\\Id                             | Sequência de caracteres      | O código de identificação da pergunta atual. |
    | Raiz\\Questionário\\Pergunta\\MustBeCompleted                | Sequência de caracteres      | Um sinalizador que indica se a pergunta atual deve ser respondida. |
    | Raiz\\Questionário\\Pergunta\\PrimaryQuestion                | Sequência de caracteres      | Um sinalizador que indica se a pergunta atual é a principal. |
    | Raiz\\Questionário\\Pergunta\\SequenceNumber                 | Inteiro     | O número de sequência da pergunta atual. |
    | Raiz\\Questionário\\Pergunta\\Texto                           | Sequência de caracteres      | O texto da pergunta atual. |
    | Raiz\\Questionário\\Pergunta\\Resposta                         | Registrar lista | A lista de respostas para a pergunta atual. |
    | Raiz\\Questionário\\Pergunta\\Resposta\\CorrectAnswer          | Sequência de caracteres      | Um sinalizador que indica se a pergunta resposta atual está correta. |
    | Raiz\\Questionário\\Pergunta\\Resposta\\Pontos                 | Real        | Os pontos ganhos quando a resposta atual é selecionada. |
    | Raiz\\Questionário\\Pergunta\\Resposta\\SequenceNumber         | Inteiro     | O número de sequência da resposta atual. |
    | Raiz\\Questionário\\Pergunta\\Resposta\\Texto                   | Sequência de caracteres      | O texto da resposta atual. |

    A ilustração a seguir mostra o modelo de dados editável preenchido na página **Designer do modelo de dados**.

    ![Modelo de dados configurado no designer de modelos de dados ER](./media/er-quick-start1-model2.png)

7. Salve as alterações.
8. Feche a página **Designer de modelo de dados**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Concluir o design do modelo de dados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.
3. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
4. Selecione **Alterar status** \> **Concluir**.

O status da versão 1 dessa configuração é alterado de **Rascunho** para **Concluído**. A versão 1 não pode mais ser alterada. Esta versão contém o modelo de dados configurado e pode ser usada como base para outras configurações de ER. A versão 2 dessa configuração é criada e tem um status **Rascunho**. Você pode editar esta versão para ajustar o modelo de dados **Questionário**.

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-model-configuration.png)

Para obter mais informações sobre como usar versões para configurações de ER, consulte [Visão geral de relatório eletrônico (ER)](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> O modelo de dados configurado é sua representação abstrata do domínio comercial de **Questionário** e não contém relações para artefatos que são específicos do Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Criar um mapeamento de modelo para o modelo de dados configurado

Como um usuário na função de desenvolvedor de relatório eletrônico, você deve criar uma nova configuração ER contendo um componente de [mapeamento de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) o modelo de dados **Questionário**. Como esse componente implementa o modelo de dados configurado para o Finance, ele é específico do Finance. Você deve configurar o componente de mapeamento de modelos para especificar os objetos de aplicativo que devem ser usados para preencher o modelo de dados configurado com os dados do aplicativo no tempo de execução. Para concluir essa tarefa, você deve estar ciente dos detalhes da implementação da estrutura de dados do domínio comercial **Questionário** no Finance.

Ao concluir as etapas na seção [Importar uma nova configuração de mapeamento de modelo](#ImportModelMapping) a seguir, você pode importar a configuração de mapeamento de modelo necessário a partir do arquivo XML fornecido. Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração de mapeamento do modelo](#CreateModelMapping) para criar esse mapeamento de modelo do zero.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importar uma nova configuração de mapeamento de modelo

1. Baixe o arquivo [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.
2. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. No Painel de Ação, selecione **Câmbio** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires mapping.version.1.1.xml**.
6. Selecione **OK** para importar a configuração.

Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de mapeamento de modelo](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Criar uma nova configuração de mapeamento de modelo

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.
3. Selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, siga estas etapas:

    1. No campo **Novo**, selecione **Mapeamento de modelo baseado no modelo de dados Questionários**.
    2. No campo **Nome**, insira **Mapeamento de questionário**.
    3. No campo **Definição do modelo de dados**, selecione a definição **Raiz**.
    4. Selecione **Criar configuração** para criar a configuração.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Criar um novo componente de mapeamento de modelos

1. Na página **Configurações**, na árvore de configurações, selecione **Mapeamento de questionário**.
2. Selecione **Designer** para abrir a lista de mapeamentos.
3. Selecione o mapeamento **Mapeamento de questionários** que foi adicionado automaticamente à definição **Raiz**
4. Selecione **Designer** começar a configurar o mapeamento selecionado.

Um novo mapeamento é adicionado automaticamente à definição **Raiz**. Esse mapeamento tem a direção **Para modelo**. Portanto, esse mapeamento pode ser usado para preencher um modelo de dados com os dados necessários.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Adicionar fontes de dados para acessar tabelas de aplicativos

Você deve configurar fontes de dados para acessar as tabelas do aplicativo que contêm detalhes do questionário.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.
2. Adicione uma nova fonte de dados que será usada para acessar a tabela KMCollection, em que cada registro representa um único questionário:

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome** , insira **Questionário**.
    3. No campo **Tabela**, insira **KMCollection**.
    4. Defina a opção **Pedir consulta** como **Sim**. Em seguida, será possível especificar opções de [filtragem](../../fin-ops/get-started/advanced-filtering-query-options.md) dessa tabela na caixa de diálogo consulta do sistema no runtime.
    5. Selecione **OK** para adicionar a nova fonte de dados.

3. No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.
4. Adicione uma nova fonte de dados que será usada para acessar a tabela KMQuestion, em que cada registro representa uma única pergunta em um questionário:

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome** , insira **Pergunta**.
    3. No campo **Tabela**, insira **KMQuestion**.
    4. Selecione **OK** para adicionar a nova fonte de dados.

5. No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.
6. Adicione uma nova fonte de dados que será usada para acessar a tabela KMAnswer, em que cada registro representa uma única resposta a uma pergunta em um questionário:

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. No campo **Nome**, insira **Resposta**.
    3. No campo **Tabela**, insira **KMAnswer**.
    4. Selecione **OK** para adicionar a nova fonte de dados.

7. No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.
8. Adicione um novo campo calculado que será usado para acessar um registro da tabela KMQuestionResultGroup a partir de cada registro da tabela KMCollection pai:

    1. No painel **Fontes de dados**, selecione **Questionário**.
    2. Selecione **Adicionar**.
    3. Na caixa de diálogo, no campo **Nome** , insira **\$ResultGroup**.
    4. Selecione **Editar fórmula**.
    5. No [Editor de fórmula ER](general-electronic-reporting-formula-designer.md), no campo **Fórmula**, insira **FIRSTORNULL(\@."\<Relations'.KMQuestionResultGroup)** para usar o [caminho](er-formula-language.md#paths) da relação um para muitos entre as tabelas KMCollection e KMQuestionResultGroup.
    6. Selecione **Salvar** e feche o editor de fórmula.
    7. Selecione **OK** para adicionar o novo campo calculado.

9. No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.
10. Adicione um novo campo calculado que será usado para acessar registros de perguntas da tabela KMQuestion a partir de cada registro da tabela KMCollectionQuestion pai:

    1. No painel **Fontes de dados**, selecione **Questionário**.
    2. Expanda o nó **\<Relações** que contém relações um para muitos da tabela KMCollection.
    3. Selecione a tabela **KMCollectionQuestion** relacionada e selecione **Adicionar**.
    4. Na caixa de diálogo, no campo **Nome** , insira **\$Pergunta**.
    5. Selecione **Editar fórmula**.
    6. No editor de fórmulas, no campo **Fórmula**, insira **FILTER(Question, Question.kmQuestionId = \@.kmQuestionId)** para retornar os registros de pergunta apropriados da tabela KMQuestion.
    7. Selecione **Salvar** e feche o editor de fórmula.
    8. Selecione **OK** para adicionar o novo campo calculado.

11. No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.
12. Adicione um novo campo calculado que será usado para acessar registros de resposta da tabela KMAnswer a partir de cada registro da tabela KMQuestion pai:

    1. No painel **Fontes de dados**, selecione **Questionário.\<Relations.KMCollectionQuestion.\$Pergunta** e selecione **Adicionar**.
    2. Na caixa de diálogo, no campo **Nome** , insira **\$Resposta**.
    3. Selecione **Editar fórmula**.
    4. No editor de fórmulas, no campo **Fórmula**, insira **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** para retornar os registros de resposta apropriados da tabela KMAnswer.
    5. Selecione **Salvar** e feche o editor de fórmula.
    6. Selecione **OK** para adicionar o novo campo calculado.

13. No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Tabela**.
14. Adicione uma nova fonte de dados que será usada para acessar métodos da tabela CompanyInfo. Observe que o método **find()** dessa tabela retorna um registro que representa uma empresa da atual instância de Finanças que este mapeamento é chamado nesse contexto.

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome** , insira **CompanyInfo**.
    3. No campo **Tabela**, insira **CompanyInfo**.
    4. Selecione **OK** para adicionar a nova fonte de dados.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Adicionar fontes de dados para acessar enumerações de aplicativos

Você deve configurar fontes de dados para acessar enumerações de aplicativos e comparar valores com os valores dos campos do tipo **Enumeração** nas tabelas de aplicativos. Você deve usar o resultado da comparação para preencher os campos adequados do modelo de dados.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Enumeração**.
2. Adicione uma nova fonte de dados que será usada para acessar valores da enumeração **EnumAppNoYes**.

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome** , insira **EnumAppNoYes**.
    3. No campo **Enumeração**, insira **NoYes**.
    4. Selecione **OK** para adicionar a nova fonte de dados.

3. No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations\\Enumeração**.
4. Adicione uma nova fonte de dados que será usada para acessar os valores da enumeração **KMCollectionQuestionMode**.

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome**, insira **EnumAppQuestionOrder**.
    3. No campo **Enumeração**, insira **KMCollectionQuestionMode**.
    4. Selecione **OK** para adicionar a nova fonte de dados.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Adicionar rótulos de ER para gerar um relatório em um idioma especificado

Você pode adicionar rótulos de ER para configurar algumas fontes de dados para retornar valores que dependam do idioma definido no contexto da chamada do mapeamento de modelos.

1. Na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, selecione **Responder** e **Editar**.
2. Ative o campo **Rótulo**.
3. Selecione **Traduzir**.
4. Na caixa de diálogo **Tradução de texto**, siga estas etapas:

    1. No campo **Id do rótulo**, insira **PositiveAnswer**.
    2. No campo **Texto no idioma padrão**, insira **Sim**.
    3. Selecione **Traduzir**.
    4. No campo **Id do rótulo**, digite **NegativeAnswer**.
    5. No campo **Texto no idioma padrão**, insira **Não**.
    6. Selecione **Traduzir**.

5. Feche a caixa de diálogo **Tradução de texto**.
6. Selecione **Cancelar**.

![Adição de rótulos de ER para o mapeamento de modelo editável](./media/er-quick-start1-adding-labels.png)

Você inseriu rótulos de ER somente para o idioma padrão. Para obter informações sobre como os rótulos ER podem ser traduzidos para outros idiomas, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Adicionar uma fonte de dados para transformar os resultados da comparação de valores de enumeração em um valor de texto

Como você deve transformar os resultados da comparação entre valores de enumeração e valores de texto várias vezes para diferentes fontes, convém configurar essa lógica como uma única fonte de dados. No entanto, para tornar essa fonte de dados reutilizável, você deve configurá-la como a fonte de dados parametrizada. Para obter mais informações, consulte [Suporte a chamadas parametrizadas de fontes de dados do ER do tipo do campo Calculado](er-calculated-field-type.md).

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Geral\\Contêiner vazio**.
2. Adicionar uma nova fonte de dados de contêiner:

    1. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo, no campo **Nome** , insira **Auxiliar**.
    3. Selecione **OK** para adicionar a nova fonte de dados de contêiner.

3. No painel **Tipos de fonte de dados**, selecione **Funções\\Campo calculado**.
4. Adicionar uma nova fonte de dados:

    1. No painel **Fontes de dados**, selecione **Auxiliar**.
    2. Selecione **Adicionar**.
    3. Na caixa de diálogo suspensa, no campo **Nome** , insira **NoYesEnumToString**.
    4. Selecione **Editar fórmula**.
    5. No editor de fórmulas, selecione **Parâmetros**.
    6. Siga estas etapas para especificar parâmetros para a expressão configurada:

        1. Selecione **Novo**.
        2. Na caixa de diálogo, no campo **Nome** , insira **Argumento**.
        3. No campo **Tipo**, selecione o tipo de dados **Booliano**.
        4. Selecione **OK**.

    7. No campo **Fórmula**, insira **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** para retornar o texto do rótulo de ER apropriado, dependendo do idioma do contexto de execução e do valor do parâmetro especificado.
    8. Selecione **Salvar** e feche o editor de fórmula.
    9. Selecione **OK** para adicionar a nova fonte de dados.

![Mapeamento de modelo configurado no designer de mapeamento de modelos do ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Associar fontes de dados a campos do modelo de dados

Você deve vincular fontes de dados configuradas aos campos do modelo de dados para especificar como o modelo de dados será preenchido com os dados do aplicativo no tempo de execução.

1. Na página **Designer de mapeamento de modelo**, no painel **Modelo de dados**, selecione **CompanyName**.
2. No painel **Fontes de dados**, expanda **CompanyInfo** e siga estas etapas:

    1. Expanda o nó **CompanyInfo.find()** que representa o método **find()** da tabela CompanyInfo.
    2. Selecione **CompanyInfo.find().Name**.
    3. Selecione **Associar** para preencher o nome da empresa com o qual o mapeamento de modelo configurado é chamado no contexto de tempo de execução.

3. No painel **Modelo de dados**, selecione **Questionário**.
4. No painel **Fontes de dados**, selecione **Questionário** e, depois, **Adicionar** para preencher registros de questionário.
5. No painel **Modelo de dados**, expanda **Questionário** e siga estas etapas:

    1. No painel **Modelo de dados**, selecione **Ativo**.
    2. No painel **Modelo de dados**, selecione **Editar**.
    3. No campo **Fórmula**, insira **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** para preencher o resultado dependente de texto e dependente do idioma da comparação entre valores de enumeração.

6. Continue a associar fontes de dados a campos de modelo de dados da mesma maneira até atingir o resultado a seguir.

    | Caminho do campo                                              | Tipo de dados   | Ação | Expressão de associação |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Sequência de caracteres      | Associar   | CompanyInfo.'find()'.Name |
    | Questionário                                           | Registrar lista | Associar   | Questionário |
    | Questionário\\Ativo                                   | Sequência de caracteres      | Edição   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Questionário\\Código                                     | Sequência de caracteres      | Associar   | \@.kmCollectionId |
    | Questionário\\Descrição                              | Sequência de caracteres      | Associar   | \@.Description |
    | Questionário\\QuestionnaireType                        | Sequência de caracteres      | Associar   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionário\\QuestionOrder                            | Sequência de caracteres      | Edição   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "aleatório (porcentagem no questionário)",<br>EnumAppQuestionOrder.RandomGroup, "aleatório (porcentagem no grupo de resultados)",<br>EnumAppQuestionOrder.Sequence, "Sequencial",<br>"") |
    | Questionário\\ResultsGroup                             | Registrar      |        | |
    | Questionário\\ResultsGroup\\Code                       | Sequência de caracteres      | Associar   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionário\\ResultsGroup\\Descrição                | Sequência de caracteres      | Associar   | \@.'\$ResultGroup'.description |
    | Questionário\\ResultsGroup\\MaxNumberOfPoints          | Real        | Associar   | \@.'\$ResultGroup'.maxPoint |
    | Questionário\\Pergunta                                 | Registrar lista | Associar   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionário\\Pergunta\\CollectionSequenceNumber       | Inteiro     | Associar   | \@.answerCollectionSequenceNumber |
    | Questionário\\Pergunta\\Id                             | Sequência de caracteres      | Associar   | \@.kmQuestionId |
    | Questionário\\Pergunta\\MustBeCompleted                | Sequência de caracteres      | Edição   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionário\\Pergunta\\PrimaryQuestion                | Sequência de caracteres      | Associar   | \@.parentQuestionId |
    | Questionário\\Pergunta\\SequenceNumber                 | Inteiro     | Associar   | \@.SequenceNumber |
    | Questionário\\Pergunta\\Texto                           | Sequência de caracteres      | Associar   | \@.'\$Question'.text |
    | Questionário\\Pergunta\\Resposta                         | Registrar lista | Associar   | \@.'\$Question'.'\$Answer' |
    | Questionário\\Pergunta\\Resposta\\CorrectAnswer          | Sequência de caracteres      | Edição   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionário\\Pergunta\\Resposta\\Pontos                 | Real        | Associar   | \@.point |
    | Questionário\\Pergunta\\Resposta\\SequenceNumber         | Inteiro     | Associar   | \@.sequenceNumber |
    | Questionário\\Pergunta\\Resposta\\Texto                   | Sequência de caracteres      | Associar   | \@.text |

    A ilustração a seguir mostra o estado final do mapeamento de modelo configurado na página **Designer de mapeamento de modelo**.

    ![Mapeamento de modelo totalmente configurado no designer de mapeamento de modelo do ER](./media/er-quick-start1-mapping2.png)

7. Salve as alterações.
8. Feche a página **Designer de mapeamento de modelo**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Concluir o design de mapeamento de modelo

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione **Mapeamento de questionário**.
3. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
4. Selecione **Alterar status** \> **Concluir**.

O status da versão 1.1 dessa configuração é alterado de **Rascunho** para **Concluído**. A versão 1.1 não pode mais ser alterada. Esta versão contém o mapeamento de modelo configurado e pode ser usada como base para outras configurações de ER. A versão 1.2 dessa configuração é criada e tem um status **Rascunho**. Você pode editar esta versão para ajustar a configuração de **Mapeamento de questionário**.

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> O mapeamento de modelo configurado é a implementação específica do Finance do modelo de dados abstratos que representa o domínio comercial de **Questionário**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Criar um modelo para um relatório personalizado

A estrutura de ER gera usa modelos predefinidos para gerar relatórios nos formatos do Microsoft Office (pastas de trabalho do Excel ou documentos do Word). Enquanto o relatório necessário está sendo gerado, um modelo é preenchido com os dados necessários de acordo com o fluxo de dados configurado. Portanto, você deve primeiro criar um modelo para o relatório personalizado. Esse modelo deve ser criado como uma pasta de trabalho do Excel cuja estrutura representa o layout de um relatório personalizado. Você deve nomear todos os itens do Excel que pretende preencher com os dados necessários.

1. Baixe o arquivo [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.
2. Abra o arquivo no Excel e revise a estrutura da pasta de trabalho.

Como mostra a ilustração a seguir, o modelo baixado foi projetado para imprimir questionários especificados que apresentam as perguntas de um questionário junto com as respostas apropriadas.

![Modelo do Excel para imprimir questionários especificados](./media/er-quick-start1-template-layout.png)

Os nomes do Excel foram adicionados a este modelo para preencher os detalhes do questionário. Você pode usar o Gerenciador de nomes para revisar os nomes do Excel.

![Usando o Gerenciador de nomes para revisar nomes do Excel no modelo do Excel fornecido](./media/er-quick-start1-template-names.png)

Os rótulos de relatório foram adicionados como texto fixo no idioma inglês. Você pode substituir os rótulos de relatório por novos nomes do Excel que preenchem os rótulos com o texto dependente do idioma, usando os [rótulos](#AddMmLabels) do formato ER, como fez para expressões dependentes de idioma no mapeamento de modelo configurado. Nesse caso, os rótulos de ER devem ser adicionadas ao formato ER editável.

Como mostra a ilustração a seguir, o cabeçalho do relatório personalizado foi especificado para habilitar a paginação do Excel.

![O cabeçalho do relatório personalizado no modelo do Excel fornecido](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Criar um formato

Como usuário na função de consultor funcional de relatório eletrônico, você deve criar uma nova configuração do ER contendo um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound). Você deve configurar o componente de formato para especificar como um modelo de relatório será preenchido com dados necessários no tempo de execução.

Ao concluir as etapas na seção [Importar uma configuração de formato projetado](#FormatImport), você pode importar o formato necessário a partir do arquivo XML fornecido. Como alternativa, você pode concluir as etapas na seção [Criar uma nova configuração de formato](#FormatCreate) para criar esse formato do zero.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Importar uma configuração de formato criado

1. Baixe o arquivo [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) e salve-o no computador local.
2. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. No Painel de Ações, selecione **Câmbio** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Questionnaires format.version.1.1.xml**.
6. Selecione **OK** para importar a configuração.

Para continuar, ignore o próximo procedimento, [Criar uma nova configuração de formato](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Criar uma nova configuração de formato
 
1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, selecione **Modelo de questionário**.
3. Selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, siga estas etapas:

    1. No campo **Novo**, selecione **Formato baseado no modelo de dados Questionários**.
    2. No campo **Nome**, insira **Relatório de questionário**.
    3. No campo **Versão de modelo de dados**, selecione **1**.

        > [!NOTE]
        > - Se você selecionar uma versão específica do modelo de dados básicos, a estrutura da versão correspondente do modelo de dados será apresentada como a estrutura da fonte de dados **Modelo** no formato criado.
        > - Este campo pode ser deixado em branco. Nesse caso, a estrutura da versão de **Rascunho** do modelo de dados será apresentada como a estrutura da fonte de dados **Modelo** no formato criado. Em seguida, você pode ajustar o modelo e ver imediatamente esses ajustes no seu formato. Esta abordagem pode melhorar a eficiência do design da solução ER quando você configura o modelo de dados, o mapeamento de modelos e o formato simultaneamente.
        > - Se você selecionar uma versão específica do modelo de dados básicos, poderá alternar para o uso da versão **Rascunho** posteriormente, ao começar a editar um formato.

    4. No campo **Definição do modelo de dados**, selecione a definição **Raiz**.

5. Selecione **Criar configuração** para criar a configuração.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Importar um modelo do relatório

1. Na página **Configurações**, na árvore de configurações, selecione **Relatório de questionário**.
2. Selecione **Designer** para começar a configurar um formato personalizado.
3. Na página **Designer de formato**, no Painel de Ações, selecione **Importar** \> **Importar do Excel**.
4. Na caixa de diálogo, siga estas etapas:

    1. Selecione **Adicionar modelo**.
    2. Localize e selecione arquivo **Questionnaires report template.xslx** salvo localmente e selecione **Abrir**.
    3. Selecione **OK** para importar o modelo.

    ![Importar um modelo de relatório](./media/er-quick-start1-template-import.png)

O formato **Excel\\Arquivo** é adicionado automaticamente ao formato editável como um elemento raiz. Além disso, o elemento de formato **Excel\\Intervalo** ou o elemento de formato **Excel\\Célula** é automaticamente adicionado a cada nome do Excel reconhecido do modelo importado. O formato **Excel\\Cabeçalho** que tem o elemento **Cadeia de caracteres** aninhado é automaticamente adicionado para refletir as configurações de cabeçalho do modelo importado.

![Estrutura de formato que inclui elementos adicionados automaticamente no designer de Operação do ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Configurar um formato

1. Na página **Designer de formato**, na árvore de formatos, selecione o elemento raiz do **Excel**.
2. Na guia **Formatar** no lado direito da página, no campo **Nome**, insira <a name="AddFormatRootElement"></a>**Relatório**.
3. No campo **Preferência de idioma**, selecione a **Preferência de usuário** para executar o relatório no idioma preferencial do usuário.
4. No campo **Preferência de cultura**, selecione a **Preferência de usuário** para executar o relatório na cultura preferencial do usuário.

    Para obter informações sobre como especificar o idioma e os contextos de cultura para um processo ER, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).

    ![Como definir configurações de idioma e cultura para o relatório criado no designer de Operações do ER](./media/er-quick-start1-template-format-structure1.png)

5. Na árvore de formatos, expanda o nó raiz e selecione **ResultsGroup**.
6. Na guia **Formatar**, no campo **Direção da replicação**, selecione **Sem replicação**, porque você não espera ter vários grupos de resultados para um único questionário.

    ![Como definir a direção de replicação para elementos de formato de intervalo no designer de Operação do ER](./media/er-quick-start1-template-format-structure2.png)

7. Selecione **Salvar**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Definir a associação de dados para um título de relatório

Você deve especificar uma associação de dados para um elemento de formato que é usado para preencher o título de um relatório gerado.

1. Na página **Designer de formato**, na guia **Mapeamento** à direita, selecione o elemento **Relatório\\ReportTitle**.
2. Selecione **Editar fórmula**.
3. No editor de fórmulas, selecione **Traduzir**.
4. Na caixa de diálogo **Tradução de texto**, siga estas etapas:

    1. No campo **ID do rótulo**, insira **ReportTitle**.
    2. No campo **Texto no idioma padrão**, insira **Relatório Questionários**.
    3. Selecione **Traduzir** e, depois, **Salvar**.
    4. Selecione **Traduzir** para fechar a caixa de diálogo **Tradução de texto**.

5. Feche o editor de fórmulas.

    ![Como configurar a associação para preencher o título de um relatório gerado](./media/er-quick-start1-add-report-title-label.png)

Você pode usar essa técnica para tornar todos os outros rótulos do modelo atual dependentes de idioma. Para obter informações sobre como os rótulos adicionados de uma única configuração de ER podem ser traduzidos em todos os idiomas com suporte, consulte [Criar relatórios multilíngues](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Analisar a fonte de dados do modelo

1. Na página **Designer de formato**, na guia **Mapeamento**, selecione a fonte de dados <a name="ModelDSName"></a>**modelo** que representa o modelo de dados base deste formato ER.
2. Selecione **Editar**.
3. Revise as informações na caixa de diálogo **Propriedades da fonte de dados**. Essa fonte de dados representa a versão 1 do componente do modelo de dados **Questionários** que reside na configuração ER do **modelo Questionários**.

![Propriedades da fonte de dados do modelo no designer de Operações do ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Associar elementos a campos da fonte de dados

Para especificar como um modelo é preenchido no tempo de execução, você deve associar todos os elementos de formato associados a um nome do Excel apropriado a um único campo da fonte de dados desse formato.

1. Na página **Designer de formato**, na árvore de formatos, selecione o elemento **Relatório\\CompanyName**.
2. Na guia **Mapeamento**, selecione o campo de fonte de dados **model.CompanyName** do tipo **Cadeia de caracteres**.
3. Selecione **Associar** para inserir um nome de empresa em um modelo.
4. Na árvore de formatos, selecione o elemento **Relatório\\Questionário**.
5. Na guia **Mapeamento**, selecione o campo de fonte de dados **model.Questionnaire** do tipo **Lista de registros**.
6. Selecione **Associar**.
7. Selecione **Mostrar detalhes** para ver mais detalhes dos elementos de formato.

    O elemento de formato do intervalo **Questionário** é configurado como replicado verticalmente. Quando ele está associado a uma fonte de dados do tipo **Lista de registros**, o intervalo de **Questionário** apropriado do modelo do Excel é repetido para cada registro da fonte de dados associada.
 
    ![Associação do elemento Formato do intervalo do questionário a fontes de dados de Lista de registros apropriadas no designer de Operação do ER](./media/er-quick-start1-bindings1.png)

    Como o intervalo **Questionário** do modelo do Excel é definido entre as linhas 5 e 14, essas linhas são repetidas para todos os questionários relatados.

    ![Linhas do modelo do Excel que serão repetidas em um relatório gerado para cada registro das fontes de dados da lista de registros](./media/er-quick-start1-template-questionnaire-range.png)

8. Configure associações semelhantes para os elementos de formato restantes, conforme descrito na tabela a seguir.

    > [!NOTE]
    > Nesta tabela, as informações na coluna "Caminho da fonte de dados" supõem que o recurso do ER [caminho relativo](relative-path-data-bindings-er-models-format.md) está ativado.

    | Caminho do elemento de formato                                      | Caminho da fonte de dados |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionário                                     | **model.Questionnaire** |
    | Excel\\Questionário\\Ativo                             | **\@.Active**, onde **\@** é **model.Questionnaire** |
    | Excel\\Questionário\\Código                               | **\@.Code** |
    | Excel\\Questionário\\Descrição                        | **\@.Description** |
    | Excel\\Questionário\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionário\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionário\\ResultsGroup\\Código\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionário\\ResultsGroup\\Descrição\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionário\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionário\\Pergunta                           | **\@.Question** |
    | Excel\\Questionário\\Pergunta\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, onde **\@** é **model.Questionnaire.Question** |
    | Excel\\Questionário\\Pergunta\\Id                       | **\@.Id** |
    | Excel\\Questionário\\Pergunta\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionário\\Pergunta\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionário\\Pergunta\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionário\\Pergunta\\Texto                     | **\@.Text** |
    | Excel\\Questionário\\Pergunta\\Resposta                   | **\@.Answer** |
    | Excel\\Questionário\\Pergunta\\Resposta\\CorrectAnswer    | **\@.CorrectAnswer**, onde **\@** é **model.Questionnaire.Answer** |
    | Excel\\Questionário\\Pergunta\\Resposta\\Pontos           | **\@.Points** |
    | Excel\\Questionário\\Pergunta\\Resposta\\Texto             | **\@.Text** |

9. Quando terminar, selecione **Salvar**.

A ilustração a seguir mostra o estado final de associações de dados configuradas na página **Designer de formato**.

![Associações de dados configuradas no designer Operação do ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> Toda a coleção de fontes de dados e associações especificadas representa um componente de mapeamento de formato do formato configurado. Esse mapeamento de formato é chamado quando você executa o formato configurado para a geração de relatórios.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Executar um formato criado a partir do ER

Agora você pode executar um formato criado para fins de teste na página **Configurações**.

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configuração**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.
3. Selecione **Designer** para a versão de formato que tem um status **Rascunho**.
4. Na página **Designer de formato**, selecione **Executar**.
5. Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
6. Selecione **OK** para confirmar a opção de filtragem.
7. Selecione **OK** para executar o relatório.
8. Revise o relatório gerado.

Por [padrão](electronic-reporting-destinations.md#default-behavior), um relatório gerado é entregue como um arquivo do Excel que pode ser baixado. As ilustrações a seguir mostram duas páginas do relatório gerado no formato Excel.

![Exemplo de um relatório gerado no formato Excel, página 1](./media/er-quick-start1-report1a.png)

![Exemplo de um relatório gerado no formato Excel, página 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Ajustar um formato criado

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Modificar um formato para alterar o nome de um documento gerado

Por padrão, um documento gerado é nomeado usando o alias do usuário atual. Ao modificar o formato, você pode alterar esse comportamento para que um documento gerado seja nomeado com base na lógica personalizada. Por exemplo, o nome de um documento gerado pode se basear na data e na hora da sessão atual e no título do relatório.

1. Na página **Designer de formato**, selecione o item de raiz **Relatório**.
2. Na guia **Mapeamento**, selecione **Editar nome do arquivo**.
3. No campo **Fórmula**, insira **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "aaaa-MM-dd hh-mm-ss"))**.
4. Selecione **Salvar** e feche o editor de fórmula.
5. Selecione **Salvar**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Modificar um formato para alterar a ordem das perguntas

As perguntas não são ordenadas corretamente em um relatório gerado. Você pode alterar a ordem modificando o formato.

1. Na página **Designer de formato**, selecione o item de raiz **Relatório**.
2. Na guia **Mapeamento**, na árvore de formatos, expanda **Relatório\\Questionário\\Pergunta**.

    ![Elemento de formato da pergunta do tipo de intervalo no designer de Operação do ER](./media/er-quick-start1-bindings3.png)

3. Na guia **Mapeamento**, selecione **model.Questionnaire**.
4. Selecione **Adicionar** \> **Funções\\Campo calculado** e, em seguida, no campo **Nome**, insira **OrderedQuestions**.
5. Selecione **Editar fórmula**.
6. No editor de fórmulas, no campo **Fórmula**, insira **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** para ordenar a lista de perguntas do questionário atual pelo número da ordem de sequência.
7. Selecione **Salvar** e feche o editor de fórmula.
8. Selecione **OK** para concluir a entrada de um novo campo calculado.
9. Na guia **Mapeamento**, selecione **model.Questionnaire.OrderedQuestions**.
10. Na árvore de formatos, selecione **Excel\\Questionário\\Pergunta**.
11. Selecione **Associar** e confirme se o caminho **model.Questionnaire.Questions** atual é substituído pelo novo caminho **model.Questionnaire.OrderedQuestions** em todas as associações de elementos aninhados.
12. Selecione **Salvar**.

![Associação do elemento de formato da pergunta à fonte de dados OrderedQuestions configurada no designer de Operação do ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Executar um formato modificado a partir de ER

Agora você pode executar um formato modificado para fins de teste a partir da estrutura de ER.

1. Na página **Designer de formato**, selecione **Executar**.
2. Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
3. Selecione **OK** para confirmar a opção de filtragem.
4. Selecione **OK** para executar o relatório.
5. Revise o relatório gerado.

A ilustração a seguir mostra um relatório gerado no formato Excel, no qual as perguntas estão corretamente ordenadas.

![Relatório gerado no formato Excel com perguntas corretamente ordenadas](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Concluir a criação do formato

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.
3. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
4. Selecione **Alterar status** \> **Concluir**.

O status da versão 1.1 dessa configuração é alterado de **Rascunho** para **Concluído**. A versão 1.1 não pode mais ser alterada. Esta versão contém o formato configurado e pode ser usada para imprimir o relatório personalizado. A versão 1.2 dessa configuração é criada e tem um status **Rascunho**. Você pode editar esta versão para ajustar a formatar o relatório **Questionário**.

![Versões da configuração do ER editável na página Configurações](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> O formato configurado é o design do relatório **Questionário** e não contém relações com artefatos específicos do Finance.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Desenvolver artefatos de aplicativos para chamar o relatório criado

Como um usuário na função Administrador do sistema, você deve desenvolver uma nova lógica para que o formato ER configurado possa ser chamado a partir da interface do usuário do aplicativo (IU) para gerar o relatório personalizado. No momento, o ER não oferece recursos para a configuração desse tipo de lógica. Portanto, é necessário algum trabalho de engenharia. 

Para desenvolver a nova lógica, você deve implantar uma topologia que dê suporte à compilação contínua. Para obter mais informações, consulte [Implantar topologias que dão suporte à contínua automação de compilações e testes](../perf-test/continuous-build-test-automation.md). Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia. Para obter mais informações sobre a API de ER disponível, consulte [API da estrutura de ER](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Modificar o código-fonte

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Adicionar uma classe de contrato de dados

Adicione a nova classe **QuestionnairesErReportContract** ao projeto Microsoft Visual Studio e escreva o código que especifica o contrato de dados que deve ser usado para executar o formato ER configurado.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Adicionar uma classe do construtor de interface de usuário

Adicione a nova classe **QuestionnairesErReportUIBuilder** ao projeto do Visual Studio e escreva o código para gerar uma caixa de diálogo em tempo de execução que será usada para pesquisar a ID de mapeamento do formato do formato de ER que deve ser executado. O código fornecido pesquisa somente os formatos de ER que contêm uma fonte de dados do tipo **Modelo de dados**, que se refere ao modelo de dados **[Questionários](#DataModeName)**, por meio do uso da definição **[Raiz](#RootDefinitionName)**.

> [!NOTE]
> Como alternativa, você pode usar os pontos de integração de ER para filtrar os formatos de ER. Para obter mais informações, consulte [API para mostrar uma pesquisa de mapeamento de formato](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Adicionar uma classe de provedor de dados

Adicione a nova classe **QuestionnairesErReportDP** ao projeto Visual Studio e escreva o código que apresenta o provedor de dados que deve ser usado para executar o formato de ER configurado. O código fornecido inclui somente o contrato de dados deste provedor de dados.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Adicionar um arquivo de rótulos

Adicione o novo arquivo de rótulos **QuestionnairesErReportLabels\_en-US** ao projeto do Visual Studio e especifique os seguintes rótulos para novos recursos da interface do usuário:

- O rótulo **\@QuestionnairesReport** de um novo item de menu que contém o seguinte texto em inglês dos EUA (en-US): **Relatório Questionários (alimentado pelo ER)**
- O rótulo **\@QuestionnairesReportBatchJobDescription** de um cargo de lote se um formato de ER selecionado for agendado para execução como um trabalho em lotes

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Adicionar uma classe de serviço de relatório

Adicione a nova classe **QuestionnairesErReportService** ao projeto do Visual Studio e escreva o código que chama um formato de ER, o identifica por uma ID de mapeamento de formato e fornece um contrato de dados como um parâmetro.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Quando você precisa usar um formato de ER que executa dados de aplicativo, deve configurar uma fonte de dados do tipo **Modelo de dados** no mapeamento de formato. Essa fonte de dados se refere a uma parte específica do modelo de dados especificado usando uma única definição de raiz. Quando o formato de ER é executado, ele chama essa fonte de dados para acessar o mapeamento do modelo de ER apropriado configurado para determinada definição de modelo e raiz.

Todas as informações que você pode preparar no código-fonte e no armazenamento como parte do contrato de dados podem ser passadas para o formato de ER em execução usando um mapeamento do modelo de ER deste tipo. No mapeamento do modelo de ER, você deve configurar uma fonte de dados do tipo **Objeto** que se refere à classe **[QuestionnairesErReportContract](#DataContractClass)**. Para identificar um mapeamento de modelos, você deve especificar uma fonte de dados que chame esse mapeamento de modelo. No código fornecido, essa fonte de dados especificada pela constante **ERModelDataSourceName** que tem o valor do **[modelo](#ModelDSName)**. Para identificar qual fonte de dados é usada para expor o contrato de dados no mapeamento do modelo, você deve especificar um nome de fonte de dados. No código fornecido, esse nome é especificado pela constante **ParametersDataSourceName** que tem o valor <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> Em um novo ambiente, talvez seja necessário atualizar os metadados ER para que esse tipo de classe esteja disponível no designer de mapeamento do modelo ER. Para obter mais informações, consulte [Configurar a estrutura do ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Adicionar uma classe de controlador de relatório

Adicione a nova classe **QuestionnairesErReportController** ao projeto do Visual Studio e escreva o código que executa um formato de ER no modo síncrono ou no modo de lotes, como preferir, na caixa de diálogo criada com base na lógica da classe **QuestionnairesErReportUIBuilder** fornecida.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Adicionar um item de menu

Adicione o novo item de menu **QuestionnairesErReport** ao projeto do Visual Studio. Na propriedade **Objeto**, esse item de menu se refere à classe **QuestionnairesErReportController** e é usado para especificar uma permissão de usuário para selecionar e executar um formato de ER. Na propriedade **Rótulo**, esse item de menu se refere ao rótulo **\@QuestionnairesReport** que você criou anteriormente, de forma que o texto correto seja apresentado na interface do usuário do aplicativo.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Adicionar um item de menu a um menu

Adicione o menu **KM** existente ao projeto do Visual Studio. Você deve adicionar um novo item **QuestionnairesErReport** do tipo **Saída** a este menu. Este item deve se referir ao item de menu **QuestionnairesErReport** descrito na seção anterior.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Criar um projeto do Visual Studio

Crie seu projeto para disponibilizar um novo item de menu para os usuários.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Executar um formato do aplicativo

1. Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.

    ![Seleção do item de menu do relatório Questionários (alimentado pelo ER) no módulo Questionário para executar o formato de ER configurado](./media/er-quick-start1-application-menu-modified.png)

2. Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.
3. Selecione **OK**.
4. Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
5. Selecione **OK** para confirmar a opção de filtragem.
6. Selecione **OK** para executar o relatório.

    ![Como especificar os critérios de seleção na caixa de diálogo Relatório eletrônico](./media/er-quick-start1-report-run-dialog-page.png)

7. Revise o relatório gerado.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Ajustar uma solução de ER criada

Você pode modificar a solução de ER configurada de forma que use a classe de provedor de dados que desenvolveu para acessar detalhes da execução do formato de ER e para que ela insira o nome do formato de ER em um relatório gerado.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modificar um mapeamento de modelo

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Adicionar fontes de dados para acessar um objeto de contrato de dados

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Mapeamento de questionário**.
3. Selecione **Designer** para abrir a página **Modelo para mapeamento de fonte de dados**.
4. Selecione **Designer** para abrir o mapeamento selecionado no designer de mapeamento de modelo.
5. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Objeto**.
6. No painel **Fontes de dados**, selecione **Adicionar raiz**.
7. Na caixa de diálogo, no campo **Nome**, insira **[RunTimeParameters](#DataContractDSName)**, conforme definido no código-fonte da classe **QuestionnairesErReportService**.
8. No campo **Classe**, insira **[QuestionnairesErReportContract](#DataContractClass)**, que foi codificado anteriormente.
9. Selecione **OK**.
10. Expanda **RunTimeParameters**.

A fonte de dados adicionada fornece informações sobre a ID de registro do mapeamento de formato de ER em execução.

![Fonte de dados adicionada no designer de mapeamento do modelo de ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Adicionar uma fonte de dados para acessar registros de mapeamento de formato de ER

Continue para editar o mapeamento de modelos selecionado, adicionando uma fonte de dados para acessar registros de mapeamento de formato de ER.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Dynamics 365 for Operations\\Registros de tabela**.
2. No painel **Fontes de dados**, selecione **Adicionar raiz**.
3. Na caixa de diálogo, no campo **Nome** , insira **ER1**.
4. No campo **Tabela**, insira **ERFormatMappingTable**.
5. Selecione **OK**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Adicionar uma fonte de dados para acessar um registro de mapeamento de formato de um formato de ER em execução

Continue para editar o mapeamento de modelos selecionado, adicionando uma fonte de dados para acessar o registro de mapeamento do formato de ER em execução.

1. Na página **Designer de mapeamento de modelo**, no painel **Tipos de fontes de dados**, selecione **Funções\\Campo calculado**.
2. No painel **Fontes de dados**, selecione **Adicionar raiz**.
3. Na caixa de diálogo, no campo **Nome** , insira **ER2**.
4. Selecione **Editar fórmula**.
5. No editor de fórmulas, no campo **Fórmula**, insira **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Selecione **Salvar** e feche o editor de fórmula.
7. Selecione **OK**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Inserir o nome do formato de ER em execução no modelo de dados

Continue para editar o mapeamento de modelo selecionado, de forma que o nome do formato ER em execução seja inserido no modelo de dados.

1. Na página **Designer de mapeamento de modelo**, no painel **Modelo de dados**, expanda **ExecutionContext** e selecione **ExecutionContext\\FormatName**.
2. No painel **Modelo de dados**, selecione **Editar** para configurar uma associação de dados para o campo do modelo de dados selecionado.
3. No editor de fórmulas, no campo **Fórmula**, insira **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.
4. Selecione **Salvar** e feche o editor de fórmula.

Como você utilizou o campo **FormatName**, o mapeamento do modelo configurado agora expõe o nome de um formato de ER que chama esse mapeamento de modelo durante a execução.

![Associação do campo de modelo de dados ao método da fonte de dados adicionada no designer de mapeamento do modelo de ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Concluir o design de mapeamento de modelo

1. Na página **Designer de mapeamento de modelo**, selecione **Salvar**.
2. Feche a página.
3. Feche a página de mapeamentos de modelo.
4. Na página **Configurações**, na árvore de configurações, verifique se a configuração de **Mapeamento de questionário** ainda está selecionada. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
5. Selecione **Alterar status** \> **Concluir**.

O status da versão 1.2 dessa configuração é alterado de **Rascunho** para **Concluído**. A versão 1.2 não pode mais ser alterada. Esta versão contém o mapeamento de modelo configurado e pode ser usada como base para outras configurações de ER. A versão 1.3 dessa configuração é criada e tem um status **Rascunho**. Você pode editar esta versão para ajustar o mapeamento de modelo **Questionário**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Modificar um formato

Você pode modificar o formato de ER configurado de forma que o nome dele apareça no rodapé de um relatório que é gerado quando o formato de ER é executado.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Adicionar um novo elemento de formato

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.
3. Selecione **Designer**.
4. Na página **Designer de formato**, selecione o item de raiz **Relatório**.
5. Selecione **Adicionar** para adicionar um novo elemento de formato aninhado ao item raiz **Relatório** selecionado.
6. Selecione **Excel\\Rodapé**.
7. No campo **Nome**, insira **Rodapé**.
8. Selecione **Relatório\Rodapé** e, depois, **Adicionar**.
9. Selecione **Texto\\Cadeia de caracteres**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Vincular o elemento de formato adicionado

1. Na página **Designer de formato**, na guia **Mapeamento**, selecione a árvore de formatos para o elemento **Rodapé\\Cadeia de caracteres** ativo e selecione **Editar fórmula**
2. No editor de fórmulas, no campo **Fórmula**, insira **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.
3. Selecione **Salvar** e feche o editor de fórmula.
4. Selecione **Salvar**.

O formato configurado foi modificado para que o nome dele seja inserido no rodapé de um relatório gerado usando o elemento **Rodapé\\Cadeia de caracteres**.

![Adição do elemento de formato do rodapé ao formato configurado no designer de Operação do ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Concluir a criação do formato

1. Feche a página **Designer de formato**.
2. Na página **Configurações**, na árvore de configurações, verifique se a configuração de **Relatório de questionário** ainda está selecionada. Na FastTab **Versões**, selecione a versão de configuração com o status **Rascunho**.
3. Selecione **Alterar status** \> **Concluir**.

O status da versão 1.2 dessa configuração é alterado de **Rascunho** para **Concluído**. A versão 1.2 não pode mais ser alterada. Esta versão contém o formato configurado e pode ser usada como base para outras configurações de ER. A versão 1.3 dessa configuração é criada e tem um status **Rascunho**. Você pode editar esta versão para ajustar o relatório **Questionário**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Executar um formato do aplicativo

1. Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.
2. Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.
3. Selecione **OK**.
4. Na caixa de diálogo **Parâmetros de ER**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
5. Selecione **OK** para confirmar a opção de filtragem.
6. Selecione **OK** para executar o relatório.
7. Revise o relatório gerado no formato Excel.

Observe que o rodapé do relatório gerado contém o nome do formato de ER que foi usado para gerá-lo.

![Relatório gerado no formato Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Executar um formato de ER

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações, expanda **Modelo de questionário** e selecione **Relatório de questionário**.
3. No Painel de Ação, selecione **Executar**.
4. Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
5. Selecione **OK** para confirmar a opção de filtragem.
6. Selecione **OK** para executar o relatório.
7. Revise o relatório gerado no formato Excel.

Observe que o rodapé do relatório gerado não contém o nome do formato de ER que foi usado para gerá-lo, pois o objeto de contrato de dados não foi passado para o mapeamento do modelo em execução quando ele foi chamado pelo formato de ER executado a partir de ER.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Configurar um destino de formato para versão prévia na tela

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Destino de relatório eletrônico**.
2. Na página **Destino do relatório eletrônico**, adicione um registro de destino para o formato de ER configurado para o formato de ER **Relatório de questionário**.
3. Na FastTab **Destino do arquivo**, configure o [destino](er-destination-type-screen.md) da **Tela** para o componente de formato de **Relatório** que foi [adicionado](#AddFormatRootElement) como o elemento-raiz do formato de ER do **Relatório de questionário** configurado.
4. Na FastTab **Configurações de conversão de PDF**, configure o destino para converter um relatório em [formato PDF](electronic-reporting-destinations.md#OutputConversionToPDF) que usa a orientação de página **Paisagem**.

![Configuração do destino de tela personalizado para o formato de ER na página destino Relatório eletrônico](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Executar um formato do aplicativo para visualizá-lo como um documento PDF

1. Vá para **Questionário** \> **Design** \> **Relatório Questionários (alimentado pelo ER)**.
2. Na caixa de diálogo, no campo **Mapeamento de formato**, selecione **relatório Questionários**.
3. Selecione **OK**.
4. Na caixa de diálogo **Parâmetros de relatório eletrônico**, na FastTab **Registros a serem incluídos**, configure a opção de filtragem para que somente o questionário **SBCCrsExam** seja incluído.
5. Selecione **OK** para confirmar a opção de filtragem.

    Na FastTab **Destinos**, observe que o campo **Saída** está definido como **Tela**. Se desejar alterar o destino configurado, selecione **Alterar**.

    ![Caixa de diálogo Tempo de execução de relatório de ER, em que você pode alterar o destino configurado](./media/er-quick-start1-run-settings.png)

6. Selecione **OK** para executar o relatório.
7. Revise o relatório gerado no formato PDF.

    ![Versão prévia na tela do relatório gerado no formato PDF](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
- [Criar relatórios multilíngues](er-design-multilingual-reports.md)
- [API da estrutura de ER](er-apis-app73.md)
- [Função CASE](er-functions-logical-case.md)
- [Função CONCATENATE](er-functions-text-concatenate.md)
- [Função DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [Função FILTER](er-functions-list-filter.md)
- [Função FIRSTORNULL](er-functions-list-firstornull.md)
- [Função FORMAT](er-functions-text-format.md)
- [Função IF](er-functions-logical-if.md)
- [Função ORDERBY](er-functions-list-orderby.md)
- [Função SESSIONNOW](er-functions-datetime-sessionnow.md)
