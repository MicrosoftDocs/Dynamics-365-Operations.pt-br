---
title: Fornecimento com o LinkedIn Recruiter
description: "Este tópico fornece informações sobre o uso de machine learning para obter recomendações de trabalho e recomendações de candidatos ao trabalho."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: pt-br
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a>Fornecimento com o LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

O LinkedIn é o maior banco de dados de talentos do mundo e geralmente o principal sistema que os recrutadores usam para encontrar, se comunicar e fornecer candidatos para os trabalhos que os recrutadores buscam preencher. A integração do LinkedIn Recruiter com Dynamics 365 for Talent: Attract facilita para os usuários fazerem contratações e manterem os dados sincronizados entre os dois sistemas.

> [!NOTE]
> Você precisa do complemento de Contratação abrangente e de estações do LinkedIn Recruiter para poder usar a integração do LinkedIn Recruiter com o Attract.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Configurar o LinkedIn Recruiter com o Attract 

Para poder usar os recursos do LinkedIn Recruiter, você deve configurar o acesso no nível de contrato ou o acesso no nível da empresa com sua instância do Attract. Para concluir o processo de configuração, é necessário trabalhar com o usuário que seja um Administrador no contrato do LinkedIn Recruiter. Conclua as etapas abaixo para configurar o LinkedIn Recruiter com o Attract.

1.  Entre no Attract como Administrador e acesse **Configurações de Administração**.

2.  No painel esquerdo, clique na guia **Integração com o LinkedIn**.

