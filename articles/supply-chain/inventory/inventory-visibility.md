---
title: Suplemento Visibilidade de Estoque
description: Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8709b91b354fa4e1319b406c009bfdadeef48a41
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358089"
---
# <a name="inventory-visibility-add-in"></a>Suplemento Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

O Suplemento Visibilidade de Estoque é um microsserviço independente e altamente escalonável que permite o rastreamento de estoque disponível em tempo real, oferecendo, assim, uma visão global da visibilidade de estoque.

Todas as informações relacionadas ao estoque disponível são exportadas para o serviço quase em tempo real por meio de uma integração SQL de nível baixo. Os sistemas externos acessam o serviço por meio de APIs RESTful para consultar informações disponíveis sobre determinados conjuntos de dimensões, recuperando, dessa forma, uma lista de posições disponíveis.

A Visibilidade de Estoque é um microsserviço criado no Microsoft Dataverse, o que significa que você pode estendê-lo criando Power Apps e aplicando o Power BI para fornecer funcionalidade personalizada para atender aos seus requisitos de negócios. Também é possível atualizar o índice para fazer consultas de estoque.

A Visibilidade de Estoque fornece opções de configuração que permitem a integração com vários sistemas de terceiros. Ela oferece suporte à dimensão de estoque padronizada, à extensibilidade personalizada e a quantidades calculadas padronizadas e configuráveis.

Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management e como usar sua interface de programação de aplicativo (API).

## <a name="install-the-inventory-visibility-add-in"></a>Instalar o Suplemento Visibilidade de Estoque

É necessário instalar o Suplemento Visibilidade de Estoque usando o Microsoft Dynamics Lifecycle Services (LCS). O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Dynamics 365 Finance and Operations.

Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="inventory-visibility-add-in-prerequisites"></a>Pré-requisitos do complemento Visibilidade do inventário

Antes de instalar o Suplemento Visibilidade de Estoque, você deve fazer o seguinte:

- Obter um projeto de implementação do LCS com, pelo menos, um ambiente implantado.
- Verifique se os pré-requisitos para a configuração de suplementos fornecidos na [Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) foram concluídos. A visibilidade de estoque não exige link de gravação dupla.
- Entre em contato com a equipe de visibilidade de estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os três seguintes arquivos necessários:
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - `Inventory Visibility Integration.zip` (se a versão do Supply Chain Management que você está executando for anterior à versão 10.0.18)
- Outra opção é entrar em contato com a Equipe do Visibilidade do inventário em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os pacotes do Package Deployer. Esses pacotes podem ser usados por uma ferramenta oficial do Package Deployer.
  - `InventoryServiceBase.PackageDeployer.zip`
  - `InventoryServiceApplication.PackageDeployer.zip` (este pacote contém todas as alterações do pacote `InventoryServiceBase`, além de componentes de UI adicionais do aplicativo)
