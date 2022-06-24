---
title: Instalar e conectar o aplicativo móvel Warehouse Management
description: Este artigo explica como instalar o aplicativo móvel Warehouse Management em cada um dos seus dispositivos móveis e configurá-lo para se conectar ao ambiente do Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9bd208ba78d28046782d03221b0f23471f56b574
ms.sourcegitcommit: 3f544f8671821be915b289a614e4e440bd38994f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8941756"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Instalar e conectar o aplicativo móvel Warehouse Management

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Este artigo descreve como configurar o novo aplicativo móvel Warehouse Management. Se você estiver procurando informações sobre como configurar o aplicativo de depósito antigo, (atualmente obsoleto), consulte [Instalar e conectar o aplicativo de depósito](../../supply-chain/warehousing/install-configure-warehousing-app.md).

Este artigo explica como baixar e instalar o aplicativo móvel Warehouse Management em cada um dos dispositivos móveis e como configurar o aplicativo para se conectar ao ambiente do Supply Chain Management. Você pode configurar os dispositivos manualmente ou importar as configurações de conexão usando um arquivo ou digitalizando um código QR.

## <a name="system-requirements"></a>Requisitos do sistema

O aplicativo móvel Warehouse Management está disponível nos sistemas operacionais Google Android e Windows. Para usar este aplicativo, você deve ter um dos sistemas operacionais instalados em seus dispositivos móveis:

- Windows 10 (Plataforma Universal do Windows \[UWP\]) Atualização de outubro de 2018 1809 (build 10.0.17763) ou posterior
- Android 4.4 ou posterior

## <a name="turn-warehouse-management-mobile-app-features-on-or-off-in-supply-chain-management"></a>Habilitar ou desabilitar recursos do Warehouse Management mobile app no Supply Chain Management

Para usar o aplicativo móvel Warehouse Management, o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* deve estar ativado no sistema. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="get-the-warehouse-management-mobile-app"></a>Baixe o aplicativo móvel Warehouse Management

Para implantações menores, em geral, você pode instalar o aplicativo em cada dispositivo da loja relevante e configurar manualmente a conexão com os ambientes utilizados.

