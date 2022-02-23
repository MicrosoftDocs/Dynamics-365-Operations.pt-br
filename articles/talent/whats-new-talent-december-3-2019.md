---
title: Novidades ou alterações no Dynamics 365 Talent (3 de dezembro de 2019)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528684"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Novidades ou alterações no Dynamics 365 Talent (3 de dezembro de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2646. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espaço de trabalho do gerenciamento de recursos

O espaço de trabalho **Gerenciamento de recursos** fornece uma lista de recursos entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles. Para obter mais informações sobre o Gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.
 
Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho **Gerenciamento de recursos**).
 
Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Adicionar agendamento automático da limpeza de Histórico de trabalho em lotes (332528)

Com esta alteração, o **Histórico de trabalho em lotes** é executado todas as noites e remove os itens do histórico de trabalho em lotes com mais de 30 dias.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>O Talent não responde em ações do trabalho quando o comprimento do número da identificação não corresponde ao tipo de identificação (390971)

Esta versão corrige o problema que ocorre quando o comprimento do número de identificação não corresponde à definição dentro do tipo de identificação. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>A remuneração fixa não atualiza o nível com alterações nos detalhes da posição (348085)

A versão desta semana, **Data de início da remuneração** determina o trabalho associado à posição no momento em que um novo registro de remuneração fixa foi criado para um funcionário.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>As listas de trabalhadores, funcionários e prestadores de serviço exibem Tipo de trabalhador como Ambos quando deveria ser apenas Trabalhador ou Prestador de serviço (384473)

Esta alteração precisamente reflete o tipo de trabalhador inserido (prestador de serviços ou funcionário).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>As notificações por e-mail para ações de novas contratações não contêm informações devido às políticas de segurança (383402)

Esta alteração corrige as informações exibidas nos campos de nome ou sobrenome dentro dos espaços reservados para o fluxo de trabalho quando a segurança avançada for habilitada.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>O sistema permite solicitações de ausência de dois dias inteiros para o mesmo dia (379284)

Com esta alteração, não é possível emitir duas solicitações de ausência para o mesmo dia. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>A lista de alterações de endereço devem ser classificadas por Data de vigência (352798)

Com esta alteração, a lista de alterações de endereço é classificada por **Data de vigência**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>As solicitações de ausência devem permitir exclusões do Common Data Service para o Talent (376999)

Com esta alteração, as solicitações de ausência em modo rascunho ou canceladas podem ser excluídas do Common Data Service e removidas do Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>Excluir os códigos de ganhos é permitido quando o mesmo código de ganhos é atribuído a um funcionário (371792)

Nesta versão, é necessário primeiro remover o código de ganhos do funcionário antes de excluir o código de ganhos do sistema.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>O fluxo de trabalho de licenças e ausências com dois estágios de aprovação não é concluído (391116)

Com esta alteração, o fluxo de trabalho de licenças e ausências continuará por todas as etapas quando mais de um estágio de aprovação for configurado para a solicitação.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>A data de emissão não é sincronizada com o Common Data Service quando atualizada ou inserida no Talent (397361)

Esta alteração corrige um problema no qual a data de emissão de registros de **Identificação da pessoa** não sincroniza com o Common Data Service no Talent.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>O erro de referência circular da hierarquia emitido ao atribuir um gerente a uma posição (386659)

Esta alteração corrige um cenário exclusivo no qual um erro de referência circular aparece ao atribuir um novo gerente a uma posição.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>As entidades do Common Data Service que agora oferecem suporte a campos personalizados

As entidades do Common Data Service a seguir agora oferecem suporte a campos personalizados:

