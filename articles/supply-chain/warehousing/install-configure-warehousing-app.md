---
title: "Instalação e configuração do Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing"
description: "Este tópico descreve como instalar e configurar o Microsoft Dynamics 365 for Finance and Operations - Warehousing."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 31e77b27d4bf95c997817b3a053b33119562adf8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Instalação e configuração do Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing

[!include[banner](../includes/banner.md)]


Este tópico descreve como instalar e configurar o Microsoft Dynamics 365 for Finance and Operations - Warehousing.

Finance and Operations - Warehousing é um aplicativo disponível na Play Google Store e na Windows Store. Para a versão atual do Finance and Operations, este aplicativo é fornecido como um componente autônomo, o que significa a auto-implantação de dispositivos usados para tarefas de depósito. Para usar o aplicativo em seu ambiente do Finance and Operations, você deve baixar o aplicativo em cada dispositivo e configurá-lo para conectar-se ao ambiente do Finance and Operations. Este tópico descreve como instalar o aplicativo em seus dispositivos. Também explica como configurar o aplicativo para conectar-se ao ambiente do Finance and Operations.

## <a name="prerequisites"></a>Pré-requisitos
O aplicativo está disponível em sistemas operacionais Android e Windows. Para usar este aplicativo, você deve ter um dos sistemas operacionais suportados instalados em seus dispositivos. Você também deve ter uma das seguintes versões suportadas do Finance and Operations. Use as informações na seguinte tabela para avaliar se o ambiente do hardware e o software está pronto para oferecer suporte à instalação.

| Plataforma                    | Versão                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (todas as versões)                                                                                                                                                   |
| Finance and Operations | Microsoft Finance and Operations versão 1611 <br>-ou- <br>Microsoft Dynamics Dynamics AX versão 7.0/7.0.1 e Microsoft Dynamics AX atualização da plataforma 2 com hotfix KB 3210014 |

