---
title: Solucionar problemas durante a configuração inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração entre aplicativos Finance and Operations e Common Data Service.
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
ms.openlocfilehash: 76e104c9ebd7db7ebcbaf214e84be6c4353e8a73
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275432"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Solucionar problemas durante a configuração inicial

[!include [banner](../../includes/banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a>Não é possível vincular um aplicativo Finance and Operations ao Common Data Service

**Função necessária para configurar a gravação dupla:** administrador do sistema nos aplicativos Finance and Operations e Common Data Service.

Erros na página **Configurar link para Common Data Service** geralmente são causados por configuração incompleta ou problemas de permissão. Verifique se toda a verificação de integridade foi aprovada na página **Configurar link para Common Data Service**, conforme mostrado na ilustração a seguir. Não é possível vincular a dupla gravação, a menos que toda a verificação de integridade seja aprovada.

![Verificação bem-sucedida de integridade](media/health_check.png)

Você deve ter credenciais de administração de locatário do Azure AD para vincular os ambientes Finance and Operations e Common Data Service. Depois de vincular os ambientes, os usuários podem fazer login usando suas credenciais de conta e atualizar um mapa de entidade existente.

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a>Erro ao abrir o link para a página do Common Data Service

**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD

Você pode receber a seguinte mensagem de erro ao abrir a página **Link para Common Data Service** em um aplicativo Finance and Operations:

*O código de status de resposta não indica êxito: 404 (Não encontrado).*

Este erro ocorre quando a etapa de consentimento não foi concluída. Para validar se a etapa de consentimento foi concluída, efetue login no portal do Azure.com usando a conta de administrador de locatário do Azure AD e verifique se o aplicativo de terceiros que tem a ID **33976c19-1db5-4c02-810e-c243db79efde** aparece na lista de **aplicativos corporativos do Azure AD**. Se não tiver, você deverá fornecer consentimento ao aplicativo.

Para fornecer consentimento ao aplicativo, siga estas etapas.

1. Abra a seguinte URL usando suas credenciais administrativas. Você deve receber um aviso de consentimento.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Selecione **Aceitar** para indicar que você está dando seu consentimento a instalação do aplicativo que tem a ID no seu locatário do **33976c19-1db5-4c02-810e-c243db79efde**.

    > [!TIP]
    > Este aplicativo é necessário para vincular aplicativos Common Data Service e Finance and Operations. Se você tiver problemas com essa etapa, abra seu navegador no modo Incognito (no Google Chrome) ou no modo InPrivate (em Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Verificar se os dados da empresa e as equipes de gravação dupla estão configurados corretamente durante a vinculação

Para garantir que a gravação dupla funcione corretamente, as empresas selecionadas durante a configuração são criadas no ambiente do Common Data Service. Por padrão, essas empresas são apenas leitura e a propriedade **IsDualWriteEnable** está definida como **Verdadeira**. Além disso, o proprietário e a equipe padrão da unidade de negócios são criados e incluem o nome da empresa. Antes de habilitar os mapas, verifique se o proprietário padrão da equipe foi especificado. Para encontrar a entidade **Empresas (Empresa\_CDM)**, siga estas etapas.

1. No aplicativo baseado em modelo no Dynamics 365, selecione o filtro no canto superior direito.
2. Na lista suspensa, selecione **Empresa**.
3. Selecione **Executar** para ver os resultados.
4. Selecione a empresa que estava vinculada quando você configurou a gravação dupla.
5. Verifique se o campo **Equipe proprietária padrão** tem um valor. Na ilustração a seguir, o campo **Padrão de propriedade da equipe** é definido como **Gravação dupla USMF**.

    ![Verificando a equipe proprietária padrão](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a>Encontre o limite para o número de entidades legais ou empresas que podem ser vinculadas para gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar habilitar os mapas:

*Falha na gravação dupla - Falha no registro de plug-in: \[(Não foi possível obter mapa de partição para o projeto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Erro excede as partições máximas permitidas para mapeamento de DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Um ou mais erros ocorreram.*

O limite atual ao vincular os ambientes é de aproximadamente 40 entidades legais. Este erro ocorre se você tentar habilitar mapas, e mais de 40 entidades legais serão vinculadas entre os ambientes.
