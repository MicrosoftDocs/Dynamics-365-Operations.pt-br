---
title: Detectar carrinhos abandonados e enviar notificações aos clientes
description: Este tópico descreve como personalizar o aplicativo de exemplo do conector de carrinho abandonado do Microsoft Dynamics 365 Commerce para detectar os carrinhos abandonados e enviar notificações por email de lembrete aos clientes.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1db4e988653aa55db2b18fb201edeafc4d16a1bc
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2022
ms.locfileid: "8489021"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Detectar carrinhos abandonados e enviar notificações aos clientes

[!include [banner](../includes/banner.md)]

Este tópico descreve como personalizar o aplicativo de exemplo do conector de carrinho abandonado do Microsoft Dynamics 365 Commerce para detectar os carrinhos abandonados e enviar notificações por email de lembrete aos clientes.

A possibilidade de recuperar receita e reter clientes por meio de notificações de carrinhos abandonados é uma capacidade importante à qual o Dynamics 365 Commerce oferece suporte. Personalizando o aplicativo de exemplo do conector de carrinho abandonado do Commerce, os varejistas podem acessar os carrinhos de compras no Retail Server que não foram modificados durante um período definido pelos varejistas. Esses carrinhos podem ser recuperados, aumentados com dados de produtos e clientes e transferidos para um provedor de email de marketing de terceiros que pode gerar notificações por email e enviá-las aos clientes.

A notificação por email de carrinho abandonado que os clientes recebem pode conter as seguintes informações:

- O nome do cliente.
- O sobrenome do cliente.
- O endereço de email do cliente.
- Uma URL que retorna o cliente ao seu carrinho.
- A moeda da transação.
- Uma lista de produtos no carrinho do cliente. Para cada produto, são incluídas as seguintes informações:

    - O nome de exibição do produto
    - A ID do produto (usada para montar uma URL para a página de descrição do produto)
    - Uma imagem do produto que pode ser redimensionada automaticamente para ajustar diferentes tamanhos de visor
    - Texto alternativo para a imagem do produto
    - O preço unitário do produto

## <a name="abandoned-cart-connector-sample"></a>Exemplo de conector de carrinho abandonado

