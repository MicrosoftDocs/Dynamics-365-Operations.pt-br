---
title: Adicionar análise a espaços de trabalho usando o Power BI Embedded
description: Este artigo mostra como incorporar um relatório do Power BI na guia Análise de um espaço de trabalho.
author: RichdiMSFT
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b06821f02e6a80f2e15db7d0dd95ef6c9a30d5bc
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206406"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Adicionar análise a espaços de trabalho usando o Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Este recurso é aceito nos aplicativos de finanças e operações (versão 7.2 e posterior).

## <a name="introduction"></a>Introdução
Este artigo mostra como inserir um relatório do Microsoft Power BI na guia **Análise** de um espaço de trabalho. No exemplo dado aqui, estenderemos o espaço de trabalho **Gerenciamento de reservas** no aplicativo de Gerenciamento de Frota para incorporar um espaço de trabalho analítico em uma guia **Análise**.

## <a name="prerequisites"></a>Pré-requisitos
+ Acesso a um ambiente de desenvolvedor que executa a atualização 8 da plataforma ou posterior.
+ Um relatório analítico (.pbix file) que foi criado por meio usando o Microsoft Power BI Desktop e que apresenta um modelo de dados com origem no banco de dados do Repositório de entidades.

## <a name="overview"></a>Visão Geral
Se você estender um espaço de trabalho de aplicativo existente ou introduzir seu próprio espaço de trabalho, é possível usar exibições analíticas incorporadas para fornecer exibições intuitivas e interativas de seus dados comerciais. O processo para adicionar uma guia de espaço de trabalho analítico apresenta quatro etapas.

1. Adicione um arquivo .pbix como um recurso do Dynamics 365.
2. Define uma guia de espaço de trabalho analítico.
3. Incorpore o recurso .pbix na guia do espaço de trabalho.
4. Opcional: adicione extensões para personalizar a exibição.

> [!NOTE]
> Para obter informações sobre como criar relatórios analíticos, consulte [Introdução ao Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/). Esta página é um grande recurso para informações que podem ajudar a criar soluções de relatório analítico atrativas.

## <a name="add-a-pbix-file-as-a-resource"></a>Adicionar um arquivo .pbix como um recurso
Antes de começar, é preciso criar ou obter o relatório do Power BI que será incorporado no espaço de trabalho. Para obter informações sobre como criar relatórios analíticos, consulte [Introdução ao Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).

Siga essas etapas para adicionar um arquivo .pbix como um artefato de projetos do Visual Studio.

1. Crie um projeto no modelo apropriado.
2. No Gerenciador de Soluções, selecione o projeto, clique com o botão direito do mouse e depois selecione **Adicionar** \> **Novo Item**.
3. Na caixa de diálogo **Adicionar novo item**, em **Artefatos do Operations**, selecione o modelo **Recurso**.
4. Insira um nome que será usado para referenciar o relatório em metadados X++ e depois clique em **Adicionar**.

    ![Adicionar a caixa de diálogo Novo item.](media/analytical-workspace-add.png)

5. Localize o arquivo .pbix que contém a definição do relatório analítico e depois clique em **Abrir**.

    ![Selecionar uma caixa de diálogo Arquivo de recurso.](media/analytical-workspace-select-resource.png)

Agora que você já adicionou o arquivo .pbix como um recurso do Dynamics 365, é possível incorporar os relatórios nos espaços de trabalho e adicionar links diretos usando itens de menu.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Adicionar um controle de guias a um espaço de trabalho de aplicativo
Neste exemplo, estenderemos o espaço de trabalho **Gerenciamento de reservas** no modelo de Gerenciamento de Frota adicionando a guia **Análise** à definição do formulário **FMClerkWorkspace**.

A ilustração a seguir mostra a aparência do formulário **FMClerkWorkspace** no designer do Microsoft Visual Studio.

![Formulário FMClerkWorkspace antes de alterações.](media/analytical-workspace-definition-before.png)

Siga essas etapas para estender a definição de formulário para o espaço de trabalho **Gerenciamento de reservas**.

