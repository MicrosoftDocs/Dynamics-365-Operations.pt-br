---
title: Instalar e conectar o aplicativo móvel Gerenciamento de depósito
description: Este tópico explica como instalar o aplicativo móvel Gerenciamento de depósito em cada um dos seus dispositivos móveis e configurá-lo para se conectar ao ambiente do Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e2ffd12011b133bb13b69b49d6e894c6a887a8a0
ms.sourcegitcommit: bd53794cb94f8c1ce29a7d6102119a0975f155e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142314"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Instalar e conectar o aplicativo móvel Gerenciamento de depósito

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> Este tópico descreve como configurar o novo aplicativo móvel Gerenciamento de depósito, que está atualmente na versão preliminar pública. Se você estiver procurando informações sobre como configurar o aplicativo de depósito antigo, consulte [Instalar e conectar o aplicativo de depósito](../../supply-chain/warehousing/install-configure-warehousing-app.md).

A versão preliminar pública do aplicativo móvel Gerenciamento de depósito está disponível para download no Microsoft App Center. Ele é fornecido como um componente autônomo. Portanto, você deve baixá-lo em cada dispositivo e configurá-lo para se conectar ao ambiente do Microsoft Dynamics 365 Supply Chain Management.

Este tópico explica como instalar o aplicativo móvel Gerenciamento de depósito em cada um dos seus dispositivos móveis e configurá-lo para se conectar ao ambiente do Supply Chain Management. Você pode configurar os dispositivos manualmente ou importar as configurações de conexão usando um arquivo ou digitalizando um código QR.

## <a name="system-requirements"></a>Requisitos do sistema

O aplicativo móvel Gerenciamento de depósito está disponível nos sistemas operacionais Google Android e Windows. Para usar este aplicativo, você deve ter um dos sistemas operacionais instalados em seus dispositivos móveis:

- Windows 10 (Plataforma Universal do Windows \[UWP\]) Atualização de outubro de 2018 1809 (build 10.0.17763) ou posterior
- Android 4.4 ou posterior

## <a name="turn-on-the-feature"></a>Ativar o recurso

Para que você possa usar o aplicativo, ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *configurações do usuário, ícones e títulos de etapa do novo aplicativo de depósito*

## <a name="get-the-warehouse-management-mobile-app"></a>Baixe o aplicativo móvel de Gerenciamento de depósito

Use um dos seguintes links para baixar o aplicativo:

