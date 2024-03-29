---
title: Solucionar problemas durante a configuração inicial
description: Este artigo fornece informações sobre como solucionar problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289504"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Solucionar problemas durante a configuração inicial

[!include [banner](../../includes/banner.md)]

Este artigo fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.

> [!IMPORTANT]
> Alguns dos problemas que este artigo aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Não é possível vincular um aplicativo de finanças e operações ao Dataverse

**Função necessária para configurar a gravação dupla**: administrador do sistema em aplicativos de finanças e operações e no Dataverse.

Erros na página **Configurar link para Dataverse** geralmente são causados por configuração incompleta ou problemas de permissão. Verifique se toda a verificação de integridade foi aprovada na página **Configurar link para Dataverse**, conforme mostrado na ilustração a seguir. Não é possível vincular a dupla gravação, a menos que toda a verificação de integridade seja aprovada.

![Verificação bem-sucedida de integridade.](media/health_check.png)

Você deve ter credenciais de administração de locatário do Azure AD para vincular os ambientes de finanças e operações e do Dataverse. Depois de vincular os ambientes, os usuários podem fazer login usando suas credenciais de conta e atualizar um mapa de tabela existente.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Encontre o limite para o número de tabelas legais ou empresas que podem ser vinculadas para gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar habilitar os mapas:

*Falha na gravação dupla - Falha no registro de plug-in: [(Não foi possível obter mapa de partição para o projeto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. O erro excede as partições máximas permitidas para mapeamento de DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Ocorreram um ou mais erros.*

O limite atual ao vincular os ambientes é de aproximadamente 40 tabelas legais. Este erro ocorre se você tentar habilitar mapas, e mais de 40 tabelas legais serão vinculadas entre os ambientes.

## <a name="connection-set-failed-while-linking-environment"></a>Falha no conjunto de conexões ao vincular o ambiente

Ao vincular o ambiente de gravação dupla, a ação falha com uma mensagem de erro:

*Falha ao salvar conjunto de conexões! Um item com a mesma chave já foi adicionado.*

A gravação dupla não oferece suporte a várias entidades legais/empresas com o mesmo nome. Por exemplo, caso você tenha duas empresas com o nome "DAT" no Dataverse, ele receberá essa mensagem de erro.

Para desbloquear o cliente, remova os registros duplicados da tabela **cdm_company** no Dataverse. Além disso, se a tabela **cdm_company** tiver registros com nome em branco, remova ou corrija esses registros.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Erro ao abrir a página Gravação dupla em aplicativos de finanças e operações

Você poderá receber a seguinte mensagem de erro quando tentar vincular um ambiente do Dataverse para gravação dupla:

*O código de status de resposta não indica êxito: 404 (Não encontrado).*

Este erro ocorre quando a etapa de consentimento do aplicativo não é concluída. Você pode validar se o consentimento tiver sido fornecido com o logon no `portal.azure.com` usando a conta de administrador de locatário e verificar se o aplicativo de terceiros com a ID `33976c19-1db5-4c02-810e-c243db79efde` é exibido na lista de aplicativos corporativos do AAD. Caso contrário, execute novamente a etapa de consentimento, conforme descrito na próxima seção.

### <a name="providing-app-consent"></a>Fornecendo consentimento de aplicativo

+ Inicie a seguinte URL usando suas credenciais administrativas.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Selecione **Aceitar** como consentimento. Você está fornecendo o consentimento para instalar o aplicativo (com `id=33976c19-1db5-4c02-810e-c243db79efde`) no seu locatário.
+ Este aplicativo é necessário para o Dataverse se comunicar com aplicativos de finanças e operações.

    ![Solução de problemas durante a configuração inicial.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Se isso não funcionar, inicie a URL no modo particular do Microsoft Edge ou no modo Incognito do Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>O ambiente de finanças e operações não é detectável

Você poderá receber a seguinte mensagem de erro:

*O ambiente de aplicativos de finanças e operações \*\*\*.cloudax.dynamics.com não é detectável.*

Há duas coisas que podem fazer com que um ambiente não seja detectável:

+ O usuário usado para logon não está no mesmo locatário da instância de finanças e operações.
+ Existem algumas instâncias herdadas de finanças e operações que eram hospedadas pela Microsoft que tinham um problema com a descoberta. Para corrigir isso, atualize a instância de finanças e operações. O ambiente torna-se detectável com qualquer atualização.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>403 (proibido), erro ao criar conexões

Como parte do processo de vinculação de gravação dupla, duas conexões Power Apps (também conhecidas como conexões *Apihub*) são criadas em nome do usuário no ambiente vinculado Dataverse. Se o cliente não tiver uma licença para o ambiente Power Apps, a criação das conexões de ApiHub apresentará uma falha e um erro 403 (proibido) será exibido. Veja aqui um exemplo da mensagem de erro:

> MSG =\[falha ao configurar o ambiente de gravação dual. Detalhes do erro: o código de status de resposta não indica êxito: 403 (proibido). -O código de status de resposta não indica êxito: 403 (proibido).\] RASTREAMENTO DE PILHA =\[   em Microsoft. Dynamics. Integrator. ProjectManagementService. DualWrite. DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29. MoveNext () em X:\\BT\\1158727\\repositório\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs: linha 297---fim do rastreamento de pilha a partir do local anterior onde a exceção foi lançada---em System. Runtime. ExceptionServices. TaskAwaiter. HandleNonSuccessAndDebuggerNotification (tarefa de tarefa) em Microsoft. Dynamics. Integrator. ProjectManagementService. Controllers. DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext () em X:\\BT\\1158727\\os controladores\\de ProjectManagementService\\do repositório\\src\\DualWriteEnvironmentManagementController.cs: linha 265\]

Este erro ocorre devido à falta de uma licença Power Apps. Atribua uma licença apropriada (por exemplo, plano de avaliação 2 para Power Apps) ao usuário, para que o usuário tenha permissão para criar as conexões. Para verificar a licença, o cliente pode ir para o [site "Minha conta"](https://portal.office.com/account/?ref=MeControl#subscriptions) a fim de exibir as licenças atribuídas ao usuário no momento.

Para obter mais informações sobre a licença do Power Apps, veja os seguintes artigos:

- [Atribuir licenças a usuários](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Comprar Power Apps para sua organização](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