1. Abra o designer de formulário para estender a definição de design.
2. Na definição de design, selecione o elemento superior que é rotulado **Design | Pattern: Workspace Operational**.
3. Clique com o botão direito do mouse e depois selecione **Novo** \> **Guia** para adicionar um novo controle que é chamado **FormTabControl1**.
4. No designer de formulário, selecione **FormTabControl1**.
5. Clique com o botão direito do mouse e depois selecione **Nova página de guia** para adicionar uma nova página de guia.
6. Renomeie a página de guia para algo significativo, como **Espaço de trabalho**.
7. No designer de formulário, selecione **FormTabControl1**.
8. Clique com o botão direito do mouse e depois selecione **Nova página de guia**.
9. Renomeie a página de guia para algo significativo, como **Análise**.
10. No designer de formulário, selecione **Análise (Página da Guia)**.
11. Defina a propriedade **Legenda** como **Analytics**, e defina a propriedade **Declaração automática** como **Sim**.
12. Clique com o botão direito do mouse e depois selecione **Novo** \> **Grupo** para adicionar um novo controle de grupo de formulários.
13. Renomeie o grupo do formulários para algo significativo, como **powerBIReportGroup**.
14. No designer de formulário, selecione **PanoramaBody (Guia)** e depois arraste o controle até a guia **Espaço de trabalho**.
15. Na definição de design, selecione o elemento superior que é rotulado **Design | Pattern: Workspace Operational**.
16. Clique com o botão direito do mouse e depois selecione **Remover padrão**.
17. Clique com o botão direito do mouse e depois selecione **Adicionar padrão** \> **Espaço de trabalho com guias**.
18. Execute uma compilação para verificar suas alterações.

A ilustração a seguir mostra a aparência do design após a aplicação dessas alterações.

![FMClerkWorkspace após as alterações.](media/analytical-workspace-definition-after.png)

Agora que você já adicionou os controles de formulário que serão usados para incorporar o relatório de espaço de trabalho, é preciso definir o tamanho do controle pai para que ele acomode o layout. Por padrão, as páginas **Painel de filtros** e **Guia** estarão visíveis no relatório. No entanto, você pode alterar a visibilidade desses controles conforme apropriado para o consumidor alvo do relatório.

> [!NOTE]
> Para espaços de trabalho incorporados, recomendamos o uso de extensões para ocultar as páginas **Painel de filtros** e **Guia** para que haja consistência.

Agora você já concluiu a tarefa de estender a definição de formulário de aplicativo. Para obter mais informações sobre como usar extensões para fazer personalizações, consulte [Personalizar por meio de extensão e sobreposição](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Adicionar a lógica comercial X++ para incorporar um controle mais amplo
Siga essas etapas para adicionar a lógica comercial que inicializa o controle de relatório mais amplo incorporado no espaço de trabalho **Gerenciamento de reservas**.

1. Abra o designer de formulário **FMClerkWorkspace** para estender a definição de design.
2. Pressione F7 para acessar o código por trás da definição de código.
3. Adicione o código X++ a seguir.

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Execute uma compilação para verificar suas alterações.

Agora você já concluiu a tarefa de adicionar a lógica comercial para inicializar o controle de relatório incorporado mais amplo. A ilustração a seguir mostra a aparência do espaço de trabalho após a aplicação dessas alterações.

![Relatório incorporado no espaço de trabalho.](media/analytical-workspace-final.png)

> [!NOTE]
> É possível acessar a exibição operacional existente usando as guias de espaço de trabalho abaixo do título da página.

## <a name="reference"></a>Demonstrativo

### <a name="pbireporthelperinitializereportcontrol-method"></a>Método PBIReportHelper.initializeReportControl
Esta seção fornece informações sobre a classe auxiliar usada para incorporar um relatório do Power BI (recurso .pbix) em um controle de grupo de formulários.

#### <a name="syntax"></a>Sintaxe
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Parâmetros

| Nome             | descrição                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | O nome do recurso .pbix.                                                                              |
| formGroupControl | O controle de grupo de formulário ao qual aplicar o controle de relatório do Power BI.                                              |
| defaultPageName  | O nome de página padrão.                                                                                       |
| showFilterPane   | Um valor booliano que indica se o painel de filtros deve ser mostrado (**true**) ou ocultado (**false**).     |
| showNavPane      | Um valor booliano que indica se o painel de navegação deve ser mostrado (**true**) ou ocultado (**false**). |
| defaultFilters   | Os filtros padrão para o relatório do Power BI.                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
