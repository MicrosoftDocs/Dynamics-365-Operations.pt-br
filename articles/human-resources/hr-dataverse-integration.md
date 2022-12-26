---
title: Configurar a integração com tabelas do Dataverse
description: Este artigo descreve a integração entre o Microsoft Dynamics 365 Human Resources e o Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838618"
---
# <a name="configure-integration-with-dataverse-tables"></a>Configurar a integração com tabelas do Dataverse

>[!Important]
>A funcionalidade mencionada neste artigo está disponível para clientes do Dynamics 365 Human Resources na infraestrutura de finanças e operações. 


Para integrar o Microsoft Dynamics 365 Human Resources ao Dataverse, você poderá usar o [Integrador de Dados](/powerapps/administrator/data-integrator). O modelo Human Resources–para–Dataverse permite que os dados de trabalhos, cargos, trabalhadores e outros fluam do Human Resources para o Dataverse, e do Dataverse para o Human Resources, criando uma gravação nos dois sistemas.

## <a name="system-requirements-for-human-resources"></a>Requisitos de sistema para Human Resources

A solução de integração requer as seguintes versões do Human Resources e do Dynamics 365 Finance: 

- Dynamics 365 Finance versão 7.2 ou posterior
- Ambiente do Dynamics CRM em que um banco de dados tenha sido criado e os aplicativos do Dynamics 365 sejam permitidos

## <a name="template-and-tasks"></a>Modelo e tarefas

Siga estas etapas para acessar o modelo Human Resources-para-Finance.

