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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172751"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations

[!include [banner](../../includes/banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de **dupla gravação** nos aplicativos Finance and Operations.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Não é possível carregar o módulo de gravação dupla em um aplicativo do Finance and Operations

Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados**, o serviço de integração de dados está provavelmente desligado. Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Erro ao tentar criar um novo mapeamento de entidade

**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD

A seguinte mensagem de erro pode ser exibida ao tentar configurar uma nova entidade para gravação dupla:

*O código de status de resposta não indica êxito: 401 (Não autorizado)*

Este erro ocorre porque somente um administrador de locatário do Azure AD pode adicionar um novo mapeamento de entidade.

Para corrigir o problema, faça login no aplicativo Finance and Operations como um locatário de administração do Azure AD. Você também deve ir para a web.PowerApps.com e revalidar a conexão.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erro ao abrir a interface do usuário de gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados**:

*login.microsoftonline.com recusou a conexão.*

Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome. Você também deve desbloquear ou limpar cookies de terceiros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de entidade

**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD

Você pode encontrar o seguinte erro ao vincular ou criar mapas:

*O código de status de resposta não indica sucesso: 403 (tokenexchange).<br> ID da sessão: \<seu ID da sessão\><br> ID da atividade raiz: \<seu ID de atividade raiz\>*

Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas. Você deve usar uma conta de administrador de locatário do Azure AD para vincular ambientes e adicionar novos mapeamentos de entidade. No entanto, após a configuração, você pode usar uma conta de não-administrador para monitorar o status e editar os mapeamentos.

## <a name="error-when-you-stop-the-entity-mapping"></a>Erro ao interromper o mapeamento de entidade

A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de entidade:

*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*

Este erro ocorre quando o ambiente Common Data Service vinculado não está disponível.

Para corrigir o problema, crie um tíquete para a equipe de integração de dados. Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.
