---
title: Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de dupla gravação nos aplicativos Finance and Operations.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f99f3760e75ec1bbf2ccdea497cf2eec3e28e233
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997365"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de **dupla gravação** nos aplicativos Finance and Operations.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Não é possível carregar o módulo de gravação dupla em um aplicativo do Finance and Operations

Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados** , o serviço de integração de dados está provavelmente desligado. Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.

## <a name="error-when-you-try-to-create-a-new-entity-map"></a>Erro ao tentar criar um novo mapa de entidade

**Credenciais necessárias para corrigir o problema:** o mesmo usuário que configura a gravação dupla.

A seguinte mensagem de erro poderá ser exibida quando você tentar configurar uma nova entidade para gravação dupla: O único usuário que poderá criar um mapa é o usuário que configurou a conexão de gravação dupla.

*O código de status de resposta não indica êxito: 401 (Não autorizado)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erro ao abrir a interface do usuário de gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados** :

*login.microsoftonline.com recusou a conexão.*

Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome. Você também deve desbloquear ou limpar cookies de terceiros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de entidade

**Função necessária para corrigir o problema:** administrador do sistema nos aplicativos Finance and Operations e Common Data Service.

Você pode encontrar o seguinte erro ao vincular ou criar mapas:

*O código de status de resposta não indica êxito: 403 (tokenexchange).<br> ID da sessão: \<your session id\><br> ID da atividade raiz: \<your root activity id\>*

Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas. Esse erro também pode ocorrer se o ambiente do Common Data Service foi redefinido sem desvincular a gravação dupla. Qualquer usuário com a função de administrador do sistema nos aplicativos Finance and Operations e Common Data Service pode vincular os ambientes. Somente o usuário que configurou a conexão de gravação dupla poderá adicionar novos mapas de entidade. Após a configuração, qualquer usuário com a função de administrador do sistema poderá monitorar o status e editar os mapeamentos.

## <a name="error-when-you-stop-the-entity-mapping"></a>Erro ao interromper o mapeamento de entidade

A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de entidade:

*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*

Este erro ocorre quando o ambiente Common Data Service vinculado não está disponível.

Para corrigir o problema, crie um tíquete para a equipe de integração de dados. Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.

## <a name="error-while-trying-to-start-an-entity-mapping"></a>Erro ao tentar iniciar um mapeamento de entidade

A seguinte mensagem de erro pode ser exibida ao tentar definir esse estado de um mapeamento como **Em execução** :

*Não é possível concluir a sincronização de dados inicial. Erro: falha de gravação dupla — falha no registro do plug-in: não é possível criar metadados de pesquisa da gravação dupla. A referência do objeto do erro não está definida como uma instância de objeto.*

A correção desse erro depende da causa do erro:

+ Se o mapeamento tiver mapeamentos dependentes, certifique-se de habilitar os mapeamentos dependentes deste mapeamento de entidade.
+ O mapeamento pode estar ter campos de origem ou de destino ausentes. Se um campo no aplicativo Finance and Operations estiver ausente, siga as etapas na seção [Problemas de campos de entidade ausentes nos mapas](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps). Se um campo no Common Data Service estiver ausente, clique no botão **Atualizar entidades** no mapeamento para que os campos sejam automaticamente preenchidos no mapeamento.
