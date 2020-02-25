---
title: Configurar a integração com o Finance
description: Este artigo descreve a funcionalidade disponível para integração de Dynamics 365 Human Resources e Dynamics 365 Finance.
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
ms.openlocfilehash: 2e7070f627654c9eb889f3e0ee27e37681db0502
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008063"
---
# <a name="configure-integration-with-finance"></a>Configurar a integração com o Finance

Este artigo descreve a funcionalidade disponível para integração de Dynamics 365 Human Resources e Dynamics 365 Finance. O modelo de Human Resources a Finance disponível com o [Integrador de Dados](https://docs.microsoft.com/powerapps/administrator/data-integrator) permite o fluxo de dados para trabalhos, posições e trabalhadores. Os dados fluem de Human Resources em Finance. O modelo não permite que os dados fluam de Finance de volta para Human Resources. 

![Integração do Human Resources ao fluxo de integração do Finance](./media/TalentFinOpsFlow.png)

A solução Human Resources para Finance fornece os seguintes tipos de sincronização de dados. 

- Manter trabalhos em Human Resources e sincronizá-los de Human Resources para Finance.
- Manter cargos e atribuições de cargo em Human Resources e sincronizá-los de Human Resources para Finance.
- Manter empregos em Human Resources e sincronizá-los de Human Resources para Finance.
- Manter trabalhadores e endereço de trabalhador em Human Resources e sincronizá-los de Human Resources para Finance.

## <a name="system-requirements-for-human-resources"></a>Requisitos de sistema para Human Resources
A solução de integração requer as seguintes versões de Human Resources e Finance: 
- Dynamics 365 Human Resources em Common Data Service.
- Dynamics 365 Finance versão 7.2 e posterior.

## <a name="template-and-tasks"></a>Modelo e tarefas

Para acessar o modelo, faça o seguinte.
1. Abrir [Centro de administração do Power Apps](https://admin.powerapps.com/). 
1. Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos. Será necessário criar um novo projeto para cada entidade legal que você deseja integrar em Finance.

O modelo a seguir é usado para sincronizar registros de Human Resources para Finance.

- **Nome do modelo na integração de dados:** Human Resources (Human Resources Common Data Service a Finance)

  > [!NOTE]
  > O nome da tarefa contém as entidades usadas em cada aplicativo. A origem (Human Resources) está à esquerda e o destino (Finance and Operations) está à direita.

As tarefas subjacentes a seguir são usadas para sincronizar registros de Human Resources para Finance.
- Função de trabalho a função de trabalho de compensação
- Departamentos a Unidade operacional
- Tipos de trabalho a tipo de trabalho de compensação
- Trabalhos a trabalhos
- Trabalhos a Detalhes do Trabalho
- Tipos de posição a tipo de posição
- Cargos de trabalho a cargo base
- Cargos de trabalho a detalhes de cargo
- Cargos de trabalho a durações de cargo
- Cargos de trabalho a hierarquias de cargo
- Trabalhadores a Trabalhador
- Empregos a emprego
- Empregos a Detalhe de emprego
- Atribuição do Trabalhador da Posição a Atribuições do Trabalhador da Posição
- Endereços de trabalhador a endereço postal do trabalhador V2

## <a name="template-mappings"></a>Mapeamentos de modelo

### <a name="job-functions-to-compensation-job-function"></a>Função de trabalho a função de trabalho de compensação

| Entidade do Common Data Service (origem)                 | Entidade do Finance and Operations (destino) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Nome da função)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | DESCRIPTION   (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Departamentos a Unidade operacional

| Entidade do Common Data Service (origem)                           | Entidade do Finance and Operations (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Tipos de trabalho a tipo de trabalho de compensação

| Entidade do Common Data Service (origem)                   | Entidade do Finance and Operations (destino) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | DESCRIPTION   (DESCRIPTION)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Trabalhos a trabalhos

| Entidade do Common Data Service (origem)                                           | Entidade do Finance and Operations (destino)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | DESCRIPTION   (DESCRIPTION)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Trabalhos a Detalhes do Trabalho

| Entidade do Common Data Service (origem)                                             | Entidade do Finance and Operations (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Tipo de trabalho (Nome do tipo de trabalho))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Função de trabalho (Nome da função de trabalho)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Válido de)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Válido até)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Valor equivalente de tempo integral)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Tipos de posição a tipo de posição