[![Exibição do administrador no Attract para iniciar a integração com o LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Clique em **Conectar** para iniciar a configuração e ser guiado no processo de logon do LinkedIn.

4.  Se você tiver estações em vários contratos do LinkedIn, selecione o contrato ao qual você deseja conectar o sistema Attract. Se você tiver uma estação em apenas um contrato do LinkedIn, essa etapa não será necessária.

5.  O widget do LinkedIn agora carregará suas configurações de administração com a lista de integrações exibidas. Em **Recruiter System Connect**, clique em **Solicitar**.

[![Exibição do administrador no Attract para solicitar a integração com o LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Depois que a integração for solicitada no Attract, ele será exibido como **Parceiro pronto** e estará pronto para ser ativado em **Configurações de administração do Recruiter**. Se você vir a mensagem **Notificar o parceiro** nesta página, aguarde alguns segundos, clique em **Notificar o parceiro**e atualize a página. Ele agora deverá ser exibido como **Parceiro pronto**.

[![Exibição do administrador no Attract para indicar o lado do Attract das solicitações que foram concluídas](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Para concluir a etapa seguinte, você precisará ter um privilégio de administrador no contrato do LinkedIn Recruiter.

7.  Entre no LinkedIn usando a conta de administrador e acesse o LinkedIn Recruiter na parte superior direita. 

8. No menu **Mais**, na parte superior da tela, clique em **Configurações de Administração** e na guia **ATS** .

O sistema Attract será listado com algumas opções que poderão ser ativadas.

9. Se quiser habilitar somente a exportação em um clique para o **Indicador em ATS** e para o **Widget de perfil em ATS**, selecione **Acesso no nível da empresa**. Se você deseja habilitar todos os recursos de acesso no nível da empresa além do histórico do InMail, histórico de Observações e o acesso a perfil do comprovante do InMail, selecione **Acesso no nível de contrato**.

10. Ative o nível de acesso desejado nas configurações **Admin-ATS** do LinkedIn Recruiter.

[![Ativar a integração com o Attract a partir da Exibição do administrador do LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Volte às Configurações de Administração do Attract como administrador do Attract e selecione a guia **Integração com o LinkedIn** . Agora você deverá ver o widget do LinkedIn carregado mostrando **Habilitado** com o nível de acesso selecionado ativado.

[![Integração com o LinkedIn Recruiter concluída](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Usando os recursos do LinkedIn Recruiter

Depois que os recursos do LinkedIn Recruiter forem habilitados pelo administrador do Attract, eles estarão disponíveis para o acesso pelos gerentes de contratação e recrutadores. Para usar esses recursos, conecte sua conta do LinkedIn em **Configurações do usuário**. Vários recursos estarão disponíveis depois que as configurações do administrador e do usuário forem conectadas.

### <a name="in-ats-profile-widget"></a>Widget de perfil em ATS

Você pode exibir o perfil do LinkedIn do candidato no Attract. O widget do LinkedIn exibirá o perfil do candidato quando as informações de ATS corresponderem com as informações do LinkedIn de seus usuários.

Para exibir um perfil, acesse o perfil do candidato a partir de um trabalho ou de um grupo de talentos. No perfil do candidato, selecione a guia **LinkedIn** e o widget de perfil será carregado. Usando o widget de perfil, indique se esta é a correspondência correta. Caso contrário, encontre a pessoa correta. Você também pode salvar o candidato em seus projetos do LinkedIn Recruiter a nessa página.

### <a name="1-click-export"></a>Exportação em um clique 

Ao fornecer candidatos no LinkedIn, é possível fazer a exportação em um clique do candidato para os trabalhos que você tiver em aberto o momento. Conclua as etapas a seguir para fazer uma exportação em um clique. Antes de concluir essas etapas, verifique se você está atribuído à função de Gerente de contratação ou Recrutador para o trabalho e se o trabalho tem um estágio **Cliente potencial**.

1.  Crie o trabalho, atribua as funções adequadas e ative o trabalho.

2.  Quando o trabalho for ativado, navegue até o LinkedIn Recruiter.

3.  Encontre o candidato que você está procurando e acesse seu perfil.

4.  Usando a caixa de pesquisa de trabalhos no cartão de contato, encontre o trabalho usando o título ou a ID do trabalho que foi ativado no Attract. Se você não encontrar o trabalho, clique em **Alterar ATS** para encontrar a instância correta do Attract.

5. Depois que o trabalho for selecionado, clique em **Exportar**. O candidato agora será obtido pelo Attract.

6.  Acesse o Attract e abra o respectivo trabalho. Você encontrará o candidato que acabou de exportar no estágio **Candidato ao trabalho** do trabalho.

### <a name="in-ats-indicator"></a>Indicador em ATS 

Usando o LinkedIn Recruiter, você poderá rastrear se um candidato se candidatou a outros trabalhos em sua organização, acompanhar em que parte está em estágios diferentes de solicitações de emprego e exibir os comentários do Attract no LinkedIn Recruiter.

1.  Abra o LinkedIn Recruiter e localize o perfil do candidato que você está procurando.

2.  Role para baixo para exibir a seção **Em ATS** no perfil do candidato.

3.  Você pode usar este widget para exibir todas as informações sobre o candidato que estejam presentes no Attract na exibição do LinkedIn Recruiter.

4.  Selecione a guia **Trabalhos e status** para ver quais trabalhos fazem parte, o status mais recente e como eles vêm mudando em relação a cada trabalho.

5.  Selecione a guia **Comentários da entrevista** para ver os comentários que os entrevistadores enviaram no Attract.

6.  Selecione a guia **Observações** para consultar as observações que foram feitas sobre o candidato no Attract.

### <a name="inmail-history"></a>Histórico do InMail

O histórico do LinkedIn InMail está disponível com o acesso no nível de contrato do LinkedIn Recruiter. Quando habilitado, você poderá exibir o histórico completo do InMail com o candidato. Você também poderá consultar quem mais em sua organização trocou InMails com o candidato, no entanto, você não poderá exibir as mensagens entre eles.

Para exibir o histórico do InMail, acesse o perfil de um candidato, acesse a guia **LinkedIn** e role para a parte inferior da página para exibir o histórico. Você poderá exibir o histórico do InMail somente se o candidato tiver respondido à sua solicitação e optado por compartilhar o perfil com você no LinkedIn. As mensagens do InMail sincronizam com o Attract a cada duas horas.

### <a name="notes-history"></a>Histórico de observações 

O histórico de observações do LinkedIn está disponível com o acesso no nível de contrato do LinkedIn Recruiter. Quando habilitado, você poderá exibir as observações que foram feitas sobre o candidato por diferentes recrutadores de sua organização.

Para exibir o histórico de observações, acesse o perfil de um candidato, acesse a guia **LinkedIn** e role para a parte inferior da página para exibir o histórico. Você poderá exibir as observações sobre o candidato no LinkedIn Recruiter.

### <a name="inmail-stub-profile"></a>Perfil do comprovante do InMail

O perfil do comprovante do está disponível com o acesso no nível de contrato do LinkedIn Recruiter. Se os candidatos concordarem em compartilhar seus perfis do LinkedIn com qualquer usuário em sua organização, você poderá rastrear os candidatos no Attract e um novo registro de candidato será criado para cada um.

Para exibir a lista de candidatos, acesse **Grupos de talentos** para exibir um grupo de talentos do LinkedIn criado pelo sistema. Esse grupo de talentos contém a lista de candidatos e seus perfis do comprovante conforme recebidos do LinkedIn, mostrando o nome e sobrenome do candidato. A ID do email do candidato será exibida se o candidato tiver optado por compartilhar o endereço de email.

