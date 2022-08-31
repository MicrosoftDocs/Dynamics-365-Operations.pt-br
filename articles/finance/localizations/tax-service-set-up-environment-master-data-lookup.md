---
title: Habilitar pesquisa de dados mestres para configuração de cálculo de imposto
description: Este artigo explica como configurar e habilitar o recurso de pesquisa de dados mestres do cálculo de imposto.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f9d882340171173e5e503f8b5e3aa856e8544b0
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306193"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Habilitar pesquisa de dados mestres para configuração de cálculo de imposto 

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar e habilitar o recurso de pesquisa de dados mestres do cálculo de imposto. Uma lista suspensa está disponível para selecionar valores na configuração do cálculo de imposto para campos como **Entidade legal**, **Conta de fornecedor**, **Código do item** e **Prazo de entrega**. Esses valores são provenientes do ambiente conectado do Microsoft Dynamics 365 Finance usando a fonte de dados do Microsoft Dataverse.

> [!NOTE] 
> A funcionalidade de pesquisa de dados mestres do cálculo de imposto é opcional. Você poderá ignorar as etapas a seguir se desabilitar o recurso **Suporte à fonte de dados do Serviço de Imposto do Dataverse** no RCS (Regulatory Configuration Service). No entanto, nesse caso, a lista suspensa não estará disponível na configuração de cálculo de imposto.

Para habilitar a lista suspensa na configuração da versão do recurso do Cálculo de Imposto, conclua as etapas a seguir.

