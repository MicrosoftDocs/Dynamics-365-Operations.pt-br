---
title: Commerce Analytics (Versão preliminar)
description: Este artigo explica como instalar e usar o recurso de análise no Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/24/2022
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 9ffa0affa0b80af65dd2aa37ef2fe969752ae332
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887157"
---
# <a name="commerce-analytics-preview"></a>Commerce Analytics (Versão preliminar)

[!include [banner](includes/banner.md)]

Este artigo explica como instalar o Commerce Analytics (versão preliminar), o recurso de análise funcional incluído no Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Demonstração ao vivo do Commerce Analytics (Versão preliminar)

Você pode experimentar uma [demonstração ao vivo do Commerce Analytics (Versão preliminar)](https://aka.ms/CommerceAnalyticsDemo).

![Resumo do Commerce Analytics (Versão preliminar)](media/CommerceAnalytics_Summary.png)
![Pagamentos do Commerce Analytics (Versão preliminar)](media/CommerceAnalytics_Payments.png)
![Atividade na Web do Commerce Analytics (Versão preliminar)](media/CommerceAnalytics_WebActivity.png)

## <a name="commerce-analytics-preview-system-architecture"></a>Arquitetura do sistema do Commerce Anaytics (Versão preliminar)

### <a name="key-components"></a>Componentes da chave

O Commerce Analytics (Versão preliminar) é composto pelos seguintes componentes principais:

- Relatórios interativos prontos para uso do Power BI
- Exibições do SQL no Azure Synapse Analytics
- Dados de entidades e ontologia no Azure Data Lake
- Dados brutos no Data Lake

![Componentes principais da arquitetura de sistema do Commerce Analytics](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Fluxo de dados

#### <a name="step-1-data-generation"></a>Etapa 1: geração de dados

Os dados se originam como dados transacionais ou dados comportamentais de uma das seguintes fontes:

- Um associado de um call center usa o cliente do Commerce HQ para processar ordens de venda.
- Um caixa no ponto de venda (POS) processa as transações de vendas.
- As vendas são criadas em aplicativos personalizados usando o Commerce sem periféricos (Commerce Scale Unit).
- Um comprador de comércio eletrônico pesquisa seu site de comércio eletrônico.
- Um comprador de comércio eletrônico faz um pedido em seu site de comércio eletrônico.
- Os dados são produzidos por outros sistemas, como Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Etapa 2: ingestão e pré-processamento

Os dados transacionais vão para o Commerce HQ diretamente (no caso das ordens que são capturadas diretamente no cliente do Commerce HQ) ou pela Commerce Scale Unit (no caso de ordens que são capturadas no POS, comércio eletrônico ou em clientes personalizados que usam o Commerce sem sem periféricos).

O recurso Exportar para Data Lake é usado para copiar os dados transacionais para o Data Lake como dados brutos. No Data Lake, os dados brutos são armazenados na pasta Tabelas.

Os dados de atividade da Web de comércio eletrônico são enviados diretamente ao Data Lake. Os dados produzidos por outros sistemas, como o Dynamics 365 Connected Spaces, são enviados diretamente ao Data Lake por esses sistemas.

#### <a name="step-3-transformation-and-aggregation"></a>Etapa 3: transformação e agregação

Depois que os dados brutos estão em seu Data Lake, o serviço do Commerce Analytics faz a leitura deles, os transforma, os agrega e os grava de volta no Data Lake na forma de entidades lógicas (na pasta Entidades) e em métricas agregadas (na pasta Ontologias).

#### <a name="step-4-querying"></a>Etapa 4: consulta

O Azure Synapse Analytics é usado para consultar dados no Data Lake por meio de uma interface do Transact-SQL (T-SQL). Essa interface inclui visualizações de SQL. As visualizações de SQL permitem a consulta federada de dados no Data Lake, diretamente por meio de um cliente T-SQL (para análise ad-hoc) ou por meio de uma ferramenta de visualização como Power BI.

#### <a name="step-5-modeling-and-serving"></a>Etapa 5: modelagem e serviço

Os dados consultados pelo Azure Synapse Analytics vão até o modelo de semântica do Power BI. Dependendo do tipo de dados, ele é importado periodicamente na memória no Power BI ou diretamente consultado no tempo de execução.

Finalmente, os dados são renderizados nas visões do Power BI para que os usuários possam exibir e interagir com ele.

## <a name="commerce-analytics-preview-functional-overview"></a>Visão geral funcional do Commerce Analytics (Versão preliminar)

### <a name="summary"></a>Resumo

O aplicativo de modelo do Commerce Analytics inclui as seguintes páginas de relatório principal:

1. [Filtros de nível superior](#TopLevelFilters)
2. [Produtos](#ProductsPage)
3. [Clientes](#CustomersPage)
4. [Canais](#ChannelsPage)
5. [Vendas](#SalesPage)
6. [Margens](#MarginsPage)
7. [Volta](#ReturnsPage)
8. [Descontos](#DiscountsPage)
9. [Pagamentos](#PaymentsPage)
10. [Clientes](#CustomersPage)
11. [Comparação](#ComparisonPage)
12. [Atividade da Web](#WebActivityPage)
13. [Atividade da Web - Filtro de nível superior](#WebActivityTopLevelFilters)

#### <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtros de nível superior

- Configurações de data

    - Ano
    - Trimestre
    - Mês
    - Semana
    - Dia

- Configurações do canal

    - Pessoa jurídica em geral
    - Tipo de canal
    - Tipo de cliente
    - Tipo de vendas
    - Canal
    - Hierarquia da organização

- Configurações de produtos

    - Hierarquia de categoria
    - Categoria

#### <a name="products"></a><a name="ProductsPage"></a> Produtos

- Vendas
- Margem
- Volta

#### <a name="customers"></a><a name="CustomersPage"></a> Clientes

- Vendas
- Margem
- Volta

#### <a name="channels"></a><a name="ChannelsPage"></a> Canais

- Vendas
- Margem
- Volta

### <a name="sales"></a>Vendas <a name="SalesPage"></a>

- Por local de entrega
- Por canal/armazenamento/terminal
- Por funcionário
- Por data
- Por hora
- Por categoria de produtos

### <a name="margins"></a><a name="MarginsPage"></a> Margens

- Por local de entrega
- Subproduto
- Por data

### <a name="returns"></a><a name="ReturnsPage"></a> Devoluções

- Devolução por valor

    - Por loja
    - Subproduto
    - Por data

- Devolução por transação

    - Por loja
    - Subproduto
    - Por data

### <a name="discounts"></a><a name="DiscountsPage"></a> Descontos

- Por loja
- Subproduto
- Por data
- Decomposição

    - Pessoa jurídica em geral
    - Armazenar
    - Tipo de desconto
    - Nome do desconto
    - Produto

### <a name="payments"></a><a name="PaymentsPage"></a> Pagamentos

- Por canal/terminal
- Por tipo/forma de pagamento
- Por data
- Decomposição

    - Pessoa jurídica em geral
    - Tipo de canal
    - Armazenar
    - Terminal
    - Forma de pagamento

### <a name="customers"></a><a name="CustomersPage"></a> Clientes

- Valor da vida útil (LTV)

    O LTV é calculado com base no valor total que um cliente gasta em todos os canais de venda do Dynamics 365 Commerce (incluindo POS, comércio eletrônico e call center).

- Recency

    A recência é calculada com base no número de dias desde o último contrato transacional de um cliente com a organização. No momento, a recência não considera sinais de contratos não transacionais, como atividades de pesquisa de comércio eletrônico.

- Frequência

    A frequência é calculada com base no contrato transacional de um cliente com a organização. No momento, a frequência não considera sinais de contratos não transacionais, como atividades de pesquisa de comércio eletrônico.

- Duração dos relacionamentos

    A duração do relacionamento é calculada com base no número de dias desde que o registro do cliente foi criado no sistema.

- Contagem de transações

### <a name="comparison"></a><a name="ComparisonPage"></a> Comparação

- Comparação de produtos por período de tempo

    - Vendas e diferença de vendas
    - Margem e diferença de margem

- Cliente por período de tempo

    - Vendas e diferença de vendas
    - Margem e diferença de margem

### <a name="web-activity"></a><a name="WebActivityPage"></a> Atividade da Web

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filtros de nível superior

- Intervalo de datas
- Tipo de canal
- Canal
- Hierarquia de categoria

#### <a name="acquisitions"></a>Aquisições

- Exibições de página

    - Por país ou região
    - Subproduto
    - Por status de inscrição do usuário
    - Por data

- Pedidos do comércio eletrônico
- Taxa de conversão

    - Por data

- Funil de conversão

    - Exibição de página por tipo de página (página inicial, página de categoria ou página de detalhes do produto)
    - Adicionar ao carrinho
    - Finalizar Compra
    - Compra

#### <a name="sessions"></a>Sessões

Uma sessão é um episódio da visita de um usuário para seu site de comércio eletrônico. Uma sessão é considerada encerrada após 30 minutos de inatividade ou 24 horas de uso ativo.

- Por país ou região
- Por origem (referenciador externo)
- Por status de inscrição do usuário
- Contagem de sessões

    - Por data
    - Por página de entrada

- Pedido por sessão

    - Por data

- Taxa de salto de sessão

    Um salto de sessão é uma sessão na qual um usuário sai imediatamente depois de visitar o seu site de comércio eletrônico. Para obter mais informações, consulte [Taxa de saltos](https://en.wikipedia.org/wiki/Bounce_rate).

- Cliques por sessão

#### <a name="visitors"></a>Visitantes

Um visitante anônimo em seu site de comércio eletrônico é identificado exclusivamente com base no navegador específico e no dispositivo específico que o usuário está usando. O Commerce Analytics não rastreia visitantes anônimos em diferentes navegadores ou dispositivos. Um visitante anônimo que usa o mesmo navegador no mesmo dispositivo é identificado exclusivamente por várias sessões do usuário, até que os dados armazenados em cache do navegador sejam eliminados ou depois de decorrência de um período (normalmente, 12 meses), o que ocorrer primeiro.

Se os visitantes navegarem no site de comércio eletrônico enquanto estiverem conectados, o Commerce Analytics poderá fornecer informações adicionais sobre eles. Essas informações se baseiam no relacionamento existente entre a sua organização e os visitantes como resultado de suas compras anteriores em todos os canais de vendas do Dynamics 365 Commerce (incluindo POS, comércio eletrônico e call center). As informações adicionais incluem recência, duração do relacionamento, valor da vida útil e dados de frequência.

- Margem do visitante
- Média de pedidos do visitante
- Média de vendas do visitante
- Contagem de visitantes do comércio eletrônico

    - Por data
    - Por localização

        No momento, o Commerce Analytics pode fornecer somente granularidade no nível de país/região para insights de localização para visitantes do comércio eletrônico.

    - Por recência

        A recência é calculada com base no número de dias desde o último contrato transacional de um cliente com a organização. No momento, a recência não considera sinais de contratos não transacionais, como atividades de pesquisa de comércio eletrônico.

    - Por duração dos relacionamentos

        A duração do relacionamento é calculada com base no número de dias desde que o registro do cliente foi criado no sistema.

    - Por valor da vida útil (LTV)

        O LTV é calculado com base no valor total que um cliente gasta em todos os canais de venda do Dynamics 365 Commerce (incluindo POS, comércio eletrônico e call center).

    - Por frequência

        A frequência é calculada com base no contrato transacional de um cliente com a organização. No momento, a frequência não considera sinais de contratos não transacionais, como atividades de pesquisa de comércio eletrônico.

#### <a name="impressions"></a>Impressões

Uma impressão é uma única exibição de uma visão de produto por um visitante de comércio eletrônico. Por exemplo, um visitante de comércio eletrônico vai para a página inicial do seu site de comércio eletrônico e visualiza tapete de yoga em um módulo de listagem de **Produtos mais vendidos**. Em seguida, o visitante visualiza o mesmo tapete de yoga em um módulo de listagem de **Seleções para você**. Nesse caso, há duas impressões de produto.

No momento, as impressões são rastreadas nas seguintes superfícies:

- Listagens (por exemplo, **Recomendados**, **Produtos mais vendidos**, **Seleções para você** e **Mais populares**)
- Módulo de carrinho
- Contêiner de resultados de pesquisa
- Contêiner de resultados de pesquisa por categoria

No momento, os produtos que são processados em um módulo de carrossel ou em visões personalizadas não são contados nas métricas relacionadas à impressão.

A página **Relatório de impressões** inclui as seguintes métricas:

- Contagem de impressões

    - Por tipo de página e módulo

        O tipo de página é o tipo genérico de página definido para cada página no seu site de comércio eletrônico. Tipo de módulo é o tipo de módulo de visão do comércio eletrônico no qual o produto é mostrado.

        Para exibir impressões por módulo, talvez seja necessário fazer uma busca detalhada na página e nas visões do módulo.

    - Subproduto
    - Por status de inscrição do usuário
    - Por data

- Contagem de cliques de impressão

    Um clique de impressão ocorre quando um visitante de comércio eletrônico seleciona uma visão de produto. Normalmente, o visitante é levado para a página de detalhes do produto.

- Taxa de cliques de impressão (CTR)

    O CTR é calculado como o número total de cliques de impressão divididos pelo número total de impressões.

## <a name="commerce-analytics-preview-installation"></a>Instalação do Commerce Analytics (Versão preliminar)

> [!NOTE]
> O Commerce Analytics (Versão preliminar) está disponível como versão preliminar nas regiões dos Estados Unidos, do Canadá, do Reino Unido, da Europa, do Sudeste da Ásia, do Leste da Ásia, da Austrália e do Japão. Se o ambiente de Finanças e Operações estiver em qualquer uma dessas regiões, você poderá habilitar esse recurso no ambiente usando o Lifecycle Services (LCS) do Microsoft Dynamics. Para poder usar este recurso, consulte [Configurar a exportação para o Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Habilitar e configurar o Commerce Analytics (Versão preliminar)

Para instalar o Commerce Analytics (Versão preliminar), você deve ter permissões para criar recursos em uma assinatura do Azure. Você também deve ter permissões para instalar suplementos no LCS.

Para habilitar e configurar o Commerce Analytics (versão preliminar), siga estas etapas.

1. [Envie o formulário de ingestão de Versão preliminar do Commerce Analytics (Versão preliminar)](#joinPreview)
2. [Habilitar e configurar o suplemento Exportar para o Data Lake](#enableExportToDataLake).
3. [Instale e configure um Azure Synapse workspace](#configureAzureSynapse).
4. [Adicionar segredos ao cofre de chaves](#addSecrets).
5. [Habilite e configure o suplemento Commerce Analytics (Versão preliminar)](#enableCommerceAnalyticsAddin).
6. [Instale o aplicativo de modelo do Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Envie o formulário de ingestão de Versão preliminar do Commerce Analytics (Versão preliminar)

Envie o [formulário de ingestão de Versão preliminar do Commerce Analytics (Versão preliminar)](https://forms.office.com/r/vW5VLJGXZ2). Depois que a solicitação for processada, um email de confirmação será enviado para o endereço de email fornecido no formulário.

### <a name="enable-and-configure-the-export-to-data-lake-add-in"></a><a name="enableExportToDataLake"></a>Habilitar e configurar o suplemento Exportar para o Data Lake

> [!IMPORTANT]
> Ao configurar o suplemento Exportar para o Data Lake, desmarque a caixa de seleção **Alterações de dados em tempo real** na página de configuração do suplemento Exportar para o Data Lake a fim de garantir que as alterações de dados em tempo real não estejam habilitadas. O recurso **Alterações de dados em tempo real** está em versão prévia e não é compatível com o Commerce Analytics no momento. Se você habilitar o recurso, o Commerce Analytics não poderá processar seus dados no Data Lake e a maioria dos relatórios do Power BI não mostrará dados.

O Commerce Analytics (versão preliminar) depende do recurso Exportação para Data Lake para exportar dados do Commerce headquarters para o Data Lake e manter os dados atualizados. Antes de configurar o Commerce Analytics (Versão preliminar), habilite e configure a Exportação para o Data Lake seguindo as etapas em [Configurar a exportação para o Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Ao configurar o suplemento Exportar para o Data Lake, anote as informações a seguir, pois você terá que digitá-las posteriormente:

- <a name="keyVault"></a>O nome do DNS (sistema de nome de domínio) do cofre de chaves fornecido.
- Os nomes de segredo que você forneceu e que contêm a ID do aplicativo e o segredo do aplicativo. Para obter mais informações, consulte [Adicionais segredos aos cofre de chaves](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Instale e configure um Azure Synapse workspace

O Commerce Analytics (versão preliminar) exige que o SQL sob demanda do Synapse seja provisionado no Azure Synapse workspace. Para instalar e configurar um Azure Synapse workspace, siga estas etapas.

1. Instale um Azure Synapse workspace na sua assinatura do Azure. Para obter mais informações, consulte [Início Rápido: Criar um espaço de trabalho do Synapse](/azure/synapse-analytics/quickstart-create-workspace).
1. <a name="serverlessep"></a>Depois que o espaço de trabalho for provisionado, abra a página Visão geral do recurso e anote o valor do **Ponto de extremidade do SQL sem servidor**. Você terá de armazenar esse valor no cofre de chaves na próxima seção.
1. Na página Visão geral, selecione o link **Abrir Synapse Studio** para abrir o Azure Synapse Studio no espaço de trabalho.
1. Selecione **Gerenciar** no menu à esquerda. Para ver os nomes dos menus, talvez você precise selecionar o link de expansão no menu à esquerda.
1. No **Grupo de segurança**, selecione **Controle de acesso**. 
1. Selecione **Adicionar**.
1. No painel **Adicionar atribuição de função**, defina as opções conforme descrito na tabela a seguir.

    | Opção | Valor |
    |--------|-------|
    | Escopo | Selecione **Espaço de trabalho**. |
    | Função | Selecione **Administrador do SQL Synapse**.|
    | Selecionar usuário | Procure o nome do aplicativo que você [criou durante a instalação do suplemento Exportar para o Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createapplication). Quando o aplicativo aparecer nos resultados da pesquisa, selecione-o. Agora, o aplicativo aparecerá na seção **Usuários, grupos ou entidades de serviço selecionados**. |

1. Selecione **Aplicar** para concluir a atribuição de função. O aplicativo recebe privilégios de Administrador do SQL Synapse. Portanto, ele pode criar as exibições necessárias durante a configuração do suplemento Commerce Analytics (versão preliminar) do LCS.

### <a name="add-secrets-to-the-key-vault"></a><a name="addSecrets"></a>Adicionar segredos ao cofre de chaves

No mesmo [cofre de chaves](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createkeyvault) que você usou enquanto configurou o suplemento Exportar para o Data Lake, é necessário adicionar os segredos mostrados na tabela a seguir. Para cada segredo, é necessário fornecer um nome secreto e o valor especificado.

| Nome secreto sugerido | Valor do segredo | Exemplo de valor secreto |
|---------|---------|---------|
| synapse-sql-server | O valor do ponto de extremidade do SQL sem servidor que você anotou enquanto [configurou o Azure Synapse workspace](#serverlessep). | `test-ondemand.sql.azuresynapse.net` |
| <a name="roUser"></a>readonly-sql-pwd | A senha a ser definida para o usuário somente leitura do SQL. O relatório do Power BI usará essa senha para conectar-se ao SQL sem servidor. Para definir a senha, siga as políticas de senha da sua organização. | |

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Habilite e configure o suplemento Commerce Analytics (Versão preliminar)

Para instalar o suplemento Commerce Analytics (Versão preliminar) no LCS, você deve ser um administrador de ambiente no LCS para o ambiente que pretende usar.

Para instalar e configurar o suplemento Commerce Analytics (Versão preliminar), siga estas etapas.

1. Entre no [LCS](https://lcs.dynamics.com/) e acesse seu ambiente.
2. Na página **Ambiente**, na guia **Suplementos do ambiente**, selecione **Instalar um novo suplemento**.
3. Na caixa de diálogo, selecione **Commerce Analytics (Versão preliminar)**.
4. Na caixa de diálogo **Configurar suplemento**, insira as informações a seguir.

    | Informações | Origem | Exemplo de valor |
    |---|---|---|
    | ID de locatário do Azure Active Directory (Azure AD) | Faça login no [portal do Azure](https://portal.azure.com/) e abra o serviço **Azure Active Directory**. Em seguida, abra a página **Propriedades** e copie o valor no campo **ID do Locatário**. | `72f988bf-0000-0000-00000-2d7cd011db47` |
    | Nome DNS do cofre de chaves do Azure | Insira o nome DNS de cofre de chaves. Você deve ter anotado esse valor enquanto [configurou o suplemento Exportar para o Data Lake](#keyVault). | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Nome do segredo que contém a ID do aplicativo | Insira o nome do segredo que armazena a ID do aplicativo. Você deve ter anotado esse valor enquanto [configurou o suplemento Exportar para o Data Lake](#keyVault). | `app-id` |
    | Nome do segredo que contém o segredo do aplicativo | Insira o nome do segredo que armazena o segredo do aplicativo. Você deve ter anotado esse valor enquanto [configurou o suplemento Exportar para o Data Lake](#keyVault). | `app-secret` |
    | Nome do segredo que contém o ponto de extremidade do SQL sem servidor do Azure Synapse | Insira o nome do segredo que armazena o ponto de extremidade do SQL sem servidor. Você deve ter criado o segredo enquanto [adicionou segredos ao valor da chave](#addSecrets). | `synapse-sql-server` |
    | Nome do segredo que contém a senha a ser definida para os usuários de somente leitura do SQL no Azure Synapse | Insira o nome do segredo que armazena a senha a ser definida para o usuário somente leitura do SQL sem servidor. Este usuário será criado para você e deverá ser usado no relatório do Power BI para conectar-se ao SQL Server sem servidor. Você deve ter criado o segredo enquanto [adicionou segredos ao valor da chave](#addSecrets). | `readonly-sql-pwd` |

1. Aceite os termos da oferta marcando a caixa de seleção e selecione **Instalar**.

    O sistema instala e configura o suplemento Commerce Analytics (Versão preliminar) para o ambiente. Esse processo pode levar alguns minutos. Depois de concluído, o **Commerce Analytics (Versão preliminar)** deve estar listado na página **Ambiente** e o status deve ser **Instalado**.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Instale o aplicativo de modelo do Power BI

Para instalar o aplicativo de modelo do Power BI para Commerce Analytics (Versão preliminar), siga estas etapas.

1. Faça login no [portal do Power BI](https://powerbi.microsoft.com/) usando a ID da sua organização.
1. Instale o aplicativo de modelo do Power BI do Commerce Analytics (Versão preliminar) acessando [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Como alternativa, acesse a [Página do AppSource do Dynamics 365 Commerce Analytics](https://appsource.microsoft.com/product/power-bi/dynamics-365-commerce.dydnamics-365-commerce-analytics) e selecione **Obter agora**.
1. Se você estiver instalando o aplicativo pela primeira vez, pule para a etapa 5. Se você já o instalou, as seguintes opções para atualizar o aplicativo se aplicam:

    - **Atualizar o espaço de trabalho e o aplicativo** – atualize o aplicativo de modelo existente e substitua as configurações do aplicativo existentes, como o nome da instância do aplicativo e as configurações de permissão.
    - **Atualizar somente o conteúdo do espaço de trabalho sem atualizar o aplicativo** – atualize o aplicativo de modelo existente, mas mantenha suas configurações do aplicativo existentes. *Esta opção é a opção recomendada para atualizações de aplicativos.*
    - **Instalar outra cópia do aplicativo em um novo espaço de trabalho** – crie um novo espaço de trabalho e crie uma cópia do aplicativo de modelo existente nele. O espaço de trabalho existente permanecerá intacto.

1. Selecione uma das opções de atualização e, em seguida, selecione **Instalar**.
1. Abra o aplicativo instalado selecionando **Aplicativos** no painel esquerdo e selecionando o aplicativo.
1. Conecte o aplicativo à fonte de dados selecionando **Conectar**. Se você tiver instalado o aplicativo antes, selecione o link **Conectar seus dados** na barra de mensagens amarela.
1. Defina os campos a seguir.

    | Campo | Valor |
    |---|---|
    | Servidor | Insira o ponto de extremidade do SQL sem servidor que você anotou depois de [criar o Azure Synapse workspace](#serverlessep). |
    | Banco de dados | Digite **CommerceAnalytics**. |
    | Idioma | Selecione um valor na lista. Este campo é usado para nomes de categorias e produtos localizados. O valor diferencia maiúsculas de minúsculas. |
    | Intervalo de Datas | Selecione um valor na lista. Os dados do número de meses selecionado serão importados para o conjunto de dados do Power BI. O valor selecionado afeta o tamanho do conjunto de dados e o tempo necessário para a sincronização. |

1. Selecione **Avançar**. Quando você for solicitado a inserir as credenciais para conexão com o banco de dados SQL do Azure Synapse, defina os valores de campo conforme mostrado na tabela a seguir.

    | Campo | Valor |
    |---|---|
    | Método de autenticação | Selecione **Básico**. |
    | Nome de usuário | Insira **reportreadonlyuser**. |
    | Senha | Digite a senha [armazenada para o usuário somente leitura do SQL no cofre de chaves](#roUser). |

1. Selecione **Efetuar login e conectar**.
1. Aguarde até que o conjunto de dados seja atualizado com sucesso. Em seguida, selecione **Editar aplicativo** para abrir o espaço de trabalho do aplicativo, no qual você pode exibir o status da atualização do conjunto de dados. No espaço de trabalho do aplicativo, você também pode configurar programações de atualização automática para o conjunto de dados,, gerenciar permissões e renomear a instância do aplicativo.

### <a name="privacy"></a><a name="privacy"></a>Política de Privacidade

Sua privacidade é importante para nós. Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
