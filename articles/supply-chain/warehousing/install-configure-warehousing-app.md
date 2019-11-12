---
title: Visão geral da instalação e configuração do aplicativo de depósito
description: Este tópico descreve como instalar e configurar o aplicativo Dynamics 365 for Finance and Operations – Warehousing.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f629fffc5c424c244a25bb8faef0435814398ee1
ms.sourcegitcommit: 4aac45c84b87f463b22b318f5f6f729f8d737090
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2548959"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>Visão geral da instalação e configuração do aplicativo de depósito

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Este tópico descreve como configurar o depósito para implantações na nuvem. Se quiser saber como configurar o depósito para implantações locais, consulte [Depósito para implantações locais](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Este tópico descreve como instalar e configurar o aplicativo Dynamics 365 for Finance and Operations – Warehousing.

O aplicativo Warehousing está disponível na Google Play Store e na Windows Store. Para a versão atual do Dynamics 365 Supply Chain Management, esse aplicativo é fornecido como um componente autônomo, o que significa a autoimplantação em dispositivos usados para tarefas de depósito. Para usar o aplicativo, você deve baixá-lo em cada dispositivo e configurá-lo para conectar-se ao seu ambiente do Supply Chain Management. Este tópico descreve como instalar o aplicativo em seus dispositivos. Também explica como configurar o aplicativo para conectar-se ao seu ambiente do Supply Chain Management.

## <a name="prerequisites"></a>Pré-requisitos
O aplicativo está disponível em sistemas operacionais Android e Windows. Para usar este aplicativo, você deve ter um dos sistemas operacionais suportados instalados em seus dispositivos. Você também deve ter uma das seguintes versões com suporte. Use as informações na seguinte tabela para avaliar se o ambiente do hardware e o software está pronto para oferecer suporte à instalação.

| Plataforma                    | Versão                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0, 9.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (todas as versões)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, versão 1611 <br>- ou - <br>Microsoft Dynamics AX versão 7.0/7.0.1 e atualização 2 da plataforma do Microsoft Dynamics AX com hotfix KB 3210014 |

## <a name="get-the-app"></a>Obter o aplicativo
-   Windows (UWP)
     - [Finance and Operations - Warehousing na Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations - Warehousing na Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> A Zebra App Gallery foi desativada, o que significa que o aplicativo Warehousing não está mais disponível para download nesse local.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Criar um aplicativo de serviço Web no Azure Active Directory
Para habilitar o aplicativo para interagir com um servidor específico do Supply Chain Management, registre um aplicativo de serviço Web em um Azure Active Directory para o locatário do Supply Chain Management. Por motivo de segurança, recomendamos que você crie um aplicativo de serviço Web para cada dispositivo que você usar. Para criar uma solicitação de serviço da Web no Azure Active Directory (Azure AD), conclua as seguintes etapas:

1.  Em um navegador da Web, vá para <https://portal.azure.com>.
2.  Insira o nome e a senha do usuário que tem acesso à assinatura do Azure.
3.  No Portal do Azure, no painel de navegação esquerdo, clique em **Azure Active Directory**.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Verifique se a instância do Active Directory é a mesma usada pelo Supply Chain Management.
5.  Na lista, clique em **Registros de aplicativos**. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  No painel superior, clique em **Novo registro**. O **assistente Registrar um aplicativo** é iniciado.
7.  Insira um nome para o aplicativo e selecione **Contas somente neste diretório organizacional**. Clique em **Registrar**.  [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  O novo registro de aplicativo será aberto. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Lembre-se da **ID do aplicativo**, você precisará dela posteriormente. A **ID do aplicativo** será mencionada posteriormente como **ID do cliente**.
10. Clique em **Certificado e segredos** no painel **Gerenciar** . Clique em **Novo segredo do cliente**. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)
11. Crie uma chave inserindo uma descrição de chave e uma duração na seção **Senhas**. Clique em **Adicionar** e copie a chave. Esta chave será mencionada posteriormente como **Segredo do cliente**. [![WMA-06-active-directory-save-key](./media/WMA-06-active-directory-save-key.png)](./media/WMA-06-active-directory-save-key.png)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Criar e configurar uma conta de usuário no Supply Chain Management
Para habilitar o Supply Chain Management para usar seu aplicativo do Azure AD, é necessário concluir as seguintes etapas de configuração:

1.  Crie um usuário que corresponda às credenciais de usuário do aplicativo Warehousing.
    1.  Vá para **Administração do sistema** &gt; **Comum** &gt; **Usuários**.
    2.  Crie um novo usuário.
    3.  Atribua o usuário do dispositivo móvel do Warehouse, conforme mostrado na seguinte captura de tela. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Associe o aplicativo Azure Active Directory ao usuário do aplicativo Warehousing.
    1.  No Supply Chain Management, vá para **Administração do sistema** &gt; **Configuração** &gt; **Aplicativos do Azure Active Directory**.
    2.  Crie uma nova linha.
    3.  Insira o **ID do Cliente** (obtido na última seção), forneça um nome e selecione o usuário criado anteriormente. É recomendável marcar todos os dispositivos para que você possa remover facilmente o acesso deles ao Supply Chain Management desta página, em caso de perda. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurar o aplicativo
É necessário configurar o aplicativo no dispositivo para conectar-se ao servidor do Supply Chain Management através do aplicativo do Azure AD. Para fazer isso, conclua as seguintes etapas.

1.  No aplicativo, vá para **Configurações da conexão**.
2.  Desmarque o campo **Modo de demonstração**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Digite as seguintes informações: 
    + **ID do cliente do Azure Active Directory** - A ID do cliente é obtida na etapa 9 em "Criar um aplicativo de serviço Web no Active Directory". 
    + **Segredo do cliente do Azure Active Directory** - O segredo do cliente é obtido na etapa 11 em "Criar um aplicativo de serviços Web no Active Directory". 
    + **Recurso do Azure Active Directory** - O recurso do Azure AD exibe a URL raiz do Supply Chain Management. **Nota**: Este campo não termina com um caractere de barra (/). 
    + **Locatário do Azure Active Directory** - O locatário do Azure AD usado com o servidor do Supply Chain Management: `https://login.windows.net/your-AD-tenant-ID`. Por exemplo: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Nota**: Este campo não termina com um caractere de barra (/). 
    + **Empresa** - Insira a entidade legal no Supply Chain Management à qual você quer que o aplicativo se conecte. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Selecione o botão **Voltar** no canto superior esquerdo do aplicativo. O aplicativo agora se conectará ao seu servidor do Supply Chain Management e a tela de logon do trabalhador do depósito será exibida. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Para obter informações sobre como configurar o aplicativo Warehousing para digitalizar códigos de barras usando uma câmera em um dispositivo móvel, consulte [Digitalizar códigos de barras usando uma câmera no Dynamics 365 for Finance and Operations – Warehousing](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Remover acesso de um dispositivo
Em caso de perda ou comprometimento do dispositivo, será necessário remover o acesso dele ao Supply Chain Management. Estas etapas a seguir descrevem o processo recomendado para remover o acesso.

1.  Vá para **Administração do sistema** &gt; **Configuração** &gt; **Aplicativos do Azure Active Directory**.
2.  Exclua a linha que corresponde ao dispositivo para o qual você deseja remover o acesso. Lembre-se da **ID do cliente** usada para o dispositivo removido, você precisará dela posteriormente.
3.  Entre no portal do Azure em <https://portal.azure.com>.
4.  Clique no ícone **Active Directory** no menu esquerdo e verifique se está no diretório correto.
5.  Na lista, clique em **Registros de aplicativos** e, em seguida, clique no aplicativo que deseja configurar. A página **Configurações** aparecerá com informações de configuração.
6.  Verifique se a **ID do Cliente** do aplicativo é igual à da etapa 2 nesta seção.
7.  Clique no botão **Excluir** no painel superior.
8.  Clique em **Sim** na mensagem de confirmação.