Para implantações maiores, é possível automatizar a implantação e/ou a configuração de aplicativos, o que pode ser mais conveniente se você gerenciar vários dispositivos. Por exemplo, você pode usar uma solução de gerenciamento de dispositivo móvel e de gerenciamento de aplicativo móvel como o [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Para obter mais informações sobre como usar o Intune para adicionar aplicativos, consulte [Adicionar aplicativos ao Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Instalar o aplicativo de uma loja de aplicativos

A maneira mais fácil de instalar o aplicativo em um único dispositivo é instalá-lo de uma loja de aplicativos, que sempre fornece a versão mais recente geralmente disponível. O Microsoft Intune também pode buscar aplicativos nas lojas de aplicativos. Use um dos seguintes links para instalar o aplicativo a partir de uma loja de aplicativos:

- **Windows (UWP):** [Warehouse Management na Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Warehouse Management no Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Baixar o aplicativo do Microsoft App Center

Como alternativa para a instalação de uma loja de aplicativos, você pode baixar o aplicativo no Microsoft App Center. O App Center fornece pacotes instaláveis que podem ser sideload. Além da versão atual, o App Center também permite baixar versões anteriores e pode fornecer versões de visualização com recursos futuros que você pode testar. Para baixar versões atuais, anteriores ou preliminares do aplicativo móvel Warehouse Management do Microsoft App Center, use um dos seguintes links:

- **Windows (UWP):** [Warehouse Management (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Para obter instruções sobre como instalar um pacote baixado em um dispositivo do Windows e configurar os certificados necessários, consulte [Instalar um build no App Center](/appcenter/distribution/installation).

- **Android:** [Warehouse Management (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Se você baixar uma versão preliminar, serão necessárias algumas etapas adicionais para instalá-la. Para ver mais detalhes, consulte [Testar aplicativos Android](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Criar um aplicativo de serviço Web no Azure Active Directory

Para permitir que o aplicativo móvel Warehouse Management interaja com um determinado servidor do Supply Chain Management, registre um aplicativo de serviço Web para o locatário do Supply Chain Management no Azure Active Directory (Azure AD). O seguinte procedimento mostra uma forma de concluir esta tarefa. Para obter informações detalhadas e alternativas, consulte os links após o procedimento.

1. Em um navegador da Web, Acesse [https://portal.azure.com](https://portal.azure.com/).
1. Insira o nome e a senha do usuário que tem acesso à assinatura do Azure.
1. No portal do Azure, no painel de navegação à esquerda, selecione **Azure Active Directory**.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Azure Active Directory")

1. Certifique-se de que esteja trabalhando com a instância do Azure AD usada pelo Supply Chain Management.
1. Na lista **Gerenciar**, selecione **Registros de aplicativos**.

    ![Registros de aplicativos.](media/app-connect-azure-register.png "Registros de aplicativos")

1. Na barra de ferramentas, selecione **Novo registro** para abrir o assistente **Registrar um aplicativo**.
1. Insira um nome para o aplicativo, selecione **Contas somente neste diretório organizacional** e clique em **Registrar**.

    ![Assistente Registrar um aplicativo.](media/app-connect-azure-register-wizard.png "Assistente Registrar um aplicativo")

1. O novo registro de aplicativo é aberto. Anote o valor da **ID do aplicativo (cliente)**, porque você precisará dele mais tarde. A ID será mencionada posteriormente neste artigo como *ID do cliente*.

    ![ID do aplicativo (cliente).](media/app-connect-azure-app-id.png "ID do aplicativo (cliente)")

1. Clique na lista **Gerenciar**, selecione **Certificado e segredos**. Em seguida, selecione um dos seguintes botões, dependendo de como deseja configurar o aplicativo para autenticação. (Para obter mais informações, consulte a seção [Autenticar usando um certificado ou segredo do cliente](#authenticate) posteriormente neste artigo.)

    - **Carregar certificado** – carregar um certificado para usá-lo como segredo. Recomendamos essa abordagem porque é mais segura e porque também pode ser automatizada de modo mais completo. Se você estiver executando o aplicativo Warehouse Management em dispositivos Windows, anote o valor de **Impressão digital** exibido depois que você carrega o certificado. Você precisará desse valor ao configurar o certificado em dispositivos Windows.
    - **Novo segredo do cliente** – crie uma chave inserindo uma descrição de chave e uma duração na seção **Senhas** e depois clique em **Adicionar**. Faça uma cópia da chave e armazene-a com segurança.

    ![Certificado e segredos.](media/app-connect-azure-authentication.png "Certificado e segredos")

Para obter mais informações sobre como configurar os aplicativos de serviço no Azure AD, consulte os seguintes recursos:

- Para obter instruções que mostram como usar o Windows PowerShell para configurar aplicativos de serviço Web no Azure AD, consulte [Como: usar o Azure PowerShell para criar uma entidade de serviço com um certificado](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Para obter detalhes completos sobre como criar manualmente um aplicativo de serviço Web no Azure AD, consulte os seguintes artigos:

    - [Início rápido: Registrar um aplicativo na plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app)
    - [Como: Usar o portal para criar um aplicativo do Azure AD e uma entidade de serviço que possa acessar recursos](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a><a name="user-azure-ad"></a>Criar e configurar uma conta de usuário no Supply Chain Management

Para habilitar o Supply Chain Management para usar o aplicativo do Azure AD, siga estas etapas.

1. Crie um usuário que corresponda às credenciais de usuário do aplicativo Warehouse Management:

    1. No Supply Chain Management, Acesse **Administração do sistema \> Usuários \> Usuários**.
    1. Crie um usuário.
    1. Atribua a função *Usuário do dispositivo móvel do depósito* ao usuário.

    ![Atribua o usuário do dispositivo móvel do depósito.](media/app-connect-app-users.png "Atribua o usuário do dispositivo móvel do depósito")

1. Associe o aplicativo Azure AD ao usuário do aplicativo Warehouse Management:

    1. Acesse **Administração do sistema \> Configuração \> Aplicativos do Azure Active Directory**.
    1. No Painel de Ações, selecione **Novo** para criar uma linha.
    1. No campo **ID do Cliente**, insira a ID do cliente que você anotou na seção anterior.
    1. No campo **Nome**, insira um nome.
    1. No campo **ID de Usuário**, selecione a ID de usuário que você acaba de criar.

    ![Aplicativos do Azure Active Directory.](media/app-connect-aad-apps.png "Aplicativos do Azure Active Directory")

> [!TIP]
> Uma forma de usar essas configurações é criar uma ID de cliente no Azure para cada dispositivo físico e, em seguida, adicionar cada ID de cliente à página **Aplicativos do Azure Active Directory**. Se um dispositivo for perdido, você conseguirá remover facilmente o acesso ao Supply Chain Management removendo a ID do cliente dele dessa página. (Essa abordagem funciona porque as credenciais de conexão salvas em cada dispositivo também especificam uma ID de cliente, conforme descrito posteriormente neste artigo.)
>
> Além disso, as configurações padrão de idioma, formato de número e fuso horário para cada ID de cliente são estabelecidas pelas preferências definidas para o valor de **ID de Usuário** mapeado aqui. Portanto, você pode usar essas preferências para estabelecer configurações padrão para cada dispositivo ou coleção de dispositivos, com base na ID do cliente. No entanto, essas configurações padrão serão substituídas se também forem definidas para a *conta de usuário do aplicativo de depósito* que um trabalhador usa para entrar no dispositivo. (Para obter mais informações, consulte [Contas de usuário de dispositivo móvel](mobile-device-work-users.md).)

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Autenticar usando um certificado ou segredo do cliente

A autenticação com o Azure AD fornece uma forma segura de conectar um dispositivo móvel ao Supply Chain Management. Você pode autenticar usando um certificado ou um segredo do cliente. Caso pretenda importar configurações de conexão, recomendamos usar um certificado em vez de um segredo do cliente. Como o segredo do cliente deve sempre ser armazenado com segurança, não é possível importá-lo de um arquivo de configurações de conexão ou de um código QR, conforme descrito posteriormente neste artigo.

Os certificados podem ser usados como segredos para comprovar a identidade do aplicativo quando um token for solicitado. A parte pública do certificado é carregada no registro de aplicativos no portal do Azure, enquanto o certificado completo deve ser implantado em cada dispositivo no qual o aplicativo Warehouse Management está instalado. A sua organização é responsável por gerenciar o certificado em termos de rotação, e assim por diante. Você pode usar certificados autoassinados, mas deve sempre usar certificados não exportáveis.

É necessário disponibilizar o certificado localmente em cada dispositivo no qual o aplicativo Warehouse Management está sendo executado. Para obter informações sobre como gerenciar certificados para dispositivos controlados pelo Intune se você estiver usando o Intune, consulte [Usar certificados para autenticação no Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Configurar o Warehouse Management mobile app para unidades de escala de nuvem e borda

Algumas etapas adicionais são necessárias se você planeja executar o aplicativo Warehouse Management mobile app em uma unidade de escala de nuvem ou de borda. Para mais instruções, consultar [Configurar o Warehouse Management mobile app para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md).

## <a name="configure-the-application-by-importing-connection-settings"></a>Configurar o aplicativo ao importar configurações de conexão

Para facilitar a manutenção e implantação do aplicativo em vários dispositivos móveis, é possível importar as configurações de conexão em vez de inseri-las manualmente em cada dispositivo. Esta seção explica como criar e importar as configurações.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Criar um arquivo de configurações de conexão ou código QR

Você pode importar configurações de conexão de um arquivo ou código QR. Para ambas abordagens, é necessário primeiro criar um arquivo de configurações que usa o formato e a sintaxe do JavaScript Object Notation (JSON). O arquivo deve incluir uma lista de conexões que contém as conexões individuais que devem ser adicionadas. A tabela a seguir resume os parâmetros que você deve especificar no arquivo de configurações de conexão.

| Parâmetro | descrição |
|---|---|
| ConnectionName | Especifique o nome da configuração de conexão. O tamanho máximo é de 20 caracteres. Como esse valor é o identificador exclusivo de uma configuração de conexão, certifique-se de que ele seja exclusivo na lista. Se já houver uma conexão com o mesmo nome no dispositivo, ela será substituída pelas configurações do arquivo importado. |
| ActiveDirectoryClientAppId | Especifique a ID do cliente para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Especifique a URL raiz do Supply Chain Management. |
| ActiveDirectoryTenant | Especifique o nome de domínio do Azure AD que você está usando com o servidor do Supply Chain Management. Esse valor tem o formulário `https://login.windows.net/<your-Azure-AD-domain-name>`. Este é um exemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`. Para obter mais informações sobre como encontrar o nome de domínio do Azure AD, consulte [Localizar IDs importantes para um usuário](/partner-center/find-ids-and-domain-names). |
| Empresa | Especifique a entidade legal no Supply Chain Management à qual você quer que o aplicativo se conecte. |
| ConnectionType | (Opcional) Especifique se a configuração de conexão deve usar um certificado ou um segredo de cliente para se conectar a um ambiente. Os valores válidos são *"certificate"* e *"clientsecret"*. O valor padrão é *"certificate"*.<p>**Observação:** não é possível importar segredos do cliente.</p> |
| IsEditable | (Opcional) Especifique se o usuário do aplicativo deve ter permissão para editar a configuração de conexão. Os valores válidos são *"true"* e *"false"*. O valor padrão é *"true"*. |
| IsDefault | (Opcional) Especifique se a conexão é a conexão padrão. Uma conexão definida como padrão será automaticamente pré-selecionada quando o aplicativo for aberto. Somente uma conexão pode ser definida como padrão. Os valores válidos são *"true"* e *"false"*. O valor padrão é *"false"*. |
| CertificateThumbprint | (Opcional) Para dispositivos Windows, é possível especificar a impressão digital do certificado para a conexão. Para dispositivos Android, o usuário do aplicativo deve selecionar o certificado na primeira vez em que uma conexão for usada. |

O exemplo a seguir mostra um arquivo de configurações de conexão válido que contém duas conexões. Como pode ver, a lista de conexões (chamada *"ConnectionList"* no arquivo) é um objeto que tem uma matriz que armazena cada conexão como um objeto. Cada objeto deve ser colocado entre chaves ({}) e separado por vírgulas, e a matriz deve estar entre colchetes (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Você pode salvar as informações como um arquivo JSON ou gerar um código QR que tenha o mesmo conteúdo. Se você salvar as informações como um arquivo, recomendamos salvá-lo usando o nome padrão, *connections.json*, principalmente se você o armazenar no local padrão em cada dispositivo móvel.

### <a name="save-the-connection-settings-file-on-each-device"></a>Salve o arquivo de configurações de conexão em cada dispositivo

Normalmente, você usará uma ferramenta ou um script de gerenciamento de dispositivo para distribuir os arquivos de configurações de conexão para cada dispositivo que estiver gerenciando. Se você usar o nome e o local padrão ao salvar o arquivo de configurações de conexão em cada dispositivo, o aplicativo Warehouse Management o importará automaticamente, mesmo durante a primeira execução depois que o aplicativo for instalado. Se você usar um nome ou local personalizado para o arquivo, o usuário do aplicativo deverá especificar os valores durante a primeira execução. No entanto, o aplicativo continuará usando o nome e o local especificado posteriormente.

Sempre que o aplicativo for iniciado, ele importará novamente as configurações de conexão do local anterior para determinar se houve alterações. O aplicativo atualizará somente conexões com nomes iguais aos das conexões no arquivo de configurações de conexão. As conexões criadas pelo usuário que usam nomes diferentes não serão atualizadas.

Não é possível remover uma conexão usando o arquivo de configurações de conexão.

Conforme foi mencionado, o nome do arquivo padrão é *connections.json*. O local do arquivo padrão depende de você estar usando um dispositivo Windows ou Android:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Geralmente, os caminhos são criados automaticamente após a primeira execução do aplicativo. No entanto, é possível criá-los manualmente caso precise transferir o arquivo de configurações de conexão para o dispositivo antes da instalação.

> [!NOTE]
> Se o aplicativo for desinstalado, o caminho padrão e o respectivo conteúdo serão removidos.

### <a name="import-the-connection-settings"></a>Importar as configurações de conexão

Siga estas etapas para importar configurações de conexão de um arquivo ou código QR.

1. Inicie o aplicativo Warehouse Management no dispositivo móvel. Na primeira vez que você iniciar o aplicativo, será exibida uma mensagem de boas-vindas. Selecione **Selecionar uma conexão**.

    ![Mensagem de boas-vindas.](media/app-configure-welcome-screen.png "Mensagem de boas-vindas")

1. Se você estiver importando as configurações de conexão de um arquivo e o nome e o local padrão tiverem sido usados ao salvá-lo, talvez o aplicativo já tenha encontrado o arquivo. Neste caso, pule para a etapa 4. Caso contrário, selecione **Configurar conexão** e Acesse a etapa 3.

    ![Configurar conexão.](media/app-configure-set-up-connection.png "Configurar conexão")

1. Na caixa de diálogo **Configuração de conexão**, selecione **Adicionar do arquivo** ou **Adicionar do código QR**, dependendo de como você deseja importar as configurações:

    - Se estiver importando as configurações de conexão de um arquivo, selecione **Adicionar do arquivo**, navegue até o arquivo no dispositivo local e selecione-o. Se você selecionar um local personalizado, o aplicativo o armazenará e o utilizará na próxima vez.
    - Se você estiver importando as configurações de conexão ao digitalizar um código QR, selecione **Adicionar do código QR**. O aplicativo solicita a permissão para usar a câmera do dispositivo. Depois de conceder a permissão, a câmera será iniciada para que você possa usá-la na digitalização. Dependendo da qualidade da câmera do dispositivo e da complexidade do código QR, pode ser difícil obter uma digitalização correta. Nesse caso, tente reduzir a complexidade do código QR gerando apenas uma conexão por código QR. (Atualmente, é possível usar somente a câmera do dispositivo para digitalizar o código QR.)

    ![Menu de configuração de conexão.](media/app-configure-connection-setup-flyout.png "Menu de configuração de conexão")

1. Quando as configurações de conexão são carregadas com êxito, a conexão selecionada é mostrada.

    ![Configurações de conexão carregadas.](media/app-configure-select-connection.png "Configurações de conexão carregadas")

1. Se você estiver usando um dispositivo Android e estiver usando um certificado para autenticação, o dispositivo solicitará a seleção do certificado.

    ![Solicitação Selecionar certificado em um dispositivo Android.](media/app-configure-select-certificate.png "Solicitação Selecionar certificado em um dispositivo Android")

1. O aplicativo se conecta ao servidor do Supply Chain Management e mostra a página de entrada.

    ![Página de entrada.](media/app-configure-sign-in-page.png "Página de entrada")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Configurar o aplicativo manualmente

Se você não tiver um arquivo ou código QR, é possível configurar o aplicativo manualmente no dispositivo para ele se conectar ao servidor do Supply Chain Management por meio do aplicativo do Azure AD.

1. Inicie o aplicativo Warehouse Management no dispositivo móvel.
1. Se o aplicativo for iniciado no **Modo de demonstração**, selecione **Configurações de conexão**. Se a página **Entrar** aparecer quando o aplicativo for iniciado, selecione **Alterar conexão**.
1. Selecione **Configurar conexão**.

    ![Configurar conexão.](media/app-configure-set-up-connection.png "Configurar conexão")

1. Selecione **Inserir manualmente**.

    ![Menu de configuração de conexão.](media/app-configure-connection-setup-flyout.png "Menu de configuração de conexão")

    A página **Nova conexão** aparece e mostra as configurações necessárias para inserir manualmente os detalhes da conexão.

    ![Campos de conexão manual.](media/app-configure-input-manually.png "Campos de conexão manual")

1. Digite as seguintes informações:

    - **Usar segredo do cliente** – Defina esta opção como _Sim_ para usar um segredo do cliente para autenticar com o Supply Chain Management. Defina como _Não_ para usar um certificado para autenticação. (Para obter mais informações, consulte a seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service) anterior deste artigo.)
    - **Nome da conexão** – Insira um nome para a nova conexão. O nome será exibido no campo **Selecionar conexão** na próxima vez em que abrir as configurações de conexão. O nome inserido deve ser exclusivo. (Em outras palavras, deve ser diferente de todos os demais nomes de conexão armazenados no seu dispositivo, se houver outros nomes de conexão armazenados nele.)
    - **ID do cliente do Active directory** – Insira a ID do cliente para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Segredo do cliente do Active directory** – Este campo estará disponível somente quando a opção **Usar segredo do cliente** estiver definida como _Sim_. Especifique o segredo do cliente para o qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Impressão digital do certificado do Active directory** – Este campo só estará disponível para dispositivos Windows e quando a opção **Usar segredo do cliente** estiver definida como _Não_. Especifique a impressão digital do certificado para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Recurso do Active directory** – Especifique a URL raiz do Supply Chain Management.

        > [!IMPORTANT]
        > Não finalize esse valor com uma barra (/).

    - **Locatário do Active directory** – Insira o nome de domínio do Azure AD que você está usando com o servidor do Supply Chain Management. Esse valor tem o formulário `https://login.windows.net/<your-Azure-AD-domain-name>`. Este é um exemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`. Para obter mais informações sobre como encontrar o nome de domínio do Azure AD, consulte [Localizar IDs importantes para um usuário](/partner-center/find-ids-and-domain-names).

        > [!IMPORTANT]
        > Não finalize esse valor com uma barra (/).

    - **Empresa** – Insira a entidade legal (empresa) no Supply Chain Management à qual você quer que o aplicativo se conecte.

1. Selecione o botão **Salvar** no canto superior direito da página.
1. Se você estiver usando um dispositivo Android e estiver usando um certificado para autenticação, o dispositivo solicitará a seleção do certificado.
1. O aplicativo se conecta ao servidor do Supply Chain Management e mostra a página de entrada.

## <a name="remove-access-for-a-device"></a>Remover acesso de um dispositivo

Em caso de perda ou comprometimento do dispositivo, será necessário remover o acesso dele ao Supply Chain Management. As etapas a seguir descrevem o processo recomendado para remover o acesso.

1. Acesse **Administração do sistema \> Configuração \> Aplicativos do Azure Active Directory**.
1. Exclua a linha que corresponde ao dispositivo para o qual você deseja remover o acesso. Anote a ID do cliente usada para o dispositivo, pois precisará dela mais tarde.

    Se você tiver registrado somente uma ID de cliente e vários dispositivos usarem a mesma ID de cliente, será necessário enviar novas configurações de conexão para esses dispositivos. Caso contrário, eles perderão o acesso.

1. Entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com/).
1. No painel de navegação à esquerda, selecione **Active Directory** e verifique se está no diretório correto.
1. Na lista **Gerenciar**, clique em **Registros de aplicativos** e, em seguida, selecione o aplicativo que deseja configurar. A página **Configurações** é exibida contendo informações de configuração.
1. Verifique se a ID do cliente do aplicativo é igual à ID do cliente para a qual fez uma anotação na etapa 2.
1. Na barra de ferramentas, selecione **Excluir**.
1. Na mensagem de confirmação exibida, selecione **Sim**.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurações do usuário do dispositivo móvel](mobile-device-user-settings.md)
- [Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management](step-icons-titles.md)
- [Configurar o Warehouse Management mobile app para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
