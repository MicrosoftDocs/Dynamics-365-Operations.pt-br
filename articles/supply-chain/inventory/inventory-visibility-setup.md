---
title: Instalar o Suplemento Visibilidade de Estoque
description: Este tópico descreve como instalar o Suplemento Visibilidade de Estoque para Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 26f8820fe707b8a2dff0dcc1a24884ef02e5616f
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952487"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalar e configurar Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como instalar o Suplemento Visibilidade de Estoque para Microsoft Dynamics 365 Supply Chain Management.

Você deve usar o Microsoft Dynamics LCS (Lifecycle Services) para instalar o Suplemento Visibilidade de Estoque. O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Finance and Operations.

Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Pré-requisitos de Visibilidade de Estoque

Antes de instalar o Visibilidade de Estoque, você deve concluir as seguintes tarefas:

- Obter um projeto de implementação do LCS em que pelo menos um ambiente seja implantado.
- Verificar se os pré-requisitos para configurar suplementos foram concluídos. Para obter informações sobre esses pré-requisitos, consulte [Visão geral de suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A visibilidade de estoque não exige link de gravação dupla.

> [!NOTE]
> Os países/regiões com suporte no momento incluem Canadá (CCA, ECA), Estados Unidos (WUS, EUS), União Europeia (NEU, WEU), Reino Unido (SUK, WUK), Austrália (EAU, SEAU), Japão (EJP, WJP) e Brasil (SBR, SCUS).

Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar o Suplemento Visibilidade de Estoque

Antes de instalar o suplemento, registre um aplicativo e adicione um segredo de cliente ao Azure Active Directory (Azure AD) em sua assinatura do Azure. Para obter instruções, consulte [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app) e [Adicionar um segredo de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Anote os valores de **ID do aplicativo (cliente)**, **Segredo do cliente** e **ID do locatário**, porque você precisará deles mais tarde.

Depois de registrar um aplicativo e adicionar um segredo de cliente ao Azure AD, siga estas etapas para instalar o Suplemento Visibilidade de Estoque.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index).
1. Na home page, selecione o projeto no qual seu ambiente foi implantado.
1. Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.
1. Na página do ambiente, role para baixo até encontrar a seção **Suplementos de ambiente** na seção **Integração do Power Platform**. Lá, você pode encontrar o nome do ambiente do Dataverse. Confirme se o nome do ambiente do Dataverse é aquele que você deseja usar para Visibilidade de Estoque.

    > [!NOTE]
    > No momento, apenas os ambientes do Dataverse que foram criados usando o LCS têm suporte. Se seu ambiente do Dataverse foi criado de alguma outra forma (por exemplo, usando o centro de administração do Power Apps) e se ele estiver vinculado a seu ambiente do Supply Chain Management, primeiro você deverá entrar em contato com a equipe de produto do Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para corrigir o problema de mapeamento. Você pode então instalar o Visibilidade de Estoque.

1. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.

    ![Página do ambiente no LCS](media/inventory-visibility-environment.png "Página do ambiente no LCS")

1. Selecione o link **Instalar um novo suplemento**. Uma lista de suplementos disponíveis é exibida.
1. Na lista, selecione **Visibilidade de Estoque**.
1. Defina os seguintes campos para seu ambiente:

    - **ID do aplicativo (cliente) AAD** — insira a ID do aplicativo do Azure AD que você criou e anotou anteriormente.
    - **ID do locatário do AAD** — insira a ID do locatário que você anotou anteriormente.

    ![Página de suplemento de configuração](media/inventory-visibility-setup.png "Página de suplemento de configuração")

1. Concorde com os termos e condições marcando a caixa de seleção **Termos e condições**.
1. Selecione **Instalar**. O status do suplemento é mostrado como **Instalando**. Quando a instalação for concluída, atualize a página. O status deve mudar para **Instalado**.
1. No Dataverse, selecione a seção **Aplicativos** na navegação à esquerda e verifique se o Power Apps **Visibilidade de Estoque** foi instalado com êxito. Se a seção **Aplicativos** não existir, entre em contato com a equipe de produto do Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!TIP]
> Recomendamos que você ingresse no grupo de usuários do Suplemento de Visibilidade de Estoque, no qual é possível encontrar guias úteis, obter nossas atualizações mais recentes e postar perguntas que possam ser obtidas usando a Visibilidade de Estoque. Para entrar, envie um email para a equipe de produto da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) e inclua sua ID de ambiente do Supply Chain Management.

> [!IMPORTANT]
> Se você tiver mais de um ambiente LCS, crie um aplicativo Azure AD diferente para cada ambiente. Se você usar a mesma ID de aplicativo e ID de locatário para instalar o Suplemento de Visibilidade de Estoque para ambientes diferentes, ocorrerá uma saída de token para ambientes mais antigos. Somente o último que foi instalado será válido.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar o suplemento Visibilidade de Estoque

