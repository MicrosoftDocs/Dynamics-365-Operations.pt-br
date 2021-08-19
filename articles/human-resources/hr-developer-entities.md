---
title: Tabelas do Dataverse
description: O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.
author: andreabichsel
ms.date: 01/25/2021
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb1ffb3b29fbfa92aa4401124d019854aa639fe58a63c10886e86adaa6cfad89
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732024"
---
# <a name="dataverse-tables"></a>Tabelas do Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.

> [!NOTE]
> Entidades do Human Resources correspondem a tabelas do Dataverse. Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

As tabelas do Dataverse a seguir estão disponíveis com base em entidades do Human Resources.

## <a name="benefit-tables"></a>Tabelas de benefícios

| Nome | Tabela |
| --- | --- |
| Frequência de Cálculo do Benefício | cdm_benefitcalculationfrequency |
| Período de Pagamento da Frequência de Cálculo de Benefícios | cdm_benefitcalculationfrequencypayperiod |
| Taxa de Cálculo de Benefícios | cdm_benefitcalculationrate |
| Detalhes da Taxa de Cálculo de Benefícios | cdm_benefitcalculationratedetail |
| Opção de Benefícios | cdm_benefitoption |
| Plano de Benefícios | cdm_benefitplan (Não habilitado para suporte a campos personalizados) |
| Tipo de Benefício | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Tabelas de tarefas do processo empresarial

| Organização | Tabela |
| --- | --- |
| Calendário de Processo de Negócios | cdm_businessprocesscalendar |
| Atribuição de Grupo de Processos de Negócios | cdm_businessprocessgroupassignment |
| Grupo de Tarefas da Biblioteca de Processos de Negócios | cdm_businessprocesslibrarytaskgroup |
| Estágio do Processo de Negócios | cdm_businessprocessstage |
| Cabeçalho do Modelo de Lista de Verificação | cdm_businessprocesstemplateheader |
| Tarefa do Modelo de Lista de Verificação | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Tabelas de remuneração

| Organização | Tabela |
| --- | --- |
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
| Evento de Remuneração Fixa | cdm_fixedcompensationevent |
| Regra de Benefício Proporcional Diferido | cdm_vestingrule |
| Remuneração Fixa do Trabalhador | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Tabelas da organização

| Organização | Tabela |
| --- | --- |
| Departamento | cdm_department |
| Emprego | cdm_employment |
| Empresa | cdm_company |
| Cargo | cdm_job |
| Função de Trabalho | cdm_jobfunction |
| Posição de Trabalho | cdm_jobposition |
| Tipo de Posição | cdm_positiontype |
| Atribuição do Trabalhador da Posição | cdm_positionworkerassignmentmap |
| Dimensão da Posição de Trabalho | cdm_jobpositiondimension|
| Tipo de trabalho | cdm_jobtype |
| Idioma | cdm_language |
| Cargo | cdm_title |

> [!NOTE]
> As dimensões financeiras para **Tipo de posição**, **Atribuição do trabalhador da posição** e **Emprego** fornecem integração de uma direção a Dataverse. As atualizações de dimensões financeiras não são sincronizadas atualmente de Dataverse a Recursos Humanos. 

## <a name="leave-and-absence-tables"></a>Tabelas de licença e ausência

| Organização | Tabela |
| --- | --- |
| Transação Bancária de Licença | cdm_leavebanktransaction |
| Inscrição para Licença | cdm_leaveenrollment |
| Plano de Licença | cdm_leaveplan |
| Solicitação de Licença | cdm_leaverequest |
| Detalhes da Solicitação da Licença | cdm_leaverequestdetail |
| Tipo de Licença | cdm_leavetype |
| Código de Motivo do Tipo de Licença | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Tabelas de folha de pagamento

| Organização | Tabela |
| --- | --- |
| Ciclo de Pagamento | cdm_paycycle |
| Período de Pagamento | cdm_payperiod |
| Código de Ganhos de Folha de Pagamento | cdm_payrollearningcode |
| Pagamento em Conta Bancária | cdm_bankaccountdisbursement |
| Região Fiscal | cdm_taxregion |

## <a name="worker-tables"></a>Tabelas de trabalhadores

| Organização | Tabela |
| --- | --- |
| Trabalhador | cdm_worker |
| Endereço do Trabalhador | cdm_workeraddress |
| Informações Pessoais do Trabalhador | cdm_workerpersonaldetail |
| Número de Identificação do Trabalhador | cdm_workerpersonidentificationnumber |
| Tipo de Identificação do Trabalhador | cdm_workerpersonidentificationtype |
| Calendário de Trabalho | cdm_workcalendar |
| Dia do Calendário de Trabalho | cdm_workcalendarday |
| Feriado do Calendário de Trabalho |cdm_workcalendarholiday |
| Linha de Feriados do Calendário de Trabalho | cdm_workcalendarholidayline |
| Intervalo do Calendário de Trabalho | cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados) |
| Conta Bancária de Trabalhador | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>Tabelas de configuração de trabalhador

| Nome | Tabela |
| --- | --- |
| Situação Militar | cdm_veteranstatus |
| Origem Étnica | cdm_ethnicorigin |
| Código de Motivo | cdm_reasoncode |
| Agência Emissora de Identificação Pessoal | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Tabelas de competência

| Nome | Tabela |
| --- | --- |
| Tipo de Habilidade | cdm_skilltype |

## <a name="table-relationship-models"></a>Modelos de relacionamento de tabela

### <a name="worker"></a>Trabalhador

![Trabalhador.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Trabalho e Cargo

![Trabalho e Cargo.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Benefícios

![Benefícios.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Remuneração

![Remuneração.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Sair

![Licença.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendário de Trabalho

![Calendário de Trabalho.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Consulte também

[Escolher uma tecnologia de integração de dados](hr-admin-integration-choose-technology.md)<br>
[Configurar integração do Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Perguntas frequentes de tabelas virtuais do Human Resources](hr-admin-virtual-entity-faq.md)<br>
[O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Atualizações de terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]