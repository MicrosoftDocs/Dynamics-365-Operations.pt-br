---
title: Personalizar configurações do relatório eletrônico para gerar um documento eletrônico
description: Este artigo explica como personalizar as configurações do relatório eletrônico (ER) fornecido pela Microsoft usadas para gerar um documento eletrônico personalizado.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30ef9a0fa9b61b1e2016f85407ec0ec8fb70a6c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854688"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Personalizar configurações do relatório eletrônico para gerar um documento eletrônico

[!include[banner](../includes/banner.md)]

A [estrutura do relatório eletrônico (ER)](general-electronic-reporting.md) permite carregar as [configurações](general-electronic-reporting.md#Configuration) do ER que a Microsoft fornece na instância do Microsoft Dynamics 365 Finance. Dessa forma, as configurações fornecidas pela Microsoft podem servir como a solução de ER usada para gerar faturas eletrônicas de clientes. É possível usar essa solução de ER para configurar a sua solução de ER para acessar os campos do banco de dados personalizado e gerar faturas eletrônicas de acordo com suas necessidades específicas, sem precisar editar o código-fonte.

## <a name="overview"></a>Visão geral

No exemplo deste artigo, é necessário especificar um código de identificação de imposto federal como um novo atributo personalizado de cada cliente que você faturar eletronicamente. Portanto, é necessário personalizar a estrutura da fatura usada atualmente, adicionando um novo item que deve ser preenchido com o código de imposto em cada fatura eletrônica gerada.

Os procedimentos descritos neste artigo explicam como um usuário que tem a função de Administrador do Sistema, Desenvolvedor de Relatórios Eletrônicos ou de Consultor Funcional de Relatório Eletrônico pode executar as seguintes tarefas na instância do Finance:

- [Configurar o conjunto mínimo de parâmetros de ER necessários para iniciar o uso da estrutura de ER](#ConfigureER).
- [Importar as versões iniciais das configurações de ER padrão fornecidas para gerar faturas eletrônicas](#ImportERConfigurations1).
- [Configurar os parâmetros de Contas a receber para iniciar o uso de configurações de ER padrão](#ConfigureAR1).
- [Configurar os parâmetros da entidade legal para faturar clientes](#ConfigureLE).
- [Preparar um registro de cliente para faturamento eletrônico](#ConfigureCustomer1).
- [Adicionar, lançar e enviar uma fatura de cliente usando as configurações de ER padrão](#ProcessInvoice1).
- [Adicionar um campo de banco de dados personalizado para gerenciar um código de identificação de imposto federal para clientes](#AddCustomField).
- [Atualizar os metadados de ER para habilitar alterações no banco de dados para o designer de mapeamento de modelo de ER](#RefreshERMetadata).
- [Criar configurações de ER personalizadas para gerar faturas eletrônicas que contenham o novo código de imposto](#DesignCustomERConfigurations).
- [Configurar os parâmetros de Contas a receber para iniciar o uso de configurações de ER personalizadas](#ConfigureAR2).
- [Atualizar um registro de cliente para faturamento eletrônico](#ConfigureCustomer2).
- [Adicionar, lançar e enviar uma fatura de cliente usando as configurações de ER personalizadas](#ProcessInvoice2).
- [Importar novas as versões das configurações padrão de ER fornecidas para gerar faturas eletrônicas](#ImportERConfigurations2).
- [Adotar as alterações das novas versões das configurações de ER padrão nas configurações de ER personalizadas](#RebaseCustomERConfigurations).
- [Adicionar, lançar e enviar uma fatura de cliente usando as novas versões das configurações de ER personalizadas](#ProcessInvoice3).

Todos esses procedimentos podem ser concluídos na empresa **DEMF**.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Configurar a estrutura de ER

Como usuário na função de Consultor Funcional de Relatório Eletrônico ou Desenvolvedor de Relatório Eletrônico, é necessário configurar o conjunto mínimo de parâmetros de ER. Em seguida, você pode começar a usar a estrutura de ER para criar versões personalizadas das configurações padrão da solução ER usada para gerar faturas eletrônicas.

### <a name="configure-er-parameters"></a>Configurar parâmetros de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na página **Parâmetros de relatório eletrônico**, na guia **Geral**, defina a opção **Habilitar modo de design** como **Sim**.
4. Na guia **Anexos**, no campo **Configurações**, selecione **Arquivo**.
5. Nos campos **Arquivo de trabalho**, **Temporário**, **Linha de base** e **Outros**, selecione o tipo **Arquivo**.

Para obter mais informações sobre parâmetros de ER, consulte [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Ativar um provedor de configuração de ER

Toda configuração de ER adicionada é marcada como pertencente a um provedor de configuração de ER. O provedor de configuração de ER ativado no espaço de trabalho **Relatório eletrônico** é usado para essa finalidade. Por isso você deve ativar um provedor de configuração de ER no espaço de trabalho **Relatório eletrônico** antes de começar a adicionar ou editar configurações de ER.

> [!NOTE]
> Somente o proprietário de uma configuração de ER pode editá-la. Assim, para que uma configuração de ER possa ser editada, o provedor de configuração de ER apropriado deve estar ativado no espaço de trabalho **Relatório eletrônico**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Examinar a lista de provedores de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Tabela de provedores de configuração**, cada registro de provedor tem um nome e uma URL exclusivos. Examine o conteúdo dessa página. Se já existir um registro para **Litware, Ltda.** (`https://www.litware.com`), ignore o próximo procedimento, [Adicionar um novo provedor de configuração de ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Adicionar um novo provedor de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Links relacionados**, selecione **Provedores de configuração**.
3. Na página **Provedores de configuração**, selecione **Novo**.
4. No campo **Nome**, insira **Litware, Ltda.**
5. No campo **Endereço na Internet**, insira `https://www.litware.com`.
6. Selecione **Salvar**.

#### <a name="activate-an-er-configuration-provider"></a>Ativar um provedor de configuração de ER

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Provedores de configuração**, selecione o bloco **Litware, Ltda.** e, depois, **Definir como ativo**.

Para obter mais informações sobre provedores de configuração de ER, consulte [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importar as versões iniciais das configurações de ER padrão

Para adicionar as configurações de ER padrão à instância atual do Finance, você deve importá-las do [repositório](general-electronic-reporting.md#Repository) de ER configurado para essa instância.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.
3. Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**. Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.
4. Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **Fatura de Venda Peppol**.
5. Na Guia Rápida **Versões**, selecione a versão **11.2.2**.
6. Selecione **Importar** para baixar a versão selecionada do repositório Global.

![Página do repositório de configuração.](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Se você tiver problemas para acessar o [repositório global](er-download-configurations-global-repo.md), poderá [baixar configurações](download-electronic-reporting-configuration-lcs.md) do Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a>Examinar as configurações de ER importadas

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Blueprint de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, expanda a FastTab **Componentes de configuração**.
4. Na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** e depois **Fatura de Venda UBL**.

Observe que além do formato de ER selecionado da **Fatura de Venda Peppol**, outras configurações de ER necessárias foram importadas. Como novas versões de configurações de ER são publicadas constantemente no repositório Global e LCS para manter as correspondentes soluções em conformidade com novos requisitos, as versões mais recentes da configuração necessária do modelo de dados e as configurações do mapeamento de modelos foram importadas.

![Página Configurações.](./media/er-quick-start3-imported-solution1a.png)

Para simular o estado em que as configurações de ER na atual instância do Finance estariam se você importasse a versão **11.2.2** do formato de ER da **Fatura de Venda Peppol** no passado (por exemplo, 7 de agosto de 2019), siga estas etapas.

- No Painel de Ações, selecione **Excluir** para excluir todas as configurações de ER publicadas após 7 de agosto de 2019. As únicas configurações de **Modelo de fatura**, **Mapeamento de modelo de fatura** (inicialmente chamado de **Mapeamento de modelo de fatura de cliente**), **Fatura de Venda UBL** e **Fatura de Venda Peppol** devem ser mantidas.
- Para as demais configurações de ER, na FastTab **Versões**, selecione **Excluir** para excluir todas as versões de configurações de ER publicadas após 7 de agosto de 2019.

Em seguida, verifique se as seguintes configurações estão disponíveis na árvore de configuração:

- Configuração do modelo de dados de ER do **Modelo de fatura** (inicialmente chamado de **Modelo de fatura de cliente**):

    - A versão 11 contém a versão 10 do componente de ER do modelo de dados que representa a estrutura de dados do domínio corporativo de faturamento. Essa configuração de ER foi importada como um ancestral do formato de ER da **Fatura de Venda Peppol** selecionada para importação.
    - A versão 50 contém a versão 31 do componente de ER do modelo de dados. Esta configuração de ER foi importada como ancestral da versão de 7 de agosto de 2019 da configuração do mapeamento de modelo de ER do **Mapeamento de modelo de fatura**.

    ![Configuração do modelo de dados de ER do modelo de fatura na página Configurações.](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Caso não veja a versão 50 deste modelo de dados, abra o repositório Global e importe a versão 50.19 da configuração de ER do **Mapeamento de modelo de fatura**.

- Configuração do mapeamento de modelo de ER do **Mapeamento de modelo de fatura** (inicialmente chamado de **Mapeamento de modelo de fatura de cliente**):

    - A versão 50.19 foi importada como a implementação mais recente da versão 50 da configuração do modelo de dados de ER do **Modelo de fatura**. Ela contém dois componentes de ER de mapeamento de modelo que descrevem como o modelo de dados é preenchido com os dados de aplicativos no runtime.

    ![Configuração do mapeamento de modelo de ER do mapeamento de modelo de fatura na página Configurações.](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Caso não veja a versão 50.19 deste mapeamento de modelo, abra o repositório Global e importe a versão 50.19 da configuração de ER do **Mapeamento de modelo de fatura**.

- Configuração de formato de ER de **Fatura de venda UBL**:

    - A versão 11.2 contém os componentes de ER formato e mapeamento de formato. O componente de formato especifica o layout do relatório. O componente mapeamento de formato contém a fonte de dados do modelo e especifica como essa fonte de dados é usada para preencher o layout do relatório no runtime. Este formato de ER foi configurado para gerar faturas eletrônicas no formato Universal Business Language (UBL). Ele foi importado como pai do formato de ER **Fatura de Venda Peppol** selecionado para importação.

- Configuração de formato de ER de **Fatura de Venda Peppol**:

    - A versão 11.2.2 contém os componentes de ER do formato e de mapeamento de formato que foram configurados para gerar faturas eletrônicas no formato Pan-European Public Procurement OnLine (PEPPOL).

    ![Configuração de formato de ER da fatura de venda Peppol na página Configurações.](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Configurar os Parâmetros de contas a receber

1. Acesse **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber**.
2. Na guia **Documentos eletrônicos**, na FastTab **Relatório eletrônico**, no campo **Vendas e fatura de texto livre**, selecione **Fatura de Venda Peppol**.
3. Selecione **Salvar**.

![Guia de documentos eletrônicos na página Parâmetros de contas a receber.](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Configurar os parâmetros da entidade legal

1. Acesse **Administração da organização** \> **Organizações** \> **Entidades legais**.
2. Para a empresa **DEMF** selecionada, na FastTab **Informações de conta bancária**, no campo **Número do banco**, insira **1234**.
3. Selecione **Salvar**.
4. Feche a página **Entidades legais**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Preparar um registro de cliente

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na página **Todos os clientes**, selecione o link de conta de cliente **DE-014**.

### <a name="add-a-customer-contact"></a>Adicionar um contato do cliente

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. No Painel de Ações, na guia **Cliente**, no grupo **Contas**, selecione **Contatos**.
3. Selecione **Adicionar contatos**.
4. Na página **Contatos**, no campo **Nome**, abra a pesquisa, selecione **Adam Carter** e depois **Selecionar** para fechar a pesquisa.
5. Selecione **Salvar**.
6. Feche a página **Contatos**.

### <a name="define-a-primary-contact"></a>Definir um contato principal

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na FastTab **Dados demográficos de vendas**, no campo **Contato principal**, selecione **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Definir a opção de faturamento eletrônico

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na FastTab **Fatura e entrega**, defina a opção **Fatura eletrônica** como **Sim**.
3. Selecione **Salvar**.
4. Feche a página **Todos os clientes**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Processar uma fatura de cliente usando as configurações de ER padrão

Agora você pode usar as configurações de ER padrão importadas para enviar eletronicamente uma fatura de texto livre para um cliente.

### <a name="add-a-new-invoice"></a>Adicionar uma nova fatura

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, selecione **Novo**.
3. Na FastTab **Cabeçalho de fatura de texto livre**, no campo **Conta de cliente**, selecione **DE-014**.
4. Na FastTab **Linhas da fatura**, uma linha da fatura será adicionada automaticamente. Nessa linha, defina os seguintes campos:

    - No campo **Descrição**, insira **Notebook**.
    - No campo **Conta principal**, selecione **401100**.
    - No campo **Preço unitário**, insira **1000**.

5. Selecione **Salvar**.

![Página de fatura de texto livre.](./media/er-quick-start3-add-invoice.png)

Para obter mais informações, consulte [Criar uma fatura de texto livre](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Lançar uma nova fatura

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, no Painel de Ações, selecione **Lançar**.
3. Na caixa de diálogo **Lançar fatura de texto livre**, selecione **OK**.

![Página de detalhes da fatura de texto livre.](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Enviar uma fatura lançada

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, no Painel de Ações, no grupo **Documento**, selecione **Enviar** \> **Original**.

    ![Visualização da fatura original.](./media/er-quick-start3-send-invoice.png)

3. Feche a página **Fatura de texto livre**.

### <a name="analyze-a-generated-e-invoice"></a>Analisar uma fatura eletrônica gerada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos**.
2. Na página **Trabalhos de relatórios eletrônicos**, selecione o registro inicial que contém a descrição da tarefa **Enviar XML da fatura eletrônica**.
3. Selecione **Mostrar arquivos** para acessar a lista de arquivos gerados.

    ![Página de trabalhos de relatório eletrônico.](./media/er-quick-start3-jobs-list.png)

4. Selecione **Abrir** para baixar o arquivo XML da fatura eletrônica gerada.
5. Analise o arquivo XML da fatura eletrônica. Observe que o esquema de impostos do cliente é atualmente representado pelos atributos XML **schemeID** e **schemeAgencyID**. Observe também que o elemento XML **cbc:CustomizationID** atualmente contém o seguinte texto: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Visualização do arquivo XML da fatura eletrônica gerada.](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Adicionar campo de banco de dados personalizado

É possível usar o recurso [Campo personalizado](../../fin-ops/get-started/user-defined-fields.md) para fazer a seguinte personalização na atual instância do Finance:

- Personalize a estrutura do banco de dados adicionando um novo campo de banco de dados personalizado que armazene um código de identificação de imposto federal para cada cliente.
- Personalize a página **Cliente** adicionando um novo campo de entrada de dados que possa ser usado para inserir um valor de código de imposto no novo campo de banco de dados personalizado.

Siga estas etapas para personalizar.

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na página **Todos os clientes**, selecione o link de conta de cliente **DE-014**.
3. Na FastTab **Geral**, clique com o botão direito em qualquer área em branco no campo **Idioma** e selecione **Personalizar: UpperGroup**.

    O conteúdo da FastTab **Geral** é destacado e um menu **Personalizar** é exibido.

4. No menu **Personalizar**, selecione **Adicionar um campo**.
5. Na caixa de diálogo **Adicionar colunas**, selecione **Criar campo**.
6. Na caixa de diálogo **Criar campo**, no campo **Nome da tabela**, selecione **Clientes**.
7. No campo **Prefixo do nome**, insira **FederalTaxID**.

    > [!NOTE]
    > O nome inteiro do campo foi definido automaticamente como **FederalTaxID\_Custom**.

8. No campo **Rótulo**, insira **ID de Imposto Federal**.
9. No campo **Tipo**, selecione **Texto**.
10. No campo **Comprimento**, insira **20**.
11. Selecione **Salvar**.
12. Na caixa de mensagem exibida, selecione **Sim** para confirmar que deseja criar uma nova entrada do campo **FederalTaxID** para a tabela **Clientes**.
13. Selecione **Inserir** para <a name="insert_custom_field"></a>adicionar o campo **FederalTaxID\_Custom** à página atual.

    ![Página Todos os clientes.](./media/er-quick-start3-create-new-field.gif)

14. Feche a página **Todos os clientes**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Atualizar os metadados de ER

É necessário atualizar os metadados de ER para tornar o campo personalizado adicionado [visível](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) no designer de mapeamento de modelo de ER.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Recriar referências de tabela**.
2. Na caixa de diálogo **Atualizar modelo de dados**, selecione **OK**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Criar configurações de ER personalizadas

É possível usar as configurações de ER fornecidas pela Microsoft para criar suas configurações de ER personalizadas para gerar faturas eletrônicas que contenham o novo código de imposto.

### <a name="customize-the-data-model-configuration"></a>Personalizar a configuração do modelo de dados

Como usuário na função de Consultor Funcional de Relatório Eletrônico, é possível criar seu modelo de dados de ER personalizado.

#### <a name="add-a-custom-data-model-configuration"></a>Adicionar uma configuração de modelo de dados personalizada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Modelo de fatura personalizado**.
3. No Painel de Ações, selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, no campo **Novo**, selecione **Derivar do Nome: Modelo de fatura de cliente, Microsoft** para indicar que a nova configuração do modelo de dados de ER personalizada deve ser baseada na configuração do modelo de dados de ER.
5. No campo **Nome**, insira **Modelo de fatura (Litware)**.
6. Selecione **Criar configuração** para adicionar a nova configuração de ER.

Agora é possível usar o designer de modelo de dados de ER para editar a versão 50.1 da configuração de ER do **Modelo de fatura (Litware)** no [status](general-electronic-reporting.md#component-versioning) de **Rascunho**.

![Versão 50.1 da configuração do ER na página Configurações.](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Configurar um modelo de dados personalizado

É necessário modificar o modelo de dados personalizado adicionando um novo campo para fornecer o valor de um código de identificação de imposto federal. Esse código faz parte dos dados do cliente para todos os formatos de ER que usarão esse modelo de dados como fonte de dados.

1. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Modelo de fatura (Litware)**.
2. Na FastTab **Versões**, selecione a versão **50.1** da configuração do modelo de dados de ER selecionado no status de **Rascunho**.
3. No Painel de Ações, selecione **Designer** para a versão de configuração selecionada.
4. Na página **Designer do modelo de dados**, na árvore do modelo de dados, selecione **Informações do cliente (Cliente)**.
5. Selecione **Novo**.
6. Na caixa suspensa, no campo **Novo nó como um**, aceite o valor padrão, **Filho de um nó ativo**.
7. No campo **Nome**, insira **FederalTaxID\_Litware**.
8. No campo **Tipo de item**, aceite o valor padrão, **String**.
9. Selecione **Adicionar** e, depois, **Salvar**.

    ![Página do designer de modelo de dados.](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > Os campos **Rótulo** e **Descrição** descrevem a finalidade do novo campo. É possível preencher esses campos em vários idiomas. Para obter mais informações, consulte [Criar relatórios de vários idiomas no Relatório eletrônico](er-design-multilingual-reports.md).

10. Feche a página **Designer de modelo de dados**.

#### <a name="complete-a-custom-data-model-configuration"></a>Concluir uma configuração de modelo de dados personalizada

É necessário [concluir](general-electronic-reporting.md#component-versioning) seu trabalho com a versão 50.1 da sua configuração de modelo de dados de ER personalizada a fim de disponibilizá-lo para que outras configurações de ER personalizadas possam ser adicionadas.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** e selecione **Modelo de fatura (Litware)**.
3. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 50.1 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 50.2, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração do modelo de dados de ER personalizada.

![Versão 50.1 concluída na página Configurações.](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Personalizar a configuração do mapeamento de modelo

Como usuário na função de Desenvolvedor de Relatório Eletrônico, é possível criar seu mapeamento de modelo de ER personalizado.

#### <a name="add-a-custom-model-mapping-configuration"></a>Adicionar uma configuração de mapeamento de modelo personalizada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** e selecione **Modelo de fatura de cliente**.
3. No Painel de Ações, selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, no campo **Novo**, selecione **Derivar do Nome: Mapeamento de modelo de fatura de cliente, Microsoft** para indicar que a nova configuração de mapeamento de modelo de ER personalizada deve ser baseada na configuração de mapeamento de modelo de ER.
5. No campo **Nome**, insira **Mapeamento de modelo de fatura (Litware)**.
6. No campo **Modelo de destino**, selecione **Modelo de fatura (Litware)**.

    > [!IMPORTANT]
    > Essa etapa é muito importante. Se você a omitir, não será possível usar o modelo de dados personalizado no mapeamento do modelo configurado.

7. Selecione **Criar configuração** para adicionar a nova configuração de ER.

![Adicionar uma configuração do mapeamento de modelo de ER personalizado na página Configurações.](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Configurar um mapeamento do modelo personalizado

É necessário modificar o mapeamento de modelo personalizado e especificar como o campo **FederalTaxID\_Litware** do modelo de dados personalizado deve ser preenchido com os dados de aplicativos no runtime.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** \> **Mapeamento de modelo de fatura de cliente** e selecione **Mapeamento de modelo de fatura (Litware)**.
3. No Painel de Ação, selecione **Designer**.
4. Na página **Modelo para mapeamento de fonte de dados**, selecione o mapeamento da **Fatura de cliente**.

    ![Página Modelo para mapeamento de fonte de dados.](./media/er-quick-start3-select-customer-mapping.png)

5. Selecione **Designer**.
6. Na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, expanda a fonte de dados **CustInvoiceJour** que representa a tabela de aplicativos **CustInvoiceJour**.
7. Em **CustInvoiceJour**, expanda **Relações** para revisar a lista de relações do tipo muitos para um (N:1) para a tabela **CustInvoiceJour**.
8. Em **CustInvoiceJour** \> **Relações**, expanda **Clientes (CustTable)** para acessar os campos e as relações da tabela **Clientes (CustTable)**.
9. Selecione o campo da fonte de dados **FederalTaxID\_Custom** implementado [anteriormente](#insert_custom_field).
10. No painel **Modelo de dados**, expanda **Informações do cliente (Cliente)** e selecione o campo do modelo de dados **FederalTaxID\_Litware**.
11. Selecione **Associar**.

    ![Página do designer de mapeamento de modelo.](./media/er-quick-start3-customize-model-mapping.gif)

12. Selecione **Salvar**.
13. Feche a página **Designer de mapeamento de modelo**.
14. Feche a página **Modelo para mapeamento de fonte de dados**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Conclua uma configuração do mapeamento de modelo personalizada

É necessário [concluir](general-electronic-reporting.md#component-versioning) o trabalho com a versão 50.19.1 da configuração do mapeamento de modelo de ER personalizada para disponibilizá-lo para uso.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** \> **Mapeamento de modelo de fatura de cliente** e selecione **Mapeamento de modelo de fatura (Litware)**.
3. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 50.19.1 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 50.19.2, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração do mapeamento de modelo de ER personalizada.

![Versão 50.19.1 concluída na página Configurações.](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> A configuração compatível do [ciclo de vida](general-electronic-reporting-manage-configuration-lifecycle.md) não inclui o ciclo de vida de alterações no banco de dados. Se você exportar a versão 50.19.1 da configuração do **Mapeamento de modelo de fatura (Litware)** da instância atual do Finance e tentar importá-la para outra instância que não contenha o campo personalizado **FederalTaxID\_Custom** na tabela **CustTable**, ocorrerá uma exceção. A exceção informará que a configuração de ER importada não é compatível com os metadados da instância de destino do Finance.

### <a name="customize-the-format-configuration"></a>Personalizar a configuração de formato

Como usuário na função de Consultor Funcional de Relatório Eletrônico, é possível criar seu formato de ER personalizado.

#### <a name="add-a-custom-format-configuration"></a>Adicionar uma configuração de formato personalizada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** \> **Fatura de Venda UBL** e selecione **Modelo de fatura Peppol**.
3. No Painel de Ações, selecione **Criar configuração**.
4. Na caixa de diálogo suspensa, no campo **Novo**, selecione **Derivar do Nome: Fatura de Venda Peppol, Microsoft** para indicar que a nova configuração de formato de ER personalizada deve ser baseada na configuração de formato de ER.
5. No campo **Nome**, insira **Fatura de Venda Peppol (Litware)**.
6. No campo **Modelo de dados**, selecione **Modelo de fatura (Litware)** para usar o modelo de dados personalizado e componentes de mapeamento de modelo.

    > [!NOTE]
    > Essa etapa é muito importante. Se você a omitir, não será possível usar o modelo de dados personalizado no formato configurado.

7. No campo **Modelo de dados**, selecione a definição raiz **InvoiceCustomer**.
8. Selecione **Criar configuração** para adicionar a nova configuração de ER.

![Adicionar uma configuração de formato personalizada na página Configurações.](./media/er-quick-start3-adding-custom-format.png)

Agora é possível usar o designer de Operações de ER para editar a versão 11.2.2.1 da configuração de ER da **Fatura de Venda Peppol** no [status](general-electronic-reporting.md#component-versioning) de **Rascunho**.

![Versão 11.2.2.1 da configuração do ER na página Configurações.](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Configurar um formato personalizado

É necessário modificar o formato personalizado adicionando um novo elemento de formato para preencher o valor de um código de identificação de imposto federal de um cliente faturado.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** \> **Fatura de Venda UBL** \> **Fatura de Venda Peppol** e selecione **Fatura de Venda Peppol (Litware)**.
3. No Painel de Ação, selecione **Designer**.
4. Na árvore de formato, expanda **XMLHeader** \> **Fatura** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** e selecione **cbc:ID**.
5. Selecione **Adicionar** e depois **XML** \> **Atributo**.
6. Na caixa de diálogo **Propriedade do componente**, no campo **Nome**, insira **FederalTaxID**.
7. Selecione **OK** para adicionar um novo elemento de formato para criar um novo atributo XML **FederalTaxID** em um arquivo XML gerado.
8. Na árvore de formato, em **XMLHeader** \> **Fatura** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID**, selecione **FederalTaxID**.
9. Selecione **Mover para cima**.

![Novo elemento de formato na página Designer de formato.](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Configurar um mapeamento de formato personalizado

1. Na página **Designer de formato**, na guia **Mapeamento**, expanda a fonte de dados **Fatura** do tipo **Modelo**.
2. Em **Fatura**, expanda **Informações do cliente (Cliente)** e selecione **FederalTaxID\_Litware**.
3. Selecione **Associar**.

    ![Página do designer de formatos.](./media/er-quick-start3-customized-format-mapping.png)

4. Selecione a fonte de dados **Fatura** do tipo **Modelo** e, em seguida,**Editar**.
5. No campo **Versão**, selecione a versão **1** do modelo de dados personalizado e depois selecione **OK**.
6. Selecione **Salvar**.
7. Feche a página **Designer de formato**.

#### <a name="complete-a-custom-format-configuration"></a>Concluir uma configuração de formato personalizada

É necessário [concluir](general-electronic-reporting.md#component-versioning) o trabalho com a versão 11.2.2.1 da configuração de formato de ER personalizada para disponibilizá-lo para uso.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura de cliente** \> **Fatura de Venda UBL** \> **Fatura de Venda Peppol** e selecione **Fatura de Venda Peppol (Litware)**.
3. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 11.2.2.1 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 11.2.2.2, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração de formato de ER personalizada.

![Versão 11.2.2.1 concluída na página Configurações.](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Configurar os parâmetros de Contas a receber para iniciar o uso de configurações de ER personalizadas

1. Acesse **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber**.
2. Na guia **Documentos eletrônicos**, na FastTab **Relatório eletrônico**, no campo **Vendas e fatura de texto livre**, selecione **Fatura de Venda Peppol (Litware)**.
3. Selecione **Salvar**.

![Página Parâmetros de contas a receber, guia Documentos eletrônicos, guia rápida Relatório eletrônico.](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Atualizar registro de cliente adicionando um código de identificação de imposto federal

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na página **Todos os clientes**, selecione o link de conta de cliente **DE-014**.
3. Na FastTab **Geral**, no campo **ID de Imposto Federal**, insira **LITWARE-6789**.
4. Selecione **Salvar**.

    ![Página de detalhes de cliente DE-014.](./media/er-quick-start3-added-tax-id-value.png)

5. Feche a página **Todos os clientes**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Processar uma fatura de cliente usando as configurações de ER personalizadas

### <a name="select-and-send-a-posted-invoice"></a>Selecionar e enviar uma fatura lançada

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, selecione a fatura adicionada e lançada anteriormente.
3. No Painel de Ações, no grupo **Documento**, selecione **Enviar** \> **Original**.
4. Feche a página **Fatura de texto livre**.

### <a name="analyze-a-generated-e-invoice"></a>Analisar uma fatura eletrônica gerada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos**.
2. Na página **Trabalhos de relatórios eletrônicos**, selecione o registro mais recente que contém a descrição da tarefa **Enviar XML da fatura eletrônica**.
3. Selecione **Mostrar arquivos** para acessar a lista de arquivos gerados.
4. Selecione **Abrir** para baixar o arquivo XML da fatura eletrônica gerada.
5. Analise o arquivo XML da fatura eletrônica. Observe que, de acordo com a sua personalização, o esquema de imposto do cliente inclui o atributo XML personalizado **FederalTaxID**, além dos atributos XML **schemeID** e **schemeAgencyID**. O valor desse novo atributo XML é especificado pela ID de imposto federal **LITWARE-6789** inserida para um cliente faturado.

    ![Visualização do arquivo XML da fatura eletrônica gerada com suas personalizações.](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importar as versões mais recentes das configurações de ER padrão

Para manter o conjunto de configurações de ER padrão na instância do Finance [atualizado](general-electronic-reporting-manage-configuration-lifecycle.md), é necessário importar novas versões sempre que elas forem disponibilizadas no [repositório](general-electronic-reporting.md#Repository) de ER configurado para essa instância.

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, selecione o bloco **Microsoft** e, depois, selecione **Repositórios** para ver a lista de repositórios do provedor Microsoft.
3. Na página **Repositórios de configuração**, selecione o repositório do tipo **Global** e, depois, selecione **Abrir**. Se você precisar de autorização para se conectar ao Regulatory Configuration Service, siga as instruções de autorização.
4. Na página **Repositório de configuração**, na árvore de configuração no painel esquerdo, selecione a configuração de formato **Fatura de Venda Peppol**.
5. Na FastTab **Versões**, selecione a versão **32.6.7** da configuração de formato de ER selecionada que foi lançada para oferecer suporte a faturas eletrônicas de clientes no formato PEPPOL BIS 3. Para obter mais informações, consulte [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.

![Versão 32.6.7 selecionada na página Repositório de configuração.](./media/er-quick-start3-import-solution2.png)

Para obter mais informações sobre como esse processo pode ser automatizado, consulte [Importar versões atualizadas de configurações de ER](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Examinar as configurações de ER importadas

1. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Expanda a FastTab **Componentes de configuração**.
4. Na árvore de configuração no painel esquerdo, expanda **Modelo de fatura**. Observe que o nome de **Modelo de fatura de cliente** foi alterado para **Modelo de fatura** em uma das configurações importadas de modelo de dados de ER.
5. Na árvore de configuração no painel esquerdo, expanda **Mapeamento de modelo de fatura**. Observe que o nome de **Mapeamento de modelo de fatura de cliente** foi alterado para **Mapeamento de modelo de fatura** em uma das configurações importadas de mapeamento de modelo de ER.
6. Expanda **Fatura de Venda UBL** \> **Fatura de Venda Peppol**.

Observe que, além do formato de ER **Fatura de Venda Peppol** selecionado, as versões mais recentes de outras configurações de ER necessárias foram importadas. Como novas versões de configurações de ER são publicadas constantemente no repositório Global e LCS para manter as correspondentes soluções de ER em conformidade com novos requisitos, as versões mais recentes da configuração necessária do modelo de dados e as configurações do mapeamento de modelos foram importadas.

Verifique se as seguintes configurações de ER estarão futuramente disponíveis na árvore de configuração:

- Configuração de modelo de dados de ER do **Modelo de fatura**:

    - A versão 206 (ou posterior) contém a versão 24 (ou posterior) do componente de ER do modelo de dados que representa a estrutura de dados do domínio corporativo de faturamento. Esta configuração de ER foi importada como ancestral da configuração mais recente disponível do mapeamento do modelo de ER do **Mapeamento do modelo de fatura**.

    ![Versão 206 na página Configurações.](./media/er-quick-start3-imported-solution2b1.png)

- Configuração de mapeamento de modelo de ER do **Mapeamento de modelo de fatura**:

    - A versão 206.132 (ou posterior) foi importada como a implementação mais recente da versão 206 da configuração do modelo de dados de ER do **Modelo de fatura**. Ela contém vários componentes de ER de mapeamento de modelo que descrevem como o modelo de dados é preenchido com os dados do aplicativo no runtime.

    ![Versão 206.132 na página Configurações.](./media/er-quick-start3-imported-solution2b2.png)

- Configuração de formato de ER de **Fatura de venda UBL**:

    - A versão 32.6 contém os componentes de ER formato e mapeamento de formato. O componente de formato especifica o layout do relatório. O componente mapeamento de formato contém a fonte de dados do modelo e especifica como essa fonte de dados é usada para preencher o layout do relatório no runtime. Este formato de ER foi configurado para gerar faturas eletrônicas no formato UBL. Ele foi importado como pai do formato de ER **Fatura de Venda Peppol** selecionado para importação.

- Configuração de formato de ER de **Fatura de Venda Peppol**:

    - A versão 32.6.7 contém os componentes de ER do formato e de mapeamento de formato que foram configurados para gerar faturas eletrônicas no formato PEPPOL.

    ![Versão 32.6.7 na página Configurações.](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Adotar as alterações das novas versões das configurações de ER padrão nas configurações de ER personalizadas

### <a name="adopt-your-custom-er-data-model"></a>Adotar seu modelo de dados de ER personalizado

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** e selecione **Modelo de fatura (Litware)**.
3. Na FastTab **Versões**, para a versão de rascunho **50.2** da configuração de modelo de dados escolhida, selecione **Trocar base**.
4. No campo **Versão de destino**, confirme a seleção da versão **206** da configuração do modelo de dados base de ER e selecione **OK**.

    A versão de rascunho da configuração do modelo de dados de ER personalizado é renumerada de **50.2** para **206.2** indicando que agora contém a personalização que foi mesclada com as alterações na versão anterior (206) da configuração do modelo de dados base de ER.

    > [!NOTE]
    > A ação de troca de base é reversível. Para cancelar essa troca de base, selecione a versão **50.1** do **Modelo de fatura (Litware)** na FastTab **Versões** e selecione **Obter esta versão**. A versão 206.2 será renumerada para **50.2**, e o conteúdo da versão de rascunho 50.2 será compatível com o conteúdo da versão 50.1.

5. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 206.2 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 206.3, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração do modelo de dados de ER personalizada.

![Versão 206.2 concluída na página Configurações.](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Adotar seu mapeamento de modelo de ER personalizado

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** \> **Mapeamento de modelo de fatura** e selecione **Mapeamento de modelo de fatura (Litware)**.
3. Na FastTab **Versões**, para a versão de rascunho **50.19.2** da configuração do mapeamento de modelo escolhido, selecione **Trocar base**.
4. No campo **Versão de destino**, confirme a seleção da versão **206.132** da configuração do mapeamento de modelo de dados base de ER e selecione **OK**.

    A versão de rascunho da configuração do mapeamento de modelo de ER personalizado é renumerada de **50.19.2** para **206.132.2** indicando que agora contém a personalização que foi mesclada com as alterações na versão anterior (206.132) da configuração do mapeamento de modelo base de ER.

    Observe que alguns conflitos de troca de base foram descobertos. Agora você deve resolver esses conflitos manualmente.

    ![Mensagem de conflito de troca de base na página Configurações.](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. No Painel de Ações, selecione **Designer** e, na lista de mapeamentos, selecione **Fatura de cliente**.
6. Para cada conflito de troca de base, selecione **Reter valor próprio**, pois é necessário manter o número da versão do seu modelo de dados personalizado para cada componente mencionado.

    ![Conflitos de troca de base na página Designer de mapeamento de modelo.](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Selecione **Salvar** e feche a página **Designer de mapeamento de modelo**.
8. Na lista de mapeamentos, selecione **Fatura do Projeto**.
9. Para cada conflito de troca de base, selecione **Reter valor próprio**, pois é necessário manter o número da versão do seu modelo de dados personalizado para cada componente mencionado.
10. Selecione **Salvar** e feche a página **Designer de mapeamentos**.

    > [!NOTE]
    > A ação de troca de base é reversível. Para cancelar essa troca de base, selecione a versão **50.19.1** do **Mapeamento de modelo de fatura (Litware)** na FastTab **Versões** e selecione **Obter esta versão**. A versão 206.132.2 será renumerada para **50.19.2**, e o conteúdo da versão de rascunho 50.19.2 será compatível com o conteúdo da versão 50.19.1.

11. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 206.132.2 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 206.132.3, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração do mapeamento de modelo de ER personalizada.

![Versão 206.132.2 concluída na página Configurações.](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Adotar seu formato de ER personalizado

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura** \> **Fatura de Venda UBL** \> **Fatura de Venda Peppol** e selecione **Fatura de Venda Peppol (Litware)**.
3. Na FastTab **Versões**, para a versão de rascunho **11.2.2.2** da configuração de formato escolhida, selecione **Trocar base**.
4. No campo da versão **Destino**, confirme a seleção da versão **32.6.7** da configuração de formato base de ER e selecione **OK**.

    A versão de rascunho da configuração de formato de ER personalizada é renumerada de **11.2.2.2** para **32.6.7.2** indicando que agora contém a personalização que foi mesclada com as alterações na versão anterior (32.6.7) da configuração de formato base de ER.

    Observe que alguns conflitos de troca de base foram descobertos. Agora você deve resolver esses conflitos manualmente.

5. No Painel de Ação, selecione **Designer**.
6. Para cada conflito de troca de base, selecione **Reter valor próprio**, pois é necessário manter o número da versão do seu modelo de dados personalizado para cada componente mencionado.
7. Selecione **Salvar**.
8. Na guia **Mapeamento**, selecione a fonte de dados **Fatura** do tipo **Modelo** e, em seguida, **Editar**.
9. No campo **Versão**, selecione a versão **2** do modelo de dados personalizado e depois selecione **OK**.
10. Selecione **Salvar**.

    > [!NOTE]
    > A ação de troca de base é reversível. Para cancelar essa troca de base, selecione a versão **11.2.2.1** do formato de **Fatura de Venda Peppol (Litware)** na FastTab **Versões** e selecione **Obter esta versão**. A versão 32.6.7.2 será renumerada para **11.2.2.2**, e o conteúdo da versão de rascunho 11.2.2.2 será compatível com o conteúdo da versão 11.2.2.1.

11. Feche a página **Designer de formato**.
12. Na FastTab **Versões**, selecione **Alterar status** \> **Concluído** e clique em **OK**.

O status da versão 32.6.7.2 muda de **Rascunho** para **Concluído** e a versão se torna somente leitura. Uma nova versão editável, 32.6.7.3, foi adicionada e tem o status de **Rascunho**. Você pode usar essa versão para fazer outras alterações na configuração de formato de ER personalizada.

![Versão 32.6.7.2 concluída na página Configurações.](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Processar uma fatura de cliente usando as novas versões das configurações de ER personalizadas

### <a name="select-and-send-a-posted-invoice"></a>Selecionar e enviar uma fatura lançada

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Na página **Fatura de texto livre**, selecione a fatura adicionada e lançada anteriormente.
3. No Painel de Ações, no grupo **Documento**, selecione **Enviar** \> **Original**.

    > [!NOTE] 
    > Como agora você tem duas versões da configuração de formato de ER da **Fatura de Venda Peppol (Litware)** e nenhuma delas tem um valor de [data de vigência](general-electronic-reporting.md#component-date-effectivity), a versão mais recente será usada para gerar uma fatura eletrônica.

4. Feche a página **Fatura de texto livre**.

### <a name="analyze-a-generated-e-invoice"></a>Analisar uma fatura eletrônica gerada

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos**.
2. Na página **Trabalhos de relatórios eletrônicos**, selecione o registro mais recente que contém a descrição da tarefa **Enviar XML da fatura eletrônica**.
3. Selecione **Mostrar arquivos** para acessar a lista de arquivos gerados.
4. Selecione **Abrir** para baixar o arquivo XML da fatura eletrônica gerada.
5. Analise o arquivo XML da fatura eletrônica. Observe que, de acordo com a sua personalização, o esquema de imposto do cliente ainda contém o atributo XML personalizado **FederalTaxID**, além dos atributos XML **schemeID** e **schemeAgencyID**. Além disso, como as alterações na nova versão do formato base da **Fatura de Venda UBL** foram mescladas com a sua personalização, o texto do elemento XML **cbc:CustomizationID** foi alterado de `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` para `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Visualização do arquivo XML da fatura eletrônica gerada com as personalizações.](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Baixar configurações de ER do Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Baixar configurações de ER do repositório global de serviço de configuração](er-download-configurations-global-repo.md)
- [Criar uma fatura de texto livre](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [Criar e trabalhar com campos personalizados](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