1. [Habilite a integração com o Microsoft Power Platform e abra o ambiente do Dataverse.](#enable)
2. [Instale as entidades virtuais de finanças e operações.](#install)
3. [Registre um aplicativo do Azure Active Directory (Azure AD).](#register)
4. [Conceda permissões de aplicativo em aplicativos de finanças e operações.](#grant)
5. [Configure a fonte de dados da entidade virtual.](#configure)
6. [Habilite as entidades virtuais do Dataverse.](#virtual)
7. [Configure o aplicativo conectado para o Cálculo de Imposto.](#set-up)
8. [Importe e configure a configuração de Mapeamento do Modelo do Dataverse.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Habilitar a integração com o Microsoft Power Platform e abrir o ambiente do Dataverse

A integração de aplicativos de finanças e operações com o Microsoft Power Platform pode ser habilitada quando você cria um novo ambiente desses aplicativos no portal Lifecycle Services (LCs) do Microsoft Dynamics. Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Depois de concluir essa etapa, o nome de um ambiente do Microsoft Power Platform aparecerá na seção **Integração do Power Platform**.

1. No LCS, dentro do seu ambiente de finanças e operações, na seção **Integração do Power Platform**, encontre e anote o valor do **Nome do Ambiente** do ambiente vinculado.

    [![Valor do nome do ambiente.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. No [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments), na guia **Ambientes**, selecione aquele que corresponde ao valor do **Nome do ambiente** que você anotou.
3. Na página **Detalhes**, encontre o valor do **URL do ambiente** do Dataverse. Anote esse valor, pois ele será necessário na [Etapa 7. Configure o aplicativo conectado para Cálculo do Imposto](#set-up).
4. Verifique se você consegue abrir o ambiente do Dataverse no seu navegador selecionando o valor **URL do ambiente**.

    [![Página do ambiente do Dataverse.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Mantenha o ambiente do Dataverse aberto no navegador. Você precisará dele na [Etapa 5. Configure a fonte de dados da entidade virtual](#configure).

Para ver mais informações, consulte [Habilite a integração com o Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Instalar as entidades virtuais de finanças e operações

A solução do Dataverse para as entidades virtuais de finanças e operações precisa ser instalada a partir da solução da entidade virtual do Microsoft AppSource.

1. No AppSource, encontre a [entidade virtual de finanças e operações](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Selecione **Obter agora**.
3. No campo **Selecionar um ambiente**, insira o valor do **Nome do ambiente** que você anotou.
4. Selecione as caixas de seleção e **Instalar**.

Quando a instalação terminar, você encontrará o aplicativo da **Entidade virtual de finanças e operações** no [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/), em **Recursos** \> **Aplicativos do Dynamics 365**.

Para obter mais informações, consulte [Como obter a solução de entidade virtual](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Registrar um aplicativo Azure AD

Você precisa registrar um aplicativo Azure AD no mesmo locatário dos aplicativos de finanças e operações para que eles possam ser chamados pelo Dataverse.

1. No [portal do Azure](https://portal.azure.com), acesse **Azure Active Directory \> Registros de aplicativo**.
2. Selecione **Novo registro** e digite as seguintes informações:

    - **Nome** – insira um nome exclusivo.
    - **Tipo de Conta** – insira **Qualquer diretório do Azure AD** (um ou vários locatários).
    - **Redirecionar URI** – deixe este campo em branco.

3. Selecione **Registrar**.
4. Anote o valor da **ID do aplicativo (cliente)**, porque você precisará dele mais tarde.

    [![Valor do ID do aplicativo Azure AD (cliente).](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Crie uma chave simétrica para o aplicativo.
6. No novo aplicativo, selecione **Certificados e segredos**.
7. Selecione **Novo segredo do cliente**.
8. Insira uma descrição, escolha uma data de validade e selecione **Salvar**. Uma chave será criada e depois mostrada. Copie o valor para usar depois.

Para mais informações, consulte [Registre o aplicativo Azure AD](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Conceder permissões de aplicativo em aplicativos de finanças e operações

O Dataverse usa o aplicativo Azure AD criado para chamar os aplicativos de finanças e operações. Sendo assim, ele precisa ser de confiança dos aplicativos de finanças e operações e associado a uma conta de usuário com os direitos relevantes. Nesses aplicativos, você precisa criar um usuário de serviço especial com direitos **apenas** para a funcionalidade da entidade virtual. Esse usuário de serviço não pode ter outros direitos. Depois de concluir essa etapa, qualquer aplicativo que tiver o segredo do aplicativo Azure AD que você criou poderá chamar o ambiente de aplicativos de finanças e operações, além de acessar a funcionalidade da entidade virtual.

1. No seu ambiente, acesse **Administração do Sistema** \> **Usuários** \> **Usuários**.
2. Selecione **Novo** para adicionar um novo usuário e insira as seguintes informações:

    - **ID do Usuário** – insira **Integração com o Dataverse** ou outro valor.
    - **Nome do usuário** – insira **Integração com o Dataverse** ou outro valor.
    - **Provedor** – defina este campo como **NonAAD**.
    - **Email** – insira **Integração com o Dataverse** ou outro valor. (O valor não precisa ser uma conta de email válida.)

3. Atribua a função de segurança **Aplicativo de integração de entidade virtual do Dataverse** ao usuário.
4. Remova todas as outras funções, incluindo **Usuário do sistema**.
5. Acesse **Administração do Sistema** \> **Configuração** \> **Aplicativos do Azure Active Directory** para registrar o Dataverse. 
6. Adicione uma linha e, no campo **ID do Cliente**, insira o valor **ID do Aplicativo (cliente)** que você anotou.
7. No campo **Nome**, insira um nome. Por exemplo, insira **Integração com o Dataverse**.
8. No campo **ID do Usuário**, insira a ID de usuário que você criou.

Para mais informações, consulte [Conceda permissões de aplicativo em aplicativos de finanças e operações](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Configurar a fonte de dados da entidade virtual

Você precisa fornecer o Dataverse com a instância do aplicativo de finanças e operações para se conectar.

1. Seu ambiente do Dataverse deve estar aberto no seu navegador desde a [Etapa 1. Habilite a integração com o Microsoft Power Platform e abra o ambiente do Dataverse](#enable). Selecione o botão Configurações (símbolo de engrenagem) no canto superior direito e escolha **Configurações Avançadas**.

    [![Como abrir as Configurações avançadas no ambiente do Dataverse.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. No menu suspenso **Configurações**, selecione **Administração**.

    [![Administração.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Selecione **Fontes de Dados da Entidade Virtual**.

    [![Fontes de Dados da Entidade Virtual.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Selecione a fonte de dados chamada **Finanças e Operações**.

    [![Fonte de dados de Finanças e Operações.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Insira as seguintes informações de etapas anteriores:

    - **URL de Destino** – insira a URL em que você pode acessar os aplicativos de finanças e operações.
    - **URL do OAuth** – insira `https://login.windows.net/`.
    - **ID do Locatário** – especifique seu locatário. Esse valor pode ser o nome de domínio do email da sua empresa (como contoso.com).
    - **ID do Aplicativo do AAD** – insira o valor **ID do Aplicativo (cliente)** que já foi criado.
    - **Segredo do Aplicativo do AAD** – insira o segredo que já foi gerado.
    - **Recurso do AAD** – insira **00000015-0000-0000-c000-000000000000**. Esse valor é o aplicativo Azure AD que representa os aplicativos de finanças e operações. O valor deve ser sempre o mesmo.

6. Salve as alterações.
7. Feche a página para voltar à página **Administração**, onde você começará a [Etapa 6. Habilite as entidades virtuais do Dataverse](#virtual).

    [![Como fechar a entidade para edição.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Para mais informações, consulte [Configure a fonte de dados da entidade virtual](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Habilitar as entidades virtuais do Dataverse

A visibilidade das entidades virtuais dos aplicativos de finanças e operações precisa ser definida como **Sim** para que sejam utilizadas pela configuração do Cálculo de Imposto.

> [!NOTE]
> Você pode ignorar essa etapa habilitando as entidades virtuais relacionadas ao Cálculo do Imposto em apenas um clique na [Etapa 8. Configure o aplicativo conectado para o Cálculo de Imposto](#import). No entanto, recomendamos que você habilite manualmente pelo menos uma entidade virtual para indicar que a conexão entre os aplicativos de finanças e operações e o Dataverse está bem estabelecida.

1. No seu ambiente do Dataverse, na página **Administração**, selecione o botão Filtrar (símbolo de funil) no canto superior direito.

    [![Botão Filtrar.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. Na janela **Localização Avançada**, no campo **Procurar**, selecione **Entidades de Finanças e Operações Disponíveis**.
3. Adicione a seguinte regra: **Nome** – **Contém** – **CompanyInfoEntity**. Selecione **Resultados**.

    [![Janela Localização Avançada.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Escolha **CompanyInfoEntity** nos resultados da pesquisa, marque a caixa de seleção **Visível** e selecione **Salvar**.

    [![Como configurar a visibilidade da entidade.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Repita as etapas anteriores para as seguintes entidades mencionadas na configuração do Cálculo de Imposto:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Somente os primeiros 5.000 registros de uma entidade podem ser recuperados pelo Dataverse e disponibilizados na lista suspensa da configuração do Cálculo de Imposto.

Para obter mais informações, consulte [Habilitar entidades virtuais do Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Configurar o aplicativo conectado para o Cálculo de Imposto

1. Acesse o **Relatório Eletrônico** e, na seção **Links relacionados**, selecione **Aplicativos conectados**.

    [![Aplicativos conectados.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

2. Selecione **Novo** para adicionar um registro e insira as seguintes informações.

    - **Nome** - Digite um nome.
    - **Tipo** – Selecione **Dataverse**.
    - **Aplicativo** – insira o valor da **URL do ambiente** do seu ambiente do Dataverse, que você anotou na [Etapa 1. Habilite a integração com a Microsoft Power Platform e abra seu ambiente do Dataverse](#enable).
    - **Locatário** – insira seu locatário.
    - **URL personalizada** – insira sua URL do Dataverse e acrescente **/api/data/v9.1** a ela.

3. Selecione **Verificar conexão** e, na caixa de diálogo, selecione **Clique aqui para se conectar ao aplicativo remoto selecionado**.

    [![Como verificar a conexão.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
4. Verifique se você recebeu uma mensagem "Êxito" que indica que a conexão foi estabelecida.

    [![Mensagem de êxito.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)
    
5. No RCS, abra o espaço de trabalho **Gerenciamento de recursos** e habilite estes recursos:

    - Recursos de globalização
    - Suporte às fontes de dados do Dataverse para relatório eletrônico
    - Suporte à fonte de dados do Serviço de Imposto do Dataverse

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Importar e configurar a configuração de Mapeamento do Modelo do Dataverse

A Microsoft fornece configurações de mapeamento de modelo padrão para entidades de aplicativos de finanças e operações para o Cálculo de Imposto.

1. No RCS, acesse **Relatório Eletrônico**.
2. Na seção **Provedores de configuração**, no bloco do provedor **Microsoft** selecione, **Repositórios**.

    [![Repositórios.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Selecione o registro **Repositório de configuração global** e, depois, **Abrir**.
4. Em **Modelo de Dados do Imposto** \> **Modelo de Dados do Cálculo do Imposto**, selecione a configuração do **Mapeamento do Modelo do Dataverse**.
5. Na Guia Rápida **Versões**, selecione uma versão compatível com a versão dos aplicativos de finanças e operações e selecione **Importar**.

    [![Como importar a configuração do Mapeamento do Modelo do Dataverse.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > A configuração **Mapeamento do Modelo do Dataverse** é válida apenas na versão dela mais alta que foi importada. Portanto, você não deve importar uma versão da configuração de **Mapeamento de Modelo do Dataverse** superior à versão da configuração do Cálculo do Imposto que você planeja implementar. Por exemplo, se você planeja implementar a versão 40.50.225 da configuração do Cálculo de Imposto, importe apenas a versão 40.50.13 da configuração do **Mapeamento do Modelo do Dataverse**. Você não deve importar a versão 40.54.14. Caso contrário, haverá uma incompatibilidade com o modelo de dados na configuração.

6. Acesse o **Relatório Eletrônico** e selecione o bloco **Configurações do imposto**.
7. Selecione a configuração do **Mapeamento do Modelo do Dataverse** e selecione **Editar**.
8. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.
9. No campo **Aplicativo conectado**, selecione o aplicativo conectado que você configurou na [Etapa 7. Configure o aplicativo conectado do Cálculo de Imposto](#set-up).
10. Defina a opção **Definir visibilidade da tabela virtual** como **Sim** para que todas as entidades virtuais relacionadas ao Cálculo de Imposto fiquem visíveis.

Você configurou a funcionalidade da pesquisa de dados mestre. Agora, será habilitada uma lista suspensa para campos como **Entidade Legal**, **Conta de fornecedor**, **Código do item** e **Prazo de entrega** do Dynamics 365 Finance na configuração da **Versão do recurso do Cálculo de Imposto**.

[![Lista suspensa da entidade legal.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
