---
title: Instalar o Suplemento Visibilidade de Estoque
description: Este artigo descreve como instalar o Suplemento Visibilidade de Estoque para Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: eb17f24b90933dac0f875bb0ef2d5039a240b197
ms.sourcegitcommit: 1ca4ad100f868d518f3634dca445c9878962108e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2022
ms.locfileid: "9388531"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalar e configurar Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artigo descreve como instalar o Suplemento Visibilidade de Estoque para Microsoft Dynamics 365 Supply Chain Management.

Você deve usar o Microsoft Dynamics LCS (Lifecycle Services) para instalar o Suplemento Visibilidade de Estoque. O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Finance and Operations. Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Recomendamos que você ingresse no grupo de usuários do Suplemento de Visibilidade de Estoque, no qual é possível encontrar guias úteis, obter nossas atualizações mais recentes e postar perguntas que possam ser obtidas usando a Visibilidade de Estoque. Para entrar, envie um email para a equipe de produto da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) e inclua sua ID de ambiente do Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Pré-requisitos de Visibilidade de Estoque

Antes de instalar o Visibilidade de Estoque, você deve concluir as seguintes tarefas:

- Obter um projeto de implementação do LCS em que pelo menos um ambiente seja implantado.
- Verificar se os pré-requisitos para configurar suplementos foram concluídos. Para obter informações sobre esses pré-requisitos, consulte [Visão geral de suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A visibilidade de estoque não exige link de gravação dupla.

> [!NOTE]
> Os países/regiões com suporte no momento incluem Canadá (CCA, ECA), Estados Unidos (WUS, EUS), União Europeia (NEU, WEU), Reino Unido (SUK, WUK), Austrália (EAU, SEAU), Japão (EJP, WJP) e Brasil (SBR, SCUS).

Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar o Suplemento Visibilidade de Estoque

Antes de instalar o suplemento, registre um aplicativo e adicione um segredo de cliente ao Azure Active Directory (Azure AD) em sua assinatura do Azure. Para obter instruções, consulte [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app) e [Adicionar um segredo de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Anote os valores de **ID do aplicativo (cliente)**, **Segredo do cliente** e **ID do locatário** porque você precisará deles mais tarde.

> [!IMPORTANT]
> Se você tiver mais de um ambiente LCS, crie um aplicativo Azure AD diferente para cada ambiente. Se você usar a mesma ID de aplicativo e ID de locatário para instalar o Suplemento de Visibilidade de Estoque para ambientes diferentes, ocorrerá uma saída de token para ambientes mais antigos. Como resultado, somente a última instalação será válida.

Depois de registrar um aplicativo e adicionar um segredo de cliente ao Azure AD, siga estas etapas para instalar o Suplemento Visibilidade de Estoque.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index).
1. Na home page, selecione o projeto no qual seu ambiente foi implantado.
1. Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.
1. Na página do ambiente, role para baixo até encontrar a seção **Suplementos de ambiente** na seção **Integração do Power Platform**. Lá, você pode encontrar o nome do ambiente do Dataverse. Confirme se o nome do ambiente do Dataverse é aquele que você deseja usar para Visibilidade de Estoque.

    > [!NOTE]
    > No momento, apenas os ambientes do Dataverse que foram criados usando o LCS têm suporte. Se seu ambiente do Dataverse foi criado de outra forma (por exemplo, usando o centro de administração do PowerApps) e se ele estiver vinculado a ambiente do Supply Chain Management, primeiro corrija o problema de mapeamento antes de instalar o suplemento de visibilidade de estoque.
    >
    > É possível que seu ambiente de gravação dupla esteja vinculado a uma instância do Dataverse enquanto o LCS não está configurado para integração do Power Platform. Essa incompatibilidade de vinculação pode causar um comportamento inesperado. É recomendável que os detalhes do ambiente LCS correspondam ao que você está conectado em uma gravação dupla, de forma que a mesma conexão possa ser usada por eventos de negócios, tabelas virtuais e suplementos. Consulte [Incompatibilidade de vinculação](../../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#linking-mismatch) para obter informações sobre como corrigir o problema de mapeamento. Depois que a questão de mapeamento for resolvida, você poderá continuar a instalar a visibilidade do estoque.

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

> [!NOTE]
> Se levar mais de uma hora para instalar a partir da página LCS, sua conta de usuário provavelmente não terá permissão para instalar soluções no ambiente do Dataverse. Siga estas etapas para resolver o problema:
>
> 1. Cancele o processo de instalação do suplemento de Visibilidade de Estoque na página LCS.
> 1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) e certifique-se de que a conta de usuário que você deseja usar para instalar o suplemento tenha a licença do "Plano do Dynamics 365 Unified Operations" atribuída a ela. Atribua a licença, se necessário.
> 1. Entre no [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com) usando a conta de usuário relevante. Depois, instale o suplemento de visibilidade de estoque executando as seguintes etapas:
>     1. Selecione o ambiente em que deseja instalar o suplemento.
>     1. Selecione **Aplicativos do Dynamics 365**.
>     1. Selecione **Instalar aplicativo**.
>     1. Selecione **Visibilidade de Estoque**
>
> 1. Após a conclusão da instalação, volte para a página LCS e tente novamente reinstalar o complemento **Visibilidade de Estoque**.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar Visibilidade de Estoque no Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implantar o pacote de integração de Visibilidade de Estoque

Se você estiver executando o Supply Chain Management versão 10.0.17 ou anterior, contate a equipe de suporte de integração da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter o arquivo de pacote. Em seguida, implante o pacote no LCS.

> [!NOTE]
> Se ocorrer um erro de incompatibilidade de versão durante a implantação, você deverá importar manualmente o projeto X++ no ambiente de desenvolvimento. Em seguida, crie o pacote implantável no ambiente de desenvolvimento e implante-o no ambiente de produção.
>
> O código está incluído no Supply Chain Management versão 10.0.18. Se você estiver executando essa versão ou posterior, a implantação não será necessária.

Verifique se os recursos a seguir estão ativados no ambiente do Supply Chain Management. (Por padrão, eles estão ativados.)

| Descrição do recurso | Versão de código | Alternar classe |
|---|---|---|
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurar a integração da Visibilidade de Estoque

Após instalar o suplemento, prepare o sistema do Supply Chain Management para trabalhar com ele seguindo as etapas abaixo.

1. No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative os seguintes recursos:
    - *Integração de Visibilidade de Estoque* – Obrigatório.
    - *Integração de Visibilidade de Estoque com compensação de reserva* – Recomendado, mas opcional. Exige a versão 10.0.22 ou posterior. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

1. Acesse **Gerenciamento de Estoque \> Configurar \> Parâmetros de Integração de Visibilidade de Estoque**.
1. Abra a guia **Geral** e defina as seguintes configurações:
    - **Ponto de extremidade de Visibilidade de Estoque** – Insira a URL do ambiente em que Visibilidade de Estoque está sendo executada. Para obter mais informações, consulte [Localizar o ponto de extremidade de serviço](inventory-visibility-configuration.md#get-service-endpoint).
    - **Número máximo de registros em uma única solicitação** – Defina como o número máximo de registros a serem incluídos em uma única solicitação. Você deve inserir um inteiro positivo, menor ou igual a 1.000. O valor padrão é 512. É recomendável manter o valor padrão, a menos que você tenha recebido orientações do suporte da Microsoft ou tiver certeza de que precisa alterá-lo.

1. Se você ativou a recurso opcional *Integridade de Visibilidade de Estoque com compensação de reserva*, abra a guia **Compensação de reserva** e defina as seguintes configurações:
    - **Habilitar compensação de reserva** – Defina como *Sim* para habilitar essa funcionalidade.
    - **Modificador de compensação de reserva** – Selecione o status da transação de estoque que compensará as reservas feitas em Visibilidade de Estoque. Essa configuração determina a fase de processamento da ordem que dispara compensações. O estágio é rastreado pelo status de transação do estoque da ordem. Escolha uma das seguintes opções:
        - *Em ordem* — para o status *Na transação*, uma ordem enviará uma solicitação de compensação quando for criada. A quantidade de compensação será a quantidade da ordem criada.
        - *Reserva* — para o status de *Transação com solicitação de reserva*, uma ordem enviará uma solicitação de compensação quando for reservada, retirada, quando a guia de remessa for postada ou quando for faturada. A solicitação será disparada apenas uma vez, para a primeira etapa quando ocorrer o referido processo. A quantidade de compensação será a quantidade na qual o status da transação de estoque é alterado de *Em ordem* para *Qtd. encomendada* (ou status posterior) na linha da ordem correspondente.

1. Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho. Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar o suplemento Visibilidade de Estoque

Para desinstalar o suplemento de visibilidade de estoque, siga estas etapas:

1. Entre no Supply Chain Management.
1. Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e desabilite o trabalho.
1. Vá para LCS e abra a página do ambiente em que você deseja desinstalar o suplemento (consulte também [Instalar o suplemento de visibilidade de estoque](#install-add-in)).
1. Selecione **Desinstalar**.
1. O processo de desinstalação agora encerra o suplemento Visibilidade de Estoque, cancela o registro do suplemento do LCS e exclui todos os dados temporários armazenados no cache de dados do Suplemento Visibilidade de Estoque. No entanto, os dados de estoque principal sincronizados para a assinatura do Dataverse ainda estão armazenados ali. Para excluir esses dados, conclua o resto deste procedimento.
1. Abra o [Power Apps](https://make.powerapps.com).
1. Selecione **Ambiente** na barra de navegação
1. Selecione o ambiente do Dataverse vinculado ao seu ambiente LCS.
1. Acesse **Soluções** e exclua as cinco seguintes soluções, nesta ordem:
    1. Visibilidade de Estoque do Dynamics 365 - Âncora
    1. Visibilidade de Estoque do Dynamics 365 - Aplicativo
    1. Visibilidade de Estoque do Dynamics 365 - Controles
    1. Visibilidade de Estoque do Dynamics 365 - Plugins
    1. Visibilidade de Estoque do Dynamics 365- Base

    Depois que você excluir essas soluções, os dados armazenados nas tabelas também serão excluídos.

> [!NOTE]
> Se você restaurar um banco de dados do Supply Chain Management depois de desinstalar o suplemento de visibilidade de estoque e desejar reinstalar o suplemento, certifique-se de ter excluído os antigos dados de visibilidade de estoque armazenados na sua assinatura do Dataverse (conforme descrito no procedimento anterior) antes de reinstalar o suplemento. Isso impedirá problemas de inconsistência de dados que poderiam ocorrer.

## <a name="clean-inventory-visibility-data-from-dataverse-before-restoring-the-supply-chain-management-database"></a><a name="restore-environment-database"></a>Limpar dados de visibilidade de estoque do Dataverse antes de restaurar o banco de dados do Supply Chain Management

Se você estiver usando a visibilidade de inventário e restaurar seu banco de dados do Supply Chain Management, o banco de dados restaurado poderá conter dados que não são mais consistentes com os dados antes sincronizados pela visibilidade de estoque para o Dataverse. Essa inconsistência de dados pode causar erros do sistema e outros problemas. Portanto, é importante sempre limpar todos os dados de visibilidade do estoque do Dataverse antes de restaurar um banco de dados do Supply Chain Management.

Se for necessário restaurar um banco de dados do Supply Chain Management, use o seguinte procedimento:

1. Desinstale o suplemento de visibilidade de estoque e remova todos os dados relacionados no Dataverse, conforme descrito em [Desinstalar o suplemento de visibilidade de estoque](#uninstall-add-in)
1. Recupere o banco de dados do Supply Chain Management, por exemplo, conforme descrito em [Recuperação pontual do banco de dados (PITR)](../../fin-ops-core/dev-itpro/database/database-point-in-time-restore.md) ou [Recuperação pontual do banco de dados de produção para um ambiente de área restrita](../../fin-ops-core/dev-itpro/database/database-pitr-prod-sandbox.md).
1. Se você ainda desejar usá-lo, reinstale e configure o suplemento de visibilidade de estoque, conforme descrito em [Instalar o suplemento de visibilidade de estoque](#install-add-in) e [Configurar a integração da visibilidade do estoque](#setup-inventory-visibility-integration)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
