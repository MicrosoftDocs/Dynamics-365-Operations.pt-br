---
title: Configurar a integração do LinkedIn com o Attract
description: Este tópico explica como configurar a integração com o LinkedIn para o Microsoft Dynamics 365 Talent - Attract para que você possa postar trabalhos com facilidade no LinkedIn por meio do Attract, e para que seus recrutadores possam sincronizar suas informações de recrutamento com o perfil do LinkedIn de um candidato.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4c518fb7036d44aa52c8db859ee3616fc4e58a06
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460352"
---
# <a name="set-up-linkedin-integration-with-attract"></a>Configurar a integração do LinkedIn com o Attract

[!include [banner](includes/banner.md)]

Ajude os recrutadores e gerentes de contratação a atrair os melhores talentos configurando a integração do LinkedIn com o Microsoft Dynamics 365 Talent: Attract. O Attract permite que você lance trabalhos diretamente no LinkedIn, a maior rede profissional online.

Os trabalhos que você lança no LinkedIn pelo Attract são Listagens Limitadas e são fornecidos sem custo adicional para sua empresa. Essas listagens estão disponíveis somente por meio dos parceiros de software do LinkedIn, como o Attract. Elas não são exibidas no painel **Carreiras** na página do LinkedIn de sua empresa porque somente as listagens pagas são exibidas nele. No entanto, elas são exibidas quando candidatos potenciais exibem todos os trabalhos disponíveis. As Listagens Limitadas também são exibidas nas pesquisas de trabalhos do LinkedIn.

O Attract fornece duas maneiras de integração com o LinkedIn para ajudar você a fornecer candidatos desse popular site de carreiras:

- Lance trabalhos do Attract no LinkedIn.
- Forneça candidatos do LinkedIn para o Attract.

