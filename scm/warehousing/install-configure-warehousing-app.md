---
title: "Instalar e configurar o Microsoft Dynamics 365 para operações &#8211; Armazenamento"
description: "Este tópico descreve como instalar e configurar o Microsoft Dynamics 365 para operações do armazenamento."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Instalar e configurar o Microsoft Dynamics 365 para operações &#8211; Armazenamento

Este tópico descreve como instalar e configurar o Microsoft Dynamics 365 para operações do armazenamento.

Dynamics 365 para operações - id é um aplicativo disponível em Play Google Store e no Windows Store. Para a versão atual do Microsoft Dynamics 365 para operações, este descritivo é fornecido como um componente autônomo, que significa a auto- implantação dispositivos usados para tarefas de depósito. Para usar o descritivo no dynamics 365 do ambiente de operações, você deve baixar o dispositivo em cada descritivo e configurá-lo para conectar-se ao 365 para o ambiente de operações. Este tópico descreve como instalar o descritivo em seus dispositivos. Também explica como configurar o descritivo para conectar-se ao 365 para o ambiente de operações.

## <a name="prerequisites"></a>Pré-requisitos
O descritivo disponível em Android e sistemas operacionais Windows. Para usar esse descritivo, você deve ter um dos sistemas operacionais suportados instalados em seus dispositivos. Você também pode ter uma das seguintes versões suportadas do 365 para as operações. Use as informações na seguinte tabela para avaliar se o ambiente do hardware e o software está pronto para oferecer a instalação.

| Plataforma                    | Versão                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (todas as versões)                                                                                                                                                   |
| Dynamics 365 for Operations | Microsoft Dynamics 365 para a versão 1611 de operações - ou 7.0/7.0.1 versão de dados dynamics AX no Microsoft Dynamics e de preparo do Microsoft Dynamics AX 2 KB atualização com 3210014 de hotfix |

