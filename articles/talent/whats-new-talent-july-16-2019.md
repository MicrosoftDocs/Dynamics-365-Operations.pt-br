---
title: Novidades ou alterações no Dynamics 365 Talent (16 de julho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cd7f288e5c1015f4266db527adfcd62a5dbbc95f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528090"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Novidades ou alterações no Dynamics 365 Talent (16 de julho de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Em breve no Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>As aprovações de trabalho aparecem na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que mostra os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entidades Common Data Service que agora são compatíveis com campos personalizados

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Não é possível exibir metas e revisões no autoatendimento do gerente

As alterações desta semana agora permitem exibir e editar metas e revisões para gerentes em nível de salto no autoatendimento do gerente.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>O formulário da meta não pode ser fechado depois que um usuário edita qualquer campo da meta

Esta versão corrige um problema em que o formulário da meta não fecha ao selecionar **Fechar**.

### <a name="creating-new-goals-and-saving-displays-error"></a>Criando novas metas e salvando os erros de exibição

Esta versão corrige um problema ao salvar metas no autoatendimento do funcionário e do gerente.

### <a name="unable-to-add-a-field-to-position-details"></a>Não foi possível adicionar um campo aos detalhes do cargo 

Com esta versão, os campos personalizados agora têm suporte nos detalhes do cargo.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Não foi possível configurar a data de vencimento no código de ganhos por meio do gerenciamento de dados

As alterações agora permitem definir datas de vencimento nos códigos de ganho no gerenciamento de dados.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Os novos campos personalizados não são sincronizados com rapidez suficiente

O desempenho da sincronização de campo personalizado para o Common Data Service foi aprimorado com o lançamento desta semana.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>A exportação da entidade para trabalhos de banco de dados falha com a mensagem de erro: "O formato da sequência de inicialização não está em conformidade com a especificação iniciando no índice 0".

Esta versão corrige o problema em que os trabalhos em lote do banco de dados estão com falha. Para atualizar manualmente, siga estas etapas:

1. Vá para **Gerenciamento de dados**.
2. Selecione **Configurar exportação de entidade para banco de dados**.
3. Insira novamente a sequência de conexão no banco de dados de destino e selecione **Salvar**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>A configuração de email SMTP falha repentinamente com a mensagem de erro: "O servidor SMTP requer uma conexão segura ou o cliente não foi autenticado".

Esta versão corrige uma configuração de email SMTP que falha repentinamente. Para atualizar manualmente, siga estas etapas:

1. Vá para **Administração do sistema**.
2. Selecione **Parâmetros de email**.
3. Selecione **configurações SMTP**. 
4. Insira novamente o nome de usuário e a senha usados ​​para o servidor SMTP e selecione **Salvar**.

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é **Produção** ou **Área restrita**. As instâncias do tipo **Área restrita** permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos diferentes de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Exiba informações de desempenho para relatórios diretos e estendidos no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]