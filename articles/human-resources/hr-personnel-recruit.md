---
title: Recrutar candidatos ao trabalho
description: Este tópico mostra como recrutar candidatos no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 529f419a4e3e4e8807c6938fd2425ae01ce282f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051800"
---
# <a name="recruit-job-candidates"></a>Recrutar candidatos ao trabalho

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Dynamics 365 Human Resources ajuda a gerenciar solicitações de recrutamento. Ele também ajuda você a fazer a transição completa de candidatos ao trabalho para funcionários. Se a sua organização usar um aplicativo de recrutamento separado, o processo de recrutamento poderá incluir as seguintes etapas:

- Insira sua solicitação de recrutamento no Human Resources.
- Receba indicações de candidatos no Human Resources do aplicativo de recrutamento.
- Conclua o processo de aprovação de candidatos no Human Resources.

Se não estiver usando um aplicativo de recrutamento separado, você também poderá gerenciar candidatos manualmente no Human Resources.

>[!NOTE]
>Se você for um administrador ou desenvolvedor e quiser integrar o Human Resources com um aplicativo de recrutamento de terceiros, consulte [Configurar integração do Dataverse](hr-admin-integration-common-data-service.md) e [Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> Também é possível encontrar aplicativos de integração de recrutamento no [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
> Para testar a versão prévia do recurso para integração com o LinkedIn Talent Hub, consulte [Integrar com o LinkedIn Talent Hub](hr-admin-integration-linkedin.md).

## <a name="enable-recruiting-requests"></a>Habilitar solicitações de recrutamento

Se você deseja enviar solicitações de recrutamento no Human Resources, primeiro habilite a funcionalidade em **Parâmetros compartilhados de recursos humanos**.

1. No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links**.

2. Em **Configuração**, selecione **Parâmetros compartilhados de recursos humanos**.

3. Na guia **Recrutamento**, em **RECRUTAMENTO**, defina **Habilitar solicitações de recrutamento** como **Sim**.

## <a name="add-a-recruiting-request-location"></a>Adicionar um local de solicitação de recrutamento

Se a sua organização tiver vários locais, você poderá adicioná-los de forma que os solicitantes possam selecionar um local no qual o novo recrutamento funcionará. O local será incluído no lançamento do trabalho.

1. Na barra de pesquisa, insira o **local da solicitação de recrutamento**.

2. Selecione **Novo**.

3. No campo **Local da solicitação de recrutamento**, insira o nome do local.

   ![Adicionar um local de solicitação de recrutamento](./media/hr-recruit-0a-add-location.png)

4. No campo **Descrição**, insira uma descrição do local.

5. Em **Local**, selecione **Adicionar**. Se o popout **Novo endereço** aparecer, insira o endereço do local.

   ![Inserir endereço](./media/hr-recruit-0b-address.png)

6. Em **Informações de contato**, insira as informações do contato do local.

7. Selecione **Salvar**.

## <a name="add-a-recruiting-request"></a>Adicionar uma solicitação de recrutamento

Os gerentes podem enviar solicitações de recrutamento no Human Resources. Se você usar um aplicativo de recrutamento separado, ao concluir essas etapas, uma solicitação de recrutamento será enviada e o processo de recrutamento iniciará nesse aplicativo. Caso contrário, conclua esse procedimento para iniciar o fluxo de trabalho para seu próprio processo de recrutamento interno.

1. Selecione **Autoatendimento para funcionários**.

2. Selecione a guia **Minha equipe**.

3. Selecione **Solucionar recrutamento**.

   ![Iniciar uma solicitação de recrutamento](./media/hr-recruit-1-request-to-recruit.png)

4. Preencha os campos **Descrição**, **Trabalho** e **Data de início estimada**.

   ![Concluir a solicitação de recrutamento](./media/hr-recruit-2-request-to-recruit.png)

5. Selecione **Continuar**. A solicitação de recrutamento do seu cargo é exibida.

6. Em **Geral**, selecione um recrutador na lista suspensa **Recrutador** e selecione um local no menu suspenso **Localização da solicitação de recrutamento**.

7. Em **Trabalho**, altere as informações conforme necessário e selecione **Criar detalhes do trabalho**.

   ![Criar detalhes do trabalho](./media/hr-recruit-3-create-details-from-job.png)

   O restante da solicitação de recrutamento será preenchido com as informações padrão para o trabalho inserido.

8. Em **Descrição externa**, insira uma descrição de trabalho externa.

9. Em **Posições**, selecione **Adicionar** e selecione um cargo para essa solicitação de recrutamento.

   ![Adicionar uma posição](./media/hr-recruit-4-select-position.png)

10. Em **Habilidades**, selecione **Adicionar** e, depois, uma habilidade.

11. Em **Requisitos de formação educacional**, selecione **Adicionar** e, depois, selecione os valores das **Educação** e **Nível de formação educacional**.

   ![Adicionar requisitos educacionais](./media/hr-recruit-5-select-educational-requirements.png)

12. Em **Comentário**, adicione comentários, conforme necessário.

13. Em **Remuneração**, selecione um nível no menu suspenso **Nível** e ajuste **Limite baixo**, **Ponto de controle** e **Limite alto**, conforme necessário.

14. Quando sua solicitação de recrutamento for concluída e você estiver pronto para iniciar o processo de recrutamento, selecione **Ativar** na barra de menus.

   ![Ativar solicitação de recrutamento](./media/hr-recruit-6-activate-recruit-request.png)

15. Selecione **Salvar**.

## <a name="view-and-edit-your-recruiting-requests"></a>Exibir e editar solicitações de recrutamento

Se você for um gerente e desejar exibir suas próprias solicitações:

1. Selecione **Autoatendimento para funcionários**.

2. Selecione a guia **Minha equipe**.

3. Em **Informações da minha equipe**, selecione a guia **Solicitações de recrutamento**.

   ![Selecionar a guia Solicitações de recrutamento](./media/hr-recruit-7-recruiting-requests.png)

4. Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.

Se você for um profissional de RH e quiser exibir todas as solicitações de recrutamento:

1. Selecione **Gerenciamento de pessoal**.

2. Selecione **Solicitações de recrutamento**.

   ![Exibir solicitações de recrutamento no Gerenciamento de pessoal](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.

## <a name="add-or-edit-a-candidate-profile"></a>Adicionar ou editar um perfil de candidato

Se a sua organização se integrou a outro aplicativo para gerenciar solicitações de recrutamento, as solicitações de recrutamento serão encaminhadas para esse aplicativo. O aplicativo de recrutamento reenvia informações sobre candidatos para o Human Resources. Caso contrário, você poderá seguir seus próprios processos internos de recrutamento e inserir informações sobre os candidatos manualmente.

1. Selecione **Gerenciamento de pessoal**.

2. Selecione **Links**.

3. Em **Recrutamento**, selecione **Candidatos**.

   ![Exibir candidatos](./media/hr-recruit-9-candidates.png)

4. Para adicionar um candidato, selecione **Novo**. Para editar um candidato existente, selecione o candidato na lista e selecione **Editar**. O perfil do candidato aparece.

5. Em **Resumo de candidatos**, insira ou edite as informações do candidato conforme necessário.

6. Em **Solicitação de recrutamento**, selecione uma solicitação de recrutamento para vincular o candidato. Em seguida, preencha os campos **Data de início estimada**, **Gerente de contratação** e **Cargo** e **Descrição**, conforme apropriado.

   ![Vincular à solicitação de recrutamento](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Preencha todas as informações nas seguintes áreas a serem incluídas no registro do candidato:
   - **Comentários**
   - **Experiência Profissional**
   - **Informações do contato**
   - **Formação**
   - **Habilidades**
   - **Certificados**
   - **Triagens**

8. Selecione **Salvar**.

## <a name="hire-a-candidate"></a>Contratar um candidato

Quando estiver pronto para contratar um candidato, siga este procedimento para fazer a transição do candidato para um funcionário.

1. No formulário do candidato, selecione **Contratar**.

   ![Contratar um candidato](./media/hr-recruit-11-hire.png)

2. No formulário **Contratar novo trabalhador**, em **Detalhes**, preencha todos os campos.

   ![Inserir detalhes de novos contratados](./media/hr-recruit-12-hire-new-worker.png)

3. Em **Detalhes do cargo**, verifique e altere as informações conforme necessário.

4. Em **Listas de verificação de integração**, selecione as listas de verificação de integração relevantes para este funcionário.

5. Selecione **Continuar** para criar o registro de funcionário.

   >[!NOTE]
   >Dependendo dos fluxos de trabalho da organização, o registro de candidatos pode passar por etapas de aprovação adicionais antes de se tornar um registro de funcionário.

## <a name="decide-not-to-hire-a-candidate"></a>Decidir não contratar um candidato

Se você optar por não contratar um candidato, siga este procedimento para removê-lo do processo de habilitação. 

1. No formulário do candidato, selecione **Não contratar**.

   ![Não contratar candidato](./media/hr-recruit-13-do-not-hire.png)

2. Selecione um **Código de motivo** e inclua comentários.

3. Selecione **OK**.

## <a name="dismiss-a-candidate"></a>Ignorar um candidato

Se necessário, você poderá ignorar um candidato após contratá-lo. Por exemplo, um candidato pode rejeitar sua oferta ou não aparecer no primeiro dia.

- No formulário do candidato, selecione **Ignorar candidato**.

  ![Ignorar o candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Consulte também

[Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organizar sua força de trabalho](hr-personnel-departments-jobs-positions.md)<br>
[Configurar os componentes de um trabalho](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
