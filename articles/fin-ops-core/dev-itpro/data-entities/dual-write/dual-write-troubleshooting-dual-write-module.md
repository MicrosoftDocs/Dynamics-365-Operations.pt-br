---
title: Solucionar problemas de gravação dupla em aplicativos de finanças e operações
description: Este artigo fornece informações sobre solução de problemas que podem ajudar a corrigir problemas no módulo de dupla gravação em aplicativos de finanças e operações.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2743b99538b332af7cc6ad8d951eede562c14235
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111160"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Solucionar problemas de gravação dupla em aplicativos de finanças e operações

[!include [banner](../../includes/banner.md)]



Este artigo fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse. Especificamente, ele fornece informações que podem ajudar a corrigir problemas no módulo **Gravação dupla** em aplicativos de finanças e operações.

> [!IMPORTANT]
> Alguns dos problemas que este artigo aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Não é possível carregar o módulo de gravação dupla em um aplicativo de finanças e operações

Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados**, o serviço de integração de dados está provavelmente desligado. Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Erro ao tentar criar um novo mapa de tabela

**Credenciais necessárias para corrigir o problema:** o mesmo usuário que configura a gravação dupla.

A seguinte mensagem de erro poderá ser exibida quando você tentar configurar uma nova tabela para gravação dupla: O único usuário que poderá criar um mapa é o usuário que configurou a conexão de gravação dupla.

*O código de status de resposta não indica êxito: 401 (Não autorizado).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erro ao abrir a interface do usuário de gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados**:

*login.microsoftonline.com recusou a conexão.*

Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome. Você também deve desbloquear ou limpar cookies de terceiros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de tabela

**Função necessária para corrigir o problema**: administrador do sistema em aplicativos de finanças e operações ou no Dataverse.

Você pode encontrar o seguinte erro ao vincular ou criar mapas:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas. Esse erro também pode ocorrer se o ambiente do Dataverse foi redefinido sem desvincular a gravação dupla. Qualquer usuário com a função de administrador do sistema em aplicativos de finanças e operações e no Dataverse pode vincular os ambientes. Somente o usuário que configurou a conexão de gravação dupla poderá adicionar novos mapas de tabela. Após a configuração, qualquer usuário com a função de administrador do sistema poderá monitorar o status e editar os mapeamentos.

## <a name="error-when-you-stop-the-table-mapping"></a>Erro ao interromper o mapeamento de tabela

A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de tabela:

*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*

Este erro ocorre quando o ambiente Dataverse vinculado não está disponível.

Para corrigir o problema, crie um tíquete para a equipe de integração de dados. Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Habilite o processamento paralelo em aplicativos de finanças e operações para melhorar o desempenho

A habilitação do processamento paralelo pode reduzir o tempo necessário para importar dados dos aplicativos do Dynamics 365 Customer Engagement e do Microsoft Dataverse para aplicativos de finanças e operações. 

Para habilitar o processamento paralelo em aplicativos de finanças e operações, siga as etapas a seguir.

1. Faça logon no seu ambiente de finanças e operações.
2. Acesse **Gerenciamento de Dados > Parâmetros de estrutura**.
3. Selecione **Configurações da entidade** e selecione **Configurar parâmetros de execução de entidade**.
4. Adicione os parâmetros para processamento paralelo:
    - **Contagem de registros do limite de importação**: o número de registros que devem ser atendidos antes que o processamento em paralelo seja habilitado.
    - **Contagem de tarefas de importação**: o número de threads (tarefas) a serem executadas em paralelo.
5. Selecione **Salvar**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Erros ao tentar iniciar um mapeamento de tabela

### <a name="unable-to-complete-initial-data-sync"></a>Não é possível concluir a sincronização de dados inicial

Talvez você recebe um erro como o seguinte ao tentar executar a sincronização de dados inicial:

*Não é possível concluir a sincronização de dados inicial. Erro: falha de gravação dupla — falha no registro do plug-in: não é possível criar metadados de pesquisa da gravação dupla. A referência do objeto do erro não está definida como uma instância de objeto.*

Quando você tenta definir esse estado de um mapeamento como **Em execução**, você pode receber este erro. A correção depende da causa do erro:

+ Se o mapeamento tiver mapeamentos dependentes, certifique-se de habilitar os mapeamentos dependentes deste mapeamento de tabela.
+ Pode haver colunas de origem ou de destino ausentes no mapeamento. Se uma coluna no aplicativo de finanças e operações estiver ausente, siga as etapas na seção [Problemas de colunas de tabela ausentes em mapas](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Se a coluna no Dataverse estiver ausente, clique no botão **Atualizar tabelas** no mapeamento para que as colunas sejam automaticamente preenchidas no mapeamento.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Erro de incompatibilidade de versão e atualizando soluções de gravação dupla

Talvez você receba as seguintes mensagens de erro ao tentar executar os mapeamentos de tabela:

+ *Grupos de clientes (msdyn_customergroups): falha de gravação dupla- a solução 'Dynamics365Company' do Dynamics 365 for Sales é incompatível com a versão. Versão: '2.0.2.10' versão necessária: '2.0.133'*
+ A solução 'Dynamics365FinanceExtended' do *Dynamics 365 for Sales tem incompatibilidade de versão. Versão: '1.0.0.0' versão necessária: '2.0.227'*
+ A solução 'Dynamics365FinanceAndOperationsCommon' do *Dynamics 365 for Sales tem incompatibilidade de versão. Versão: '1.0.0.0' versão necessária: '2.0.133'*
+ A solução 'CurrencyExchangeRates' do *Dynamics 365 for Sales tem incompatibilidade de versão. Versão: '1.0.0.0' versão necessária: '2.0.133'*
+ A solução 'Dynamics365SupplyChainExtended' do *Dynamics 365 for Sales tem incompatibilidade de versão. Versão: '1.0.0.0' versão necessária: '2.0.227'*

Para corrigir os problemas, atualize as soluções de gravação dupla no Dataverse. Certifique-se de atualizar para a última solução que corresponde à versão da solução necessária.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

