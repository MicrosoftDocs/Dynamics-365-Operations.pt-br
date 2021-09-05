---
title: Configurar Visibilidade de Estoque
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
ms.openlocfilehash: 8573fe01abb1c6092012baf85e8b7df40b74a31f
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343575"
---
# <a name="set-up-inventory-visibility"></a>Configurar Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como instalar o Suplemento Visibilidade de Estoque para Microsoft Dynamics 365 Supply Chain Management.

Você deve usar o Microsoft Dynamics LCS (Lifecycle Services) para instalar o Suplemento Visibilidade de Estoque. O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Finance and Operations.

Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Pré-requisitos de Visibilidade de Estoque

Antes de instalar o Visibilidade de Estoque, você deve concluir as seguintes tarefas:

- Obter um projeto de implementação do LCS em que pelo menos um ambiente seja implantado.
- Verificar se os pré-requisitos para configurar suplementos foram concluídos. Para obter informações sobre esses pré-requisitos, consulte [Visão geral de suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A visibilidade de estoque não exige link de gravação dupla.
- Entre em contato com a equipe de produto do Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os seguintes arquivos necessários:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (se a versão do Supply Chain Management que você está executando for anterior à versão 10.0.18)

> [!NOTE]
> Os países/regiões com suporte no momento incluem Canadá (CCA, ECA), Estados Unidos (WUS, EUS), União Europeia (NEU, WEU), Reino Unido (SUK, WUK) e Austrália (EAU, SEAU).

Se você tiver alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe de produto do Visibilidade de Estoque.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Configurar Dataverse

Para configurar o Dataverse para que possa ser usado com o Visibilidade de Estoque, use a ferramenta de implantação de pacote para implantar o pacote do Visibilidade de Estoque. As subseções a seguir descrevem como concluir cada tarefa.

> [!NOTE]
> No momento, apenas os ambientes do Dataverse que foram criados usando o LCS têm suporte. Se seu ambiente do Dataverse foi criado de alguma outra forma (por exemplo, usando o centro de administração do Power Apps) e se ele está vinculado a seu ambiente do Supply Chain Management, primeiro você deve entrar em contato com a equipe de produto do Visibilidade de Estoque para corrigir o problema de mapeamento. Você pode então instalar o Visibilidade de Estoque.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrar de uma versão antiga da solução Dataverse

Se você instalou uma versão mais antiga da solução Dataverse Visibilidade de Estoque, use estas instruções para atualizar sua versão. Existem dois casos:

- **Caso 1:** se você configurar manualmente o Dataverse importando a solução `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip`, siga estas etapas:

    1. Baixe os três seguintes arquivos:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Importe manualmente `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` e `InventoryServiceBase_managed.cab` para o Dataverse seguindo estas etapas:

        1. Abra a URL do ambiente do Dataverse.
        1. Abra a página **Soluções**.
        1. Selecione **Importar**.

    1. Use a ferramenta de implantação de pacote para implantar o pacote `InventoryServiceApplication.PackageDeployer.zip`. Para obter instruções, consulte a seção [Use a ferramenta de implantação de pacote para implantar o pacote](#deploy-package) posteriormente neste tópico.

- **Caso 2:** se você configurar o Dataverse usando a ferramenta de implantação de pacote antes de instalar o pacote `.*PackageDeployer.zip` mais antigo, baixe o `InventoryServiceApplication.PackageDeployer.zip` e faça uma atualização. Para obter instruções, consulte a seção [Use a ferramenta de implantação de pacote para implantar o pacote](#deploy-package).

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Use a ferramenta de implantação de pacote para implantar o pacote

1. Instale as ferramentas para desenvolvedores, conforme descrito em [Baixar ferramentas do NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Desbloqueie o arquivo `InventoryServiceApplication.PackageDeployer.zip` que você baixou do grupo do Teams seguindo estas etapas:

    1. Selecione e segure (ou clique com o botão direito do mouse) no arquivo e selecione **Propriedades**.
    1. Na caixa de diálogo **Propriedades**, na guia **Geral**, localize a seção **Segurança**, selecione **Desbloquear** e aplique a alteração. Se não houver uma seção **Segurança** na guia **Geral**, isso indicará que o arquivo não está bloqueado. Nesse caso, vá para a próxima etapa.

    ![Desbloquear o arquivo baixado](media/unblock-file.png "Desbloquear o arquivo baixado")

1. Descompacte `InventoryServiceApplication.PackageDeployer.zip` para encontrar os seguintes itens:

    - Pasta do `InventoryServiceApplication`
    - Arquivo `[Content_Types].xml`
    - Arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`

1. Copie cada um desses itens para o diretório `.\Tools\PackageDeployment`. (Esse diretório foi criado quando você instalou as ferramentas de desenvolvedor.)
1. Execute `.\Tools\PackageDeployment\PackageDeployer.exe` e siga as instruções na tela para importar as soluções.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar o Suplemento Visibilidade de Estoque

Antes de instalar o suplemento, registre um aplicativo e adicione um segredo de cliente ao Azure Active Directory (Azure AD) em sua assinatura do Azure. Para obter instruções, consulte [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app) e [Adicionar um segredo de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Anote os valores de **ID do aplicativo (cliente)**, **Segredo do cliente** e **ID do locatário**, porque você precisará deles mais tarde.

Depois de registrar um aplicativo e adicionar um segredo de cliente ao Azure AD, siga estas etapas para instalar o Suplemento Visibilidade de Estoque.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index).
1. Na home page, selecione o projeto no qual seu ambiente foi implantado.
1. Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.
1. Na página do ambiente, role para baixo até encontrar a seção **Suplementos de ambiente** na seção **Integração do Power Platform**. Lá, você pode encontrar o nome do ambiente do Dataverse.
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

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar o suplemento Visibilidade de Estoque

Para desinstalar o suplemento Visibilidade de Estoque, selecione **Desinstalar** na página do LCS. O processo de desinstalação encerra o suplemento Visibilidade de Estoque, cancela o registro do suplemento do LCS e exclui todos os dados temporários armazenados no cache de dados do Suplemento Visibilidade de Estoque. No entanto, os dados de estoque principal armazenados na assinatura do Dataverse não são excluídos.

Para desinstalar os dados de estoque armazenados em sua assinatura do Dataverse, abra o [Power Apps](https://make.powerapps.com), selecione **Ambiente** na barra de navegação e selecione o ambiente do Dataverse que está vinculado a seu ambiente do LCS. Em seguida, acesse **Soluções** e exclua as cinco seguintes soluções:

- Solução de ancoragem para aplicativo Visibilidade de Estoque em soluções do Dynamics 365
- Solução de Aplicativos Visibilidade de Estoque do Dynamics 365 FNO SCM
- Configuração de Serviço de Estoque
- Visibilidade de Estoque Autônomo
- Solução Base Visibilidade de Estoque do Dynamics 365 FNO SCM

Depois que você excluir essas soluções, os dados armazenados nas tabelas também serão excluídos.

## <a name="set-up-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar o Supply Chain Management

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

1. No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative o recurso *Integração da Visibilidade de Estoque*.
1. Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de Integração da Visibilidade de Estoque** e insira a URL do ambiente em que você está executando a Visibilidade de Estoque. Para obter mais informações, consulte [Localizar o ponto de extremidade de serviço](inventory-visibility-power-platform.md#get-service-endpoint).
1. Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho. Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