## <a name="get-the-app"></a>Obter o descritivo
-   O Windows (-) [UWP dynamics 365 para operações do armazenamento em Windows Store] (https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   - Android [dynamics 365 para operações - armazena em que Play Google Store] (https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Crie uma solicitação de serviço da Web em O active Directory
Para habilitar o descritivo para interagir com dinâmica específica servidor 365 para operações, registre uma ordem de serviço da Web em Azure Active Directory para dynamics 365 do inquilino operações. Por motivo de segurança, recomendamos que você cria uma ordem de serviço da Web para cada dispositivo que você usa. Para criar uma solicitação de serviço da Web em Azure Active Directory (AD de Azure), complete as seguintes etapas:

1.  Em um navegador, vá< para> https://manage.windowsazure.com.
2.  Insira o nome e a senha do usuário que tem acesso à subscrição de Azure.
3.  No portal de Azure, no painel esquerdo de navegação, clicar ** ** o Active Directory. []. (/media/wh-01-active-directory-example.png) [![(wh-01-ative-directory-example]. /media/wh-01-active-directory-example.png)](. /media/wh-01-active-directory-example.png)
4.  Na grade, selecione a instância do active Directory que é usada por dynamics 365 para as operações.
5.  Na barra de ferramentas superior, clique ** aplicativos **. [![(wh-02-ative-directory-applications]. /media/wh-02-active-directory-applications-1024x197.png)](. /media/wh-02-active-directory-applications.png)
6.  No painel inferior, clique em adicionar. ** ** ** Adicionar aplicativo ** inicia o assistente.
7.  Insira um nome para a solicitação e selecione ** aplicativo Web e/ou API de Web **. [![(wh-03-ative-directory-add-application]. /media/wh-03-active-directory-add-application.png)](. /media/wh-03-active-directory-add-application.png)
8.  Insira o sinal- URL, que é a URL de aplicativo no inquilino, a URL de operações raiz. Sinal- URL não estiver sendo usado atualmente ativamente autenticar descritivo no, mas é um campo obrigatório. Insira a URL no mesmo campo de ID de URI descritivo. [![(wh-04-ad-add-properties]. /media/wh-04-ad-add-properties.png)](. /media/wh-04-ad-add-properties.png)
9.  ** Vá configurar ** a guia. [![(wh-05-ad-configure-app]. /media/wh-05-ad-configure-app.png)](. /media/wh-05-ad-configure-app.png)
10. Rolar para baixo até que você consulte ** permissões a outros aplicativos ** a seção. Clique ** adicionar o aplicativo. ** [![(wh-06-ad-app-add-permissions]. /media/wh-06-ad-app-add-permissions.png)](. /media/wh-06-ad-app-add-permissions.png)
11. Selecione ** Microsoft Dynamics ERP ** na lista. ** Clique em verificação concluída no canto ** botão direito da página. [![(wh-07-ad-select-permissions]. /media/wh-07-ad-select-permissions.png)](. /media/wh-07-ad-select-permissions.png)
12. ** Em permissões delegados ** lista, selecione as caixas de seleção. Click **Save**. [![(wh-08-ad-delegate-permissions]. /media/wh-08-ad-delegate-permissions.png)](. /media/wh-08-ad-delegate-permissions.png)
13. Faça uma nota das seguintes informações:
    -   ** ID de cliente ** - porque o acúmulo da página, verá ** ID de cliente ** exibido.
    -   ** A chave ** - ** chaves ** na seção, cria uma chave selecionando a duração, copia e a chave. Esta chave será referida posteriormente como ** confidencialidade ** de cliente.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Criar e configurar uma conta de usuário em dynamics 365 para operações
Para habilitar o dynamics 365 para as operações que usa seu aplicativo de AD de Azure, você precisará concluir as etapas de configuração:

1.  Crie uma nova conta de usuário em Azure Active Directory para dynamics 365 do inquilino operações. A finalidade dessa conta de usuário for acessar o serviço específico de personalizado descritivo de armazenamento, que o dynamics 365 para o servidor de expõe operações. Após concluir a etapa, você terá as suas credenciais de WMDP, que consistem em um endereço de email de WMDP e uma senha de WMDP. Para saber sobre as etapas básicas para adicionar usuários ao de Azure AD dinâmica e 365 para operações, consulte este tutorial: [Se inscrever para Microsoft Dynamics 365 para assinatura] operações (/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Crie uma dynamics 365 para o usuário de operações que correspondem às credenciais do usuário de armazenamento descritivo.
    1.  Em dynamics 365 para operações, vai ** administração de sistema ** &gt; ** a comum ** &gt; ** ** usuários.
    2.  Criar um novo usuário.
    3.  Atribua o usuário de dispositivo móvel depósito, conforme mostrado a seguir de captura de tela. [![(wh-09-add-user-security-role]. /media/wh-09-add-user-security-role.png)](. /media/wh-09-add-user-security-role.png)

3.  Associe a solicitação de Azure Active Directory com o usuário de armazenamento de descritivo.
    1.  Em dynamics 365 para operações, vá ** administração de sistema ** &gt; ** de instalação ** &gt; ** aplicativos de Azure ** o Active Directory.
    2.  Crie uma nova linha.
    3.  ** Insira o ID de cliente (** obtido na seção a último), insira um nome e o nome, selecione o usuário anteriormente criado. Recomendamos que você marcar todos os dispositivos de forma que você possa facilmente remover o acesso ao 365 para operações dessa página caso que serão perdidos. [![(wh-10-ad-applications-form]. /media/wh-10-ad-applications-form.png)](. /media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configure o aplicativo
Configure o dispositivo em descritivo para conectar o dynamics 365 para o servidor de operações com o aplicativo de AD de Azure. Para isso, siga estas etapas.

1.  Em descritivo, vá ** configurações de conexão. **
2.  Desmarcar ** modo de demonstração ** o campo. [![(wh-11-app-connection-settings-demo-mode]. /media/wh-11-app-connection-settings-demo-mode-169x300.png)](. /media/wh-11-app-connection-settings-demo-mode.png)
3.  Insira as seguintes informações: ** - ID de cliente ativa de diretório de Azure ** - ID de cliente será obtido na etapa 13 em “cria um aplicativo de serviço da Web em O active Directory”. - ** A confidencialidade de cliente ativa de diretório de Azure ** - a confidencialidade de clientes é obtida na etapa 13 em “cria um aplicativo de serviço da Web em O active Directory”. - ** O recurso ativo de diretório de Azure ** o recurso de diretório de AD de Azure descreve o dynamics 365 para a URL raiz operações. ** Nota **: Este campo não termina com um caractere de barra (/). - ** Inquilino ativo de diretório de Azure ** - do inquilino AD de diretório de Azure usado ao dynamics 365 para o servidor de operações: https://login.windows.net/your-AD-tenant-ID&lt;&gt;. Por exemplo: https://login.windows.net/contosooperations.onmicrosoft.com. 
** Nota **: Este campo não termina com um caractere de barra (/). - ** Empresa ** - insira a entidade legal em dynamics 365 para as operações em que a solicitação de emprego se conectar. [![(wh-12-app-connection-settings]. /media/wh-12-app-connection-settings-169x300.png)](. /media/wh-12-app-connection-settings.png)
4.  Selecione ** ** botão voltar no canto superior esquerdo de aplicativo. O aplicativo conectará agora a sua dynamics 365 para o servidor de operações e a tela de logon para o trabalhador de depósito será exibido. [![(wh-13-log-in-screen]. /media/wh-13-log-in-screen-180x300.png)](. /media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Remover acesso de um dispositivo
Em caso de um dispositivo perdidas ou compromisso, remova acesso o dynamics 365 para operações do dispositivo. Estas etapas descrevem o processo recomendado para remover acesso.

1.  Em dynamics 365 para operações, vá ** administração de sistema ** &gt; ** de instalação ** &gt; ** aplicativos de Azure ** o Active Directory.
2.  Excluir a linha que corresponde o dispositivo a que você deseja remover acesso. ** Nota abaixo de ID de cliente ** usado para o dispositivo removido.
3.  Conectar o portal de Azure< clássico em https://manage.windowsazure.com>.
4.  Clicar ** Active Directory ** o ícone no menu esquerdo, e clique no diretório.
5.  No menu superior, clique ** aplicativos **, e no aplicativo que deseja configurar. ** Início rápido ** o página aparecerá com logon único e outras informações de configuração.
6.  Clicar ** configurar ** guia, para rolar baixo e garantir que ** ** ID de cliente do aplicativo seja igual ao da etapa 2 nesta seção.
7.  Clicar ** ** botão excluir na barra de comandos.
8.  Clique Sim ** ** na mensagem de confirmação.



