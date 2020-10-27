---
title: Configurar entidades virtuais do Common Data Service
description: Este tópico mostra como configurar entidades virtuais para o Dynamics 365 Human Resources. Gerar e atualizar entidades virtuais existentes e analisar as entidades geradas e disponíveis.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959566"
---
# <a name="configure-common-data-service-virtual-entities"></a>Configurar entidades virtuais do Common Data Service

[!include [banner](includes/preview-feature.md)]

O Dynamics 365 Human Resources é uma fonte de dados virtual no Common Data Service. Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Common Data Service e do Microsoft Power Platform. Os dados para entidades virtuais não são armazenados no Common Data Service, mas no banco de dado do aplicativo. 

Para habilitar as operações CRUD em entidades do Human Resources do Common Data Service, você deverá disponibilizar as entidades como entidades virtuais no Common Data Service. Isso permite executar operações CRUD do Common Data Service e do Microsoft Power Platform em dados que estão no Human Resources. As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.

## <a name="available-virtual-entities-for-human-resources"></a>Entidades virtuais disponíveis para Human Resources

Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como entidades virtuais no Common Data Service. Elas também estão disponíveis no Power Platform. Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Common Data Service. Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.

Você pode exibir a lista de entidades virtuais habilitada no ambiente e começar a trabalhar com as entidades no [Power Apps](https://make.powerapps.com), na solução **Entidades Virtuais do Dynamics 365 HR**.

![Entidades Virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Entidades virtuais versus entidades naturais

As entidades virtuais para Human Resources não são iguais das entidades naturais do Common Data Service criadas para o Human Resources. As entidades naturais para o Human Resources são geradas separadamente e mantidas na solução HCM Common no Common Data Service. Com as entidades naturais, os dados são armazenados no Common Data Service e exigem a sincronização com o banco da dados do aplicativo Human Resources.

> [!NOTE]
> Para obter uma lista das entidades naturais do Common Data Service para Human Resources, consulte [Entidades do Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Configurar

Siga estas etapas de configuração para habilitar as entidades virtuais no seu ambiente. 

### <a name="register-the-app-in-microsoft-azure"></a>Registrar o aplicativo no Microsoft Azure

Primeiro, você precisa registrar o aplicativo no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários. Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Abra o [portal do Microsoft Azure](https://portal.azure.com).

2. Na lista Serviços do Azure, selecione **Registros de aplicativos**.

3. Selecione **Novo registro**.

4. No campo **Nome**, insira um nome descritivo para o aplicativo. Por exemplo, **Entidades virtuais do Dynamics 365 Human Resources**.

5. No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.

6. Selecione **Registrar**.

7. Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**. Anote a **ID do Aplicativo (cliente)** nesse momento. Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. No painel de navegação esquerdo, selecione **Certificados e segredos**.

9. Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.

10. Forneça uma descrição, selecione uma duração e selecione **Adicionar**.

11. Registre o valor do segredo. Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > Anote o valor do segredo nesse momento. O segredo nunca será exibido novamente depois que você sair desta página.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>Instalar o aplicativo Dynamics 365 HR Virtual Entity

Instale o aplicativo Dynamics 365 HR Virtual Entity no seu ambiente do Power Apps para implantar o pacote da solução da entidade virtual no Common Data Service.

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.

3. Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.

4. Selecione a ação **Instalar aplicativo**.

5. Selecione **Dynamics 365 HR Virtual Entity** e selecione **Avançar**.

6. Analisar e marcar para concordar com os termos de serviço.

7. Selecione **Instalar**.

A instalação demora alguns minutos. Ao concluir, prossiga para as próximas etapas.

![Instalar o aplicativo Dynamics 365 HR Virtual Entity do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>Configurar a fonte de dados da entidade virtual 

A próxima etapa é configurar a fonte de dados de entidade virtual no ambiente do Power Apps. 

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.

3. Selecione a **URL de Ambiente** na seção **Detalhes** da página.

4. No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.

5. Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.

6. Selecione **Resultados**.

7. Selecione o registro **Fonte de Dados do Microsoft HR**.

8. Insira as informações necessárias para a configuração da fonte de dados.

   - **URL de Destino**: a URL do namespace do Human Resources.
   - **ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).
   - **ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure. Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).
   - **Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure. Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

9. Selecione **Salvar e Fechar**.

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a>Conceder permissões de aplicativo no Human Resources

Conceda permissões para os dois aplicativos do Azure AD no Human Resources:

- O aplicativo criado para o seu locatário no portal do Microsoft Azure
- O aplicativo Dynamics 365 HR Virtual Entity instalado no ambiente do Power Apps 

1. No Human Resources, abra a página **Aplicativos do Azure Active Directory**.

2. Selecione **Novo** para criar um novo registro de aplicativo:

    - No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.
    - No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.
    - No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.

3. Selecione **Novo** para criar um segundo registro de aplicativo:

    - **ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nome**: Dynamics 365 HR Virtual Entity
    - No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.

## <a name="generate-virtual-entities"></a>Gerar entidades virtuais

Quando a configuração for concluída, você poderá selecionar as entidades virtuais que deseja gerar e habilitar na instância do Common Data Service.

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.

3. Selecione a **URL de Ambiente** na seção **Detalhes** da página.

4. No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página.

5. Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Entidades do HR Disponíveis**.

6. Use as opções de filtro para localizar a entidade ou entidades que deseja habilitar.

7. Selecione uma entidade na lista.

8. Na página da entidade, altere a propriedade **Foi Gerada** para **Sim** para a entidade.

9. Salve e feche a página da entidade.

> [!NOTE]
> Você pode gerar várias entidades virtuais de uma só vez usando a página **Alterar Vários Registros**. Selecione vários registros na página e selecione **Editar** na faixa de opções. Em seguida, você poderá alterar a propriedade **Foi Gerada** para todos os registros selecionados.

![Entidades do HR Disponíveis](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> Para simplificar o processo de geração de entidades virtuais em versões futuras, o processo ocorrerá em uma página no Human Resources.

## <a name="see-also"></a>Consulte também

[O que é o Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Visão geral de entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Visão geral de relacionamentos entre entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Criar e editar entidades virtuais que contenham dados de uma fonte de dados externa](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[O que são os portais do Power Apps?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Visão geral da criação de aplicativos no Power Apps](https://docs.microsoft.com/powerapps/maker/)