- **Windows (UWP):** [Programa de versão prévia do App Center - Windows](https://go.microsoft.com/fwlink/?linkid=2154406)

    Como este aplicativo é um aplicativo em versão prévia, são necessárias algumas etapas adicionais para instalá-lo. Para ver mais detalhes, consulte [Instalar uma build no App Center](https://docs.microsoft.com/appcenter/distribution/installation).

- **Android:** [Programa de versão prévia do App Center - Android](https://go.microsoft.com/fwlink/?linkid=2154613)

    Como este aplicativo é um aplicativo em versão prévia, são necessárias algumas etapas adicionais para instalá-lo. Para ver mais detalhes, consulte [Testar aplicativos Android](https://docs.microsoft.com/appcenter/distribution/testers/testing-android).

Para implantações menores, você pode instalar o aplicativo da loja relevante em cada dispositivo e configurar manualmente a conexão com os ambientes que estiver usando. No entanto, você também pode automatizar a implantação e/ou a configuração de aplicativos. Essa abordagem pode ser conveniente se você gerencia vários dispositivos e estiver usando um gerenciamento de dispositivos móveis e uma solução de gerenciamento de aplicativos móveis, como o [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune). Para obter mais informações sobre como usar o Intune para adicionar aplicativos, consulte [Adicionar aplicativos ao Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-add).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Criar um aplicativo de serviço Web no Azure Active Directory

Para permitir que o aplicativo móvel Gerenciamento de depósito interaja com um determinado servidor do Supply Chain Management, registre um aplicativo de serviço Web para o locatário do Supply Chain Management no Azure Active Directory (Azure AD). O seguinte procedimento mostra uma forma de concluir esta tarefa. Para obter informações detalhadas e alternativas, consulte os links após o procedimento.

1. Em um navegador da Web, vá para [https://portal.azure.com](https://portal.azure.com/).
1. Insira o nome e a senha do usuário que tem acesso à assinatura do Azure.
1. No portal do Azure, no painel de navegação à esquerda, selecione **Azure Active Directory**.

    ![Azure Active Directory](media/app-connect-azure-aad.png "Azure Active Directory")

1. Certifique-se de que esteja trabalhando com a instância do Azure AD usada pelo Supply Chain Management.
1. Na lista **Gerenciar**, selecione **Registros de aplicativos**.

    ![Registros de aplicativos](media/app-connect-azure-register.png "Registros de aplicativos")

1. Na barra de ferramentas, selecione **Novo registro** para abrir o assistente **Registrar um aplicativo**.
1. Insira um nome para o aplicativo, selecione **Contas somente neste diretório organizacional** e clique em **Registrar**.

    ![Assistente Registrar um aplicativo](media/app-connect-azure-register-wizard.png "Assistente Registrar um aplicativo")

1. O novo registro de aplicativo é aberto. Anote o valor da **ID do aplicativo (cliente)**, porque você precisará dele mais tarde. A ID será mencionada posteriormente neste tópico como *ID do cliente*.

    ![ID do aplicativo (cliente)](media/app-connect-azure-app-id.png "ID do aplicativo (cliente)")

1. Clique na lista **Gerenciar**, selecione **Certificado e segredos**. Em seguida, selecione um dos seguintes botões, dependendo de como deseja configurar o aplicativo para autenticação. (Para obter mais informações, consulte a seção [Autenticar usando um certificado ou segredo do cliente](#authenticate) posteriormente neste tópico.)

    - **Carregar certificado** – carregar um certificado para usá-lo como segredo. Recomendamos essa abordagem porque é mais segura e porque também pode ser automatizada de modo mais completo. Se você estiver executando o aplicativo Gerenciamento de depósito em dispositivos Windows, anote o valor de **Impressão digital** exibido depois que você carrega o certificado. Você precisará desse valor ao configurar o certificado em dispositivos Windows.
    - **Novo segredo do cliente** – crie uma chave inserindo uma descrição de chave e uma duração na seção **Senhas** e depois clique em **Adicionar**. Faça uma cópia da chave e armazene-a com segurança.

    ![Certificado e segredos](media/app-connect-azure-authentication.png "Certificado e segredos")

Para obter mais informações sobre como configurar os aplicativos de serviço no Azure AD, consulte os seguintes recursos:

- Para obter instruções que mostram como usar o Windows PowerShell para configurar aplicativos de serviço Web no Azure AD, consulte [Como: usar o Azure PowerShell para criar uma entidade de serviço com um certificado](https://docs.microsoft.com/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Para obter detalhes completos sobre como criar manualmente um aplicativo de serviço Web no Azure AD, consulte os seguintes tópicos:

    - [Início rápido: Registrar um aplicativo na plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
    - [Como: Usar o portal para criar um aplicativo do Azure AD e uma entidade de serviço que possa acessar recursos](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Criar e configurar uma conta de usuário no Supply Chain Management

Para habilitar o Supply Chain Management para usar o aplicativo do Azure AD, siga estas etapas.

1. Crie um usuário que corresponda às credenciais de usuário do aplicativo Gerenciamento de depósito:

    1. No Supply Chain Management, vá para **Administração do sistema \> Usuários \> Usuários**.
    1. Crie um usuário.
    1. Atribua o usuário do dispositivo móvel do depósito.

    ![Atribua o usuário do dispositivo móvel do depósito](media/app-connect-app-users.png "Atribua o usuário do dispositivo móvel do depósito")

1. Associe o aplicativo Azure AD ao usuário do aplicativo Gerenciamento de depósito:

    1. Vá para **Administração do sistema \> Configuração \> Aplicativos do Azure Active Directory**.
    1. Criar uma linha.
    1. Insira a ID de cliente para a qual você criou uma nota na seção anterior, atribua um nome a ela e selecione o usuário que acabou de criar. Recomendamos marcar todos os dispositivos. Se um dispositivo for perdido, você conseguirá remover facilmente o acesso ao Supply Chain Management nessa página.

    ![Aplicativos do Azure Active Directory](media/app-connect-aad-apps.png "Aplicativos do Azure Active Directory")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Autenticar usando um certificado ou segredo do cliente

A autenticação com o Azure AD fornece uma forma segura de conectar um dispositivo móvel ao Supply Chain Management. Você pode autenticar usando um certificado ou um segredo do cliente. Caso pretenda importar configurações de conexão, recomendamos usar um certificado em vez de um segredo do cliente. Como o segredo do cliente deve sempre ser armazenado com segurança, não é possível importá-lo de um arquivo de configurações de conexão ou de um código QR, conforme descrito posteriormente neste tópico.

Os certificados podem ser usados como segredos para comprovar a identidade do aplicativo quando um token for solicitado. A parte pública do certificado é carregada no registro de aplicativos no portal do Azure, enquanto o certificado completo deve ser implantado em cada dispositivo no qual o aplicativo Gerenciamento de depósito está instalado. A sua organização é responsável por gerenciar o certificado em termos de rotação, e assim por diante. Você pode usar certificados autoassinados, mas deve sempre usar certificados não exportáveis.

É necessário disponibilizar o certificado localmente em cada dispositivo no qual o aplicativo Gerenciamento de depósito está sendo executado. Para obter informações sobre como gerenciar certificados para dispositivos controlados pelo Intune se você estiver usando o Intune, consulte [Usar certificados para autenticação no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Configurar o aplicativo ao importar configurações de conexão

Para facilitar a manutenção e implantação do aplicativo em vários dispositivos móveis, é possível importar as configurações de conexão em vez de inseri-las manualmente em cada dispositivo. Esta seção explica como criar e importar as configurações.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Criar um arquivo de configurações de conexão ou código QR

Você pode importar configurações de conexão de um arquivo ou código QR. Para ambas abordagens, é necessário primeiro criar um arquivo de configurações que usa o formato e a sintaxe do JavaScript Object Notation (JSON). O arquivo deve incluir uma lista de conexões que contém as conexões individuais que devem ser adicionadas. A tabela a seguir resume os parâmetros que você deve especificar no arquivo de configurações de conexão.

| Parâmetro | descrição |
|---|---|
| ConnectionName | Especifique o nome da configuração de conexão. O tamanho máximo é de 20 caracteres. Como esse valor é o identificador exclusivo de uma configuração de conexão, certifique-se de que ele seja exclusivo na lista. Se já houver uma conexão com o mesmo nome no dispositivo, ela será substituída pelas configurações do arquivo importado. |
| ActiveDirectoryClientAppId | Especifique a ID do cliente para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Especifique a URL raiz do Supply Chain Management. |
| ActiveDirectoryTenant | Especifique o locatário do Azure AD que você está usando com o servidor do Supply Chain Management. Esse valor tem o formulário `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Este é um exemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Empresa | Especifique a entidade legal no Supply Chain Management à qual você quer que o aplicativo se conecte. |
| ConnectionType | (Opcional) Especifique se a configuração de conexão deve usar um certificado ou um segredo de cliente para se conectar a um ambiente. Os valores válidos são *"certificate"* e *"clientsecret"*. O valor padrão é *'certificate'*.<p>**Observação:** não é possível importar segredos do cliente.</p> |
| IsEditable | (Opcional) Especifique se o usuário do aplicativo deve ter permissão para editar a configuração de conexão. Os valores válidos são *"true"* e *"false"*. O valor padrão é *true*. |
| IsDefault | (Opcional) Especifique se a conexão é a conexão padrão. Uma conexão definida como padrão será automaticamente pré-selecionada quando o aplicativo for aberto. Somente uma conexão pode ser definida como padrão. Os valores válidos são *"true"* e *"false"*. O valor padrão é *false*. |
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

Normalmente, você usará uma ferramenta ou um script de gerenciamento de dispositivo para distribuir os arquivos de configurações de conexão para cada dispositivo que estiver gerenciando. Se você usar o nome e o local padrão ao salvar o arquivo de configurações de conexão em cada dispositivo, o aplicativo Gerenciamento de depósito o importará automaticamente, mesmo durante a primeira execução depois que o aplicativo for instalado. Se você usar um nome ou local personalizado para o arquivo, o usuário do aplicativo deverá especificar os valores durante a primeira execução. No entanto, o aplicativo continuará usando o nome e o local especificado posteriormente.

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

1. Inicie o aplicativo Gerenciamento de depósito no dispositivo móvel. Na primeira vez que você iniciar o aplicativo, será exibida uma mensagem de boas-vindas. Selecione **Selecionar uma conexão**.

    ![Mensagem de boas-vindas](media/app-configure-welcome-screen.png "Mensagem de boas-vindas")

1. Se você estiver importando as configurações de conexão de um arquivo e o nome e o local padrão tiverem sido usados ao salvá-lo, talvez o aplicativo já tenha encontrado o arquivo. Neste caso, pule para a etapa 4. Caso contrário, selecione **Configurar conexão** e vá para a etapa 3.

    ![Configurar conexão](media/app-configure-set-up-connection.png "Configurar conexão")

1. Na caixa de diálogo **Configuração de conexão**, selecione **Adicionar do arquivo** ou **Adicionar do código QR**, dependendo de como você deseja importar as configurações:

    - Se estiver importando as configurações de conexão de um arquivo, selecione **Adicionar do arquivo**, navegue até o arquivo no dispositivo local e selecione-o. Se você selecionar um local personalizado, o aplicativo o armazenará e o utilizará na próxima vez.
    - Se você estiver importando as configurações de conexão ao digitalizar um código QR, selecione **Adicionar do código QR**. O aplicativo solicita a permissão para usar a câmera do dispositivo. Depois de conceder a permissão, a câmera será iniciada para que você possa usá-la na digitalização. Dependendo da qualidade da câmera do dispositivo e da complexidade do código QR, pode ser difícil obter uma digitalização correta. Nesse caso, tente reduzir a complexidade do código QR gerando apenas uma conexão por código QR. (Atualmente, é possível usar somente a câmera do dispositivo para digitalizar o código QR.)

    ![Menu de configuração de conexão](media/app-configure-connection-setup-flyout.png "Menu de configuração de conexão")

1. Quando as configurações de conexão são carregadas com êxito, a conexão selecionada é mostrada.

    ![Configurações de conexão carregadas](media/app-configure-select-connection.png "Configurações de conexão carregadas")

1. Se você estiver usando um dispositivo Android e estiver usando um certificado para autenticação, o dispositivo solicitará a seleção do certificado.

    ![Solicitação Selecionar certificado em um dispositivo Android](media/app-configure-select-certificate.png "Solicitação Selecionar certificado em um dispositivo Android")

1. O aplicativo se conecta ao servidor do Supply Chain Management e mostra a página de entrada.

    ![Página de entrada](media/app-configure-sign-in-page.png "Página de entrada")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Configurar o aplicativo manualmente

Se você não tiver um arquivo ou código QR, é possível configurar o aplicativo manualmente no dispositivo para ele se conectar ao servidor do Supply Chain Management por meio do aplicativo do Azure AD.

1. Inicie o aplicativo Gerenciamento de depósito no dispositivo móvel.
1. Se o aplicativo for iniciado no **Modo de demonstração**, selecione **Configurações de conexão**. Se a página **Entrar** aparecer quando o aplicativo for iniciado, selecione **Alterar conexão**.
1. Selecione **Configurar conexão**.

    ![Configurar conexão](media/app-configure-set-up-connection.png "Configurar conexão")

1. Selecione **Inserir manualmente**.

    ![Menu de configuração de conexão](media/app-configure-connection-setup-flyout.png "Menu de configuração de conexão")

    A página **Nova conexão** aparece e mostra as configurações necessárias para inserir manualmente os detalhes da conexão.

    ![Campos de conexão manual](media/app-configure-input-manually.png "Campos de conexão manual")

1. Digite as seguintes informações:

    - **Usar segredo do cliente** – Defina esta opção como _Sim_ para usar um segredo do cliente para autenticar com o Supply Chain Management. Defina como _Não_ para usar um certificado para autenticação. (Para obter mais informações, consulte a seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service) anterior deste tópico.)
    - **Nome da conexão** – Insira um nome para a nova conexão. O nome será exibido no campo **Selecionar conexão** na próxima vez em que abrir as configurações de conexão. O nome inserido deve ser exclusivo. (Em outras palavras, deve ser diferente de todos os demais nomes de conexão armazenados no seu dispositivo, se houver outros nomes de conexão armazenados nele.)
    - **ID do cliente do Active directory** – Insira a ID do cliente para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Segredo do cliente do Active directory** – Este campo estará disponível somente quando a opção **Usar segredo do cliente** estiver definida como _Sim_. Especifique o segredo do cliente para o qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Impressão digital do certificado do Active directory** – Este campo só estará disponível para dispositivos Windows e quando a opção **Usar segredo do cliente** estiver definida como _Não_. Especifique a impressão digital do certificado para a qual criou uma nota enquanto estava configurando o Azure AD na seção [Criar um aplicativo de serviço Web no Azure Active Directory](#create-service).
    - **Recurso do Active directory** – Especifique a URL raiz do Supply Chain Management.

        > [!IMPORTANT]
        > Não finalize esse valor com uma barra (/).

    - **Locatário do Active directory** – Insira o locatário do Azure AD que está usando com o servidor do Supply Chain Management. Esse valor tem o formulário `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Este é um exemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!IMPORTANT]
        > Não finalize esse valor com uma barra (/).

    - **Empresa** – Insira a entidade legal (empresa) no Supply Chain Management à qual você quer que o aplicativo se conecte.

1. Selecione o botão **Salvar** no canto superior direito da página.
1. Se você estiver usando um dispositivo Android e estiver usando um certificado para autenticação, o dispositivo solicitará a seleção do certificado.
1. O aplicativo se conecta ao servidor do Supply Chain Management e mostra a página de entrada.

## <a name="remove-access-for-a-device"></a>Remover acesso de um dispositivo

Em caso de perda ou comprometimento do dispositivo, será necessário remover o acesso dele ao Supply Chain Management. As etapas a seguir descrevem o processo recomendado para remover o acesso.

1. Vá para **Administração do sistema \> Configuração \> Aplicativos do Azure Active Directory**.
1. Exclua a linha que corresponde ao dispositivo para o qual você deseja remover o acesso. Anote a ID do cliente usada para o dispositivo, pois precisará dela mais tarde.

    Se você tiver registrado somente uma ID de cliente e vários dispositivos usarem a mesma ID de cliente, será necessário enviar novas configurações de conexão para esses dispositivos. Caso contrário, eles perderão o acesso.

1. Entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com/).
1. No painel de navegação à esquerda, selecione **Active Directory** e verifique se está no diretório correto.
1. Na lista **Gerenciar**, clique em **Registros de aplicativos** e, em seguida, selecione o aplicativo que deseja configurar. A página **Configurações** é exibida contendo informações de configuração.
1. Verifique se a ID do cliente do aplicativo é igual à ID do cliente para a qual fez uma anotação na etapa 2.
1. Na barra de ferramentas, selecione **Excluir**.
1. Na mensagem de confirmação exibida, selecione **Sim**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]