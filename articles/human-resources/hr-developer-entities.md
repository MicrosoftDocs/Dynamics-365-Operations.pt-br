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
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008139"
---
# <a name="common-data-service-entities"></a>Entidades do Common Data Service

O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.

Para obter mais informações sobre o Common Data Service, consulte [O que é o Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

As entidades a seguir do Human Resources estão disponíveis no Common Data Service.

## <a name="benefit-entities"></a>Entidades de benefícios

**Frequência de cálculo do benefício**

| **Campos**        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------|---------------|--------------|----------------|
| Descrição       | Text          |              | X              |
| Controle de Frequência | Conjunto de opções    | X            | X              |
| É Imutável      | Duas opções   |              | X              |
| Nome              | Text          | X            | X              |


**Taxa de cálculo do benefício**

| **Campos**  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------|---------------|--------------|----------------|
| Descrição | Text          |              | X              |
| Nome        | Text          | X            | X              |
| TierType    | Conjunto de opções    | X            | X              |


**Detalhe da taxa de cálculo do benefício**

| **Campos**                             | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|----------------------------------------|----------------|--------------|----------------|
| Número de Detalhe de Taxa de Cálculo do Benefício | Text           | X            | X              |
| ID de Taxa de Cálculo                    | Pesquisa         | X            | X              |
| Método de Contribuição                    | Conjunto de Opções     | X            | X              |
| Efetivação                              | Somente Data      | X            | X              |
| Contribuição do empregador                  | Número decimal |              | X              |
| Expiração                             | Somente Data      | X            | X              |
| WorkerDeduction                        | Número decimal |              | X              |


**Tipo de benefício**

| **Campos**           | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------|---------------|--------------|----------------|
| ConcurrentEnrollment | Conjunto de opções    |              | X              |
| Descrição          | Text          |              | X              |
| Nome                 | Text          | X            | X              |
| PayrollCategory      | Conjunto de opções    |              | X              |


**Plano de benefícios**

| **Campos**                               | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|------------------------------------------|----------------|--------------|----------------|
| Método de limite de atraso de pagamento                      | Conjunto de opções     |              | X              |
| Tipo de Benefício                             | Pesquisa         | X            | X              |
| Método de limite de contribuição                | Conjunto de opções     |              | X              |
| Método de Contribuição                      | Conjunto de opções     |              | X              |
| Moeda                                 | Pesquisa         |              | X              |
| Prioridade da Dedução                       | Número inteiro   |              | X              |
| Valor Padrão do Limite de Contribuição        | Moeda       |              | X              |
| Valor limite de contribuição padrão (base) | Moeda       |              | X              |
| Período Padrão do Limite de Contribuição        | Conjunto de opções     |              | X              |
| Valor Padrão do Limite de Dedução           | Moeda       |              | X              |
| Valor limite de dedução padrão (base)    | Moeda       |              | X              |
| Período Padrão do Limite de Dedução           | Conjunto de opções     |              | X              |
| Descrição                              | Text           |              | X              |
| Taxa de Câmbio                            | Número decimal |              | X              |
| É a execução da folha de pagamento adicional                | Duas opções    |              | X              |
| Pode ser relatado em relação à Lei de Serviços de Saúde Acessíveis        | Duas opções    |              | X              |
| É gerada recuperação de atraso de pagamento                      | Duas opções    |              | X              |
| É montante bruto                              | Duas opções    |              | X              |
| É Principal                               | Duas opções    |              | X              |
| Nome                                     | Text           | X            | X              |
| Impacto da folha de pagamento                           | Conjunto de opções     |              | X              |
| Tipo de aposentadoria                          | Conjunto de opções     |              | X              |


**Entidade de emprego**

| **Campos**                     | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|--------------------------------|----------------|--------------|----------------|
| Data inicial do trabalhador ajustada     | Data e Hora  |              | X              |
| Empresa                        | Pesquisa         | X            | X              |
| Valor da unidade de aviso do empregador | Número decimal |              | X              |
| Unidade de aviso do trabalhador        | Conjunto de opções     |              | X              |
| Data final do emprego            | Data e Hora  |              | X              |
| Número de emprego              | Text           | X            | X              |
| Data de Início do Emprego          | Data e Hora  |              | X              |
| Última data de trabalho              | Data e Hora  |              | X              |
| Data da transição                | Data e Hora  |              | X              |
| Válido de                     | Data e Hora  | X            | X              |
| Válido até                       | Data e Hora  |              | X              |
| Trabalhador                         | Pesquisa         | X            | X              |
| Valor de aviso do trabalhador           | Número decimal |              | X              |
| Data inicial do trabalhador             | Data e Hora  |              | X              |
| Tipo de Trabalhador                    | Conjunto de opções     | X            | X              |
| Unidade de aviso do trabalhador          | Conjunto de opções     |              | X              |

## <a name="worker-entities"></a>Entidades do trabalhador

**Origem étnica**

| **Campos**         | **Tipo de dados** | **Necessário** | **Pesquisável** |
|--------------------|---------------|--------------|----------------|
| Descrição        | Text          |              | X              |
| Nome da origem étnica | Text          | X            | X              |


**Idioma**

| **Campos**    | **Tipo de dados** | **Necessário** | **Pesquisável** |
|---------------|---------------|--------------|----------------|
| Descrição   | Text          |              | X              |
| Nome do idioma | Text          | X            | X              |


**Situação militar**

| **Campos**           | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------|---------------|--------------|----------------|
| Descrição          | Text          |              | X              |
| É veterano protegido | Duas opções    |              | X              |
| Nome do idioma        | Text          | X            | X              |


**Trabalhador**

| **Campos**                | **Tipo de dados** | **Necessário** | **Pesquisável** |
|---------------------------|---------------|--------------|----------------|
| Data de nascimento                 | Somente Data     |              | X              |
| Descrição               | Text          |              | X              |
| Endereço de email 1           | Email         |              | X              |
| Endereço de email 2           | Email         |              | X              |
| Identidade do Facebook         | Text          |              | X              |
| Nome                | Text          |              | X              |
| Nome completo                 | Text          |              | X              |
| Sexo                    | Conjunto de opções    |              | X              |
| Geração                | Text          |              | X              |
| É permitido contato por email  | Duas opções   |              | X              |
| É permitido contato por telefone  | Duas opções   |              | X              |
| Sobrenome                 | Text          |              | X              |
| Identidade do LinkedIn         | Text          |              | X              |
| Gerente                   | Pesquisa        |              | X              |
| Nome do Meio               | Text          |              | X              |
| Telefone Celular              | Telefone         |              | X              |
| Identificador do Office Graph   | Text          |              | X              |
| Endereço de email principal     | Email         |              | X              |
| Telefone principal         | Telefone         |              | X              |
| Profissão                | Text          |              | X              |
| Rede social 1          | Conjunto de opções    |              | X              |
| Rede social 2          | Conjunto de opções    |              | X              |
| Identidade da Rede Social 1 | Text          |              | X              |
| Identidade da Rede Social 2 | Text          |              | X              |
| Fonte                    | Conjunto de opções    | X            | X              |
| Status                    | Conjunto de opções    | X            | X              |
| Telefone 1               | Telefone         |              | X              |
| Telefone 2               | Telefone         |              | X              |
| Telefone 3               | Telefone         |              | X              |
| Identidade do Twitter          | Text          |              | X              |
| Usuário                      | Pesquisa        |              | X              |
| URL do Site               | URL           |              | X              |
| Número de trabalhador             | Text          | X            | X              |
| Tipo de Trabalhador               | Conjunto de opções    | X            | X              |
| Nome de Yomi           | Text          |              | X              |
| Nome completo de Yomi            | Text          |              | X              |
| Sobrenome de Yomi            | Text          |              | X              |
| Nome do Meio de Yomi          | Text          |              | X              |


**Endereço do trabalhador**

| **Campos**           | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|----------------------|----------------|--------------|----------------|
| Número do endereço       | Text           | X            | X              |
| Tipo de Endereço         | Conjunto de opções     | X            | X              |
| Cidade                 | Text           |              | X              |
| País ou região    | Text           |              | X              |
| Região               | Text           |              | X              |
| Fax                  | Telefone          |              | X              |
| É Preferencial         | Duas opções    |              | X              |
| Latitude             | Número decimal |              | X              |
| Linha 1               | Text           |              | X              |
| Linha 2               | Text           |              | X              |
| Linha 3               | Text           |              | X              |
| Longitude            | Número decimal |              | X              |
| CEP          | Text           |              | X              |
| Caixa Postal      | Text           |              | X              |
| Código do método de remessa | Número inteiro   |              | X              |
| Estado ou Província    | Text           |              | X              |
| Telefone 1          | Telefone          |              | X              |
| Telefone 2          | Telefone          |              | X              |
| Telefone 3          | Telefone          |              | X              |
| Zona UPS             | Text           |              | X              |
| Compensação UTC           | Número inteiro   |              | X              |
| Trabalhador               | Pesquisa         | X            | X              |


**Informações pessoais do trabalhador**

| Campos                             | Tipo de dados    | Obrigatório | Pesquisável |
|------------------------------------|--------------|----------|------------|
| Cidade de Nascimento                         | Text         |          | X          |
| País ou região de nascimento            | Conjunto de opções   |          | X          |
| Data de nascimento                          | Somente Data    |          | X          |
| País ou região da nacionalidade      | Conjunto de opções   |          | X          |
| Data de falecimento                      | Somente Data    |          | X          |
| Data de verificação militar desativada | Somente Data    |          | X          |
| Formação                          | Text         |          | X          |
| Origem Étnica                     | Pesquisa       |          | X          |
| ExpatriateEndDate                  | Somente Data    |          | X          |
| ExpatriateStartDate                | Somente Data    |          | X          |
| País ou região de nascimento do pai     | Conjunto de opções   |          | X          |
| Sexo                             | Conjunto de opções   |          | X          |
| É Deficiente                        | Duas opções  |          | X          |
| É Veterano Deficiente                | Duas opções  |          | X          |
| A regra para exilados é aplicável    | Duas opções  |          | X          |
| É Aluno em período integral               | Duas opções  |          | X          |
| Estado civil                     | Conjunto de opções   |          | X          |
| Data de término do serviço militar          | Somente Data    |          | X          |
| Data de início do serviço militar        | Somente Data    |          | X          |
| País ou região de nascimento da mãe     | Conjunto de opções   |          | X          |
| País ou região de nacionalidade      | Conjunto de opções   |          | X          |
| Idioma nativo                    | Pesquisa       |          | X          |
| Número de dependentes               | Número inteiro |          |            |
| Situação Militar                     | Pesquisa       |          | X          |
| Trabalhador                             | Pesquisa       | X        | X          |
| Número de detalhe pessoal de trabalhador      | Text         | X        | X          |


**Conta bancária do trabalhador**

| **Campos**                 | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------------|---------------|--------------|----------------|
| Titular da conta             | Text          |              | X              |
| Identificação de conta     | Text          |              | X              |
| Descrição do Endereço        | Text          |              | X              |
| Tipo de conta bancária          | Conjunto de opções    |              | X              |
| Código de localização do banco         | Text          |              | X              |
| Nome da Filial                | Text          |              | X              |
| Número da Filial              | Text          |              | X              |
| Cidade                       | Text          |              | X              |
| País ou região          | Text          |              | X              |
| Região                     | Text          |              | X              |
| Descrição                | Text          |              | X              |
| Nome do bairro              | Text          |              | X              |
| Email                      | Text          |              | X              |
| Ramal                  | Text          |              | X              |
| Fax                        | Text          |              | X              |
| IBAN                       | Text          |              | X              |
| Linha 1                     | Text          |              | X              |
| Linha 2                     | Text          |              | X              |
| Linha 3                     | Text          |              | X              |
| Telefone Celular               | Text          |              | X              |
| Nome da pessoa             | Text          |              | X              |
| CEP                | Text          |              | X              |
| Caixa Postal            | Text          |              |                |
| Número identificador do banco             | Text          |              | X              |
| Tipo de número do banco        | Conjunto de opções    |              | X              |
| Estado ou Província          | Text          |              | X              |
| Código SWIFT                 | Text          |              | X              |
| Telefone                  | Text          |              | X              |
| Número de telex               | Text          |              | X              |
| URL do Site                | Text          |              | X              |
| Trabalhador                     | Pesquisa        | X            | X              |
| Número da conta bancária do trabalhador | Text          |              | X              |
| Número da conta bancária do trabalhador | Text          | X            | X              |

**Remuneração fixa do trabalhador**

| Campos                                | Tipo de dados      | Obrigatório | Pesquisável |
|---------------------------------------|----------------|----------|------------|
| Empresa                               | Pesquisa         | X        | X          |
| Tipo de Remuneração                     | Conjunto de opções     |          | X          |
| Moeda                              | Pesquisa         |          | X          |
| Data de Efetivação                        | Somente Data      |          | X          |
| Evento                                 | Pesquisa         | X        | X          |
| Taxa de Câmbio                         | Número decimal |          | X          |
| Data de Vencimento                       | Somente Data      |          | X          |
| Número da Linha                           | Número decimal |          | X          |
| Frequência de Pagamento                         | Pesquisa         | X        | X          |
| Taxa de pagamento                              | Moeda       |          | X          |
| Taxa de pagamento (base)                       | Moeda       |          | X          |
| Plano                                  | Pesquisa         | X        | X          |
| Cargo                              | Pesquisa         | X        | X          |
| Tipo de Processo                          | Conjunto de opções     | X        | X          |
| Linha da Configuração do Ponto de Referência            | Pesquisa         |          | X          |
| Trabalhador                                | Pesquisa         | X        | X          |
| Número de remuneração fixa do trabalhador      | Text           | X        | X          |

**Número de identificação do trabalhador**

| Campos                 | Tipo de dados   | Obrigatório | Pesquisável |
|------------------------|-------------|----------|------------|
| Descrição            | Text        |          | X          |
| Tipo de entrada             | Text        |          | X          |
| Data de Vencimento        | Somente Data   |          | X          |
| Número de Identificação  | Text        | X        | X          |
| Tipo de identificação    | Pesquisa      | X        | X          |
| É Principal             | Duas opções |          | X          |
| Data da emissão             | Somente Data   |          | X          |
| Agência emissora         | Pesquisa      | X        | X          |
| Trabalhador                 | Pesquisa      | X        | X          |


## <a name="position-entities"></a>Entidades de posição

**Posição de trabalho**

| **Campos**               | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|--------------------------|----------------|--------------|----------------|
| Ativação               | Data e Hora  |              | X              |
| Disponível para Atribuição | Data e Hora  |              | X              |
| Departamento               | Pesquisa         |              | X              |
| Descrição              | Text           |              | X              |
| Equivalente ao horário integral     | Número decimal |              | X              |
| Cargo                      | Pesquisa         | X            | X              |
| Número do cargo      | Text           | X            | X              |
| Cargo do pai      | Pesquisa         |              | X              |
| Tipo de Posição            | Pesquisa         |              | X              |
| Aposentadoria               | Data e Hora  |              | X              |
| Cargo                    | Conjunto de opções     |              | X              |
| Válido de               | Data e Hora  | X            | X              |
| Válido até                 | Data e Hora  |              | X              |


**Tipo de posição**

| **Campos**         | **Tipo de dados** | **Necessário** | **Pesquisável** |
|--------------------|---------------|--------------|----------------|
| Classificação     | Conjunto de opções    |              | X              |
| Descrição        | Text          |              | X              |
| Nome do tipo de posição | Text          | X            | X              |


**Atribuição do trabalhador da posição**

| **Campos**                        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------------------------|---------------|--------------|----------------|
| Posição de Trabalho                      | Pesquisa        | X            | X              |
| Número do cargo de atribuição do trabalhador | Text          | X            | X              |
| Válido de                        | Text          | X            | X              |
| Válido até                          |               |              | X              |
| Trabalhador                            |               | X            | X              |

## <a name="job-entities"></a>Entidades de trabalho

**Trabalho**

| **Campos**                   | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|------------------------------|----------------|--------------|----------------|
| Permitir posições ilimitadas    | Duas opções    |              | X              |
| Equivalente ao horário integral padrão | Número decimal |              | X              |
| Descrição                  | Text           |              | X              |
| Descrição do trabalho              | Text           |              | X              |
| Função de Trabalho                 | Pesquisa         |              | X              |
| Tipo de Trabalho                     | Pesquisa         |              | X              |
| Número máximo de posições  | Número inteiro   |              | X              |
| Nome                         | Text           | X            | X              |
| Cargo                        | Conjunto de opções     |              | X              |
| Válido de                   | Data e Hora  | X            | X              |
| Válido até                     | Data e Hora  |              | X              |


**Função de trabalho**

| **Campos**        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------|---------------|--------------|----------------|
| Descrição       | Text          | X            | X              |
| Nome do cargo | Text          | X            | X              |


**Tipo de trabalho**

| **Campos**    | **Tipo de dados** | **Necessário** | **Pesquisável** |
|---------------|---------------|--------------|----------------|
| Descrição   | Text          | X            | X              |
| Status de isenção | Conjunto de opções    | X            | X              |
| Nome do tipo de trabalho | Text          | X            | X              |

## <a name="leave-and-absence-entities"></a>Entidades de licença e ausência

**Registro da licença**

| **Campos**            | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------------|---------------|--------------|----------------|
| Data base da competência    | Somente Data     | X            | X              |
| Data inicial da competência    | Somente Data     | X            | X              |
| Data personalizada           | Somente Data     | X            | X              |
| A competência está suspensa  | Duas opções   |              | X              |
| LeaveEnrollmentNumber | Text          | X            | X              |
| Plano de Licença            | Pesquisa        | X            | X              |
| Data Inicial            | Somente Data     | X            | X              |
| Base da camada            | Conjunto de opções    | X            | X              |
| Trabalhador                | Pesquisa        | X            | X              |


**Transação bancária da licença**

| **Campos**                    | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|-------------------------------|----------------|--------------|----------------|
| Valor                        | Número decimal | X            | X              |
| Empresa                       | Pesquisa         | X            | X              |
| Número da transação bancária de licença | Text           | X            | X              |
| Plano de Licença                    | Pesquisa         |              | X              |
| Tipo de Licença                    | Pesquisa         | X            | X              |
| Data do Lançamento              | Somente Data      | X            | X              |
| Número da Transação            | Número decimal | X            | X              |
| Tipo de Transação              | Conjunto de opções     | X            | X              |
| Trabalhador                        | Pesquisa         | X            | X              |


**Plano de licença**

| **Campos**        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------|---------------|--------------|----------------|
| Frequência da Competência | Conjunto de opções    | X            | X              |
| Empresa           | Pesquisa        | X            | X              |
| Descrição       | Text          |              | X              |
| Tipo de Licença        | Pesquisa        | X            | X              |
| Nome              | Text          | X            | X              |
| Data Inicial        | Somente Data     | X            | X              |


**Solicitação de licença**

| **Campos**           | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------|---------------|--------------|----------------|
| Comentário              | Text          | X            | X              |
| Empresa              | Pesquisa        | X            | X              |
| Número da solicitação de licença | Text          |              | X              |
| Data de Solicitação         | Data e Hora | X            | X              |
| Status               | Conjunto de opções    | X            | X              |
| Trabalhador               | Pesquisa        | X            | X              |


**Detalhe da solicitação da licença**

| **Campos**                  | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|-----------------------------|----------------|--------------|----------------|
| Valor                      | Número decimal | X            | X              |
| Data da Licença                  | Data e Hora  | X            | X              |
| Solicitação de Licença               | Pesquisa         | X            | X              |
| Número do Detalhe da Solicitação de Licença | Text           | X            | X              |
| Tipo de Licença                  | Pesquisa         | X            | X              |


**Tipo de licença**

| **Campos**      | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------|---------------|--------------|----------------|
| Empresa         | Pesquisa        | X            | X              |
| Descrição     | Text          |              | X              |
| Código de Ganhos    | Pesquisa        |              | X              |
| Nome do Tipo de Licença | Text          | X            | X              |


**Calendário de trabalho**

| **Campos**  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------|---------------|--------------|----------------|
| Empresa     | Pesquisa        | X            | X              |
| Descrição | Text          |              | X              |
| Nome        | Text          | X            | X              |


**Dia do calendário de trabalho**

| **Campos**               | **Tipo de dados** | **Necessário** | **Pesquisável** |
|--------------------------|---------------|--------------|----------------|
| Data do Calendário            | Somente Data     | X            | X              |
| Empresa                  | Pesquisa        |              | X              |
| Status                   | Text          |              | X              |
| Calendário de Trabalho            | Pesquisa        | X            | X              |
| Número do Dia do Calendário de Trabalho | Text          | X            | X              |


**Feriado do calendário de trabalho**

| **Campos**  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------|---------------|--------------|----------------|
| Nome        | Text          |              | X              |
| Descrição | Text          | X            | X              |


**Linha de feriados do calendário de trabalho**

| **Campos**                        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------------------------|---------------|--------------|----------------|
| Data do Feriado                      | Somente Data     | X            | X              |
| Nome                              | Text          |              | X              |
| Feriado do Calendário de Trabalho             | Pesquisa        | X            | X              |
| Número da Linha de Feriados do Calendário de Trabalho | Text          | X            | X              |


**Intervalo do calendário de trabalho**

| **Campos**                         | **Tipo de dados** | **Necessário** | **Pesquisável** |
|------------------------------------|---------------|--------------|----------------|
| Empresa                            | Pesquisa        |              | X              |
| Hora Final                           | Número inteiro  |              | X              |
| Hora de Início                         | Número inteiro  |              | X              |
| Calendário de Trabalho                      | Pesquisa        | X            | X              |
| Dia do Calendário de Trabalho                  | Pesquisa        | X            | X              |
| Número do Intervalo do Calendário de Trabalho | Text          | X            | X              |

## <a name="organization-entities"></a>Entidades da organização

**Empresa**

| **Campos**   | **Tipo de dados** | **Necessário** | **Pesquisável** |
|--------------|---------------|--------------|----------------|
| Código de empresa | Text          | X            | X              |
| Nome         | Text          | X            | X              |


**Departamento**

| **Campos**        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------|---------------|--------------|----------------|
| Número do Departamento | Text          | X            | X              |
| Descrição       | Text          |              | X              |
| Nome              | Text          | X            | X              |
| Departamento Principal | Pesquisa        |              | X              |


**Moeda**

| **Campos**         | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|--------------------|----------------|--------------|----------------|
| Código de Moeda      | Text           | X            | X              |
| Nome da Moeda      | Text           | X            | X              |
| Precisão da Moeda | Número Inteiro   | X            | X              |
| Símbolo da Moeda    | Text           | X            | X              |
| Imagem da Entidade       | Imagem          |              |                |
| Taxa de Câmbio      | Número Decimal | X            | X              |
| Organização       | Pesquisa         | X            | X              |
| Status             | Conjunto de Opções     |              | X              |

## <a name="payroll-entities"></a>Folha de pagamento das entidades

**Ciclo de pagamento**

| **Campos**  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------|---------------|--------------|----------------|
| Descrição | Text          | X            | X              |
| Frequência   | Conjunto de Opções    | X            | X              |
| Nome        | Text          | X            | X              |


**Período de pagamento**

| **Campos**           | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------|---------------|--------------|----------------|
| Data de Pagamento Padrão | Somente Data     |              | X              |
| Descrição          | Text          |              | X              |
| Ciclo de Pagamento            | Verifique          | X            | X              |
| Número do Período de Pagamento    | Text          | X            | X              |
| Data de Término do Período      | Somente Data     | X            | X              |
| Data de Início do Período    | Somente Data     | X            | X              |
| Status               | Conjunto de Opções    |              | X              |


**Código de ganho de folha de pagamento**

| **Campos**              | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------------|---------------|--------------|----------------|
| Descrição             | Text          | X            | X              |
| Incluir no Tipo de Pagamento | Conjunto de Opções    | X            | X              |
| É Produtivo           | Duas Opções   | X            | X              |
| Nome                    | Text          |              | X              |
| Unidade da Quantidade           | Conjunto de Opções    |              | X              |
| Controlar Horas de FMLA        | Duas Opções   |              | X              |


**Região fiscal**

| **Campos**        | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------|---------------|--------------|----------------|
| Cidade              | Text          |              | X              |
| País ou Região | Text          |              | X              |
| Região            | Text          |              | X              |
| Nome              | Text          | X            | X              |
| Estado ou Província | Text          |              | X              |


**Período de pagamento da frequência de cálculo de benefícios**

| **Campos**                                      | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-------------------------------------------------|---------------|--------------|----------------|
| Frequência de Cálculo do Benefício                   | Pesquisa        | X            | X              |
| Número do Período de Pagamento da Frequência de Cálculo de Benefícios | Text          | X            | X              |
| Período de Pagamento                                      | Pesquisa        | X            | X              |


**Desembolso de conta bancária**

| **Campos**                       | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|----------------------------------|----------------|--------------|----------------|
| Valor                           | Moeda       |              | X              |
| Valor (Base)                    | Moeda       |              | X              |
| Conta Bancária                     | Pesquisa         | X            | X              |
| Número do Desembolso de Conta Bancária | Text           | X            | X              |
| Empresa                          | Pesquisa         | X            | X              |
| Moeda                         | Pesquisa         |              | X              |
| Taxa de Câmbio                    | Número Decimal |              | X              |
| É Pendência                     | Duas Opções    |              | X              |
| Prioridade                         | Número Inteiro   |              | X              |

**Agência emissora da identificação da pessoa**

| **Campos**           | **Tipo de dados** | **Necessário** | **Pesquisável** |
|----------------------|---------------|--------------|----------------|
| Descrição do Endereço  | Text          |              | X              |
| Linha de endereço 1       | Text          |              | X              |
| Linha de endereço 2       | Text          |              | X              |
| Linha de endereço 3       | Text          |              | X              |
| Cidade                 | Text          |              | X              |
| País ou Região    | Conjunto de Opções    |              | X              |
| Região               | Text          |              | X              |
| Descrição          | Text          |              | X              |
| Email                | Text          |              | X              |
| Ramal            | Text          |              | X              |
| Fax                  | Text          |              | X              |
| Nome da Agência Emissora  | Text          | X            | X              |
| Telefone Celular         | Text          |              | X              |
| Página                 | Text          |              | X              |
| CEP          | Text          |              | X              |
| Caixa Postal      | Text          |              | X              |
| SMS                  | Text          |              | X              |
| Estado ou Província    | Text          |              | X              |
| Telefone            | Text          |              | X              |
| Telex                | Text          |              | X              |
| URL do Site          | Text          |              | X              |

**Tipo de identificação do trabalhador**

| **Campos**                        | **Tipo de dados**  | **Necessário** | **Pesquisável** |
|-----------------------------------|----------------|--------------|----------------|
| Valores Permitidos                    | Conjunto de Opções     |              | X              |
| País ou Região                 | Text           |              | X              |
| Descrição                       | Text           |              | X              |
| Tamanho Fixo                      | Número Inteiro   |              | X              |
| Formato do Número de Identificação      | Text           |              | X              |
| Tipo                              | Conjunto de Opções     |              | X              |
| Tipo de Identificação do Trabalhador | Text           | X            | X              |

## <a name="fixed-compensation-entities"></a>Entidades de remuneração fixa

**Plano de remuneração fixa**

| **Campos**                  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------------------|---------------|--------------|----------------|
| Empresa                     | Pesquisa        | X            | X              |
| Grade de Remuneração           | Pesquisa        |              | X              |
| Moeda                    | Pesquisa        | X            | X              |
| Descrição                 | Text          | X            | X              |
| Data de Efetivação              | Somente Data     | X            | X              |
| Data de Vencimento             | Somente Data     | X            | X              |
| Regra de Contratação                   | Conjunto de Opções    | X            | X              |
| Nome                        | Text          | X            | X              |
| Tolerância Fora do Intervalo      | Conjunto de Opções    | X            | X              |
| Frequência de Pagamento               | Pesquisa        | X            | X              |
| Recomendação Permitida      | Duas Opções   | X            | X              |
| Configuração de Linha de Ponto de Referência  | Pesquisa        |              | X              |
| Tipo                        | Conjunto de Opções    | X            | X              |

**Grade de remuneração**

| **Campos**                  | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------------------|---------------|--------------|----------------|
| Empresa                     | Pesquisa        | X            | X              |
| Moeda                    | Pesquisa        |              | X              |
| Descrição                 | Text          | X            | X              |
| Data de Efetivação              | Somente Data     |              | X              |
| Data de Vencimento             | Somente Data     |              | X              |
| Nome                        | Text          | X            | X              |
| Configuração do Ponto de Referência       | Pesquisa        | X            | X              |
| Tipo                        | Conjunto de Opções    | X            | X              |

**Nível salarial**

| **Campos**      | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------|---------------|--------------|----------------|
| Descrição     | Text          |              | X              |
| Nome            | Text          | X            | X              |
| Tipo            | Conjunto de Opções     | X            | X              |

**Frequência de pagamento de remuneração**

| **Campos**                  | **Tipo de dados**   | **Necessário** | **Pesquisável** |
|-----------------------------|-----------------|--------------|----------------|
| Fator de Conversão Anual    | Número Decimal  |              | X              |
| Empresa                     | Pesquisa          | X            | X              |
| Descrição                 | Text            |              | X              |
| Fator de Conversão por Hora    | Número Decimal  |              | X              |
| Fator de Conversão Mensal   | Número Decimal  |              | X              |
| Nome                        | Text            | X            | X              |
| Período                      | Conjunto de Opções      |              | X              |
| Fator de Conversão Semanal    | Conjunto de Opções      |              | X              |


**Configuração do ponto de referência de compensação**

| **Campos**          | **Tipo de dados**   | **Necessário** | **Pesquisável** |
|---------------------|-----------------|--------------|----------------|
| Empresa             | Pesquisa          | X            | X              |
| Tipo de Remuneração   | Conjunto de Opções      | X            | X              |
| Descrição         | Text            | X            | X              |
| Nome                | Text            | X            | X              |

**Linha da configuração de ponto de referência de remuneração**

| **Campos**            | **Tipo de dados**   | **Necessário** | **Pesquisável** |
|-----------------------|-----------------|--------------|----------------|
| Empresa               | Pesquisa          | X            | X              |
| Descrição           | Text            | X            | X              |
| Número da Linha           | Número Decimal  | X            | X              |
| Nome                  | Text            | X            | X              |
| Configuração do Ponto de Referência | Pesquisa          | X            | X              |

**Região de remuneração**

| **Campos**      | **Tipo de dados** | **Necessário** | **Pesquisável** |
|-----------------|---------------|--------------|----------------|
| Descrição     | Text          | X            | X              |
| Nome            | Text          | X            | X              |

**Estrutura de remuneração**

| **Campos**                    | **Tipo de dados**   | **Necessário** | **Pesquisável** |
|-------------------------------|---------------  |--------------|----------------|
| Valor                        | Moeda        |              | X              |
| Base do Valor                   | Moeda        |              | X              |
| Empresa                       | Pesquisa          | X            | X              |
| Número da Estrutura de Remuneração | Text            | X            | X              |
| Moeda                      | Pesquisa          |              | X              |
| Taxa de Câmbio                 | Número Decimal  |              | X              |
| Grade                          | Pesquisa          | X            | X              |
| Nível                         | Pesquisa          | X            | X              |
| Ponto de Referência               | Pesquisa          | X            | X              |
| Configuração de Linha de Ponto de Referência    | Pesquisa          | X            | X              |

**Evento de compensação fixa**

| **Campos**            | **Tipo de dados**   | **Necessário** | **Pesquisável** |
|-----------------------|-----------------|--------------|----------------|
| Empresa               | Pesquisa          | X            | X              |
| Descrição           | Text            | X            | X              |
| Tipo de Evento            | Conjunto de Opções      | X            | X              |
| Está Ativo             | Duas Opções     | X            |                |
| Nome                  | Text            | X            | X              |

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
