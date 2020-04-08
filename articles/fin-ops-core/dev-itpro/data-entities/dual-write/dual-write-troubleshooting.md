---
title: Solução de problemas gerais
description: Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f7ee0b5aa4e72614205e129acd986376b33efc70
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172682"
---
# <a name="general-troubleshooting"></a>Solução de problemas gerais

[!include [banner](../../includes/banner.md)]



Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Ao tentar instalar o pacote de gravação dupla usando a ferramenta Package Deployer, nenhuma solução disponível é mostrada

Algumas versões da ferramenta Package Deployer são incompatíveis com o pacote de solução de gravação dupla. Para instalar o pacote com êxito, certifique-se de usar a [versão 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) ou posterior da ferramenta Package Deployer.

Depois de instalar a ferramenta do Package Deployer, instale o pacote de solução seguindo essas etapas.

1. Baixe o arquivo de pacote de solução mais recente de Yammer.com. Depois que o arquivo zip do pacote for baixado, clique nele com o botão direito do mouse e selecione **Propriedades**. Marque caixa de seleção **Desbloquear** e selecione **Aplicar**. Se você não vir a caixa de seleção **Desbloquear**, o arquivo zip já está desbloqueado e você pode ignorar essa etapa.

    ![Caixa de diálogo de propriedades](media/unblock_option.png)

2. Extraia o arquivo compactado no pacote e copie todos os arquivos na pasta **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.

    ![Conteúdo da pasta Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. Cole todos os arquivos copiados na pasta **Ferramentas** da ferramenta Package Deployer. 
4. Execute **PackageDeployer.exe** para selecionar o ambiente Common Data Service e instale as soluções.

    ![Conteúdo da pasta Ferramentas](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a>Habilite e exiba o log de rastreamento de plug-in no Common Data Service para exibir detalhes do erro

**Função necessária para ativar o log de rastreamento e erros de exibição**: administrador do sistema

Para ativar o log de rastreamento, siga estas etapas.

1. Efetue login no aplicativo Finance and Operations, abra a página **Configurações** e, em **Sistema**, selecione **Administração**.
2. Na página **Administração**, selecione **Configuração do sistema**.
3. Na guia **Personalização**, no campo **Rastreamento de atividade de fluxo de trabalho e plug-in**, selecione **Todos** para habilitar o log de rastreamento de plug-in. Se você deseja registrar logs de rastreamento somente quando ocorrerem exceções, em vez disso, você pode selecionar **Exceção**.


Para exibir o log de rastreamento, siga estas etapas.

1. Efetue login no aplicativo Finance and Operations, abra a página **Configurações** e, em **Personalização**, selecione **Log de rastreamento de plug-in**.
2. Localize os logs de rastreamento no campo **Nome do tipo** e defina como **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.
3. Clique duas vezes em um item para exibir o log completo e, em seguida, na Guia Rápida **Execução** revise o texto do **Bloco de mensagens**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Habilitar modo de depuração para solucionar problemas de sincronização dinâmica em aplicativos Finance and Operations

**Função necessária para exibir os erros:** administrador do sistema

Os erros de gravação dupla que originam-se no Common Data Service podem aparecer no aplicativo Finance and Operations. Em alguns casos, o texto completo da mensagem de erro não está disponível porque a mensagem é muito longa ou contém informações de identificação pessoal (PII). Você pode ativar o registro detalhado de erros ao seguir estas etapas.

1. Todas as configurações de projeto nos aplicativos Finance and Operations têm uma propriedade **IsDebugMode** na entidade **DualWriteProjectConfiguration**. Abra a entidade **DualWriteProjectConfiguration** usando um suplemento do Excel.

    > [!TIP]
    > Uma forma simples de abrir a entidade é ativar o modo **Design** no suplemento do Excel e adicionar **DualWriteProjectConfigurationEntity** à planilha. Para obter mais informações, consulte [Abrir os dados da entidade no Excel e atualizá-los usando o suplemento do Excel](../../office-integration/use-excel-add-in.md).

2. Defina a propriedade **IsDebugMode** como **Sim** para o projeto.
3. Execute o cenário que está gerando erros.
4. Os logs detalhados estão disponíveis na tabela DualWriteErrorLog. Para pesquisar dados no navegador da tabela, use a seguinte URL (substitua **XXX**, conforme apropriado):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Verificar erros de sincronização na máquina virtual para o aplicativo Finance and Operations

**Função necessária para exibir os erros:** administrador do sistema

1. Entre Microsoft Dynamics Lifecycle Services (LCS).
2. Abra o projeto LCS escolhido para realizar testes de gravação dupla.
3. Selecione o bloco **Ambientes hospedados na nuvem**.
4. Use área de trabalho remota para fazer login na máquina virtual (VM) do aplicativo Finance and Operations. Use a conta local que é mostrada em LCS.
5. Abra o Visualizador de Eventos.
6. Selecione **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.
7. Revise a lista de erros recentes.

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a>Desvincular e vincular outro ambiente do Common Data Service de um aplicativo Finance and Operations

**Credenciais necessárias para desvincular o ambiente:** administrador de locatário do Azure AD

1. Entrar no aplicativo Finance and Operations.
2. Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**.
3. Selecione todos os mapeamentos em execução e selecione **Parar**.
4. Selecione **Desvincular ambiente**.
5. Selecione **Sim** para confirmar a operação.

Agora você pode vincular um novo ambiente.
