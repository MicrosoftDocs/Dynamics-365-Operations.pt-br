---
title: Solução de problemas gerais
description: Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: bcedb9f6e8fb15210512ed6a376d4329759593e4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781165"
---
# <a name="general-troubleshooting"></a>Solução de problemas gerais

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Habilite e exiba o log de rastreamento de plug-in no Dataverse para exibir detalhes do erro

**Função necessária para ativar o log de rastreamento e erros de exibição**: administrador do sistema

Para ativar o log de rastreamento, siga estas etapas.

1. Entre no aplicativo de interação com o cliente, abra a página **Configurações** e, em **Sistema**, selecione **Administração**.
2. Na página **Administração**, selecione **Configuração do sistema**.
3. Na guia **Personalização**, na coluna **Rastreamento de atividade de fluxo de trabalho e plug-in**, selecione **Todos** para habilitar o log de rastreamento de plug-in. Se você deseja registrar logs de rastreamento somente quando ocorrerem exceções, em vez disso, você pode selecionar **Exceção**.


Para exibir o log de rastreamento, siga estas etapas.

1. Efetue login no aplicativo de interação com o cliente, abra a página **Configurações** e, em **Personalização**, selecione **Log de rastreamento de plug-in**.
2. Encontre os logs de rastreamento em que a coluna **Nome do Tipo** esteja definida como **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Clique duas vezes em um item para exibir o log completo e, em seguida, na Guia Rápida **Execução** revise o texto do **Bloco de mensagens**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Habilitar modo de depuração para solucionar problemas de sincronização dinâmica em aplicativos Finance and Operations

**Função necessária para exibir os erros:** administrador do sistema

Os erros de gravação dupla que originam-se no Dataverse podem aparecer no aplicativo Finance and Operations. Para habilitar o registro detalhado de erros ao seguir estas etapas:

1. Para todas as configurações de projeto nos aplicativos Finance and Operations há uma propriedade **IsDebugMode** na tabela **DualWriteProjectConfiguration**.
2. Abra a tabela **DualWriteProjectConfiguration** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no suplemento do Excel no Finance and Operations e adicione o **DualWriteProjectConfiguration** à planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
3. Defina **Isdebugmode** como **Sim** no projeto.
4. Execute o cenário que está gerando erros.
5. Os logs detalhados são armazenados na tabela **DualWriteErrorLog**.
6. Para pesquisar dados no navegador de tabelas, use o seguinte link: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog` substituindo `999`, conforme necessário.
7. Atualize novamente após a [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), que está disponível para atualizações de plataforma 37 e posterior. Se você tiver essa correção instalada, o modo de depuração capturará mais logs.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Verificar erros de sincronização na máquina virtual para o aplicativo Finance and Operations

**Função necessária para exibir os erros:** administrador do sistema

1. Entre Microsoft Dynamics Lifecycle Services (LCS).
2. Abra o projeto LCS escolhido para realizar testes de gravação dupla.
3. Selecione o bloco **Ambientes hospedados na nuvem**.
4. Use área de trabalho remota para fazer login na máquina virtual (VM) do aplicativo Finance and Operations. Use a conta local que é mostrada em LCS.
5. Abra o Visualizador de Eventos.
6. Selecione **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.
7. Revise a lista de erros recentes.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Desvincular e vincular outro ambiente do Dataverse de um aplicativo Finance and Operations

**Função necessária para desvincular o ambiente:** administrador do sistema para os aplicativos Finance and Operations ou Dataverse.

1. Entrar no aplicativo Finance and Operations.
2. Acesse **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**.
3. Selecione todos os mapeamentos em execução e selecione **Parar**.
4. Selecione **Desvincular ambiente**.
5. Selecione **Sim** para confirmar a operação.

Agora você pode vincular um novo ambiente.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Não é possível exibir o formulário de informações da linha da ordem de venda 

Quando você cria uma ordem de venda no Dynamics 365 Sales, clicar em **Adicionar produtos** talvez redirecione você para o formulário da linha de ordem do Dynamics 365 Project Operations. Não há nenhuma maneira de esse formulário exibir o formulário de **Informações** da linha da ordem de venda. A opção de **Informações** não aparece na lista suspensa **Nova Linha da Ordem** abaixo. Isso ocorre porque o Project Operations foi instalado em seu ambiente.

Para habilitar novamente a opção de formulário de **Informações**, siga estas etapas:

1. Navegue até a tabela **Linha da Ordem**.
2. Encontre o formulário de **Informações** no nó de formulários.
3. Selecione o formulário de **Informações** e clique em **Habilitar funções de segurança**.
4. Altere a configuração de segurança para **Exibir para todos**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Como habilitar e salvar o rastreamento de rede para que os rastreamentos possam ser anexados a tíquetes de suporte

Talvez a equipe de suporte precise revisar os rastreamentos de rede para solucionar alguns problemas. Siga estas etapas para criar um rastreamento de rede:

### <a name="chrome"></a>Chrome

1. Na guia aberta, pressione **F12** ou escolha **Ferramentas do desenvolvedor** para abrir as ferramentas do desenvolvedor.
2. Abra a guia **Rede** e digite **integ** na caixa de texto do filtro.
3. Execute seu cenário e observe as solicitações que estão sendo registradas.
4. Clique com o botão direito do mouse nas entradas e selecione **Salvar tudo como um Har com conteúdo**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. Na guia aberta, pressione **F12** ou escolha **Ferramentas do desenvolvedor** para abrir as ferramentas do desenvolvedor.
2. Abra a guia **Rede**.
3. Execute seu cenário.
4. Selecione **Salvar** para exportar os resultados como Har.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
