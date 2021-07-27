---
title: Configurar a integração com o Finance
description: Este artigo descreve a funcionalidade disponível para integração de Dynamics 365 Human Resources e Dynamics 365 Finance.
author: andreabichsel
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 81b65d1aeeff6c4459fe0b2637013009958cfd55
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360631"
---
# <a name="configure-integration-with-finance"></a>Configurar a integração com o Finance

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Para integrar o Dynamics 365 Human Resources com Dynamics 365 Finance, você pode usar o modelo Human Resources para Finance no [Integrador de Dados](/powerapps/administrator/data-integrator). O modelo de Human Resources para Finance permite o fluxo de dados para trabalhos, posições e trabalhadores. O modelo permite que os dados fluam de Human Resources para Finance, mas não permite que os dados fluam de Finance para Human Resources.

![Integração do Human Resources ao fluxo de integração do Finance.](./media/hr-admin-integration-finance-flow.png)

A solução Human Resources para Finance fornece os seguintes tipos de sincronização de dados:

- Manter trabalhos em Human Resources e sincronizá-los de Human Resources para Finance
- Manter cargos e atribuições de cargo em Human Resources e sincronizá-los de Human Resources para Finance
- Manter empregos em Human Resources e sincronizá-los de Human Resources para Finance
- Manter trabalhadores e endereço de trabalhador em Human Resources e sincronizá-los de Human Resources para Finance

## <a name="system-requirements-for-human-resources"></a>Requisitos de sistema para Human Resources

A solução de integração requer as seguintes versões de Human Resources e Finance: 

- Dynamics 365 Human Resources em Dataverse
- Dynamics 365 Finance versão 7.2 e posterior

## <a name="template-and-tasks"></a>Modelo e tarefas

Para acessar o modelo Human Resources para Finance.

1. Abrir [Centro de administração do Power Apps](https://admin.powerapps.com/). 

2. Selecione **Projetos** e, em seguida, selecione **Novo projeto** no canto superior direito. Criar um novo projeto para cada entidade legal que você deseja integrar em Finance.

3. Selecione o **Human Resources (Human Resources Dataverse para Finance)** para sincronizar registros de Human Resources para Finance.

O modelo usa as tarefas subjacentes a seguir para sincronizar registros de Human Resources para Finance:

- **Função de trabalho a função de trabalho de compensação**
- **Departamentos a Unidade operacional**
- **Tipos de trabalho a tipo de trabalho de compensação**
- **Trabalhos a trabalhos**
- **Trabalhos a Detalhes do Trabalho**
- **Tipos de posição a tipo de posição**
- **Cargos de trabalho a cargo base**
- **Cargos de trabalho a detalhes de cargo**
- **Cargos de trabalho a durações de cargo**
- **Cargos de trabalho a hierarquias de cargo**
- **Trabalhadores a Trabalhador**
- **Empregos a emprego**
- **Empregos a Detalhe de emprego**
- **Atribuição do Trabalhador da Posição a Atribuições do Trabalhador da Posição**
- **Endereços de trabalhador a endereço postal do trabalhador V2**

## <a name="template-mappings"></a>Mapeamentos de modelo

Nas seguintes tabelas de mapeamento de modelos, o nome da tarefa contém as entidades usadas em cada aplicativo. A origem (Human Resources) está à esquerda e o destino (Finance) está à direita.

### <a name="job-functions-to-compensation-job-function"></a>Função de trabalho a função de trabalho de compensação

| Tabela do Dataverse (origem) | Entidade do Finance (destino) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Nome da função)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | DESCRIPTION   (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Departamentos a Unidade operacional

| Tabela do Dataverse (origem)           | Entidade do Finance (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Tipos de trabalho a tipo de trabalho de compensação

| Tabela do Dataverse (origem)   | Entidade do Finance (destino) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | DESCRIPTION   (DESCRIPTION)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Trabalhos a trabalhos

| Tabela do Dataverse (origem)                           | Entidade do Finance (destino)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | DESCRIPTION   (DESCRIPTION)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Trabalhos a Detalhes do Trabalho

| Tabela do Dataverse (origem)                             | Entidade do Finance (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Tipo de trabalho (Nome do tipo de trabalho))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Função de trabalho (Nome da função de trabalho)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Válido de)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Válido até)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Valor equivalente de tempo integral)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Tipos de posição a tipo de posição

| Tabela do Dataverse (origem)       | Entidade do Finance (destino) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | DESCRIPTION   (DESCRIPTION)                 |
| cdm_classification   (cdm_classification) | CLASSIFICATION   (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Cargos de trabalho a cargo base

| Tabela do Dataverse (origem)           | Entidade do Finance (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Cargos de trabalho a detalhes de cargo

| Tabela do Dataverse (origem)              | Entidade do Finance (destino)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Número da posição de cargo)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Cargo (Nome))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | DESCRIPTION   (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber   (Departamento (Número do departamento)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Tipo de posição (Nome))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Disponível para atribuição)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Válido de)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (Válido até)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Equivalente ao horário integral)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Cargos de trabalho a durações de cargo

| Tabela do Dataverse (origem)             | Entidade do Finance (destino) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo)   | POSITIONID (POSITIONID)                      |
| Ativação calculada (Ativação calculada) | VALIDFROM (VALIDFROM)                        |
| Aposentadoria calculada (Aposentadoria calculada) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Cargos de trabalho a hierarquias de cargo

| Tabela do Dataverse (origem)        | Entidade do Finance (destino) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número da posição de cargo)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Válido de)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Válido até)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Trabalhadores a Trabalhador
| Tabela do Dataverse (origem)           | Entidade do Finance (destino)       |
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

| Tabela do Dataverse (origem)                             | Entidade do Finance (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Empregos a Detalhe de emprego

| Tabela do Dataverse (origem)                             | Entidade do Finance (destino)   |
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

| Tabela do Dataverse (origem)                             | Entidade do Finance (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Número da posição de cargo)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (Válido de)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Válido até)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Endereços de trabalhador a endereço postal do trabalhador V2

| Tabela do Dataverse (origem)                             | Entidade do Finance (destino)   |
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

A integração de Human Resources ao Finance tenta coincidir registros com base na ID. Se os registros forem correspondidos, o Integrador de dados substitui os dados no Finance com os valores no Human Resources. No entanto, um problema pode ocorrer se logicamente esses registros forem diferentes e a mesma ID tiver sido gerada tanto em Human Resources ou Finance com base na sequência numérica respectiva.

Esse problema pode acontecer com **Trabalhador**, que usa **Número pessoal** para realizar a correspondência e **Posições**. Os trabalhos não usam sequências numéricas. Como resultado, se a mesma ID de trabalho existir em Human Resources e Finance, as informações de recursos humanos substituem as informações de Dynamics 365 Finance. 

Para evitar problemas com IDs duplicadas, você pode adicionar um prefixo na [sequência numérica](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json) ou definir um número inicial na sequência numérica que está além do intervalo do outro sistema. 

A identificação de local usada para o endereço de trabalho não faz parte de uma sequência numérica. Ao integrar um endereço de trabalhador de Human Resources a Finance, se o endereço de trabalho já existir em Finance, um registro de endereço duplicado poderá ser criado. 

A ilustração a seguir mostra um exemplo de um mapeamento de modelo no Integrador de dados. 

![Mapeamento de modelo.](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]