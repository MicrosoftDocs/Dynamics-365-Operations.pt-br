---
title: Solução de problemas gerais
description: Este artigo fornece informações gerais de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: be3d72063ac18b9abea77d5aec6e230b0c930ae6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289350"
---
# <a name="general-troubleshooting"></a>Solução de problemas gerais

[!include [banner](../../includes/banner.md)]



Este artigo fornece informações gerais de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse.

> [!IMPORTANT]
> Alguns dos problemas que este artigo aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Habilite e exiba o log de rastreamento de plug-in no Dataverse para exibir detalhes do erro

Os logs de rastreamento podem ser úteis ao solucionar problemas de sincronização ao vivo de gravação dupla entre finanças e operações e o Dataverse. Os logs podem fornecer detalhes específicos às equipes que oferecem suporte técnico e de engenharia para o Dynamics 365. Este artigo aborda como habilitar logs de rastreamento e como exibi-los. Os logs de rastreamento são gerenciados na página Configurações do Dynamics 365 e exigem privilégios de nível de administrador para alteração e exibição. 

**Função necessária para ativar o log de rastreamento e erros de exibição**: administrador do sistema

### <a name="turn-on-the-trace-log"></a>Ativar o log de rastreamento
Para ativar o log de rastreamento, siga estas etapas.

1.  Faça logon no Dynamics 365 e selecione **Configurações** na barra de navegação superior. Na página Sistemas, clique em **Administração**.
2.  Na página Administração, clique em **Configuração do sistema**.
3.  Selecione a guia **Personalização** e o plug-in e, na seção de rastreamento de atividade de fluxo de trabalho personalizado, altere o menu suspenso para **Tudo**. Isso irá rastrear todas as atividades e fornecer um conjunto abrangente de dados para as equipes que devem revisar problemas potenciais.

> [!NOTE]
> A configuração da lista suspensa como **Exceção** só fornecerá informações de rastreamento quando ocorrerem exceções (erros).

Uma vez habilitados, os logs de rastreamento do plug-in continuarão sendo coletados até que sejam manualmente desconectados, retornando a esse local e selecionando **Desativado**.

### <a name="view-the-trace-log"></a>Exiba o log de rastreamento
Para exibir o log de rastreamento, siga estas etapas.

1. Na página Configurações do Dynamics 365, selecione **Configurações** na barra de navegação superior. 
2. Selecione **Log de Rastreamento de Plug-in** na seção **Personalizações** da página.
3. Você pode encontrar entradas na lista de logs de rastreamento, com base no nome do tipo e/ou no nome da mensagem.
4. Abra a entrada desejada para exibir o log completo. O bloco de mensagens na seção Execução contém as informações disponíveis para o plug-in. Se disponíveis, os detalhes da exceção também serão fornecidos. 

Você pode copiar o conteúdo dos logs de rastreamento e colá-los em outro aplicativo, como o Bloco de notas, ou outras ferramentas para exibir logs ou arquivos de texto para ver mais facilmente todo o conteúdo. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Habilitar modo de depuração para solucionar problemas de sincronização dinâmica em aplicativos de finanças e operações

**Função necessária para exibir os erros:** administrador do sistema

Os erros de gravação dupla originados no Dataverse podem aparecer no aplicativo de finanças e operações. Para habilitar o registro detalhado de erros ao seguir estas etapas:

