---
title: Criar um formato de ER para gerar um relatório no formato Excel com imagens incorporadas em cabeçalhos ou rodapés de página
description: Este tópico explica como usar relatórios eletrônicos (ER) para gerar documentos comerciais que têm imagens e formas incorporadas em cabeçalhos ou rodapés de página.
author: NickSelin
ms.date: 06/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e67c10ecb9f297d1855a55431cd07c53ee87d40a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361370"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Criar um formato de ER para gerar um relatório no formato Excel com imagens incorporadas em cabeçalhos ou rodapés de página

[!include[banner](../includes/banner.md)]

Este tópico explica como um usuário que tem a função de Administrador do Sistema ou de Consultor Funcional de Relatório Eletrônico pode executar estas tarefas:

- Configurar parâmetros para a [estrutura de relatórios eletrônicos (ER)](general-electronic-reporting.md).
- [Configurações](general-electronic-reporting.md#Configuration) de importação de ER que são [fornecidas](general-electronic-reporting.md#Provider) pela Microsoft e usadas para gerar [faturas de texto livre](../../../finance/accounts-receivable/create-free-text-invoice-new.md), com base em um [modelo](er-fillable-excel.md#excel-file-component) no formato Microsoft Excel.
- Crie uma versão [personalizada (derivada)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) de uma configuração do formato de ER padrão fornecida pela Microsoft.
- Modifique a configuração de formato ER personalizado para que ela gere um relatório de fatura de texto livre que tenha uma imagem de logotipo da empresa no rodapé.

Os procedimentos deste tópico podem ser concluídos na empresa **USMF**. Nenhum código é necessário. Antes de começar, baixe e salve o seguinte arquivo:

| descrição        | Nome do arquivo |
|--------------------|-----------|
| Imagem do logotipo da empresa | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Conteúdo

- [Configurar a entidade legal](#ConfigureLegalEntity)
- [Configurar a estrutura de ER](#ConfigureFramework)

    - [Configurar parâmetros de ER](#ConfigureParameters)
    - [Ativar um provedor de configuração de ER](#ActivateProvider)

        - [Examinar a lista de provedores de configuração de ER](#ReviewProvidersList)
        - [Adicionar um novo provedor de configuração de ER](#AddProvider)
        - [Ativar o novo provedor de configuração de ER](#ActivateAddedProvider)

- [Importar as configurações do formato de ER padrão](#ImportERSolution1)

    - [Importar as configurações de ER padrão](#ImportERFormat)
    - [Examinar as configurações de ER importadas](#ReviewImportedERSolution)

- [Imprimir uma fatura de texto livre usando o formato de ER padrão](#PrintInvoice1)

    - [Configurar gerenciamento de impressão](#ConfigurePrintManagement1)
    - [Imprimir uma fatura de texto livre](#ProcessInvoice1)

- [Personalizar o formato de ER padrão](#CustomizeProvidedFormat)

    - [Criar uma formato personalizado](#DeriveProvidedFormat)
    - [Editar o formato personalizado](#ConfigureDerivedFormat)
    - [Marcar o formato personalizado como executável](#MarkFormatRunnable)

- [Imprimir uma fatura de texto livre usando o formato de ER personalizado](#PrintInvoice2)

    - [Configurar gerenciamento de impressão](#ConfigurePrintManagement2)
    - [Imprimir uma fatura de texto livre](#ProcessInvoice2)

- [Recursos adicionais](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Configurar a entidade legal

1. Vá para **Administração da organização** \> **Organizações** \> **Entidades legais**.
2. Na página **Entidades legais**, na Guia Rápida **Imagem do logotipo da empresa de relatório**, selecione **Alterar**.
3. Na caixa de diálogo **Selecionar arquivo de imagem a ser carregado**, selecione **Pesquisar** e selecione o arquivo **Logotipo da empresa.png** que você baixou anteriormente.
4. Selecione **Salvar** e feche a página **Entidades legais**.

![Imagem do logotipo da empresa selecionada na página Entidades legais.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurar a estrutura de ER

Como usuário na função de Consultor Funcional de Relatório Eletrônico, você deve configurar o conjunto mínimo de parâmetros de ER antes de começar a usar a estrutura de ER para criar uma versão personalizada de um formato de ER padrão.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar parâmetros de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.
4. Na guia **Anexos**, defina os seguintes parâmetros:

    - No campo **Configurações**, selecione o tipo **Arquivo** para a empresa **USMF**.
    - Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.

Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Ativar um provedor de configuração de ER

Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER. O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade. Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.

> [!NOTE]
> Somente o proprietário de uma configuração ER pode editá-la. Para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Examinar a lista de provedores de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos. Examine o conteúdo dessa página. Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Adicionar um novo provedor de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Provedores de configuração**, selecione **Novo**.
4. No campo **Nome**, insira **Litware, Ltda.**
5. No campo **Endereço na Internet**, insira `https://www.litware.com`.
6. Selecione **Salvar**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Ativar o novo provedor de configuração de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.

Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importar as configurações do formato de ER padrão

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importar as configurações de ER padrão

Para adicionar as configurações de ER padrão à instância atual do Dynamics 365 Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER configurado para essa instância.

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor **Microsoft**.
3. Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**. Se você precisar de autorização para se conectar ao [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md), siga as instruções de autorização.
4. Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **Fatura de texto livre (Excel)**.
5. Na FastTab **Versões**, selecione a versão mais recente (por exemplo, **240.112**) da configuração do formato de ER selecionada.
6. Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.

![Importar as configurações de ER padrão na página do Repositório de configuração.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Examinar as configurações de ER importadas

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura**.
4. Além do formato de ER selecionado da **Fatura de texto livro (Excel)**, outras configurações de ER necessárias foram importadas. Verifique se as seguintes configurações de ER estão disponíveis na árvore de configuração:

    - **Modelo de fatura** – Esta configuração contém o componente de ER [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) que representa a estrutura de dados do domínio corporativo de faturamento.
    - **Mapeamento de modelos de fatura** – Esta configuração contém o componente de ER [mapeamento de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) que descreve como o modelo de dados é preenchido com dados de aplicativos em tempo de execução.
    - **Fatura de texto livre (Excel)** – Esta configuração contém os componentes de ER de [formato](general-electronic-reporting.md#FormatComponentOutbound) e de mapeamento de formato. O componente de formato especifica o layout do relatório, com base em um modelo no formato Excel. O componente mapeamento de formato contém a fonte de dados do modelo e especifica como essa fonte de dados é usada para preencher o layout do relatório no runtime.

![Configurações de ER importadas na página Configurações.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Imprimir uma fatura de texto livre usando o formato de ER padrão

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Configurar gerenciamento de impressão

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, marque a fatura **FTI-00000002** e, no painel de ação, na guia **Fatura**, no grupo **Gerenciamento de impressão**, selecione **Gerenciamento de impressão**.
3. Na página **Configuração de gerenciamento de impressão**, na árvore à esquerda, expanda **Módulo - Contas a receber \> Documentos \> Fatura de texto livre** e selecione o item **Original \<Default\>**.
4. No campo **Formato do relatório**, selecione **Fatura de texto livre (Excel)**.
5. Selecione a tecla **Esc** para sair da página **Configuração de gerenciamento de impressão** e retorne à página **Fatura de texto livre**.

![Configurações de gerenciamento de impressão para uma fatura de texto livre no formato de ER padrão na página Configuração de gerenciamento de impressão.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Imprimir uma fatura de texto livre

1. Na página **Fatura de texto livre**, certifique-se de que a fatura **FTI-00000002** ainda esteja selecionada e, no Painel de Ações, na guia **Fatura**, no grupo **Documento**, selecione **Imprimir** \> **Selecionado**.
2. Baixe a fatura gerada no formato Excel e abra-a para visualização.
3. Observe que, de acordo com a estrutura do modelo Excel para o formato de ER fornecido, o rodapé da página da fatura gerada contém informações sobre o número da página atual e o número total de páginas no relatório.

![Fatura de texto livre gerada.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizar o formato de ER padrão

No exemplo desta seção, você pode usar as configurações de ER fornecidas pela Microsoft para gerar uma fatura de texto livre no formato Excel. No entanto, você deve adicionar uma personalização para colocar uma imagem de logotipo da empresa no rodapé da página das faturas geradas.

Neste caso, como representante da Litware, Ltda., você deve criar (derivar) uma nova configuração do formato de ER que é baseada na configuração **Fatura de texto livre (Excel)** fornecida pela Microsoft.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Criar uma formato personalizado

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** e selecione **Fatura de texto livre (Excel)**. A Litware, Ltda. usará a versão importada (por exemplo, **240.112**) desta configuração do formato de ER como base para a versão personalizada.
3. Selecione **Criar configuração** para abrir a caixa de diálogo suspensa. Use esta caixa de diálogo para criar uma nova configuração para um formato de pagamento personalizado.
4. No grupo de campos **Novo**, selecione a opção **Derivar de Nome: Fatura de texto livre (Excel), Microsoft**.
5. No campo **Nome**, digite **Fatura de texto livre (Excel) personalizada**.
6. Selecione **Criar configuração**.

![Criação de uma configuração para um formato de pagamento personalizado na caixa de diálogo Criar configuração.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

A versão 240.112.1 da configuração de formato de ER **Fatura de texto livre (Excel) personalizada** é criada. Essa versão tem um [status](general-electronic-reporting.md#component-versioning) de **Rascunho** e pode ser editada. O conteúdo atual do formato de ER personalizado corresponde ao conteúdo do formato fornecido pela Microsoft.

![Nova versão da configuração de formato de ER criada na página Configurações.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Editar o formato personalizado

Configure seu formato personalizado para que a imagem do logotipo de uma empresa seja colocada no rodapé em todas as páginas do relatório.

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **Fatura de texto livre (Excel) personalizada**.
3. Na FastTab **Versões**, selecione a versão **240.112.1** da configuração selecionada.
4. Selecione **Designer**.
5. Na página **Designer de formato**, selecione **Mostrar detalhes** para ver mais informações sobre os elementos de formato.
6. Expanda e examine os seguintes elementos:

    - O elemento **Fatura de texto livre** do tipo **Excel**. Esse elemento é usado para gerar uma fatura no formato de pasta de trabalho do Excel.
    - O elemento **Fatura de texto livre \\ Fatura** do tipo **Folha**. Esse elemento é usado para gerar uma planilha da pasta de trabalho do Excel gerada.
    - O elemento **Fatura de texto livre \\ Fatura \\ Rodapé** do tipo **Rodapé**. Esse elemento é usado para preencher um rodapé de fatura.

7. Selecione o elemento **Fatura de texto livre \\ Fatura \\ Rodapé**.

    ![Elemento rodapé no designer de operações de ER.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Cada rodapé de página de uma fatura gerada contém informações sobre o número de página atual e o número total de páginas do relatório. Como você pode ver, o elemento **Fatura de texto livre \\ Fatura \\ Rodapé** não contém qualquer elemento filho. Portanto, o modelo do Excel que está sendo usado é configurado para mostrar detalhes de paginação no centro de todos os rodapés do relatório.

8. Selecione **Adicionar** e, depois, selecione o tipo **Excel \\ Imagem** do elemento de formato que você está adicionando:

    1. No campo **Alinhamento**, selecione **Direita**.
    2. No campo **Dimensionar a altura**, selecione **Relativo**.
    3. No campo **Dimensionar em porcentagem**, digite **70**.
    4. Selecione **OK**.

        > [!NOTE]
        > O elemento **Excel \\ Imagem** é usado para adicionar uma imagem de logotipo da empresa e alinhá-la no lado direito do rodapé da página.

    ![Propriedades do elemento Imagem na caixa de diálogo Propriedades do componente.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. Na árvore de estrutura de formato à esquerda, selecione o elemento **Imagem** que você acabou de adicionar e, na guia **Mapeamento**, expanda a fonte de dados **Modelo**.
10. Expanda **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo** e selecione o campo de fonte de dados **model.InvoiceBase.CompanyInfo.Logo**. O campo fonte de dados do tipo [Contêiner](er-formula-supported-data-types-composite.md#container) exibe a imagem do logotipo da empresa como conteúdo de mídia.
11. Selecione **Associar**. O elemento de formato **Imagem** agora está associado ao campo fonte de dados **model.InvoiceBase.CompanyInfo.Logo**. Portanto, no tempo de execução, a imagem do logotipo da empresa será colocada no rodapé das faturas geradas.

    ![O elemento de formato Imagem agora está associado ao campo fonte de dados model.InvoiceBase.CompanyInfo.Logo no Designer de operações de ER.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Selecione **Salvar** e feche a página **Designer**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marcar o formato personalizado como executável

Como a primeira versão do formato personalizado foi criada e tem o status de **Rascunho**, você pode executar o formato para fins de teste. Para executar o relatório, processe um pagamento de fornecedor usando o método de pagamento que se refere ao seu formato de ER personalizado. Por padrão, quando você chama um formato de ER no aplicativo, somente as versões que têm o status **Concluída** ou **Compartilhada** são [consideradas](general-electronic-reporting.md#component-versioning). Esse comportamento ajuda a impedir que formatos de ER com designs não concluídos sejam utilizados. No entanto, para as execuções de teste, você pode forçar o aplicativo a usar a versão do seu formato de ER que tem o status de **Rascunho**. Dessa forma, é possível ajustar a versão do formato atual se modificações forem necessárias. Para obter mais informações, consulte [Aplicabilidade](electronic-reporting-destinations.md#applicability).

Para usar a versão de rascunho de um formato de ER, você deve marcar o formato de ER explicitamente.

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.
4. Selecione **Editar** para tornar a página atual editável e depois, na árvore de configuração no painel esquerdo, selecione **Fatura de texto livre (Excel) personalizada**.
5. Defina a opção **Executar Rascunho** como **Sim**.

![Marcar o formato personalizado como executável na página Configurações.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Imprimir uma fatura de texto livre usando o formato de ER personalizado

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Configurar gerenciamento de impressão

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, marque a fatura **FTI-00000002** e, no painel de ação, na guia **Fatura**, no grupo **Gerenciamento de impressão**, selecione **Gerenciamento de impressão**.
3. Na página **Configuração de gerenciamento de impressão**, na árvore à esquerda, expanda **Módulo - contas a receber** \> **Documentos** \> **Fatura de texto livre** e selecione o item **Original** **\<Default\>**.
4. No campo **Formato do relatório**, selecione **Fatura de texto livre (Excel) personalizada**.
5. Selecione **Esc** para sair da página **Configuração de gerenciamento de impressão** e retorne à página **Fatura de texto livre**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Imprimir uma fatura de texto livre

1. Na página **Fatura de texto livre**, certifique-se de que a fatura **FTI-00000002** ainda esteja selecionada e, no Painel de Ações, na guia **Fatura**, no grupo **Documento**, selecione **Imprimir** \> **Selecionado**.
2. Baixe a fatura gerada no formato Excel e abra-a para visualização.
3. Observe que, de acordo com a estrutura do formato de ER personalizado, o rodapé de página da fatura gerada contém uma imagem do logotipo da empresa, além de informações sobre a paginação do relatório.

![Fatura de texto livre gerada com uma imagem de logotipo da empresa no rodapé da página.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Recursos adicionais

- [Criar uma configuração para gerar documentos no formato Excel](er-fillable-excel.md)
- [Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md)
