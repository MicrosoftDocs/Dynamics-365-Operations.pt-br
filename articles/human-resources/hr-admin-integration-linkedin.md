---
title: Integrar com o LinkedIn Talent Hub
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 Human Resources e o LinkedIn Talent Hub.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: efcac2bd82956015eb822c6a493b8625a35cd194
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805049"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integrar com o LinkedIn Talent Hub

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) é uma plataforma do sistema de acompanhamento de candidatos (ATS). Ele permite que você forneça, gerencie e contrate funcionários em um único local. Ao integrar o Microsoft Dynamics 365 Human Resources ao LinkedIn Talent Hub, você pode criar registros de funcionários com facilidade no Human Resources para candidatos que foram contratados para uma posição.

## <a name="setup"></a>Configurar

Um administrador do sistema deve concluir as tarefas de configuração para habilitar a integração com o LinkedIn Talent Hub. Primeiro, no ambiente do Power Apps, você deve configurar um usuário e uma função de segurança para conceder as permissões apropriadas ao LinkedIn Talent Hub para gravar dados no Human Resources.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Vincular seu ambiente ao LinkedIn Talent Hub

1. Abra o [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. No menu suspenso do usuário, selecione **Configurações do Produto**.

3. No painel de navegação esquerdo, na seção **Avançado**, selecione **Integrações**.

4. Selecione **Autorizar** para a integração do Microsoft Dynamics 365 Human Resources.

5. Na página **Dynamics 365 Human Resources**, selecione o ambiente ao qual vincular o LinkedIn Talent Hub e, em seguida, selecione **Vincular**.

    ![Integração do LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Você pode vincular somente a ambientes nos quais sua conta de usuário tenha acesso de administrador ao ambiente do Human Resources e ao ambiente do Power Apps associado. Se nenhum ambiente estiver listado na página Link do Human Resources, verifique se você tem ambientes licenciados do Human Resources no locatário e se o usuário que entrou na página de vinculação tem permissões de administrador para o ambiente do Human Resources e o ambiente do Power Apps.

### <a name="create-a-power-apps-security-role"></a>Criar uma função de segurança do Power Apps

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista de **Ambientes**, selecione o ambiente associado ao ambiente do Human Resources ao qual você deseja vincular sua instância do LinkedIn Talent Hub.

3. Selecione **Configurações**.

4. Expanda o nó **Usuários + Permissões** e selecione **Funções de Segurança**.

5. Na página **Funções de Segurança**, na barra de ferramentas, selecione **Nova função**.

6. Na guia **Detalhes**, insira um nome para a função, como **Integração LinkedIn Talent Hub HRIS**.

7. Na guia **Personalização**, selecione a permissão **Leitura** no nível da organização para as seguintes entidades:

    - Entidade
    - Campo
    - Relacionamento

8. Salve e feche a função de segurança.

### <a name="create-a-power-apps-application-user"></a>Criar um usuário de aplicativo do Power Apps

Um usuário de aplicativo deve ser criado para o adaptador do LinkedIn Talent Hub a fim de conceder permissões ao adaptador para gravar registros de candidato no ambiente do Power Apps.

1. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2. Na lista de **Ambientes**, selecione o ambiente associado ao ambiente do Human Resources ao qual você deseja vincular sua instância do LinkedIn Talent Hub.

3. Selecione **Configurações**.

4. Expanda o nó **Usuários + Permissões** e selecione **Usuários**.

5. Selecione **Gerenciar usuários no Dynamics 365**.

6. Use o menu suspenso acima da lista para alterar a exibição do padrão **Usuários Habilitados** para **Usuários do Aplicativo**.

    ![Exibição Usuários do Aplicativo](./media/hr-admin-integration-power-apps-application-users.jpg)

7. Na barra de ferramentas, selecione **Novo**.

8. Na página **Novo usuário**, siga estas etapas:

    1. Altere o valor do campo **Tipo de usuário** para **Usuário de Aplicativo**.
    2. Defina o campo **Nome do Usuário** como **Integração Dynamics365 HR LinkedIn HRIS**.
    3. Defina o campo **ID do Aplicativo** como **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Insira qualquer valor nos campos **Nome**, **Sobrenome** e **Email Principal**.
    5. Na barra de ferramentas, selecione **Salvar \& Fechar**.

### <a name="assign-a-security-role-to-the-new-user"></a>Atribuir uma função de segurança a um usuário novo

Depois de salvar e fechar o novo usuário do aplicativo na seção anterior, você voltará para a página **Lista de usuários**.

1. Na página **Lista de usuários**, altere a exibição para **Usuários do Aplicativo**.

2. Selecione o usuário do aplicativo criado na seção anterior.

3. Na barra de ferramentas, selecione **Gerenciar Funções**.

4. Selecione a função de segurança criada anteriormente para a integração.

5. Selecione **OK**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Adicionar um aplicativo do Azure Active Directory ao Human Resources

1. No Dynamics 365 Human Resources, abra a página **Aplicativos do Azure Active Directory**.
2. Adicione um novo registro à lista e defina os seguintes campos:

    - **ID do Cliente**: insira **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Nome**: insira o nome da função de segurança do Power Apps que você criou anteriormente, como **Integração LinkedIn Talent Hub HRIS**.
    - **ID do Usuário**: selecione um usuário que tenha permissões para gravar dados no Gerenciamento de Pessoal.

### <a name="create-the-table-in-dataverse"></a>Criar a tabela no Dataverse

> [!IMPORTANT]
> A integração com o LinkedIn Talent Hub depende de tabelas virtuais no Dataverse para Human Resources. Como um pré-requisito dessa etapa na configuração, você deve configurar tabelas virtuais. Para obter informações sobre como configurar tabelas virtuais, consulte [Configurar tabelas virtuais do Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

1. No Human Resources, abra a página **Integração do Dataverse**.

2. Selecione a guia **Tabelas virtuais**.

3. Filtre a lista de entidades por etiqueta de entidade para localizar **Candidato exportado do LinkedIn**.

4. Selecione a entidade e selecione **Gerar/atualizar**.

## <a name="exporting-candidate-records"></a>Exportação de registros de candidato

Após a conclusão da configuração, os profissionais de recrutamento e recursos humanos (RH) poderão usar a função **Exportar para HRIS** no LinkedIn Talent Hub para exportar registros de candidatos contratados do LinkedIn Talent Hub para o Human Resources.

### <a name="export-records-from-linkedin-talent-hub"></a>Exportar registros do LinkedIn Talent Hub

Depois que um candidato passar pelo processo de recrutamento e tiver sido contratado, você poderá exportar o registro do candidato do LinkedIn Talent Hub para o Human Resources.

1. No LinkedIn Talent Hub, abra o projeto para o qual você contratou o novo funcionário.

2. Selecione um registro de candidato.

3. Selecione **Alterar estágio** e selecione **Contratado**.

4. No menu de reticências (**...**) para o candidato, selecione **Exportar para HRIS**.

5. No painel **Exportar para HRIS**, insira as informações que devem ser exportadas:

    - No campo **Provedor de HRIS** , selecione **Microsoft Dynamics 365 Human Resources**.
    - No campo **Data de início**, selecione um valor para o novo funcionário.
    - No campo **Cargo**, insira um cargo para o trabalho do novo funcionário.
    - No campo **Local**, insira o local em que será a base do funcionário.
    - Insira ou verifique o endereço de email do funcionário.

![Exportar para o painel HRIS no LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Concluir a integração no Human Resources

Os registros de candidato exportados do LinkedIn Talent Hub para o Human Resources são exibidos na seção **Candidatos a contratar** da página **Gerenciamento de pessoal**.

1. No Human Resources, abra a página **Gerenciamento de pessoal**.

2. Na seção **Candidatos a contratar**, selecione **Contratar** para o candidato selecionado.

3. Na caixa de diálogo **Contratar novo trabalhador**, revise o registro e adicione as informações necessárias. Você também pode selecionar o número da posição para a qual o candidato foi contratado.

Depois que as informações necessárias tiverem sido inseridas, você poderá continuar com os processos padrão para criar registros de funcionário e integrar os funcionários.

Os seguintes detalhes são importados e incluídos no novo registro de funcionário:

- Nome
- Sobrenome
- Data de início do emprego
- Endereço de email
- Número de telefone

## <a name="see-also"></a>Consulte também

[Configurar tabelas virtuais do Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]