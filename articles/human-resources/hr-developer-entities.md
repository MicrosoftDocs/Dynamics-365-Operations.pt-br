---
title: Entidades do Common Data Service
description: O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 988fa0b6d39a49b973626a8a0abe83c546f42297
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529997"
---
# <a name="common-data-service-entities"></a>Entidades do Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.

Para obter mais informações sobre o Common Data Service, consulte [O que é o Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

As entidades a seguir do Human Resources estão disponíveis no Common Data Service.

## <a name="benefit-entities"></a>Entidades de benefícios

| Nome | Entidade |
| --- | --- |
| Frequência de Cálculo do Benefício | cdm_benefitcalculationfrequency |
| Período de Pagamento da Frequência de Cálculo de Benefícios | cdm_benefitcalculationfrequencypayperiod |
| Taxa de Cálculo de Benefícios | cdm_benefitcalculationrate |
| Detalhes da Taxa de Cálculo de Benefícios | cdm_benefitcalculationratedetail |
| Opção de Benefícios | cdm_benefitoption |
| Plano de Benefícios | cdm_benefitplan (Não habilitado para suporte a campos personalizados) |
| Tipo de Benefício | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Entidades de tarefas do processo de negócios

| Nome | Entidade |
| --- | --- |
| Calendário de Processo de Negócios | cdm_businessprocesscalendar |
| Atribuição de Grupo de Processos de Negócios | cdm_businessprocessgroupassignment |
| Grupo de Tarefas da Biblioteca de Processos de Negócios | cdm_businessprocesslibrarytaskgroup |
| Estágio do Processo de Negócios | cdm_businessprocessstage |
| Cabeçalho do Modelo de Lista de Verificação | cdm_businessprocesstemplateheader |
| Tarefa do Modelo de Lista de Verificação | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Entidades de remuneração

| Nome | Entidade |
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

## <a name="organization-entities"></a>Entidades da organização

| Nome | Entidade |
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
> As dimensões financeiras para **Tipo de posição**, **Atribuição do trabalhador da posição** e **Emprego** fornecem integração de uma direção a Common Data Service. As atualizações de dimensões financeiras não são sincronizadas atualmente de Common Data Service a Recursos Humanos. 

## <a name="leave-and-absence-entities"></a>Entidades de licença e ausência

| Nome | Entidade |
| --- | --- |
| Transação Bancária de Licença | cdm_leavebanktransaction |
| Registro da Licença | cdm_leaveenrollment |
| Plano de Licença | cdm_leaveplan |
| Solicitação de Licença | cdm_leaverequest |
| Detalhes da Solicitação da Licença | cdm_leaverequestdetail |
| Tipo de Licença | cdm_leavetype |
| Código de Motivo do Tipo de Licença | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Folha de pagamento das entidades

| Nome | Entidade |
| --- | --- |
| Ciclo de Pagamento | cdm_paycycle |
| Período de Pagamento | cdm_payperiod |
| Código de Ganhos da Folha de Pagamento | cdm_payrollearningcode |
| Pagamento em Conta Bancária | cdm_bankaccountdisbursement |
| Região Fiscal | cdm_taxregion |

## <a name="worker-entities"></a>Entidades do trabalhador

| Nome | Entidade |
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
| Conta Bancária do Trabalhador | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Entidades de configuração do trabalhador

| Nome | Entidade |
| --- | --- |
| Situação Militar | cdm_veteranstatus |
| Origem Étnica | cdm_ethnicorigin |
| Código de Motivo | cdm_reasoncode |
| Agência Emissora da Identificação da Pessoa | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Entidades de competência

| Nome | Entidade |
| --- | --- |
| Tipo de Habilidade | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modelos do relacionamento de entidade

### <a name="worker"></a>Trabalhador

![Trabalhador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Trabalho e Cargo

![Trabalho e Cargo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Benefícios

![Benefícios](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Remuneração

![Remuneração](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Deixar

![Deixar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendário de Trabalho

![Calendário de Trabalho](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Consulte também

[Escolher uma tecnologia de integração de dados](hr-admin-integration-choose-technology.md)</br>
[Configurar integração do Common Data Service](hr-admin-integration-common-data-service.md)