Configure ambas as opções na guia **Integração com o LinkedIn** no Centro de administração. Para abrir o Centro de administração, acesse <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> Para usar a integração do LinkedIn Recruiter com o Attract, é necessário o [complemento de Contratação abrangente](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) e as [licenças do LinkedIn Recruiter](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Para obter mais informações, consulte [Qual versão do Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

Caso esteja tendo problemas para lançar trabalhos no LinkedIn, consulte [Solucionar problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

Para obter informações sobre outras maneiras de lançar trabalhos no LinkedIn, consulte [Perguntas frequentes sobre a integração do Attract com o LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Configurar o lançamento de trabalhos no LinkedIn

Antes que possa lançar trabalhos do Attract no LinkedIn, você precisará de uma [ID da empresa no LinkedIn](https://aka.ms/findID) A ID da sua empresa no LinkedIn é uma sequência de números que identifica exclusivamente sua empresa no LinkedIn. Para obter mais informações, consulte [Associando sua ID da Empresa no LinkedIn com o quadro de trabalhos do LinkedIn — Perguntas frequentes](https://aka.ms/findID).

O Attract envia um feed de seus lançamentos de trabalho no LinkedIn, e o LinkedIn verifica o feed cerca de uma vez por dia. Pode levar até 48 horas para que seus trabalhos sejam lançados no site.

Os trabalhos lançados no LinkedIn são exibidos no site ao vivo do LinkedIn. Não há um ambiente de teste para o lançamento de trabalhos no LinkedIn. Portanto, certifique-se de não lançar acidentalmente nenhum trabalho de teste. 

1. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Centro de administração**. Como alternativa, acesse <https://attract.talent.dynamics.com/adminsettings>.
2. Selecione a guia **Integração com o LinkedIn**.
3. Em **Nome da empresa**, insira o nome da empresa e em **ID da Empresa**, insira o ID da Empresa no LinkedIn. Verifique se o nome da empresa corresponde ao nome que é exibido na página da empresa no LinkedIn. Para obter informações sobre IDs de Empresa no LinkedIn, consulte [Associando sua ID da Empresa no LinkedIn com o quadro de trabalhos do LinkedIn — Perguntas frequentes](https://www.linkedin.com/help/linkedin/answer/98972).

    Se for necessário alterar as informações de sua organização, consulte [Alterar o endereço, o contato técnico e outras informações de sua organização](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Se ainda tiver problemas, contate o [suporte do LinkedIn](https://www.linkedin.com/help/linkedin).

4. Selecione **Salvar**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Configuração do LinkedIn Recruiter com o Attract 

Para permitir que os recrutadores forneçam trabalhos pelo LinkedIn Recruiter, você deve configurar a integração com o LinkedIn Recruiter no Attract. Para concluir o processo de configuração, é necessário trabalhar com o usuário que seja um Administrador no contrato do LinkedIn Recruiter de sua organização.

1. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Centro de administração**. Como alternativa, acesse <https://attract.talent.dynamics.com/adminsettings>.
2. Selecione a guia **Integração com o LinkedIn**.

    [![Exibição do administrador no Attract para iniciar a integração com o LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Selecione **Conectar** para iniciar a configuração. Você será orientado pelo processo de logon do LinkedIn.
4. Se tiver estações em vários contratos do LinkedIn, selecione o contrato ao qual você deseja conectar o sistema Attract. Se tiver uma estação em somente um contrato do LinkedIn, você poderá ignorar essa etapa.
5. Em **Recruiter System Connect (RSC)**, selecione **Solicitar**.

    [![Exibição do administrador no Attract para solicitar a integração com o LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. A configuração do **Recruiter System Connect (RSC)** deve ser exibida como **Parceiro pronto**. Se você vir a mensagem **Notificar o parceiro** nesta página, aguarde alguns segundos, selecione **Notificar o parceiro** e atualize a página. A configuração agora deve ser exibida como **Parceiro pronto**.

    [![Exibição do administrador no Attract para indicar o lado do Attract das solicitações que foram concluídas](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Para concluir as etapas seguintes, você deverá ter privilégios de administrador no contrato do LinkedIn Recruiter.

    1. Entre no LinkedIn usando sua conta de administrador e selecione **LinkedIn Recruiter** na parte superior direita. 
    2. No menu **Mais**, na parte superior da tela, selecione **Configurações de Administração** e selecione a guia **ATS** .
    3. Para habilitar a exportação com um clique para apenas um contrato, ative **Acesso no nível de contrato (para cada estação nesse contrato)**. Para habilitá-la para a empresa inteira, ative **Acesso no nível da empresa (para cada contrato na empresa)**.

    [![Ativar a integração com o Attract na Exibição do administrador do LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

8. No Centro de administração do Attract, selecione a guia **Integração com o LinkedIn** . A configuração do **Recruiter System Connect (RSC)** deverá ser exibida agora como **Habilitado**.

    [![Integração com o LinkedIn Recruiter concluída](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Configurar Candidatar-se com o LinkedIn no Attract

Você pode permitir que candidatos se candidatem aos trabalhos usando seus perfis do LinkedIn. Para obter mais informações sobre como Candidatar-se com o LinkedIn, consulte [O pode do LinkedIn em todos os lugares: candidate-se com o LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Este recurso está atualmente em visualização. Antes de seguir estas etapas, verifique se a opção Candidatar-se com o LinkedIn está habilitada. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Acessar os recursos de visualização no Microsoft Dynamics 365 Talent](./access-preview-feature.md).

1. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Centro de administração**. Como alternativa, acesse <https://attract.talent.dynamics.com/adminsettings>.
2. Selecione a guia **Integração com o LinkedIn**.

    [![Exibição do administrador no Attract para iniciar a integração com o LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Ao lado **Candidatar-se com o LinkedIn**, selecione **Conectar** para iniciar a configuração. Você será orientado pelo restante do processo com o LinkedIn.

## <a name="see-also"></a>Consulte também

[Perguntas frequentes sobre a integração do Attract com o LinkedIn](./attract-linkedin-faq.md)

[Lançar trabalhos de sites de carreira externos a partir do Attract](./posting-jobs-external.md)

[Contratar candidatos com o LinkedIn Recruiter no Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Criar, aprovar e lançar trabalhos no Attract](./creating-jobs-attract.md)

[Solucionar problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]