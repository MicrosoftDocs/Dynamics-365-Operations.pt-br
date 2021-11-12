---
title: Introdução à Contabilidade de estoque global
description: Este tópico descreve como começar com a Contabilidade de estoque global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cfba2b8320399cc2eb3f2231e8a172d902633f16
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678850"
---
# <a name="get-started-with-global-inventory-accounting"></a>Introdução à Contabilidade de estoque global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)] <!--KFM: Until 4/30/2022 -->

A Contabilidade de estoque global de custos permite realizar múltiplas contabilidades de inventário nos razões da Contabilidade de estoque global. É necessário associar cada razão da Contabilidade de estoque global a uma *convenção*. Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:

- Objeto de custo
- Base de medida de entrada
- Suposição de fluxo de custos
- Elemento de custo

> [!NOTE]
> Mesmo depois de ativar a Contabilidade de estoque global, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.

A Contabilidade de estoque global é um suplemento. Para disponibilizar os recursos, é necessário instalá-lo a partir do Lifecycle Services (LCS) Microsoft Dynamics. É possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo para ambientes de produção.

No momento, a Contabilidade de estoque global não permite todos os recursos de gerenciamento de custos que são incorporados ao Supply Chain Management. Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Como obter a versão preliminar pública da Contabilidade de estoque global

> [!IMPORTANT]
> Para usar a Contabilidade de estoque global, você deve ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox). Além disso, você deve estar executando a versão 10.0.19 ou posterior do Supply Chain Management.

Para se inscrever na versão preliminar pública da Contabilidade de estoque global, envie seu ID de ambiente LCS por email para a [Equipe da Contabilidade de estoque global](mailto:GlobalInvAccount@microsoft.com). Depois que você for aprovado para o programa, a equipe enviará um email de acompanhamento que contém uma chave beta da Contabilidade de estoque global e seus pontos de extremidade de serviço. Depois de receber a chave beta, você pode [instalar o suplemento](#install).

## <a name="licensing"></a>Licenciamento

A Contabilidade de estoque global é licenciada com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management. Não é necessário comprar uma licença adicional para usar a Contabilidade de Estoque Global.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="set-up-microsoft-power-platform-integration"></a>Configurar integração do Microsoft Power Platform

Antes de habilitar a funcionalidade de suplemento, você deve se integrar ao Microsoft Power Platform seguindo essas etapas.

1. Abra o ambiente LCS ao qual deseja adicionar o serviço.
1. Acesse **Detalhes completos**.
1. Na seção **Integração do Power Platform**, selecione **Configurar**.
1. Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**. Normalmente, a configuração leva entre 60 e 90 minutos.
1. Após a configuração do ambiente do Microsoft Power Platform ser concluída, a página mostra o nome do seu ambiente. Além disso, a seção **Integração do Power Platform** mostra a afirmação: "A configuração de ambiente do Power Platform foi concluída." A Contabilidade de estoque global não requer um aplicativo de gravação dupla.

Para obter mais informações, consulte a página [Habilitar após a implantação do ambiente](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

### <a name="set-up-dataverse"></a>Configurar Dataverse

Antes de configurar o Dataverse, adicione os princípios do Contabilidade de estoque global ao seu locatário seguindo essas etapas.

1. Instale o módulo Azure AD para Windows PowerShell v2, conforme descrito em [Instalar o Azure Active Directory PowerShell para o Graph](/powershell/azure/active-directory/install-adv2).
1. Execute o comando do PowerShell a seguir.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Em seguida, crie usuários de aplicativos para a Contabilidade de estoque global do Dataverse seguindo essas etapas.

1. Abra a URL do ambiente do Dataverse.
1. Acesse **Configuração Avançada \> Sistema \> Segurança \> Usuários** e crie um usuário de aplicativo. Use o campo **Visualizar** para alterar a exibição de página para *Usuários do Aplicativo*.
1. Selecione **Novo**.
1. Defina o campo **ID do Aplicativo** como *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Selecione **Atribuir Função** e, depois, selecione *Administrador do Sistema*. Se houver uma função denominada *Usuário do Common Data Service*, selecione-a.
1. Repita as etapas anteriores, mas defina o campo **ID do aplicativo** para *5f58fc56-0202-49a8-ac9e-0946b049718b*.

Para obter mais informações, consulte [Criar um usuário de aplicativo](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Se o idioma padrão da sua instalação do Dataverse não for inglês, siga estas etapas.

1. Acesse **Configurações avançadas \> Administração \> Idiomas**.
1. Selecione *Inglês* (*LanguageCode = 1033*) e selecione **Aplicar**.

## <a name="install-the-add-in"></a><a name="install"></a>Instalar o suplemento

Siga estas etapas para instalar o suplemento para que você possa usar a Contabilidade de estoque global.

1. [Inscreva-se](#sign-up) na versão preliminar pública da Contabilidade de estoque global.
1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index).
1. Acesse **Gerenciamento da versão prévia do recurso**.
1. Selecione o sinal de mais (**+**).
1. No campo **Código**, insira a chave beta do complemento da Contabilidade de estoque global. (Você deve ter recebido sua chave beta por email quando se inscreveu.)
1. Selecione **Desbloquear**.
1. Abra o ambiente LCS ao qual deseja adicionar o serviço.
1. Acesse **Detalhes completos**.
1. Acesse **Integração do Power Platform** e selecione **Configuração**.
1. Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**. Normalmente, a configuração leva entre 60 e 90 minutos.
1. Após a configuração do ambiente do Microsoft Power Platform ser concluída, na Guia Rápida **Suplementos do ambiente**, selecione **Instalar um novo suplemento**.
1. Selecione **Contabilidade de estoque global**.
1. Acompanhe o guia de instalação e concorde com os termos e condições.
1. Selecione **Instalar**.
1. Na Guia Rápida **Suplementos do ambiente**, você verá que o Contabilidade de estoque global está sendo instalado. Após alguns minutos, o status deve mudar de *Instalando* para *Instalado*. (Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, a Contabilidade de estoque global já está pronto para uso.

## <a name="set-up-the-integration"></a>Configurar a integração

Siga essas etapas para configurar a integração entre a Contabilidade de estoque global e o Supply Chain Management.

1. Entre no Supply Chain Management.
1. Acesse **Administração do sistema \> Gerenciamento de Recursos**.
1. Selecione **Verificar se há atualizações**.
1. Na guia **Tudo**, pesquise o recurso que se chama *Contabilidade de estoque global*.
1. Selecione **Habilitar agora**.
1. Acesse **Contabilidade de estoque global \> Configuração \> Parâmetros contábeis \> Integrações de parâmetros**.
1. Nos campos **Dados do ponto de extremidade de serviço** e **Ponto de extremidade da Contabilidade de estoque global**, insira os URLs com base no email que a equipe da Contabilidade de estoque global enviou quando você se inscreveu na versão preliminar.

A Contabilidade de estoque global está pronta para uso.