| Entidade do Common Data Service (origem)                       | Entidade do Finance and Operations (destino) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | DESCRIPTION   (DESCRIPTION)                 |
| cdm_classification   (cdm_classification) | CLASSIFICATION   (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Cargos de trabalho a cargo base

| Entidade do Common Data Service (origem)                           | Entidade do Finance and Operations (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Cargos de trabalho a detalhes de cargo

| Entidade do Common Data Service (origem)                                                      | Entidade do Finance and Operations (destino)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Número da posição de cargo)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Cargo (Nome))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | DESCRIPTION   (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber   (Departamento (Número do departamento)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Tipo de posição (Nome))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Disponível para atribuição)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Válido de)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (Válido até)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Fulltime Equivalent)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Cargos de trabalho a durações de cargo

| Entidade do Common Data Service (origem)                             | Entidade do Finance and Operations (destino) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo)   | POSITIONID (POSITIONID)                      |
| Ativação calculada (Ativação calculada) | VALIDFROM (VALIDFROM)                        |
| Aposentadoria calculada (Aposentadoria calculada) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hiearchies"></a>Cargos de trabalho a hierarquias de cargo

| Entidade do Common Data Service (origem)                                                                           | Entidade do Finance and Operations (destino) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Válido de)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Válido até)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Trabalhadores a Trabalhador
| Entidade do Common Data Service (origem)                           | Entidade do Finance and Operations (destino)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | BIRTHDATE   (BIRTHDATE)                           |
| cdm_gender   (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | FIRSTNAME   (FIRSTNAME)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Empregos a emprego

| Entidade do Common Data Service (origem)                                             | Entidade do Finance and Operations (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Empregos a Detalhe de emprego

| Entidade do Common Data Service (origem)                                             | Entidade do Finance and Operations (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (Válido de)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Válido até)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Atribuição do Trabalhador da Posição a Atribuições do Trabalhador da Posição

| Entidade do Common Data Service (origem)                                             | Entidade do Finance and Operations (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Número da posição de cargo)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (Válido de)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Válido até)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Endereços de trabalhador a endereço postal do trabalhador V2

| Entidade do Common Data Service (origem)                                             | Entidade do Finance and Operations (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Considerações de integração
Ao integrar dados deHuman Resources ao Finance, a integração tentará coincidir registros com base na ID. Se a correspondência ocorrer, os dados em Finance serão substituídos pelos valores de Human Resources. No entanto, um problema pode ocorrer se logicamente esses registros forem diferentes e a mesma ID tiver sido gerada tanto em Human Resources ou Finance com base na sequência numérica respectiva.

As áreas em que isso pode ocorrer são Trabalhador, que usa o número de funcionários para fazer a correspondência e as posições. Os trabalhos não usam sequências numéricas. Como resultado, se a mesma ID de trabalho estiver presente em Human Resources e Finance, as informações de recursos humanos substituirão as informações de Dynamics 365 Finance. 

Para evitar problemas com IDs duplicadas, você pode adicionar um prefixo na [sequência numérica](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=/dynamics365/unified-operations/talent/toc.json) ou definir um número inicial na sequência numérica que está além do intervalo do outro sistema. 

A identificação de local usada para o endereço de trabalho não faz parte de uma sequência numérica. Ao integrar um endereço de trabalhador de Human Resources a Finance, se o endereço de trabalho já existir em Finance, um registro de endereço duplicado poderá ser criado. 

A ilustração a seguir mostra um exemplo de um mapeamento de modelo no Integrador de dados. 

![Mapeamento de modelo](./media/IntegrationMapping.png)