| Nome | Entidade |
| --- | --- |
| Pagamento em Conta Bancária | cdm_bankaccountdisbursement |
| Frequência de Cálculo do Benefício | cdm_benefitcalculationfrequency |
| Período de Pagamento da Frequência de Cálculo de Benefícios | cdm_benefitcalculationfrequencypayperiod |
| Taxa de Cálculo de Benefícios | cdm_benefitcalculationrate |
| Detalhes da Taxa de Cálculo de Benefícios | cdm_benefitcalculationratedetail |
| Opção de Benefícios | cdm_benefitoption |
| Plano de Benefícios | cdm_benefitplan (Não habilitado para suporte a campos personalizados) |
| Tipo de Benefício | cdm_benefittype |
| Calendário de Processo de Negócios | cdm_businessprocesscalendar |
| Atribuição de Grupo de Processos de Negócios | cdm_businessprocessgroupassignment |
| Grupo de Tarefas da Biblioteca de Processos de Negócios | cdm_businessprocesslibrarytaskgroup |
| Estágio do Processo de Negócios | cdm_businessprocessstage |
| Cabeçalho do Modelo de Lista de Verificação | cdm_businessprocesstemplateheader |
| Tarefa do Modelo de Lista de Verificação | cdm_businessprocesstemplatetask |
| Empresa | cdm_company |
| Plano de Remuneração Fixa | cdm_compensationfixedplan |
| Grade de Remuneração | cdm_compensationgrid |
| Nível de Remuneração | cdm_compensationlevel |
| Frequência de Pagamento de Remuneração | cdm_compensationpayfrequency |
| Configuração de Ponto de Referência de Remuneração | cdm_compensationreferencepointsetup |
| Linha da Configuração de Ponto de Referência de Remuneração | cdm_compensationreferencepointsetupline |
| Região de Remuneração | cdm_compensationregion |
| Estrutura de Remuneração | cdm_compensationstructure |
| Plano de Remuneração Variável | cdm_compensationvariableplan |
| Nível do Plano de Remuneração Variável | cdm_compensationvariableplanlevel |
| Tipo de Plano de Remuneração Variável | cdm_compensationvariableplantype |
| Departamento | cdm_department |
| Emprego | cdm_employment |
| Origem Étnica | cdm_ethnicorigin |
| Evento de Remuneração Fixa | cdm_fixedcompensationevent |
| Cargo | cdm_job |
| Função de Trabalho | cdm_jobfunction |
| Posição de Trabalho | cdm_jobposition |
| Tipo de Trabalho | cdm_jobtype |
| Idioma | cdm_language |
| Transação Bancária da Licença | cdm_leavebanktransaction |
| Registro da Licença | cdm_leaveenrollment |
| Plano de Licença | cdm_leaveplan |
| Solicitação de Licença | cdm_leaverequest |
| Detalhes da Solicitação da Licença | cdm_leaverequestdetail |
| Tipo de Licença | cdm_leavetype |
| Código de Motivo do Tipo de Licença | cdm_leavetypereasoncode |
| Ciclo de Pagamento | cdm_paycycle |
| Período de Pagamento | cdm_payperiod |
| Código de Ganhos da Folha de Pagamento | cdm_payrollearningcode |
| Agência Emissora da Identificação da Pessoa | cdm_personidentificationissuingagency |
| Tipo de Posição | cdm_positiontype |
| Atribuição do Trabalhador da Posição | cdm_positionworkerassignmentmap |
| Código de Motivo | cdm_reasoncode |
| Tipo de Habilidade | cdm_skilltype |
| Região Fiscal | cdm_taxregion |
| Regra de Benefício Proporcional Diferido | cdm_vestingrule |
| Situação Militar | cdm_veteranstatus |
| Calendário de Trabalho | cdm_workcalendar |
| Dia do Calendário de Trabalho | cdm_workcalendarday |
| Feriado do Calendário de Trabalho |cdm_workcalendarholiday |
| Linha de Feriados do Calendário de Trabalho | cdm_workcalendarholidayline |
| Intervalo do Calendário de Trabalho | cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados) |
| Trabalhador | cdm_worker |
| Endereço do Trabalhador | cdm_workeraddress |
| Conta Bancária do Trabalhador | cdm_workerbankaccount |
| Remuneração Fixa do Trabalhador | cdm_workerfixedcompensation |
| Informações Pessoais do Trabalhador | cdm_workerpersonaldetail |
| Número de Identificação do Trabalhador | cdm_workerpersonidentificationnumber |
| Tipo de Identificação do Trabalhador | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>Em visualização

Os recursos da versão prévia estão disponíveis somente em ambientes de **Área restrita**.

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.