## <a name="get-the-app"></a>Obter o aplicativo
-   Windows (UWP): - [Finance and Operations - Warehousing na Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android:
    - [Finance and Operations - Warehousing na Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations - Warehousing na Zebra App Gallery](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-active-directory"></a>Criar um aplicativo de serviço Web no Active Directory
Para habilitar o aplicativo para interagir com o servidor específico do Finance and Operations, é necessário registrar o aplicativo de serviço Web em um Azure Active Directory para o locatário do Finance and Operations. Por motivo de segurança, recomendamos que você crie um aplicativo de serviço Web para cada dispositivo que você usar. Para criar um aplicativo de serviço Web no Azure Active Directory (Azure AD), conclua as seguintes etapas:

1.  Em um navegador da Web, vá para <https://manage.windowsazure.com>.
2.  Insira o nome e a senha do usuário que tem acesso à assinatura do Azure.
3.  No Portal do Azure, no painel de navegação esquerdo, clique em **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  Na grade, selecione a instância do Active Directory que é usada pelo Finance and Operations.
5.  Na barra de ferramentas superior, clique em **Aplicativos**. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  No painel inferior, clique em **Adicionar**. O assistente **Adicionar aplicativo** é iniciado.
7.  Insira um nome para o aplicativo e selecione **Aplicativo da Web e/ou API da Web**. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Insira a URL de entrada, que é a URL do seu aplicativo Web. Essa URL será igual à URL de implantação, mas a oauth será adicionada no final. Insira o URI da ID do Aplicativo, esse valor é obrigatório, mas não é necessário para a autenticação. Certifique-se de que esse URI da ID do Aplicativo é um URI fictício como https://contosooperations/wmapp, já que a utilização da URL de implantação pode causar problemas de logon em outros aplicativos do AAD, como o Suplemento do Excel. [![WH-04-AD-add-properties3](./media/WH-04-AD-add-properties3.png)](./media/WH-04-AD-add-properties3.png)
9.  Vá para a guia **Configurar**. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Role para baixo até ver a seção **Permissões para outros aplicativos**. Clique em **Adicionar aplicativo**. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Selecione **Microsoft Dynamics ERP** na lista. Clique no botão **Verificação concluída** no canto direito da página. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. Na lista **Delegar Permissões**, marque todas as caixas de seleção. Clique em **Salvar**. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Anote as seguintes informações:
    -   **ID do Cliente** - Conforme rola pela página, você verá o **ID do Cliente**.
    -   **Chave** - Na seção **Chaves**, crie uma chave, selecionando a duração e copie a chave. Esta chave será mencionada posteriormente como **Segredo do cliente**.

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Criar e configurar uma conta de usuário no Finance and Operations
Para habilitar o Finance and Operations para usar o aplicativo Azure AD, é necessário concluir as seguintes etapas de configuração:

1.  Criar uma nova conta de usuário no Azure Active Directory para o locatário do Finance and Operations. A finalidade dessa conta de usuário é acessar o serviço personalizado específico do aplicativo warehousing, que o servidor do Finance and Operations expõe. Após concluir esta etapa, você terá as credenciais do usuário de WMDP, que consiste em um endereço de email e senha do WMDP. Para obter mais informações sobre as etapas básicas para adicionar usuários ao Azure AD e Finance and Operations, consulte este tutorial: [Inscrever-se para uma assinatura do Finance and Operations](../../dev-itpro/dev-tools/sign-up-preview-subscription.md).
2.  Crie um usuário do Finance and Operations que corresponda às credenciais do usuário do aplicativo warehousing.
    1.  No Finance and Operations, vá para **Administração do sistema** &gt; **Comum** &gt; **Usuários**.
    2.  Crie um novo usuário.
    3.  Atribua o usuário do dispositivo móvel do Warehouse, conforme mostrado na seguinte captura de tela. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Associe o aplicativo Azure Active Directory ao usuário do aplicativo Warehousing.
    1.  No Finance and Operations, vá para **Administração do sistema** &gt; **Configurar** &gt; **aplicativos Azure Active Directory**.
    2.  Crie uma nova linha.
    3.  Insira o **ID do Cliente** (obtido na última seção), forneça um nome e selecione o usuário criado anteriormente. Recomendamos que você marque todos os dispositivos, de forma que você possa remover facilmente o acesso ao Finance and Operations desta página, em caso de perda. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurar o aplicativo
É necessário configurar o aplicativo no dispositivo para conectar-se ao servidor Finance and Operations através do aplicativo Azure AD. Para fazer isso, conclua as seguintes etapas.

1.  No aplicativo, vá para **Configurações da conexão**.
2.  Desmarque o campo **Modo de demonstração**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Digite as seguintes informações: 
    + **ID do cliente do Azure Active Directory** - A ID do cliente é obtida na etapa 13 em "Criar um aplicativo de serviço Web no Active Directory". 
    +  **Segredo do cliente do Azure Active Directory** - O segredo do cliente é obtido na etapa 13 em "Criar um aplicativo de serviços Web no Active Directory". 
    + **Recurso do Azure Active directory** - O recurso do Azure AD directory mostra a URL da raiz do Finance and Operations. **Nota**: Este campo não termina com um caractere de barra (/). 
    + **Locatário do Azure Active directory** - O locatário do Azure AD directory usado com o servidor do Finance and Operations: https://login.windows.net/your-AD-tenant-ID. Por exemplo: https://login.windows.net/contosooperations.onmicrosoft.com.
    <br>**Nota**: Este campo não termina com um caractere de barra (/). 
    + **Empresa** - Insira a entidade legal no Finance and Operations para a qual você quer conectar o aplicativo. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Selecione o botão **Voltar** no canto superior esquerdo do aplicativo. O aplicativo agora conectará seu servidor do Finance and Operations e a tela de logon do trabalhador do warehouse será exibida. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Remover acesso de um dispositivo
Em caso de perda ou comprometimento do dispositivo, será necessário remover o acesso do dispositivo ao Finance and Operations. Estas etapas a seguir descrevem o processo recomendado para remover o acesso.

1.  No Finance and Operations, vá para **Administração do sistema** &gt; **Configurar** &gt; **aplicativos Azure Active Directory**.
2.  Exclua a linha que corresponde ao dispositivo para o qual você deseja remover o acesso. Anote o **ID do Cliente** usado para o dispositivo removido.
3.  Conecte-se ao portal do Azure em <https://manage.windowsazure.com>.
4.  Clique no ícone **Active Directory** no menu esquerdo e, em seguida, clique no diretório desejado.
5.  No menu superior, clique em **Aplicativos** e, em seguida, clique no aplicativo que você deseja configurar. A página **Início Rápido** será exibida com informações sobre sign-on único e outras configurações.
6.  Clique na guia **Configurar**, role para baixo e certifique-se de que o **ID do Cliente** do aplicativo é igual ao da etapa 2 desta seção.
7.  Clique no botão **Excluir** na barra de comandos.
8.  Clique em **Sim** na mensagem de confirmação.