- Siga as instruções descritas em [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar um aplicativo e adicionar um segredo do cliente ao AAD com sua assinatura do Azure.
  - [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app)
  - [Adicionar um segredo do cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - O **ID do aplicativo (Client)**, **Segredo do cliente** e **ID do locatário** serão usados nas etapas a seguir.

> [!NOTE]
> Os países e regiões com suporte no momento incluem o Canadá, os Estados Unidos e a União Europeia (UE).

Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque.

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Configurar Dataverse

Para configurar o Dataverse para uso com o Visibilidade do Inventário, primeiro você preparar os pré-requisitos e então decidir se quer configurar o Dataverse usando a ferramenta do Package Deployer ou importando manualmente as soluções (não é necessário fazer os dois). Em seguida, instale o complemento Visibilidade do inventário. As subseções a seguir descrevem como concluir cada uma dessas ações.

#### <a name="prepare-dataverse-prerequisites"></a>Preparar pré-requisitos do Dataverse

Antes de começar a configurar o Dataverse, adicione um princípio de serviço ao seu locatário fazendo o seguinte:

1. Instale o módulo Azure AD PowerShell v2, conforme descrito em [Instalar o Azure Active Directory PowerShell para o Graph](/powershell/azure/active-directory/install-adv2).

1. Execute o seguinte comando do PowerShell:

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a>Configurar o Dataverse usando a ferramenta Package Deployer

Após preparar os pré-requisitos, use o seguinte procedimento se preferir configurar o Dataverse usando a ferramenta Package Deployer. Consulte a próxima seção para ver detalhes sobre como importar as soluções manualmente (não use os dois procedimentos).

1. Instale as ferramentas para desenvolvedores conforme descrito em [Baixar ferramentas do NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).

1. Com base em suas necessidades de negócios, escolha o pacote `InventoryServiceBase` ou `InventoryServiceApplication`.

1. Importe as soluções:
    1. Para o pacote `InventoryServiceBase`:
        - Descompacte `InventoryServiceBase.PackageDeployer.zip`
        - Encontre a pasta `InventoryServiceBase`, arquivo `[Content_Types].xml`, arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` e arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`. 
        - Copie cada uma dessas pastas e arquivos para o diretório `.\Tools\PackageDeployment`, que foi criado quando você instalou as ferramentas para desenvolvedores.
    1. Para o pacote `InventoryServiceApplication`:
        - Descompacte `InventoryServiceApplication.PackageDeployer.zip`
        - Encontre a pasta `InventoryServiceApplication`, arquivo `[Content_Types].xml`, arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` e arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.
        - Copie cada uma dessas pastas e arquivos para o diretório `.\Tools\PackageDeployment`, que foi criado quando você instalou as ferramentas para desenvolvedores.
    1. Execute `.\Tools\PackageDeployment\PackageDeployer.exe`. Siga as instruções na sua tela para importar as soluções.

1. Atribua direitos de acesso ao usuário do aplicativo.
    1. Abra a URL do ambiente do Dataverse.
    1. Vá para **Configurações avançadas \> Sistema \> Segurança \> Usuários** e encontre o usuário chamado **# InventoryVisibility**.
    1. Selecione **Atribuir Função** e, depois, selecione **Administrador do Sistema**. Se houver uma função chamada **Usuário do Common Data Service**, selecione-a também.

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a>Configurar o Dataverse manualmente importando soluções

Após preparar os pré-requisitos, use o seguinte procedimento se preferir configurar o Dataverse importando soluções manualmente. Consulte a seção anterior para ver detalhes sobre como usar a ferramenta Package Deployer (não use os dois procedimentos).

1. Crie um usuário de aplicativo para a visibilidade de estoque no Dataverse:

    1. Abra a URL do ambiente do Dataverse.
    1. Acesse **Configuração Avançada \> Sistema \> Segurança \> Usuários** e crie um usuário de aplicativo. Use o menu de exibição para alterar a exibição de página para **Usuários do Aplicativo**.
    1. Selecione **Novo**. Defina a ID do aplicativo como *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*. (A ID do objeto será carregada automaticamente quando você salvar as alterações.) Você pode personalizar o nome. Por exemplo, você pode alterá-lo para *Visibilidade do Estoque*. Quando terminar, selecione **Salvar**.
    1. Selecione **Atribuir Função** e, depois, selecione **Administrador do Sistema**. Se houver uma função denominada **Usuário do Common Data Service**, selecione-a.

    Para obter mais informações, consulte [Criar um usuário de aplicativo](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Se o idioma padrão de seu Dataverse não estiver definido como **Inglês**:

    1. Acesse **Configurações avançadas \> Administração \> Idiomas**,
    1. Selecione **Inglês (LanguageCode = 1033)** e selecione **Aplicar**.

1. Importe o arquivo `Inventory Visibility Dataverse Solution.zip`, que inclui entidades relacionadas à configuração do Dataverse e o Power Apps:

    1. Acesse a página **Soluções**.
    1. Selecione **Importar**.

1. Importe o fluxo do disparador da atualização de configuração:

    1. Acesse a página Microsoft Flow.
    1. Verifique se existe a conexão denominada *Dataverse (herdado)*. (Se ela não existir, crie-a.)
    1. Importe o arquivo `Inventory Visibility Configuration Trigger.zip`. Após ele ser importado, o disparador aparecerá em **Meus fluxos**.
    1. Inicialize as seguintes quatro variáveis, com base nas informações de ambiente:

        - ID de Locatário do Azure
        - ID do Cliente do Aplicativo Azure
        - Segredo do Cliente do Aplicativo Azure
        - Ponto de extremidade da Visibilidade de Estoque

            Para obter mais informações sobre essa variável, consulte a seção [Configurar integração da visibilidade de estoque](#setup-inventory-visibility-integration) mais adiante neste tópico.

        ![Gatilho de configurações.](media/configuration-trigger.png "Gatilho de configurações")

    1. Selecione **Ativar**.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Instalar o suplemento

Para instalar o Suplemento Visibilidade de Estoque, faça o seguinte:

1. Entre no portal [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Na home page, selecione o projeto no qual seu ambiente foi implantado.
1. Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.
1. Na página ambiente, role para baixo até ver a seção **Suplementos do ambiente** na seção **Integração do Power Platform**, em que você pode encontrar o nome do ambiente do Dataverse.
1. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.

    ![A página do ambiente no LCS.](media/inventory-visibility-environment.png "A página do ambiente no LCS")

1. Selecione o link **Instalar um novo suplemento**. Uma lista dos suplementos disponíveis será aberta.
1. Selecione **Visibilidade de Estoque** na lista.
1. Insira valores para os seguintes campos no seu ambiente:

    - **ID de aplicativo AAD (cliente)**
    - **ID de locatário do AAD**

    ![Página de configuração do suplemento.](media/inventory-visibility-setup.png "Página de configuração do suplemento")

1. Concorde com os termos e condições, marcando a caixa de seleção **Termos e condições**.
1. Selecione **Instalar**. O status do suplemento será mostrado como **Instalando**. Após a conclusão, atualize a página para ver a alteração do status para **Instalado**.

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a>Desinstalar o suplemento

Para desinstalar o suplemento, selecione **Desinstalar**. Quando você atualizar o LCS, o Suplemento de Visibilidade de Estoque será removido. O processo de desinstalação remove o registro do suplemento e também inicia um trabalho para limpar todos os dados comerciais armazenados no serviço.

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a>Consumir dados de estoque disponível do Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implantar o pacote de integração de Visibilidade de Estoque

Se você estiver executando o Supply Chain Management versão 10.0.17 ou anterior, contate a equipe de suporte de integração da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter o arquivo de pacote. Em seguida, implante o pacote no LCS.

> [!NOTE]
> Se ocorrer um erro de incompatibilidade de versão durante a implantação, você deverá importar manualmente o projeto X++ no ambiente de desenvolvimento. Em seguida, crie o pacote implantável no ambiente de desenvolvimento e implante-o no ambiente de produção.
> 
> O código está incluído no Supply Chain Management versão 10.0.18. Se você estiver executando essa versão ou posterior, a implantação não será necessária.

Verifique se os recursos a seguir estão ativados no ambiente do Supply Chain Management. (Por padrão, eles são ativados.)

| Descrição do recurso | Versão de código | Alternar classe |
|---|---|---|
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSum | 10.0.11 | InventUseDimOfInventSumToggle |
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurar a integração da Visibilidade de Estoque

1. No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative o recurso **Integração da Visibilidade de Estoque**.
1. Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de Integração da Visibilidade de Estoque** e insira a URL do ambiente em que você está executando a Visibilidade de Estoque.

    Localize a região do Azure do ambiente do LCS e insira a URL. A URL tem o seguinte formato:

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    Por exemplo, se você estiver na Europa, o ambiente terá uma das seguintes URLs:

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    As regiões a seguir estão disponíveis no momento.

    | Região do Azure | Nome curto da região |
    |---|---|
    | Leste da Austrália | eau |
    | Sudeste da Austrália | seau |
    | Canadá Central | cca |
    | Leste do Canadá | eca |
    | Norte da Europa | neu |
    | Oeste da Europa | weu |
    | Leste dos EUA | eus |
    | Oeste dos EUA | wus |

1. Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho. Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a>A API pública do Suplemento Visibilidade de Estoque

A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade específicos para integração. Ela oferece suporte a três tipos de interação principais:

- Lançar alterações de estoque disponíveis no suplemento a partir de um sistema externo
- Consultar as quantidades disponíveis no momento a partir de um sistema externo
- Sincronização automática com o estoque disponível do Supply Chain Management

A sincronização automática não faz parte da API pública. Ela é tratada em segundo plano para ambientes em que o suplemento Visibilidade de Estoque está habilitado.

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autenticação

O token de segurança da plataforma é usado para chamar o suplemento Visibilidade de Estoque. Portanto, você deve gerar um token *Azure Active Directory (Azure AD)* usando o aplicativo Azure AD. Você deve usar o token Azure AD para obter o *token de acesso* do serviço de segurança.

Obtenha um token de serviço de segurança da seguinte forma:

1. Entre no portal do Azure e use-o para localizar `clientId` e `clientSecret` para o aplicativo Supply Chain Management.
1. Busque um token do Azure Active Directory (`aadToken`) enviando uma solicitação HTTP com as seguintes propriedades:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Método** - `GET`
    - **Conteúdo do corpo (dados de formulário)**:

        | key | valor |
        | --- | --- |
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resource | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Você receberá um `aadToken` em resposta, que se parece com o seguinte exemplo.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formule uma solicitação JSON que se parece com a seguinte:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Onde:
    - O valor `client_assertion` deve ser o `aadToken` que recebeu na etapa anterior.
    - O valor de `context` deve ser a ID do ambiente em que deseja implantar o suplemento.
    - Defina todos os demais valores conforme exibido no exemplo.

1. Envie uma solicitação HTTP com as seguintes propriedades:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Método** - `POST`
    - **Cabeçalho HTTP** – inclua a versão da API (a chave é `Api-Version` e o valor é `1.0`)
    - **Conteúdo do corpo** – inclua a solicitação JSON criada na etapa anterior.

1. Você receberá um `access_token` em resposta. É disso que você precisará como um token de portador para chamar a API da Visibilidade de Estoque. Veja aqui um exemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a>Solicitação de exemplo

Para sua referência, veja aqui um exemplo de solicitação de HTTP. Você pode usar qualquer ferramenta ou linguagem de programação para enviar essa solicitação, como ``Postman``.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a>Configurar a API da Visibilidade de Estoque

Antes de usar o serviço, você deve concluir as configurações descritas nas subseções a seguir. A configuração pode variar com base nos detalhes do seu ambiente. Ela inclui principalmente quatro partes:

- [Particionamento](#partitioning)
- [Configurações de dimensões](#dimension-configurations)
- [Indexando](#indexing)
- [Medida personalizada](#custom-measurement)

#### <a name="partitioning"></a>Particionamento

O particionamento pode influenciar significativamente o desempenho da API da Visibilidade de Estoque. É uma boa ideia definir um esquema que permita pequenos agrupamentos de dados e, ao mesmo tempo, permita consultas de dados significativas.

A `organizationId` (`dataAreaId` no Supply Chain Management) sempre fará parte do particionamento e, por padrão, a Visibilidade de Estoque é configurada para particionar por dimensões como *Local + Localização*. Isso significa que o serviço sempre deve ser consultado com essas dimensões definidas nos filtros.

> [!NOTE]
> *Local* e *Localização* são duas dimensões padrão gerais na Visibilidade de Estoque. No Supply Chain Management, essas dimensões são chamadas de *Local* (`InventSiteId`) e *Depósito* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configurações de dimensões

A Visibilidade de Estoque fornecerá uma lista de dimensões padrão gerais para habilitar a integração de sistemas de várias fontes.

A tabela a seguir lista as dimensões de estoque que serão os nomes de dimensão padrão na Visibilidade de Estoque.

| Tipo de dimensão | Nome da dimensão |
|---|---|
| Produto | `ColorId` |
| Produto | `SizeId` |
| Produto | `StyleId` |
| Produto | `ConfigId` |
| Rastreamento | `BatchId` |
| Rastreamento | `SerialId` |
| Localização | `LocationId` |
| Localização | `SiteId` |
| Status do Estoque | `StatusId` |
| Específico do Depósito | `WMSLocationId` |
| Específico do Depósito | `WMSPalletId` |
| Específico do Depósito | `LicensePlateId` |

> [!NOTE]
> O tipo de dimensão listado na tabela anterior é somente para referência. Não é necessário definir o tipo de dimensão na Visibilidade de Estoque.

Se uma dimensão personalizada existir e precisar fluir para um valor padrão quando consumida pela Visibilidade de Estoque, você poderá configurar o nome **Dimensão personalizada** na Visibilidade de Estoque.

Os sistemas externos acessam a Visibilidade de Estoque por meio de APIs RESTful que habilitam informações de disponibilidade sobre determinados conjuntos de dimensões a serem consultadas. Para a integração, a Visibilidade de Estoque permite configurar a *fonte de dados do canal externo* e a dimensão de origem para as *dimensões de destino* na Visibilidade de Estoque.

As dimensões de destino devem ser uma das seguintes opções:

- Dimensões padrão na Visibilidade de Estoque
- Dimensões personalizadas

A finalidade da configuração de dimensões é padronizar a integração de vários sistemas para a consulta em dimensões e o evento de lançamento com dimensões.

#### <a name="indexing"></a>Indexando

Na maioria das vezes, a consulta de estoque disponível não só estará no nível "total" mais alto, mas talvez você queira ver resultados agregados com base nas dimensões de estoque.

A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure os índices, que se baseiam na dimensão ou na combinação das dimensões.

> [!NOTE]
> No momento, só é possível configurar índices para, no máximo, cinco. É necessário considerar cuidadosamente qual dimensão ou combinação de dimensões você usará antes da implementação para garantir que ela atenderá às suas necessidades comerciais. Por exemplo, se você quiser consultar produtos da seguinte maneira:

- Consultar o produto agregado disponível por meio das dimensões *Cor* e *Tamanho*.
- Em alguns casos, você só deseja consultar o produto no total.

Você teria dois índices definidos da seguinte forma:

- `["ColorId", "SizeId"]`
- `[]`

O colchete vazio agregará com base na ID do produto na partição.

A indexação define como você pode agrupar os resultados com base na configuração de consulta `groupBy`. Nesse caso, se você não definir nenhum valor `groupBy`, obterá totais por `productid`. Caso contrário, se você definir `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obterá várias linhas retornadas, com base nas diferentes combinações de cor e tamanho no sistema.

Você pode colocar os critérios de consulta no corpo da solicitação.

Veja uma consulta de exemplo no produto com combinação de cor e tamanho.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

No campo `filters`, somente o `ProductId` permite a inserção de vários valores no momento. Se o `ProductId` for uma matriz vazia, todos os produtos serão consultados.

#### <a name="custom-measurement"></a>Medida personalizada

As quantidades de medida padrão estão vinculadas ao Supply Chain Management. No entanto, talvez você deseje ter uma quantidade composta de uma combinação das medidas padrão. Para isso, você pode ter uma configuração de quantidades personalizadas, que será adicionada à saída das consultas de disponibilidade.

A funcionalidade simplesmente permite definir um conjunto de medidas que será adicionado e/ou um conjunto de medidas que será subtraído para formar a medida personalizada.

Por exemplo, com a seguinte condição de consulta, você configurará a quantidade de medidas personalizadas como `MyCustomAvailableforReservation` para ser consumida pelo sistema de consumo.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Sistema de consumo | Medidas calculadas | Fonte de dados | Modificador | Tipo de cálculo do modificador |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Subtração |

Com isso, a consulta na quantidade de medidas personalizadas retornará a seguinte saída.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

A saída `MyCustomAvailableforReservation` se baseia na configuração de cálculo nas medidas personalizadas como:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Lançar alterações de disponibilidade

A URL exata na qual o evento será lançado dependerá da sua região geográfica. Ela terá a forma:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Quando autenticada, essa URL pode ser usada junto com o método HTTP `POST` para enviar eventos de alteração de disponibilidade para o serviço.

Um cabeçalho especial é usado para a comunicação com os serviços do Dynamics 365 por meio de solicitações HTTP, indicando a ID de ambiente da instância do Supply Chain Management à qual os dados estão vinculados. Por exemplo:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Exemplo de consulta de lançamento de alterações de disponibilidade 1

Este exemplo mostra um cenário no qual você definirá a configuração de dimensões no Power Apps.

Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas. O sistema converterá automaticamente as dimensões personalizadas em dimensões base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Exemplo de consulta de lançamento de alterações de disponibilidade 2

Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base. Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource` é nulo, vazio ou um espaço em branco.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Propriedades de campo do documento JSON

Os campos dos exemplos de consulta JSON fornecidos anteriormente têm as propriedades listadas na tabela a seguir.

| ID do campo | descrição |
|---|---|
| `id` | Uma ID exclusiva para o evento de alteração específico. Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o reenvio do evento não resultará no mesmo evento sendo contado duas vezes no sistema. |
| `organizationId` | O identificador da organização vinculada ao evento. Isso é mapeado para as IDs de áreas de dados ou organizações do Supply Chain Management. |
| `productId` | O identificador do produto em questão. |
| `quantity` | A quantidade pela qual a disponibilidade precisa ser alterada. Se, por exemplo, 10 novos bagels forem adicionados a uma prateleira, esse valor será 10. Se 3 bagels forem removidos da prateleira ou vendidos, esse valor será -3. |
| `dimensionDataSource` | A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento. Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada. Com a configuração de dimensões, a Visibilidade de Estoque pode mapear as dimensões personalizadas para as dimensões padrão gerais. Se a `dimensionDataSource` não estiver especificada, você só poderá usar as dimensões padrão gerais nas suas consultas.   |
| `dimensions` | Um recipiente dinâmico de pares de chave/valor. Eles serão mapeados para algumas das dimensões no Supply Chain Management, mas você também pode adicionar dimensões personalizadas (como *Origem*) que podem indicar se o evento é proveniente do Supply Chain Management ou de um sistema externo. |

### <a name="querying-current-on-hand"></a>Consultar a disponibilidade atual

O ponto de extremidade para consultar a disponibilidade atual terá uma URL semelhante:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Ela será consultada com o método HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Exemplo de consulta da disponibilidade atual 1

Este exemplo mostra um cenário no qual você já concluiu a configuração de dimensões no Power Apps.

Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas. O sistema converterá automaticamente as dimensões personalizadas em dimensões base. Você pode especificar a `DimensionDataSource` em `filters` e especificar dimensões personalizadas em `filters` e `groupByValues`. O sistema converterá automaticamente as dimensões personalizadas em dimensões base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Exemplo de consulta da disponibilidade atual 2

Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base. Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource`, em `filters`, é nulo, vazio ou um espaço em branco.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exemplo de retorno de resultado

As consultas mostradas nos exemplos anteriores poderiam retornar um resultado como este.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Observe que os campos de quantidades estão estruturados como um dicionário de medidas e seus valores associados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
