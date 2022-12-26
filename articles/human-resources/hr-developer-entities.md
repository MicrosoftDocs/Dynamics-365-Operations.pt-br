---
title: Tabelas do Dataverse
description: O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838573"
---
# <a name="dataverse-tables"></a>Tabelas do Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.

> [!NOTE]
> Entidades do Human Resources correspondem a tabelas do Dataverse. Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

As tabelas do Dataverse a seguir estão disponíveis com base em entidades do Human Resources.

Para obter mais informações sobre os problemas conhecidos, consulte [Pesquisa de problemas no Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Tabelas de benefícios

| Organização | Tabela | Problemas conhecidos  | Status |
| --- | --- |    --------|----------  |
| Frequência de Cálculo do Benefício | cdm_benefitcalculationfrequency |     |     |
| Período de Pagamento da Frequência de Cálculo de Benefícios | cdm_benefitcalculationfrequencypayperiod |     |     |
| Taxa de Cálculo de Benefícios | cdm_benefitcalculationrate |    |     |
| Detalhes da Taxa de Cálculo de Benefícios | cdm_benefitcalculationratedetail |753225 | Resolvido  |
| Opção de Benefícios | cdm_benefitoption |    |     |
| Plano de Benefícios | cdm_benefitplan (Não habilitado para suporte a campos personalizados) |    |     |
| Tipo de Benefício | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Tabelas de tarefas do processo empresarial

| Organização | Tabela |Problemas conhecidos  | Status |
| --- | --- |   --------|----------   |
| Calendário de Processo de Negócios | cdm_businessprocesscalendar | 751867 | Resolvido |
| Atribuição de Grupo de Processos de Negócios | cdm_businessprocessgroupassignment | 751869  751863 | Com atividade|
| Grupo de Tarefas da Biblioteca de Processos de Negócios | cdm_businessprocesslibrarytaskgroup |751866 | Fechada |
| Estágio do Processo de Negócios | cdm_businessprocessstage |      |     |
| Cabeçalho do Modelo de Lista de Verificação | cdm_businessprocesstemplateheader |     |     |
| Tarefa do Modelo de Lista de Verificação | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Tabelas de remuneração

| Organização | Tabela |Problemas conhecidos  | Status |
| --- | --- | ----------      | -------    |
| Plano de Remuneração Fixa | cdm_compensationfixedplan |754453 | Fechada |
| Grade de Remuneração | cdm_compensationgrid |             |     |
| Nível de Remuneração | cdm_compensationlevel |           |     |
| Frequência de Pagamento de Remuneração | cdm_compensationpayfrequency |                  |     |
| Configuração de Ponto de Referência de Remuneração | cdm_compensationreferencepointsetup |               |     |
| Linha da Configuração de Ponto de Referência de Remuneração | cdm_compensationreferencepointsetupline |             |     |
| Região de Remuneração | cdm_compensationregion |                   |     |
| Estrutura de Remuneração | cdm_compensationstructure |    754456        | Fechada    |
| Plano de Remuneração Variável | cdm_compensationvariableplan |               |     |
| Nível do Plano de Remuneração Variável | cdm_compensationvariableplanlevel |                |     |
| Tipo de Plano de Remuneração Variável | cdm_compensationvariableplantype |               |     |
| Evento de Remuneração Fixa | cdm_fixedcompensationevent |               |     |
| Regra de Benefício Proporcional Diferido | cdm_vestingrule |              |     |
| Remuneração Fixa do Trabalhador | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Tabelas da organização

| Organização | Tabela |Problemas conhecidos  | Status |
| --- | --- | ----------      | -------    |
| Departamento | cdm_department |  752194    | Fechada    |
| Emprego | cdm_employment | 762414  |  Fechada  |
| Empresa | cdm_company |  |     |
| Cargo | cdm_job |  |     |
| Função de Trabalho | cdm_jobfunction |        |     |
| Posição de Trabalho | cdm_jobposition | 752214      | Fechada    |
| Tipo de Posição | cdm_positiontype |            |     |
| Atribuição do Trabalhador da Posição | cdm_positionworkerassignmentmap | 752224    |  Fechada   |
| Dimensão da Posição de Trabalho | cdm_jobpositiondimension|       |     |
| Tipo de trabalho | cdm_jobtype |      |     |
| Idioma | cdm_language |        |     |
| Cargo | cdm_title |       |     |

> [!NOTE]
> As dimensões financeiras para **Tipo de posição**, **Atribuição do trabalhador da posição** e **Emprego** fornecem integração de uma direção a Dataverse. As atualizações de dimensões financeiras não são sincronizadas atualmente de Dataverse a Recursos Humanos. 

## <a name="leave-and-absence-tables"></a>Tabelas de licença e ausência

| Organização | Tabela | Problemas conhecidos  | Status |
| --- | --- |   ----------      | -------    |
| Transação Bancária de Licença | cdm_leavebanktransaction |  752252    |    Resolvido |
| Inscrição para Licença | cdm_leaveenrollment |  752934    |Fechada     |
| Plano de Licença | cdm_leaveplan |   752232   |   Fechada  |
| Solicitação de Licença | cdm_leaverequest | 753207     | Fechada    |
| Detalhes da Solicitação da Licença | cdm_leaverequestdetail | 753207     |   Fechada  |
| Tipo de Licença | cdm_leavetype |      |     |
| Código de Motivo do Tipo de Licença | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>A integração de gravação dupla usando tabelas do Dataverse para Licença e ausência só está disponível quando o recurso **Configurar vários tipos de licença em um único plano de licença** está habilitado no Microsoft Dynamics 365 Finance usando o **Gerenciamento de recursos**. 

## <a name="payroll-tables"></a>Tabelas de folha de pagamento

| Organização | Tabela |Problemas conhecidos  | Status |
| --- | --- |  ----------      | -------    |
| Ciclo de Pagamento | cdm_paycycle |    |     |
| Período de Pagamento | cdm_payperiod |          |     |
| Código de Ganhos de Folha de Pagamento | cdm_payrollearningcode |   754458        |   Fechada  |
| Pagamento em Conta Bancária | cdm_bankaccountdisbursement |    751904     |   Fechada  |
| Região Fiscal | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Tabelas de trabalhadores

| Organização | Tabela |Problemas conhecidos  | Status |
| --- | --- |----------      | -------    |
| Trabalhador | cdm_worker |    751906    |    Fechada |
| Endereço do Trabalhador | cdm_workeraddress |   754465     |Fechada     |
| Informações Pessoais do Trabalhador | cdm_workerpersonaldetail |   751906     |   Fechada  |
| Número de Identificação do Trabalhador | cdm_workerpersonidentificationnumber |  766704      |   Fechada  |
| Tipo de Identificação do Trabalhador | cdm_workerpersonidentificationtype |        |     |
| Calendário de Trabalho | cdm_workcalendar |        |     |
| Dia do Calendário de Trabalho | cdm_workcalendarday |        |     |
| Feriado do Calendário de Trabalho |cdm_workcalendarholiday |        |     |
| Linha de Feriados do Calendário de Trabalho | cdm_workcalendarholidayline |        |     |
| Intervalo do Calendário de Trabalho | cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados) |        |     |
| Conta Bancária de Trabalhador | cdm_workerbankaccount |        |     |

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
