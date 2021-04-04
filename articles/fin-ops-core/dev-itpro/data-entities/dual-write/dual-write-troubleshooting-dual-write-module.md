---
title: Solucionar problemas de gravação dupla em aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de dupla gravação nos aplicativos Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 9bff8ad0c5716648dec6eadfb21412a2b17f155e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561217"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Solucionar problemas de gravação dupla em aplicativos do Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de **dupla gravação** nos aplicativos Finance and Operations.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Não é possível carregar o módulo de gravação dupla em um aplicativo do Finance and Operations

Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados**, o serviço de integração de dados está provavelmente desligado. Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Erro ao tentar criar um novo mapa de tabela

**Credenciais necessárias para corrigir o problema:** o mesmo usuário que configura a gravação dupla.

A seguinte mensagem de erro poderá ser exibida quando você tentar configurar uma nova tabela para gravação dupla: O único usuário que poderá criar um mapa é o usuário que configurou a conexão de gravação dupla.

*O código de status de resposta não indica êxito: 401 (Não autorizado)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erro ao abrir a interface do usuário de gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados**:

*login.microsoftonline.com recusou a conexão.*

Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome. Você também deve desbloquear ou limpar cookies de terceiros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de tabela

**Função necessária para corrigir o problema:** administrador do sistema nos aplicativos Finance and Operations e Dataverse.

Você pode encontrar o seguinte erro ao vincular ou criar mapas:

*O código de status de resposta não indica êxito: 403 (tokenexchange).<br> ID da sessão: \<your session id\><br> ID da atividade raiz: \<your root activity id\>*

Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas. Esse erro também pode ocorrer se o ambiente do Dataverse foi redefinido sem desvincular a gravação dupla. Qualquer usuário com a função de administrador do sistema nos aplicativos Finance and Operations e Dataverse pode vincular os ambientes. Somente o usuário que configurou a conexão de gravação dupla poderá adicionar novos mapas de tabela. Após a configuração, qualquer usuário com a função de administrador do sistema poderá monitorar o status e editar os mapeamentos.

## <a name="error-when-you-stop-the-table-mapping"></a>Erro ao interromper o mapeamento de tabela

A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de tabela:

*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*

Este erro ocorre quando o ambiente Dataverse vinculado não está disponível.

Para corrigir o problema, crie um tíquete para a equipe de integração de dados. Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.

## <a name="error-while-trying-to-start-a-table-mapping"></a>Erro ao tentar iniciar um mapeamento de tabela

A seguinte mensagem de erro pode ser exibida ao tentar definir esse estado de um mapeamento como **Em execução**:

*Não é possível concluir a sincronização de dados inicial. Erro: falha de gravação dupla — falha no registro do plug-in: não é possível criar metadados de pesquisa da gravação dupla. A referência do objeto do erro não está definida como uma instância de objeto.*

A correção desse erro depende da causa do erro:

+ Se o mapeamento tiver mapeamentos dependentes, certifique-se de habilitar os mapeamentos dependentes deste mapeamento de tabela.
+ Pode haver colunas de origem ou de destino ausentes no mapeamento. Se um campo no aplicativo Finance and Operations estiver ausente, siga as etapas na seção [Problemas de campos de entidade ausentes nos mapas](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Se a coluna no Dataverse estiver ausente, clique no botão **Atualizar tabelas** no mapeamento para que as colunas sejam automaticamente preenchidas no mapeamento.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]