Para desinstalar o suplemento Visibilidade de Estoque, selecione **Desinstalar** na página do LCS. O processo de desinstalação encerra o suplemento Visibilidade de Estoque, cancela o registro do suplemento do LCS e exclui todos os dados temporários armazenados no cache de dados do Suplemento Visibilidade de Estoque. No entanto, os dados de estoque principal armazenados na assinatura do Dataverse não são excluídos.

Para desinstalar os dados de estoque armazenados em sua assinatura do Dataverse, abra o [Power Apps](https://make.powerapps.com), selecione **Ambiente** na barra de navegação e selecione o ambiente do Dataverse que está vinculado a seu ambiente do LCS. Em seguida, acesse **Soluções** e exclua as cinco seguintes soluções, nesta ordem:

1. Solução de ancoragem para aplicativo Visibilidade de Estoque em soluções do Dynamics 365
1. Solução de Aplicativos Visibilidade de Estoque do Dynamics 365 FNO SCM
1. Configuração de Serviço de Estoque
1. Visibilidade de Estoque Autônomo
1. Solução Base Visibilidade de Estoque do Dynamics 365 FNO SCM

Depois que você excluir essas soluções, os dados armazenados nas tabelas também serão excluídos.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar Visibilidade de Estoque no Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implantar o pacote de integração de Visibilidade de Estoque

Se você estiver executando o Supply Chain Management versão 10.0.17 ou anterior, contate a equipe de suporte de integração da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter o arquivo de pacote. Em seguida, implante o pacote no LCS.

> [!NOTE]
> Se ocorrer um erro de incompatibilidade de versão durante a implantação, você deverá importar manualmente o projeto X++ no ambiente de desenvolvimento. Em seguida, crie o pacote implantável no ambiente de desenvolvimento e implante-o no ambiente de produção.
>
> O código está incluído no Supply Chain Management versão 10.0.18. Se você estiver executando essa versão ou posterior, a implantação não será necessária.

Verifique se os recursos a seguir estão ativados no ambiente do Supply Chain Management. (Por padrão, eles são ativados.)

| Descrição do recurso | Versão de código | Alternar classe |
|---|---|---|
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurar a integração da Visibilidade de Estoque

Depois de instalar o suplemento, prepare o sistema do Supply Chain Management para trabalhar com ele seguindo as etapas abaixo.

1. No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative os seguintes recursos:
    - *Integração de Visibilidade de Estoque* – Obrigatório.
    - *Integração de Visibilidade de Estoque com compensação de reserva* – Recomendado, mas opcional. Exige a versão 10.0.22 ou posterior. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

1. Acesse **Gerenciamento de Estoque \> Configurar \> Parâmetros de Integração de Visibilidade de Estoque**.
1. Abra a guia **Geral** e defina as seguintes configurações:
    - **Ponto de extremidade de Visibilidade de Estoque** – Insira a URL do ambiente em que Visibilidade de Estoque está sendo executada. Para obter mais informações, consulte [Localizar o ponto de extremidade de serviço](inventory-visibility-configuration.md#get-service-endpoint).
    - **Número máximo de registros em uma única solicitação** – Defina como o número máximo de registros a serem incluídos em uma única solicitação. Você deve inserir um inteiro positivo, menor ou igual a 1.000. O valor padrão é 512. É recomendável manter o valor padrão, a menos que você tenha recebido orientações do suporte da Microsoft ou tiver certeza de que precisa alterá-lo.

1. Se você ativou a recurso opcional *Integridade de Visibilidade de Estoque com compensação de reserva*, abra a guia **Compensação de reserva** e defina as seguintes configurações:
    - **Habilitar compensação de reserva** – Defina como *Sim* para habilitar essa funcionalidade.
    - **Modificador de compensação de reserva** – Selecione o status da transação de estoque que compensará as reservas feitas em Visibilidade de Estoque. Essa configuração determina a fase de processamento da ordem que dispara compensações. O estágio é rastreado pelo status de transação do estoque da ordem. Selecione uma das seguintes opções:
        - *Em ordem* — para o status *Na transação*, uma ordem enviará uma solicitação de compensação quando for criada. A quantidade de compensação será a quantidade da ordem criada.
        - *Reserva* — para o status de *Transação com solicitação de reserva*, uma ordem enviará uma solicitação de compensação quando for reservada, retirada, quando a guia de remessa for postada ou quando for faturada. A solicitação será disparada apenas uma vez, para a primeira etapa quando ocorrer o referido processo. A quantidade de compensação será a quantidade na qual o status da transação de estoque é alterado de *Em ordem* para *Qtd. encomendada* (ou status posterior) na linha da ordem correspondente.

1. Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho. Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