1. Abra o [centro de administração do Power Apps](https://admin.powerapps.com/). 
2. Em seu ambiente, selecione **Aplicativos do Dynamics 365** e selecione **Origem do aplicativo** na barra de ferramentas.
3. Para instalar o modelo, procure "Human Resources de gravação dupla" ou vá diretamente para o seguinte endereço: <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. Depois de concluída a instalação, abra o Dynamics 365 Finance.
4. Abra o espaço de trabalho **Gerenciamento de Dados**. 
5. Selecione **Gravação Dupla**. 
6. Siga o processo para vincular seu ambiente a pelo menos uma empresa na sua organização. 
7. Ao concluir a configuração de um link para o seu ambiente do Dataverse, selecione **Aplicar Solução**. A solução é aplicada e os mapeamentos são instalados no aplicativo integrador.

## <a name="template-mappings"></a>Mapeamentos de modelo

Nas seguintes tabelas de mapeamento de modelos, o nome da tarefa indica as entidades usadas em cada aplicativo. O Finance está à esquerda e o Dataverse à direita.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Pagamentos de conta bancária (Gravação dupla) para Pagamento de Conta Bancária

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| VALOR                         | cdm\_amount                                         |
| PRIORITY                       | cdm\_disbursementpriority                           |
| NÚMERO DA EQUIPE                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| REMAINDER                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Detalhe da taxa de cálculo do benefício (Gravação dupla) para Detalhe da Taxa de Cálculo de Benefícios

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CONTRIBUTIONMETHOD             | cdm\_contributionmethod                             |
| EFFECTIVE                      | cdm\_effective                                      |
| EMPLOYERCONTRIBUTION           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| WORKERDEDUCTION                | cdm\_workerdeduction                                |
| NAME                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>Cabeçalho da taxa de cálculo de benefícios para Taxa de Cálculo de Benefícios

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| NAME                           | cdm\_name                                           |
| TIERTYPE                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Opção de benefício para Opção de Benefício

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ALLOWBENEFICIARYDESIGNATIONS   | cdm\_allowbeneficiarydesignations                   |
| ALLOWDEPENDENTCOVERAGE         | cdm\_allowdependentcoverage                         |
| BENEFITOPTIONID                | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| ISWAIVE                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Tipo de benefício para Tipo de Benefício

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| BENEFITTYPEID                  | cdm\_name                                           |
| CONCURRENTENROLLMENT           | cdm\_concurrentenrollment                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| PAYROLLCATEGORY                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Calendário empresarial para Calendário de Processos Empresariais

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NAME                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ISOPENMONDAY                   | cdm\_ismondayopen                                   |
| ISOPENTUESDAY                  | cdm\_istuesdayopen                                  |
| ISOPENWEDNESDAY                | cdm\_iswednesdayopen                                |
| ISOPENTHURSDAY                 | cdm\_isthursdayopen                                 |
| ISOPENFRIDAY                   | cdm\_isfridayopen                                   |
| ISOPENSATURDAY                 | cdm\_issaturdayopen                                 |
| ISOPENSUNDAY                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Processo empresarial para Cabeçalho do Processo Empresarial

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processid                                      |
| PROCESSTYPE                    | cdm\_processtype                                    |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| STATUS                         | cdm\_status                                         |
| TARGETDATE                     | cdm\_targetdate                                     |
| STARTDATETIME                  | cdm\_startdatetime                                  |
| ENDDATETIME                    | cdm\_enddatetime                                    |
| RESOLVEDBYPERSONNELNUMBER      | cdm\_resolvedbyid.cdm\_workernumber                  |
| PROCESSOWNERPERSONNELNUMBER    | cdm\_processownerid.cdm\_workernumber                |
| SOURCETEMPLATENAME             | cdm\_sourcetemplateid.cdm\_name                      |
| SOURCETEMPLATEPROCESSTYPE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOURCETEMPLATEGENERICSUBTYPE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Grupo de tarefas de biblioteca de processos empresariais para Grupo de Tarefas de Biblioteca de Processos Empresariais

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_processtype                                    |
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Estágio do processo empresarial para Estágio do Processo Empresarial

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| SEQUENCENUMBER                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Tarefa do processo empresarial para Tarefa do Processo Empresarial

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| DUEDATE                        | cdm\_duedate                                        |
| TASKID                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| COMPLETIONDATETIME             | cdm\_completiondatetime                             |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| NAME                           | cdm\_name                                           |
| STATUS                         | cdm\_status                                         |
| RESOLVEDBY\_PERSONNELNUMBER     | cdm\_resolvedbyid.cdm\_workernumber                  |
| TEMPLATETASKID                 | cdm\_templatetaskid.cdm\_taskid                      |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Modelo de processo empresarial para Cabeçalho de Modelo de Lista de Verificação

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| NÚMERO DA EQUIPE                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Tarefa de Modelo de processo empresarial para Tarefa de Modelo de Lista de Verificação

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TASKID                         | cdm\_taskid                                         |
| NAME                           | cdm\_name                                           |
| TEMPLATEHEADER\_PROCESSTYPE     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| TEMPLATEHEADER\_GENERICSUBTYPE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| TEMPLATEHEADER\_NAME            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| DESCRIÇÃO                    | cdm\_description                                    |
| DUEDATEOFFSETDAYS              | cdm\_duedateoffsetdays                              |
| MENUITEMTYPE                   | cdm\_tasklinktype                                   |
| MENUITEM                       | cdm\_tasklink                                       |
| CONTACTPERSON\_PERSONNELNUMBER  | cdm\_contactpersonid.cdm\_workernumber               |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Frequência de cálculo para Frequência de Cálculo de Benefícios

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| FREQUENCY                      | cdm\_name                                           |
| FREQUENCYCONTROL               | cdm\_frequencycontrol                               |
| ISIMMUTABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Período de pagamento da frequência de cálculo para Período de Pagamento da Frequência de Cálculo de Benefícios

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALCULATIONFREQUENCYID         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| PERIODSTARTDATE                | cdm\_payperiodid.cdm\_periodstartdate                |
| PAYCYCLEID                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Calendário para Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| CALENDARNAME                   | cdm\_description                                    |
| WORKCALENDARHOLIDAYID          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Tabela de ações de remuneração fixa para Evento de Remuneração Fixa

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIVE                         | cdm\_isactive                                       |
| DESCRIÇÃO                    | cdm\_description                                    |
| TIPO                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Plano de remuneração fixa para Plano de Remuneração Fixa

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PLAN                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| MOEDA                       | cdm\_transactioncurrencyid.isocurrencycode          |
| PAYFREQUENCY                   | cdm\_payfrequency.cdm\_name                          |
| HIRERULE                       | cdm\_hirerule                                       |
| OUTOFRANGETOLERANCE            | cdm\_outofrangetolerance                            |
| RECOMMENDATIONALLOWED          | cdm\_recommendationallowed                          |
| COMPENSATIONSTRUCTURE          | cdm\_compensationgrid.cdm\_name                      |
| REFPOINTSETUPID                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| CONTROLPOINT                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Grades de remuneração para Grade de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| GRIDID                         | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| REFERENCESETUP                 | cdm\_referencepointsetupid.cdm\_name                 |
| TIPO                           | cdm\_type                                           |
| MOEDA                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Função de trabalho de remuneração para Função de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBFUNCTIONID                  | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Tipo de trabalho de remuneração para Tipo de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBTYPEID                      | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| EXEMPTSTATUS                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Frequência de pagamento de remuneração para Frequência de Pagamento de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYRATECONVERSION              | cdm\_name                                           |
| PERIOD                         | cdm\_period                                         |
| DESCRIÇÃO                    | cdm\_description                                    |
| ANNUALCONVERSIONFACTOR         | cdm\_annualconversionfactor                         |
| HOURLYCONVERSIONFACTOR         | cdm\_hourlyconversionfactor                         |
| MONTHLYCONVERSIONFACTOR        | cdm\_monthlyconversionfactor                        |
| WEEKLYCONVERSIONFACTOR         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Regiões de remuneração para Região de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| LOCALIZAÇÃO                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Plano de remuneração variável V2 para Plano de Remuneração Variável

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VARIABLEAWARDBASIS             | cdm\_awardbasis                                     |
| AWARDBASISCALCULATION          | cdm\_awardbasiscalculation                          |
| CALCULATIONTYPE                | cdm\_calculationtype                                |
| DESCRIÇÃO                    | cdm\_description                                    |
| ENABLEENROLLMENT               | cdm\_enableenrollment                               |
| ENABLELEVELS                   | cdm\_enablelevels                                   |
| ENABLERECOMMENDATION           | cdm\_enablerecommendation                           |
| HIRERULE                       | cdm\_hirerule                                       |
| LEVERAGE100PERCENT             | cdm\_leverage100percent                             |
| LEVERAGEMAXIMUM                | cdm\_leveragemaximum                                |
| LEVERAGEMINIMUM                | cdm\_leverageminimum                                |
| LEVERAGEOVEROBJECTIVE          | cdm\_leverageoverobjective                          |
| LEVERAGEUNDEROBJECTIVE         | cdm\_leverageunderobjective                         |
| PERCENTOFBASIS                 | cdm\_percentofbasis                                 |
| PLANID                         | cdm\_name                                           |
| VARIABLECOMPENSATIONTYPE       | cdm\_variablecompensationtypeid.cdm\_name            |
| UNITCURRENCYCODE               | transactioncurrencyid.isocurrencycode              |
| UNITRELATIONSHIP               | cdm\_unitrelationship                               |
| UNITVALUE                      | cdm\_unitvalue                                      |
| NUMBEROFUNITSREAL              | cdm\_numberofunits                                  |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VESTINGRULE                    | cdm\_vestingruleid.cdm\_name                         |
| LEVERAGETOLERANCEMAX           | cdm\_leveragetolerancemax                           |
| LEVERAGETOLERANCEMIN           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Tipo de remuneração variável para Tipo de Plano de Remuneração Variável

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| TIPO                           | cdm\_awardtype                                      |
| VARIABLECOMPENSATIONTYPE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Regras de benefício proporcional diferido de remuneração para Regra de Benefício Proporcional Diferido

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| OBSERVAÇÃO                           | cdm\_notes                                          |
| VESTINGRULE                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Departamento V2 para Departamento

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NAME                           | cdm\_name                                           |
| SEARCHNAME                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Região Fiscal de Gravação Dupla para Região Fiscal

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CITY                           | cdm\_city                                           |
| COUNTRYORREGION                | cdm\_countryorregion                                |
| COUNTY                         | cdm\_county                                         |
| STATE                          | cdm\_stateorprovince                                |
| TAXREGIONNAME                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Identificação do Trabalhador de Gravação Dupla para Número de Identificação Pessoal do Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| ENTRYTYPE                      | cdm\_entrytype                                      |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDENTIFICATIONTYPEID           | cdm\_identificationtypeid.cdm\_name                  |
| ISPRIMARY                      | cdm\_isprimary                                      |
| ISSUEDATE                      | cdm\_issuedate                                      |
| ISSUINGAGENCYID                | cdm\_issuingagencyid.cdm\_name                       |
| WORKERNUMBER                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Estrutura de remuneração para Estrutura de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VALOR                         | cdm\_amount                                         |
| GRID                           | cdm\_compensationgridid.cdm\_name                    |
| LEVELID                        | cdm\_compensationlevelid.cdm\_name                   |
| REFERENCEPOINTLINENUMBER       | cdm\_referencepointid.cdm\_linenumber                |
| REFERENCESETUP                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| REFERENCEPOINT                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Código de Ganhos para Código de Ganhos de Folha de Pagamento

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EARNINGCODE                    | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| INCLUDEINPAYMENTTYPE           | cdm\_includeinpaymenttype                           |
| QUANTITYUNIT                   | cdm\_quantityunit                                   |
| TRACKFMLAHOURS                 | cdm\_trackfmlahours                                 |
| ISPRODUCTIVE                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Remuneração fixa de funcionário para Remuneração Fixa de Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| TIPO                           | cdm\_compensationtype                               |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| PAYFREQUENCY                   | cdm\_payfrequencyid.cdm\_name                        |
| PAYRATE                        | cdm\_payrate                                        |
| PLAN                           | cdm\_planid.cdm\_name                                |
| POSITIONID                     | cdm\_positionid.cdm\_jobpositionnumber               |
| PROCESSTYPE                    | cdm\_processtype                                    |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| STEP                           | cdm\_referencepointsetuplineid.cdm\_name             |
| REFPOINTSETUPID                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Emprego por empresa para Emprego

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMPLOYMENTENDDATE              | cdm\_employmentenddate                              |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| EMPLOYMENTSTARTDATE            | cdm\_employmentstartdate                            |
| WORKERTYPE                     | cdm\_workertype                                     |
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| ADJUSTEDWORKERSTARTDATE        | cdm\_adjustedworkerstartdate                        |
| EMPLOYERNOTICEAMOUNT           | cdm\_employernoticeamount                           |
| EMPLOYERUNITOFNOTICE           | cdm\_employerunitofnotice                           |
| WORKERUNITOFNOTICE             | cdm\_workerunitofnotice                             |
| WORKERNOTICEAMOUNT             | cdm\_workernoticeamount                             |
| LASTDATEWORKED                 | cdm\_lastdateworked                                 |
| PROBATIONENDDATE               | cdm\_probationenddate                               |
| TRANSITIONDATE                 | cdm\_transitiondate                                 |
| TRANSITIONREASONCODENAME       | cdm\_transitionreasoncode.cdm\_name                  |
| WORKERSTARTDATE                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Origem étnica para Origem Étnica

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Atribuição de grupo para Atribuição de Grupo de Processos Empresariais

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Tipo de identificação para Tipo de Identificação Pessoal do Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| IDENTIFICATIONTYPEID           | cdm\_name                                           |
| ALLOWEDVALUES                  | cdm\_allowedvalues                                  |
| FIXEDLENGTH                    | cdm\_fixedlength                                    |
| IDENTIFICATIONNUMBERFORMAT     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Agência emissora para Agência Emissora de Identificação Pessoal

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMAIL                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| ISSUINGAGENCY                  | cdm\_name                                           |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| NAME                           | cdm\_description                                    |
| PAGER                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Gravação Dupla de Cargos de Trabalho para Cargo de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONID                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| AVAILABLEFORASSIGNMENT         | cdm\_availableforassignment                         |
| COMPENSATIONREGIONID           | cdm\_compensationregionid.cdm\_name                  |
| DEPARTMENTID                   | cdm\_departmentid.cdm\_departmentnumber              |
| DESCRIÇÃO                    | cdm\_description                                    |
| FULLTIMEEQUIVALENT             | cdm\_fulltimeequivalent                             |
| JOBID                          | cdm\_jobid.cdm\_name                                 |
| PARENTPOSITIONID               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| POSITIONTYPEID                 | cdm\_positiontypeid.cdm\_name                        |
| RETIREMENT                     | cdm\_retirement                                     |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Gravação Dupla de Trabalhos para Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBID                          | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| JOBDESCRIPTION                 | cdm\_jobdescription                                 |
| ALLOWUNLIMITEDPOSITIONS        | cdm\_allowunlimitedpositions                        |
| MAXIMUMNUMBEROFPOSITIONS       | cdm\_maximumnumberofpositions                       |
| JOBFUNCTIONID                  | cdm\_jobfunctionid.cdm\_name                         |
| JOBTYPEID                      | cdm\_jobtypeid.cdm\_name                             |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DEFAULTFULLTIMEEQUIVALENCY     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Códigos do idioma para Idioma

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LANGUAGECODEID                 | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transação bancária de licença e ausência V2 para Transação Bancária de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VALOR                         | cdm\_amount                                         |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Registro de licença e ausência V2 para Registro de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| CUSTOMDATE                     | cdm\_customdate                                     |
| ACCRUALSTARTDATE               | cdm\_accrualstartdate                               |
| ACCRUALDATEBASIS               | cdm\_accrualdatebasis                               |
| ISACCRUALSUSPENDED             | cdm\_isaccrualsuspended                             |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TIERBASIS                      | cdm\_tierbasis                                      |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Plano de licença e ausência V2 para Plano de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCRUALFREQUENCY               | cdm\_accrualfrequency                               |
| NAME                           | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Tipo de licença e ausência para Tipo de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EARNINGCODEID                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Código de motivo do tipo de licença e ausência para Código de Motivo de Tipo de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LEAVETYPE                      | cdm\_typeid.cdm\_type                                |
| REASONCODEID                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Detalhe de solicitação de folga por licença para Detalhe de Solicitação de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VALOR                         | cdm\_amount                                         |
| LEAVEDATE                      | cdm\_leavedate                                      |
| REQUESTID                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TIPO                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>Cabeçalho de solicitação de folga por licença para Solicitação de Licença

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REQUESTID                      | cdm\_leaverequestnumber                             |
| REQUESTDATE                    | cdm\_requestdate                                    |
| STATUS                         | cdm\_status                                         |
| COMMENT                        | cdm\_comment                                        |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Níveis para Nível de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TIPO                           | cdm\_type                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| LEVEL                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>Cabeçalho do processo de integração para Cabeçalho do Processo de Integração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ONBOARDEDEMPLOYEEPERSONNELNUMBER | cdm\_onboardedemployeeid.cdm\_workernumber           |
| EMPLOYMENTPERSONNELNUMBER      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| EMPLOYMENTSTARTDATE            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Ciclo de pagamento para Ciclo de Pagamento

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| PAYCYCLEFREQUENCY              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Período de pagamento para Período de Pagamento

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DEFAULTPAYMENTDATE             | cdm\_defaultpaymentdate                             |
| PAYCYCLEID                     | cdm\_paycycleid.cdm\_name                            |
| PERIODENDDATE                  | cdm\_periodenddate                                  |
| PERIODSTARTDATE                | cdm\_periodstartdate                                |
| STATUS                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Detalhes da folha de pagamento para cargos para Detalhe da Posição na Folha de Pagamento

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_paycycle.cdm\_name                              |
| POSITIONID                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ANNUALREGULARHOURS             | cdm\_annualregularhours                             |
| PAIDBYLEGALENTITY              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Gravação Dupla de Dimensões Padrão de Cargos para Dimensão de Cargos de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Tipo de cargo para Tipo de Cargo

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONTYPEID                 | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Atribuições do trabalhador do cargo V2 para Atribuição de Trabalhador do Cargo

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Códigos de motivo para Código de Motivo

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REASONCODEID                   | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Linha de Configuração de Ponto de Referência (Gravação Dupla) para Linha de Configuração de Ponto de Referência de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIÇÃO                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| REFPOINTSETUPID                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Configurações de ponto de referência para Configuração de Ponto de Referência de Remuneração

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REFERENCESETUP                 | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| TIPO                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Tipos de habilidade para Tipo de Habilidade

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Títulos para Título

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TITLEID                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Nível de remuneração variável V2 para Nível de Plano de Remuneração Variável

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| PLANID                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Situação militar para Situação Militar

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Registros de Calendário de Trabalho para Registro de Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| NÚMERO DA EQUIPE                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Feriado no calendário de trabalho para Feriado no Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ID                             | cdm\_name                                           |
| DESCRIÇÃO                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Linha de feriado no calendário de trabalho para Linha de Feriado no Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NAME                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Trabalhador para Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO DA EQUIPE                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| MIDDLENAME                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NAME                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Contas bancárias do trabalhador para a Conta Bancária do Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| EMAIL                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NAME                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Detalhes pessoais do trabalhador para Detalhes Pessoais do Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Gravação dupla de endereços postais do trabalhador para Endereço do Trabalhador

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO DA EQUIPE                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIVE                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ISPRIMARY                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Horário de trabalho para Intervalo de Tempo de Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Horários de trabalho para Dia do Calendário de Trabalho

| Entidade do Finance                 | Tabela do Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Considerações de integração

- Todas as alterações feitas nos dados de qualquer um dos sistemas estarão sujeitas a validação pelo outro sistema. Se ocorrer uma falha, os dados não serão gravados em nenhum dos sistemas. 
- Todas as gravações estão sujeitas ao padrão de dados (se a lógica personalizada ocorrer no Finance).
- O aplicativo integrador de gravação dupla usa chaves de integração para mapear entre os dois sistemas. Às vezes, é difícil escolher a chave de integração correta, especialmente se várias chaves de integração atenderem aos requisitos. Para ajudar nessa escolha, a tabela a seguir lista as chaves de integração sugeridas para seus mapeamentos.

| Tabela do Dataverse                          | Chaves de integração |
|------------------------------------------|------------------|
| Pagamento em Conta Bancária                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Frequência de Cálculo do Benefício            | cdm\_name |
| Período de Pagamento da Frequência de Cálculo de Benefícios | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Taxa de Cálculo de Benefícios                 | cdm\_name |
| Detalhes da Taxa de Cálculo de Benefícios          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Opção de Benefícios                           | cdm\_name |
| Tipo de Benefício                             | cdm\_name |
| Calendário de Processo de Negócios                | cdm\_name |
| Atribuição de Grupo de Processos de Negócios        | cdm\_name |
| Cabeçalho do Processo de Negócios                  | cdm\_processid |
| Grupo de Tarefas da Biblioteca de Processos de Negócios      | cdm\_processtype, cdm\_name |
| Estágio do Processo de Negócios                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Tarefa do Processo de Negócios                    | cdm\_taskid |
| Unidade de negócios                            | |
| Cabeçalho do Modelo de Lista de Verificação                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Tarefa do Modelo de Lista de Verificação                  | cdm\_taskid |
| Empresa                                  | cdm\_companycode |
| Plano de Remuneração Fixa                  | cdm\_name, cdm\_company.cdm\_companycode |
| Grade de Remuneração                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Nível de Remuneração                       | cdm\_name |
| Frequência de Pagamento de Remuneração               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Configuração de Ponto de Referência de Remuneração       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Linha da Configuração de Ponto de Referência de Remuneração  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Região de Remuneração                      | cdm\_name |
| Estrutura de Remuneração                   | cdm\_compensationlevelid.cdm\_name, cdm\_referencepointid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Plano de Remuneração Variável               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Nível do Plano de Remuneração Variável         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid.cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Tipo de Plano de Remuneração Variável          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Moeda                                 | isocurrencycode |
| Departamento                               | cdm\_departmentnumber |
| Emprego                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Origem Étnica                            | cdm\_name |
| Evento de Remuneração Fixa                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Cargo                                      | cdm\_name |
| Função de Trabalho                             | cdm\_name |
| Posição de Trabalho                             | cdm\_jobpositionnumber |
| Dimensão da Posição de Trabalho                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Tipo de trabalho                                 | cdm\_name |
| Idioma                                 | cdm\_name |
| Transação Bancária de Licença                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Inscrição para Licença                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Plano de Licença                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Solicitação de Licença                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Detalhes da Solicitação da Licença                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_companyid.cdm\_companycode |
| Tipo de Licença                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Código de Motivo do Tipo de Licença                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid.cdm\_companyid.cdm\_companycode |
| Cabeçalho do Processo de Integração                   | cdm\_processheaderid.cdm\_processid |
| Organização                             | |
| Ciclo de Pagamento                                | cdm\_name |
| Período de Pagamento                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Código de Ganhos de Folha de Pagamento                     | cdm\_name |
| Detalhe da Posição da Folha de Pagamento                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Agência Emissora de Identificação Pessoal     | cdm\_name |
| Tipo de Posição                            | cdm\_name |
| Atribuição do Trabalhador da Posição               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Código de Motivo                              | cdm\_name |
| Tipo de Habilidade                               | cdm\_name |
| Região Fiscal                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Equipe                                     | azureactivedirectoryobjectid, membershiptype |
| Cargo                                    | cdm\_name |
| Usuário                                     | azureactivedirectoryobjectid |
| Regra de Benefício Proporcional Diferido                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Situação Militar                           | cdm\_name |
| Calendário de Trabalho                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Dia do Calendário de Trabalho                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Inscrição do Calendário de Trabalho                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Feriado do Calendário de Trabalho                    | cdm\_name |
| Linha de Feriados do Calendário de Trabalho               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Intervalo do Calendário de Trabalho              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Trabalhador                                   | cdm\_workernumber |
| Endereço do Trabalhador                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Conta Bancária de Trabalhador                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Remuneração Fixa do Trabalhador                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Número de Identificação do Trabalhador      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Tipo de Identificação do Trabalhador        | cdm\_name |
| Informações Pessoais do Trabalhador                   | cdm\_workerid.cdm\_workernumber |
