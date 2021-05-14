---
title: Configurar tabelas virtuais do Dataverse
description: Este tópico mostra como configurar tabelas virtuais para o Dynamics 365 Human Resources. Gere e atualize tabelas virtuais existentes e analise as tabelas geradas e disponíveis.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 04997aba427ae6013c8154593b09ae1a45a580c3
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935744"
---
# <a name="configure-dataverse-virtual-tables"></a>Configurar tabelas virtuais do Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O Dynamics 365 Human Resources é uma fonte de dados virtual no Microsoft Dataverse. Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Dataverse e do Microsoft Power Platform. Os dados de tabelas virtuais não são armazenados no Dataverse, mas no banco de dado do aplicativo.

Para habilitar operações CRUD em entidades do Human Resources do Dataverse, você deverá disponibilizar as entidades como tabelas virtuais no Dataverse. Isso permite executar operações CRUD do Dataverse e do Microsoft Power Platform em dados que estão no Human Resources. As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.

> [!NOTE]
> Entidades do Human Resources correspondem a tabelas do Dataverse. Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Tabelas virtuais disponíveis para Human Resources

Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como tabelas virtuais no Dataverse. Elas também estão disponíveis no Power Platform. Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Dataverse. Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.

Você pode exibir a lista de tabelas virtuais habilitada no ambiente e começar a trabalhar com as tabelas no [Power Apps](https://make.powerapps.com), na solução **Tabelas virtuais do Dynamics 365 HR**.

![Tabelas virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tabelas virtuais x tabelas nativas

As tabelas virtuais para Human Resources não são iguais às tabelas nativas do Dataverse criadas para o Human Resources. 

As tabelas nativas do Human Resources são geradas separadamente e mantidas na solução HCM Common no Dataverse. Com tabelas nativas, os dados são armazenados no Dataverse e exigem a sincronização com o banco da dados do aplicativo Human Resources.

> [!NOTE]
> Para obter uma lista das tabelas nativas do Dataverse para Human Resources, consulte [Tabelas do Dataverse](./hr-developer-entities.md).

## <a name="setup"></a>Configurar

Siga estas etapas de configuração para habilitar tabelas virtuais no seu ambiente.

### <a name="enable-virtual-tables-in-human-resources"></a>Habilitar tabelas virtuais no Human Resources

Primeiro, você deve habilitar tabelas virtuais no espaço de trabalho **Gerenciamento de recursos**.

1. No Human Resources, selecione **Administração do sistema**.

2. Selecione o bloco **Gerenciamento de recursos**.

3. Selecione **Suporte da tabela virtual para HR no Dataverse** e selecione **Habilitar**.

Para obter mais informações sobre como habilitar e desabilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrar o aplicativo no Microsoft Azure

Você precisa registrar sua instância do Human Resources no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários. Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app).

1. Abra o [portal do Microsoft Azure](https://portal.azure.com).

2. Na lista Serviços do Azure, selecione **Registros de aplicativos**.

3. Selecione **Novo registro**.

4. No campo **Nome**, insira um nome descritivo para o aplicativo. Por exemplo, **Tabelas virtuais do Dynamics 365 Human Resources**.

5. No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.

6. Selecione **Registrar**.

7. Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**. Anote a **ID do Aplicativo (cliente)** nesse momento. Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. No painel de navegação esquerdo, selecione **Certificados e segredos**.

9. Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.

10. Forneça uma descrição, selecione uma duração e selecione **Adicionar**.

11. Registre o valor do segredo a partir a propriedade **Valor** da tabela. Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Anote o valor do segredo nesse momento. O segredo nunca será exibido novamente depois que você sair desta página.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Instalar o aplicativo Dynamics 365 HR Virtual Table

Instale o aplicativo Dynamics 365 HR Virtual Table no ambiente do Power Apps para implantar o pacote da solução da tabela virtual no Dataverse.

1. No Human Resources, abra a página **Integração do Microsoft Dataverse**.

2. Selecione a guia **Tabelas virtuais**.

3. Selecione **Instalar aplicativo de tabela virtual**.

### <a name="configure-the-virtual-table-data-source"></a>Configurar a fonte de dados da tabela virtual

A próxima etapa é configurar a fonte de dados de tabela virtual no ambiente do Power Apps.

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.

3. Selecione a **URL de Ambiente** na seção **Detalhes** da página.

4. No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.

5. Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.

   > [!NOTE]
   > A instalação do aplicativo de tabela virtual da etapa de configuração anterior pode levar alguns minutos. Se **Configurações de Fonte de Dados Virtual do Finance and Operations** não estiver disponível na lista, aguarde um minuto e atualize a lista.

6. Selecione **Resultados**.

7. Selecione o registro **Fonte de Dados do Microsoft HR**.

8. Insira as informações necessárias para a configuração da fonte de dados:

   - **URL de Destino**: a URL do namespace do Human Resources. O formato da URL de destino é:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Por exemplo:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Inclua o caractere "**/**" no final da URL para evitar o recebimento de um erro.

   - **ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).

   - **ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure. Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure. Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Selecione **Salvar e Fechar**.

### <a name="grant-app-permissions-in-human-resources"></a>Conceder permissões de aplicativo no Human Resources

Conceda permissões para os dois aplicativos do Azure AD no Human Resources:

- O aplicativo criado para o seu locatário no portal do Microsoft Azure
- O aplicativo Dynamics 365 HR Virtual Table instalado no ambiente do Power Apps 

1. No Human Resources, abra a página **Aplicativos do Azure Active Directory**.

2. Selecione **Novo** para criar um novo registro de aplicativo:

    - No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.
    - No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.
    - No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.

3. Selecione **Novo** para criar um segundo registro de aplicativo:

    - **ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nome**: Dynamics 365 HR Virtual Table
    - No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.

## <a name="generate-virtual-tables"></a>Gerar tabelas virtuais

Quando a configuração for concluída, você poderá selecionar as tabelas virtuais que deseja gerar e habilitar na instância do Dataverse.

1. No Human Resources, abra a página **Integração do Microsoft Dataverse**.

2. Selecione a guia **Tabelas virtuais**.

> [!NOTE]
> A alternância **Habilitar tabelas virtuais** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas. Se a alternância estiver definida como **Não**, revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.

3. Selecione uma ou mais tabelas a serem geradas no Dataverse.

4. Selecione **Gerar/atualizar**.

![Integração do Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Verificar status de geração de tabela

As tabelas virtuais são geradas no Dataverse por meio de um processo assíncrono em segundo plano. Atualizações na exibição do processo na central de ações. Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.

1. No Human Resources, abra a página **Automações de processo**.

2. Selecione a guia **Processos em segundo plano**.

3. Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de tabelas virtuais**.

4. Selecione **Exibir resultados mais recentes**.

O painel deslizante exibe os resultados da execução mais recente para o processo. Você pode exibir o log do processo, incluindo todos os erros retornados do Dataverse.

## <a name="see-also"></a>Consulte também

[O que é o Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tabelas no Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Visão geral de relacionamentos entre tabelas](/powerapps/maker/common-data-service/relationships-overview)<br>
[Criar e editar tabelas virtuais que contenham dados de uma fonte de dados externa](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[O que são os portais do Power Apps?](/powerapps/maker/portals/overview)<br>
[Visão geral da criação de aplicativos no Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
