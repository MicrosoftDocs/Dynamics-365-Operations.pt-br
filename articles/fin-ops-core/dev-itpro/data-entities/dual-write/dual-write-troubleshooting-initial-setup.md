---
title: Solucionar problemas durante a configuração inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.
author: RamaKrishnamoorthy
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
ms.openlocfilehash: 7c51a92ab101937a0ccf630fa0355485e42e9a0deca36c23327d96976f5228b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758183"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Solucionar problemas durante a configuração inicial

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Não é possível vincular um aplicativo Finance and Operations ao Dataverse

**Função necessária para configurar a gravação dupla:** administrador do sistema nos aplicativos Finance and Operations e Dataverse.

Erros na página **Configurar link para Dataverse** geralmente são causados por configuração incompleta ou problemas de permissão. Verifique se toda a verificação de integridade foi aprovada na página **Configurar link para Dataverse**, conforme mostrado na ilustração a seguir. Não é possível vincular a dupla gravação, a menos que toda a verificação de integridade seja aprovada.

![Verificação bem-sucedida de integridade.](media/health_check.png)

Você deve ter credenciais de administração de locatário do Azure AD para vincular os ambientes Finance and Operations e Dataverse. Depois de vincular os ambientes, os usuários podem fazer login usando suas credenciais de conta e atualizar um mapa de tabela existente.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Erro ao abrir o link para a página do Dataverse

**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD

Você pode receber a seguinte mensagem de erro ao abrir a página **Link para Dataverse** em um aplicativo Finance and Operations:

*O código de status de resposta não indica êxito: 404 (Não encontrado).*

Este erro ocorre quando a etapa de consentimento não foi concluída. Para validar se a etapa de consentimento foi concluída, efetue login no portal do Azure.com usando a conta de administrador de locatário do Azure AD e verifique se o aplicativo de terceiros que tem a ID **33976c19-1db5-4c02-810e-c243db79efde** aparece na lista de **aplicativos corporativos do Azure AD**. Se não tiver, você deverá fornecer consentimento ao aplicativo.

Para fornecer consentimento ao aplicativo, siga estas etapas.

1. Abra a seguinte URL usando suas credenciais administrativas. Você deve receber um aviso de consentimento.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Selecione **Aceitar** para indicar que você está dando seu consentimento a instalação do aplicativo que tem a ID no seu locatário do **33976c19-1db5-4c02-810e-c243db79efde**.

    > [!TIP]
    > Este aplicativo é necessário para vincular aplicativos Dataverse e Finance and Operations. Se você tiver problemas com essa etapa, abra seu navegador no modo Incognito (no Google Chrome) ou no modo InPrivate (em Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Verificar se os dados da empresa e as equipes de gravação dupla estão configurados corretamente durante a vinculação

Para garantir que a gravação dupla funcione corretamente, as empresas selecionadas durante a configuração são criadas no ambiente do Dataverse. Por padrão, essas empresas são apenas leitura e a propriedade **IsDualWriteEnable** está definida como **Verdadeira**. Além disso, o proprietário e a equipe padrão da unidade de negócios são criados e incluem o nome da empresa. Antes de habilitar os mapas, verifique se o proprietário padrão da equipe foi especificado. Para encontrar a tabela **Empresas (Empresa\_CDM)**, siga estas etapas.

1. No aplicativo de interação com o cliente, selecione o filtro no canto superior direito.
2. Na lista suspensa, selecione **Empresa**.
3. Selecione **Executar** para ver os resultados.
4. Selecione a empresa que estava vinculada quando você configurou a gravação dupla.
5. Verifique se a coluna **Equipe proprietária padrão** tem um valor. Na ilustração a seguir, a coluna **Padrão de propriedade da equipe** é definida como **Gravação dupla USMF**.

    ![Verificando a equipe proprietária padrão.](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Encontre o limite para o número de tabelas legais ou empresas que podem ser vinculadas para gravação dupla

A seguinte mensagem de erro pode ser exibida ao tentar habilitar os mapas:

*Falha na gravação dupla - Falha no registro de plug-in: \[(Não foi possível obter mapa de partição para o projeto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Erro excede as partições máximas permitidas para mapeamento de DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Um ou mais erros ocorreram.*

O limite atual ao vincular os ambientes é de aproximadamente 40 tabelas legais. Este erro ocorre se você tentar habilitar mapas, e mais de 40 tabelas legais serão vinculadas entre os ambientes.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]