1. Para todas as configurações de projeto em aplicativos de finanças e operações, há um sinalizador **IsDebugMode** na tabela **DualWriteProjectConfiguration**.
2. Abra a tabela **DualWriteProjectConfiguration** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no complemento do Excel em finanças e operações e adicione **DualWriteProjectConfiguration** à planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
3. Defina **Isdebugmode** como **Sim** no projeto.
4. Execute o cenário que está gerando erros.
5. Os logs detalhados são armazenados na tabela **DualWriteErrorLog**.
6. Para pesquisar dados no navegador de tabelas, use o seguinte link: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog` substituindo `999`, conforme necessário.
7. Atualize novamente após a [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), que está disponível para atualizações de plataforma 37 e posterior. Se você tiver essa correção instalada, o modo de depuração capturará mais logs.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Verificar erros de sincronização na máquina virtual para o aplicativo de finanças e operações

**Função necessária para exibir os erros:** administrador do sistema

1. Entre Microsoft Dynamics Lifecycle Services (LCS).
2. Abra o projeto LCS escolhido para realizar testes de gravação dupla.
3. Selecione o bloco **Ambientes hospedados na nuvem**.
4. Use Área de Trabalho Remota para entrar na VM (máquina virtual) do aplicativo de finanças e operações. Use a conta local que é mostrada em LCS.
5. Abra o Visualizador de Eventos.
6. Selecione **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.
7. Revise a lista de erros recentes.

## <a name="dual-write-ui-landing-page-showing-blank"></a>Página inicial da interface de usuário de gravação dupla aparece em branco
Ao abrir a página de gravação dupla no Microsoft Edge ou no Google Chrome, a página inicial não é carregada, e você vê uma página em branco ou um erro como "Algo deu errado".
Em Devtools, você verá um erro nos logs do console:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: Falha ao ler a propriedade 'sessionStorage' de 'Window': Acesso negado para este documento. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) at new t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) at ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) at Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) at jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) at Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) at Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) at Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) at vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) at hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

A interface do usuário usa o navegador de "armazenamento de sessão" para armazenar alguns valores de propriedade para carregar a Home Page. Para que isso funcione, é necessário permitir cookies de terceiros no navegador do site. O erro indica que a interface do usuário não pode acessar o armazenamento da sessão. Pode haver dois cenários nos quais esse problema é encontrado:

1.  Você está abrindo a interface do usuário no modo Incognito do Edge/Chrome, e os cookies de terceiros no modo Incognito são bloqueados.
2.  Você bloqueou cookies de terceiros totalmente no Edge/Chrome.

### <a name="mitigation"></a>Redução
Os cookies de terceiros precisam ser permitidos nas configurações do navegador.

### <a name="google-chrome-browser"></a>Navegador Google Chrome
Primeira opção:
1.  Vá para Configurações digitando chrome://settings/ na barra de endereços e navegue até Privacidade e segurança -> Cookies e outros dados do site.
2.  Selecione "Permitir todos os cookies". Se não desejar fazer isso, vá para a segunda opção.

2ª opção:
1.  Vá para Configurações digitando chrome://settings/ na barra de endereços e navegue até Privacidade e segurança -> Cookies e outros dados do site.
2.  Se a opção "Bloquear cookies de terceiros no modo Incognito" ou "Bloquear cookies de terceiros" estiver selecionada, vá para "Sites que sempre podem usar cookies" e clique em **Adicionar**. 
3.  Adicione o nome do site de seus aplicativos Finance & Operations - https://<your_FinOp_instance>.cloudax.dynamics.com. Marque a caixa de seleção para "Todos os cookies, somente neste site". 

### <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge
1.  Navegue até Configurações -> Permissões de site -> Cookies e dados do site.
2.  Desative "Bloquear cookies de terceiros".  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Desvincular e vincular outro ambiente do Dataverse a partir de um aplicativo de finanças e operações

**Função necessária para desvincular o ambiente**: administrador do sistema para aplicativo de finanças e operações ou o Dataverse.

1. Entre no aplicativo de finanças e operações.
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

## <a name="how-to-ensure-data-integration-is-using-the-most-current-finance-and-operations-schema"></a>Como garantir que a integração de dados esteja usando o esquema de finanças e operações mais atual

Você pode enfrentar problemas de dados na integração de dados se o esquema mais atual não estiver sendo usado. As etapas a seguir ajudarão você a atualizar a lista de entidades nos aplicativos de finanças e operações e as entidades no Integrador de dados.

### <a name="refresh-entity-list-in-finance-and-operations-environment"></a>Atualizar a lista de entidades no ambiente de finanças e operações
1.  Faça logon no ambiente de finanças e operações.
2.  Selecione **Gerenciamento de dados**.
3.  No Gerenciamento de dados, selecione **Parâmetros de estrutura**.
4.  Na página **Parâmetros de importação/exportação de dados**, selecione a guia **Configurações da entidade** e, em seguida, selecione **Atualizar lista de entidades**. Isso pode levar mais de 30 minutos para ser atualizado, dependendo do número de entidades envolvidas.
5.  Navegue até **Gerenciamento de dados** e selecione **Entidades de dados** para validar se as entidades esperadas estão listadas. Se as entidades esperadas não estiverem listadas, valide se as entidades aparecem no ambiente de finanças e operações e restaure as entidades ausentes, conforme necessário.

#### <a name="if-the-refresh-fails-to-resolve-the-issue-delete-and-re-add-the-entities"></a>Se a atualização não resolver o problema, exclua e adicione novamente as entidades

> [!NOTE]
> Talvez seja necessário interromper todos os grupos de processamento que estão usando ativamente as entidades antes da exclusão.

1.  Selecione **Gerenciamento de dados** no ambiente de finanças e operações e selecione **Entidades de dados**.
2.  Pesquise entidades com problemas e anote a entidade de destino, a tabela de preparo, o nome da entidade e outras configurações. Exclua a entidade ou as entidades da lista.
3.  Selecione **Nova** e adicione novamente a entidade ou as entidades usando os dados da etapa 2. 

#### <a name="refresh-entities-in-data-integrator"></a>Atualizar entidades no integrador de dados
Faça logon na central de administração do Power Platform e selecione **Integração de dados**. Abra o projeto em que os problemas estão ocorrendo e selecione **Atualizar entidades**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Como habilitar e salvar o rastreamento de rede para que os rastreamentos possam ser anexados a tíquetes de suporte

Talvez a equipe de suporte precise revisar os rastreamentos de rede para solucionar alguns problemas. Siga estas etapas para criar um rastreamento de rede:

### <a name="google-chrome-browser"></a>Navegador Google Chrome

1. Na guia aberta, pressione **F12** ou escolha **Ferramentas do desenvolvedor** para abrir as ferramentas do desenvolvedor.
2. Abra a guia **Rede** e digite **integ** na caixa de texto do filtro.
3. Execute seu cenário e observe as solicitações que estão sendo registradas.
4. Clique com o botão direito do mouse nas entradas e selecione **Salvar tudo como um Har com conteúdo**.

### <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

1. Na guia aberta, pressione **F12** ou escolha **Ferramentas do desenvolvedor** para abrir as ferramentas do desenvolvedor.
2. Abra a guia **Rede**.
3. Execute seu cenário.
4. Selecione **Salvar** para exportar os resultados como Har.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

