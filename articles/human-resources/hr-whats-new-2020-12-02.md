---
title: Novidades ou alterações no Dynamics 365 Human Resources para 2 de dezembro de 2020
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 2 de dezembro de 2020.
author: marcelbf
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d95c92fe15f4dfe77d2bc8a153f86165c17edb4e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892624"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources para 2 de dezembro de 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3788.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Os gerentes podem enviar solicitações de recrutamento para vagas | [Os gerentes podem enviar uma solicitação de recrutamento para vagas em aberto](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Adicionar uma solicitação de recrutamento](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Perfil de candidato avançado no Gerenciamento de pessoal | [Perfil de candidato avançado no gerenciamento de pessoal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Adicionar ou editar um perfil de candidato](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Habilitar integrações simplificadas com provedores de recrutamento | [Habilitar integrações simplificadas com provedores de recrutamento](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Recrutar candidatos ao trabalho](./hr-personnel-recruit.md) |
| Links personalizados no Autoatendimento para gerentes | [Links personalizados no autoatendimento para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Links personalizados no autoatendimento para gerentes](./hr-employee-manager-self-service-custom-links.md) |


### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | descrição |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult deve incluir datetime usado no processamento. | O resultado do processamento de BenefitEligibity agora inclui o datetimestamp do último processamento, que estava faltando antes. |
| 526903 | O registro de benefícios falha para planos com dependentes quando a **Seleção automática de representantes** está ativada em **Parâmetros compartilhados de recursos humanos**. | Corrigido o problema em que o registro de benefício estava falhando para dependentes quando a opção **Seleção automática de representantes** foi ativada para representantes padrão. |
| 521922 | O parâmetro **Mostrar ausência sem detalhes** mostra detalhes das solicitações de folga no calendário de ausências do grupo. | O tipo de licença, a cor do tipo de licença e os detalhes de dia foram mostrados no calendário de ausência da equipe quando **Mostrar ausência sem detalhes** foi definido como **Sim** em **Parâmetros de licença e ausência**. Isso foi resolvido. Agora o tipo de licença não é exibido e a cor do tipo de licença padrão (azul escuro) é usada para todos os tipos de licença no calendário de ausência do grupo. |
| 527316 | As alterações de título para trabalho, cargo e notificações de trabalhador não são sincronizadas. | Uma relação de título foi adicionada anteriormente às entidades de trabalho, cargo e trabalhador. A sincronização dessa relação funciona para a sincronização do Human Resources para o Dataverse, mas não funcionou para notificações do Dataverse. Isso foi abordado. |
| 512275 | Remova as opções de cor dos **Parâmetros de licença e ausência**. | Agora que as cores estão definidas no tipo de licença, as opções de cores não são mais necessárias em **Parâmetros de licença e ausência** ; portanto, elas foram removidas. |
| 437112 | Texto de mensagem de erro enganoso durante a atribuição de cargo do funcionário. | Mensagem de erro atualizada ao contratar um trabalhador e tentar atribuir o trabalhador a um cargo que não está ativo. Mensagem atualizada **O cargo especificado não está ativo a partir da data de início do emprego. Verifique a duração desse cargo.** |
| 527816 | Problemas de desempenho com a página **Folga**. | O desempenho foi aprimorado na página **Folga**. |
| 523158 | BenefitPeriodMigrationUpgrade e BenefitPlanMigrationUpgrade não estão em execução. | Problemas corrigidos com trabalhos de migração de benefícios relativos a **Período** e **Plano** não estão sendo executados corretamente. |

## <a name="in-preview"></a>Em visualização

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Plano de versão | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Aprovações e solicitações de fluxo de trabalho avançadas | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integração com o LinkedIn Talent Hub | [Integração com o LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar com o LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
|Exibição de licenças interempresariais para gerentes | [Exibição de licenças interempresariais de funcionários para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parâmetros de licença e ausência](./hr-leave-and-absence-parameters.md) |
|Fornecer insight adicional sobre saldos de licenças| [Fornecer insight adicional sobre saldos de licenças](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gerenciar licença de funcionário](./hr-leave-and-absence-manage-employee-leave.md) |
| Os gerentes podem enviar solicitações de recrutamento para vagas | [Os gerentes podem enviar uma solicitação de recrutamento para vagas em aberto](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Adicionar uma solicitação de recrutamento](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Perfil de candidato avançado no Gerenciamento de pessoal | [Perfil de candidato avançado no gerenciamento de pessoal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Adicionar ou editar um perfil de candidato](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Habilitar integrações simplificadas com provedores de recrutamento | [Habilitar integrações simplificadas com provedores de recrutamento](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Recrutar candidatos ao trabalho](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2020 do Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]