Um modelo de conector que a Microsoft fornece pelo Kit de desenvolvimento do software (SDK) do Retail permite que as informações do carrinho abandonado sejam recuperadas e enviadas para um provedor de email de marketing de terceiros. Esse conector controla a comunicação com o Retail Server, usa o Azure Key Vault para segurança, manipula o agendamento da recuperação de carrinhos para um período especificado e recupera dados de ordem e de produtos. Ele também fornece um exemplo de implementação para uma integração com um provedor de email de marketing de terceiros. O conector é criado para comunicar-se com a [Emarsys](https://emarsys.com) imediatamente. No entanto, ele pode ser facilmente personalizado para integrar com outras soluções, como Constant Contact, Mailchimp e SendGrid.

A ilustração a seguir mostra os componentes do aplicativo de exemplo do conector de carrinho abandonado.

![Componentes do aplicativo de exemplo do conector de carrinho abandonado](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> Algumas regiões exigem que os clientes possam recusar ter seus dados de carrinho transferidos para um provedor de email de marketing ou solicitar que os dados sejam removidos. No entanto, a Microsoft não fornece essas opções para clientes. Portanto, se você planeja fazer negócios em regiões que exigem essas opções, será necessário fornecer a infraestrutura e as personalizações necessárias para rastrear as preferências dos clientes e, com base nelas, impedir que os dados dos clientes sejam transferidos para a plataforma de e-mail. Também é necessário que você defina um processo para limpar dados do cliente do provedor de email de marketing na solicitação do cliente.

## <a name="obtain-the-code-sample"></a>Obter o exemplo de código

O aplicativo de exemplo do conector de carrinho abandonado está incluído no SDK do Retail a partir da versão 10.0.16. O código pode ser encontrado em **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Para obter mais informações sobre o SDK do Retail e onde obtê-lo, consulte [Kit de desenvolvimento do software (SDK) do Retail](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Embora o código de exemplo tenha sido disponibilizado pela primeira vez nas compilações da versão 10.0.16, ele é compatível com as versões 10.0.13 e posteriores do Retail Server.

## <a name="prerequisites-and-dependencies"></a>Pré-requisitos e dependências

Antes de implantar e configurar o código de exemplo do conector de carrinho abandonado, os pré-requisitos a seguir devem ser atendidos.

### <a name="access-to-commerce-resources"></a>Acesso aos recursos comerciais

Para configurar e implantar o aplicativo do conector de carrinho abandonado, é necessário ter acesso aos seguintes recursos comerciais:

- Acesso de administrador ao Commerce Headquarters para seu ambiente
- Acesso ao projeto do Lifecycle Services (LCS) do Microsoft Dynamics para seu ambiente

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

O aplicativo do conector de carrinho abandonado usa o Azure Cosmos DB para rastrear as IDs e os carimbos de data/hora dos carrinhos que foram recuperados anteriormente. Você pode usar o Azure Cosmos DB para manter esses dados ou pode personalizar o exemplo de código para integrá-lo com outra opção de armazenamento de dados. Para obter mais informações sobre o Azure Cosmos DB, consulte [Bem-vindo ao Azure Cosmos DB](/azure/cosmos-db/introduction).

Se você usar o Azure Cosmos DB, os seguintes pré-requisitos devem ser atendidos antes de executar o exemplo:

- É necessário ter uma conta ativa do Azure Cosmos DB. Se você não tiver uma conta, consulte [Criar uma conta de banco de dados](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- É necessário recuperar os valores de **URI** e **CHAVE PRIMÁRIA** (ou **CHAVE SECUNDÁRIA**) na folha **CHAVES** da sua conta do Azure Cosmos DB no portal do Azure. Para obter mais informações sobre como recuperar informações sobre o ponto de extremidade e a chave da sua conta do Azure Cosmos DB, consulte [Exibir, copiar e regenerar chaves e senhas de acesso](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

O aplicativo do conector de carrinho abandonado usa o Key Vault para armazenar os nomes e segredos dos diferentes componentes que exigem acesso seguro.

Para configurar um cofre de chaves, siga estas etapas.

1. Siga as instruções em [Gerenciar o Key Vault no Azure Stack Hub usando o portal](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Crie segredos para as seguintes informações:

    - Nome de usuário da interface de programação de aplicativos (API) da Emarsys e segredo da API
    - ID e segredo do aplicativo de carrinho abandonado

O código de exemplo do conector de carrinho abandonado usa as credenciais padrão do Azure para acessar o Key Vault. É necessário fornecer permissões de **Lista** e **Leitura** para a identidade que você planeja usar para acessar o Key Vault.

Para obter mais informações sobre as credenciais padrão do Azure, consulte a [Classe DefaultAzureCredential](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Criar uma ID de aplicativo de exemplo do conector de carrinho abandonado para o locatário do Azure AD

É necessário criar uma ID de aplicativo de exemplo do conector de carrinho abandonado para o locatário do Azure Active Directory. Para obter informações sobre como criar uma ID de aplicativo, consulte [Usar o portal para criar um aplicativo e uma entidade de serviço do Azure AD que possam acessar os recursos](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Adicionar a ID do aplicativo de exemplo do conector de carrinho abandonado à lista de permissões da API do Retail Server

Em seguida, é necessário adicionar a ID do aplicativo de exemplo do conector de carrinho abandonado à lista de permissões da API do Retail Server. Para obter informações sobre como adicionar uma ID de aplicativo à lista de permissões no Azure, consulte [Suporte para autenticação de serviço para serviço no Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Configurar o aplicativo de exemplo do conector de carrinho abandonado

Para configurar o aplicativo de exemplo do conector de carrinho abandonado, modifique o arquivo de configuração **appSettings.json** localizado na raiz do diretório **AbandonedCartDetectionSample**. As tabelas a seguir descrevem as propriedades do arquivo de configuração.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Propriedade    | Descrição |
| ----------- | ----------- |
| KeyVaultURI | O nome do Sistema de Nome de Domínio (DNS) do cofre de chaves que você está usando no portal do Azure. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Propriedade                                      | Descrição |
| --------------------------------------------- | ----------- |
| TenantId                                      | A ID de locatário do Azure AD do seu locatário do Azure. |
| RetailServerAudienceId                        | A ID do público-alvo do Retail Server. Você pode deixar o valor padrão. |
| AppIdKeyVaultSecretName                       | O nome do segredo que você criou para a ID do aplicativo de exemplo do conector de carrinho abandonado. |
| AppSecretKeyVaultSecretName                   | O nome do segredo que armazena o segredo do aplicativo para a ID do aplicativo de exemplo do conector de carrinho abandonado. |
| RetailServerUrl                               | A URL da instância do Retail Server. Esse valor pode ser encontrado no LCS. |
| OperatingUnitNumber                           | O número da unidade operacional (OUN). Esse valor pode ser encontrado no Commerce headquarters. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | O início do período dos carrinhos abandonados que você deseja recuperar. O valor é expresso como um número de minutos antes da hora atual. Por exemplo, defina esta propriedade como **120** para recuperar todos os carrinhos que foram modificados por último entre 120 minutos atrás e o final do período definido pela propriedade **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | O fim do período dos carrinhos abandonados que você deseja recuperar. O valor é expresso como um número de minutos antes da hora atual. Por exemplo, se a propriedade **IncludeAbandonedCartsModifiedSinceLastMinutes** for definida como **120**, defina esta propriedade como **30** para recuperar todos os carrinhos que foram modificados entre 120 minutos atrás e 30 minutos atrás. Na prática, essa propriedade define o período que você deseja esperar antes que um carrinho seja declarado abandonado. |
| ReturnToCartUrl                               | A URL do carrinho no site de comércio eletrônico, no formato usado no arquivo **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

O status do trabalho de recuperação do carrinho abandonado, as IDs do carrinho e os carimbos de data/hora modificados são armazenados no Azure Cosmos DB. Por padrão, as configurações no arquivo de configuração apontam para a instância do emulador local do Azure Cosmos DB. Ao implantar o conector na produção, é necessário atualizar essas configurações para que elas apontem para a instância do Azure Cosmos DB na sua assinatura do Azure. Para testes locais ou de área restrita, você pode usar o [Azure Cosmos DB Emulator](/azure/cosmos-db/local-emulator).

| Propriedade    | Descrição |
| ----------- | ----------- |
| EndPointUri | O URI do ponto de extremidade fornecido pelo Azure ou pelo emulador. |
| PrimaryKey  | A chave primária fornecida pelo Azure ou pelo emulador. |
| DatabaseId  | A ID do banco de dados. Você pode deixar o valor padrão ou fornecer o seu próprio. |
| ContainerId | A ID do contêiner. Você pode deixar o valor padrão ou fornecer o seu próprio. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Se você está integrando com um provedor de email de marketing diferente da Emarsys, será necessário estender a interface **IEmailProvider**, conforme apropriado, para comunicar-se com esse provedor.

| Propriedade                      | Descrição |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | A ID do registro de evento externo criado na Emarsys. Você pode encontrar o valor em **Configurações do Gatilho** na campanha criada para enviar notificações por email de carrinhos abandonados. |
| ApiUserNameKeyVaultSecretName | O nome da chave em que o nome de usuário da API da Emarsys está armazenado. |
| ApiSecretKeyVaultSecretName   | O nome da chave em que o segredo da API da Emarsys está armazenado. |
| EmarsysContactKeyId           | A ID da coluna de email no banco de dados de contatos da Emarsys. O valor padrão é **3** e não deve ser alterado. |

### <a name="mediaoptions"></a>MediaOptions

Se você estiver usando os recursos de comércio eletrônico no Commerce, poderá usar o gerenciamento de ativos digitais do Commerce para recuperar as imagens do produto. Para obter mais informações sobre os recursos do redimensionador de imagem no gerenciamento de ativos digitais, consulte [Configuração do visor ImageSettings](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Propriedade                             | Descrição |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | A URL raiz do gerenciador de ativos digitais do site. Você pode encontrar o valor na chave de propriedade **URL Base do Servidor de Mídia** nos perfis **Varejo e Comércio \> Configuração de canal \> Perfis de canal** no Commerce Headquarters. |
| ImageViewPorts                       | O nó de contêiner para configurações individuais do visor. |
| ImageViewPorts/viewport              | A definição do visor. Use esta propriedade para especificar os intervalos de largura para o visor, em pixels. Para obter um exemplo que mostra como essa propriedade é usada, consulte o arquivo de configuração **appSettings.json**. |
| ImageViewPorts/imageWidth            | A largura da imagem do visor, em pixels. |
| imageViewPorts/imageHeight           | A altura da imagem do visor, em pixels. |
| imageViewPorts/useForDefaultImageTag | Um valor **verdadeiro**/**falso** que indica se as dimensões de imagem definidas pelo visor devem ser usadas se a marca HTML `<picture>` não for compatível com um navegador da Web ou cliente de email. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
