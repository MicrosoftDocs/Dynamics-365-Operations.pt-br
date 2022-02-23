---
title: Criar um plano de licença e ausência
description: Crie planos de licença no Dynamics 365 Human Resources para diferentes tipos de licença.
author: andreabichsel
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb42860292c5e3e654917cf2f62b525993aa795a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417335"
---
# <a name="create-a-leave-and-absence-plan"></a>Criar um plano de licença e ausência

Defina os planos de licença e ausência no Dynamics 365 Human Resources para cada tipo de licença oferecida. Os planos de licença e ausência podem ser acumulados em frequências diferentes, como anual, mensal ou quinzenal. Você também pode definir um plano como uma concessão, em que um único acúmulo ocorra em uma data específica. Por exemplo, você pode criar um plano que conceda feriados flutuantes anuais.

Os planos de licenças hierárquicas permitem que os funcionários recebam benefícios com base na quantidade de tempo gastas com uma organização. Os planos em camadas permitem o registro automático em horas de benefícios adicionais.

Você pode especificar os valores máximos ou saldos mínimos para garantir que os funcionários usem somente as horas de benefício acumuladas.

Por exemplo, com um plano em camadas, você pode conceder um benefício de 80 horas de folga remunerada (PTO) a novos funcionários. Em seguida, você poderá conceder 120 horas de 60 meses de serviço.

Você também pode criar benefícios de licença baseada em posição, como horas de benefícios apenas executivos.

## <a name="create-a-leave-plan"></a>Criar um plano de licença

1. Na página **Licença e ausência**, selecione **Criar novo plano**.

2. Em **detalhes**, digite o **Nome**, a **Data de início**, a **Descrição** e o **Tipo de licença** para seu plano.

Se o recurso **Configurar vários tipos de licença** para um único plano de licença e ausência estiver habilitado, os tipos de licença serão configurados em **Agenda de acúmulo** em vez de em **Detalhes**. Para cada registro na tabela de agenda de competência, você pode definir um tipo de licença. Além disso, ao habilitar esse recurso, você precisará usar novas entidades de dados para integrações ou outros cenários nos quais precisa usar entidades. 

As novas entidades são:

- V2 da transação bancária de licença e ausência
- V2 da registro para licença e ausência
- V2 da camada do plano de licença e ausência
- V2 do plano de licença e ausência
- Solicitação de folga V2

 > [!IMPORTANT]
   > Após ativar esse recurso, você não poderá desativá-lo.

3. Defina competências na guia **Competências**. As competências determinam quando e com que frequência um funcionário recebe folgas. Nesta etapa, você define as políticas sobre quando as competências devem ser concedidas e as políticas sobre os benefícios da licença de rateio.

   1. Selecione um valor na caixa suspensa **Frequência das competências**:

      - Diário
      - Semanalmente
      - Quinzenal
      - Quinzenal
      - Mensalmente
      - Trimestral
      - Semestral
      - Anualmente
      - Nenhuma

   2. Selecione uma opção na caixa suspensa **Base do período de competência** para determinar a data inicial usada para calcular períodos de competência:

      | Base do período de competência | Descrição |
      | --- | --- |
      | **Data inicial do plano** | A data inicial do período de competência é a data em que o plano está disponível. |
      | **Data específica do funcionário** | A data de início do período de competência depende de um evento de funcionário:</br><ul><li>Personalizado (você deve especificar uma base de data de competência para cada registro individual)</li><li>Data do aniversário de tempo de serviço</li><li>Data original da contratação</li><li>Aniversário de tempo de serviço</li><li>Data inicial ajustada do trabalhador</li><li>Data inicial do trabalhador</li></ul> |

   3. Selecione uma opção na caixa suspensa **Data de concessão da competência**:

      - **Data do término do período de competência** – é concedida folga ao funcionário no último dia do período de concessão. Para calcular o valor correto, o processo da competências deve incluir o período inteiro. Por exemplo, se o período de acumulação for 1º de janeiro de 2020 a 31 de janeiro de 2020, você deverá executar a acumulação para 1º de fevereiro de 2020 para incluir Janeiro.

      - **Data de início do período de competência** – é concedida ao funcionário folga no primeiro dia do período de concessão.

   4. Selecione uma opção na caixa suspensa **Política de competência no registro**: Esse valor define como calcular a acumulação quando um funcionário se registra no meio de um período de acumulação.

      - **Proporcional** – O intervalo de datas entre a data de registro e a data de início é usado para determinar a diferença em dias. Essa diferença será aplicada quando as competências são processadas.

      - **Competência total** – O valor total da competência, com base na faixa, é concedido no primeiro processamento da competência.

      - **Nenhuma competência** – Nenhuma competência será concedida até o próximo período de competência.

   5. Selecione uma opção na caixa suspensa **Política de competência no cancelamento do registro**. Esse valor define como calcular a acumulação quando um funcionário cancela o registro no meio de um período de acumulação.

      - **Proporcional** – O intervalo de datas entre a data de registro e a data de início é usado para determinar a diferença em dias. Essa diferença será aplicada quando as competências são processadas.

      - **Competência total** – O valor total da competência, com base na faixa, é concedido no primeiro processamento da competência.

      - **Nenhuma competência** – Nenhuma competência será concedida até o próximo período de competência.

4. Defina a agenda de competência na guia **Agenda de competência**. A agenda de competência determina:

   - Como um funcionário acumula folga
   - Quais valores serão acumulados pelo funcionário
   - Quais valores serão mantidos

   Você pode criar camadas para conceder folgas com base em níveis diferentes.

   Caso tenha funcionários por hora, poderá conceder folga com base nas horas trabalhadas, e não no tempo de serviço na organização. Os dados de horas trabalhadas geralmente são armazenados em um sistema de horário e presença. É possível importar horas normais e hora extras trabalhadas do sistema de tempo e presença e usá-las como base para o prêmio de um funcionário.
   
    1. Selecione uma opção na caixa suspensa **Tipo de competência**:

      - **Meses de serviço** - baseie a agenda de competência em meses de serviço.

      - **Horas trabalhadas** - base da agenda de competência das horas trabalhadas. Para obter mais informações sobre competências de horas trabalhadas, consulte [Acumular folgas com base nas horas trabalhadas](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Para obter mais informações sobre a competência de benefícios, consulte [Acumular folgas com base nas horas trabalhadas](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Insira os valores na tabela de agenda de competência:

      - **Meses de serviço** - o número mínimo de meses que os funcionários devem trabalhar para serem qualificados para acúmulo de folgas. Se você não exigir um mínimo, defina o valor como 0.

      - **Horas trabalhadas** o número mínimo de horas que os funcionários devem trabalhar por período de competência para terem direito ao acúmulo de folgas. Se você não exigir um mínimo, defina o valor como 0.

      - **Valor acumulado** - O número de horas ou dias que os funcionários acumulam por período. O período se baseia na frequência de acumulação.

      - **Saldo mínimo** - Será possível usar um valor negativo para o saldo mínimo se os funcionários puderem solicitar mais licenças do que as disponíveis.

      - **Postergação máxima** - o processo de competência ajusta saldos de licença que excedem o saldo máximo de postergação no aniversário da data de início.

      - **Valor concedido** - é o número inicial de horas ou dias que é concedido aos funcionários quando se registram no plano de licença. O valor não é acumulado no cada período de competência.
      
Se o recurso **Configurar vários tipos de licença para um único plano de licença e ausência** estiver habilitado, selecione uma opção no **Tipo de licença**. 

   > [!IMPORTANT]
   > Após ativar esse recurso, você não poderá desativá-lo.

Se o recurso **Usar equivalência a período integral** estiver habilitado, os Human Resources usarão a equivalência por tempo integral (FTE) definida para a posição para ratear a competência de um funcionário. Por exemplo, se a FTE for 0,5 e o valor acumulado for 10, o funcionário acumulará 5. Você só poderá usar esse recurso se habilitar vários tipos de licença.  

5. Selecione **Salvar**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Acumular folgas com base nas horas trabalhadas

Caso tenha funcionários por hora, poderá conceder folga com base nas horas trabalhadas, e não no tempo de serviço na organização. Os dados de horas trabalhadas geralmente são armazenados em um sistema de horário e presença. É possível importar horas normais e hora extras trabalhadas do seu sistema de tempo e presença e usá-lo como base para o prêmio de um funcionário.

Ao selecionar horas trabalhadas como o tipo de competência, você pode usar dois tipos de horas para a competência: normal e hora extra. O processamento da acumulação dos planos de horas trabalhadas usa a frequência de acumulação, junto com a base do período de acumulação para determinar as horas a serem acumuladas.

### <a name="annual-accrual-frequency"></a>Frequência de acumulação anual

| Data de premiação de acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>A frequência de acumulação mensal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 8/1/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 8/1/2018-31/8/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>A frequência de acumulação quinzenal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 8/16/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 8/16/2018-31/8/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>A frequência de acumulação semanal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 8/27/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 8/27/2018-31/8/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Planos de licença atribuídos ao funcionário

Nos planos de licença atribuídos ao funcionário, a base da camada e o tipo de horas exibidos para os planos de horas trabalhadas. As horas trabalhadas reais para os períodos de acumulação a partir da data atual também são exibidas para planos ativos.

### <a name="loading-data"></a>Carregando dados

Você pode importar horas reais usando a entidade **Horas de licença e de ausência trabalhadas** no gerenciamento de dados. Se utilizar calendários de horário de trabalho, a importação validará as horas normais trabalhadas que não excedam as horas programadas em um dia definido pelo calendário. A importação também valida as horas trabalhadas por determinado dia, não excedendo 24 horas. 

Você precisa das seguintes informações para importar as horas reais a serem usadas no processo de acúmulo de licença:

- Número da equipe 
- Data de trabalho
- Tipo
- Horas

Uma única data só pode ter um de cada tipo associado a ela.

| Número da equipe       | Data de trabalho           | Tipo                  | Horas                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Regular (início no primeiro dia do ano)               | 8                    |       
| 000337                | 8/7/2018             | Regular (início no primeiro dia do ano)               | 8                    |
| 000337                | 8/7/2018             | Hora extra              | 3                    |
| 000337                | 8/8/2018             | Regular (início no primeiro dia do ano)               | 8                    |
| 000337                | 8/7/2018             | Regular (início no primeiro dia do ano)               | 8                    |
| 000337                | 8/9/2018             | Regular (início no primeiro dia do ano)               | 8                    |

## <a name="enrollments-and-balances"></a>Registros e saldos

### <a name="enrollment-date"></a>Data da registro

A data do registro determina quando um funcionário pode iniciar o acúmulo de folgas. Por exemplo, se um funcionário tiver se registrado em um plano de férias no 15 de junho de 2018, ela não pode acumular folgas antes do dia 15 de junho de 2018.

### <a name="current-balance"></a>Saldo atual

O saldo atual é o valor da licença disponível para as solicitações de folga. Esse valor inclui competências, solicitações aprovadas e ajustes até a data atual.

### <a name="current-balance-examples"></a>Exemplos de saldo atual

#### <a name="annual-plan"></a>Plano anual

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Data inicial do plano      | Término do período de competência |

As competências são processadas em 1º de janeiro de 2019 (1/1/2019) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Valor solicitado | Saldo atual (em 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

O saldo atual (160) = o valor acumulado (200) – o valor solicitado (40)

#### <a name="semimonthly-plan"></a>Plano de duas vezes por mês

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/2/2018        | Quinzenal       | Data inicial do plano      | Término do período de competência |

As competências são processadas em 1º de maio de 2018 (1/5/2018) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Valor solicitado | Saldo atual (em 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

O saldo atual (22) = o valor acumulado (5 × 6) – o valor solicitado (8)

#### <a name="monthly-plan"></a>Plano mensal

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/2/2018        | Quinzenal       | Data inicial do plano      | Término do período de competência |

As competências são processadas em 1º de maio de 2018 (1/5/2018) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Valor solicitado | Saldo atual (em 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

O saldo atual (7) = o valor acumulado (5 × 3) – o valor solicitado (8)

### <a name="forecasted-balance"></a>Saldo previsto

O *saldo previsto* é o valor da licença disponível em uma data futura. As competências e os ajustes de postergação são previstos até essa data.

Os recursos humanos usam a seguinte fórmula:

Saldo previsto na segunda-feira = saldo atual – solicitações + competências – ajuste de postergação

### <a name="forecasted-balance-examples"></a>Exemplos de saldo previsto

#### <a name="annual-plan"></a>Plano anual

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Data inicial do plano      | Término do período de competência |

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Saldo atual | Saldo previsto (em 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Saldo previsto (40) = valor da competência (20) + saldo atual (40) – ajuste de postergação (20)

#### <a name="semimonthly-plan"></a>Plano de duas vezes por mês

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/2/2018        | Quinzenal       | Data inicial do plano      | Término do período de competência |

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Saldo atual | Saldo previsto (em 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Saldo previsto (35) = valor da competência (5 × 3) + saldo atual (40) – ajuste de postergação (20)

#### <a name="monthly-plan"></a>Plano mensal

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/2/2018        | Quinzenal       | Data inicial do plano      | Término do período de competência |

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019) para incluir o período inteiro.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Saldo atual | Saldo previsto (em 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Saldo previsto (30) = valor da competência (10 × 1) + saldo atual (40) – ajuste de postergação (20)

### <a name="proration-balance-examples"></a>Exemplos do saldo proporcional

#### <a name="prorated-monthly-plan"></a>Plano mensal proporcional

**Configuração do plano**

| Data inicial do plano | Frequência das competências | Base do período de competência |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensalmente           | Data inicial do plano      |

**Resultados**

| Funcionário            | Meses de serviço | Data do registro | Data inicial | Valor da competência | Acúmulo processado | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 1/6/2018        | 1/6/2018   | 1.00           | 1/9/2018        | 3,00    |
| Jay Norman          | 0,00              | 15/6/2018       | 15/6/2018  | 1.00           | 1/9/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Plano mensal da competência completa

**Configuração do plano**

| Data inicial do plano | Frequência das competências | Base do período de competência |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensalmente           | Data inicial do plano      |

**Resultados**

| Funcionário            | Meses de serviço | Data do registro | Data inicial | Valor da competência | Acúmulo processado | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 1/6/2018        | 1/6/2018   | 1.00           | 1/9/2018        | 3,00    |
| Jay Norman          | 0,00              | 15/6/2018       | 15/6/2018  | 1.00           | 1/9/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Sem plano mensal da competência

**Configuração do plano**

| Data inicial do plano | Frequência das competências | Base do período de competência |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensalmente           | Data inicial do plano      |

**Resultados**

| Funcionário            | Meses de serviço | Data do registro | Data inicial | Valor da competência | Acúmulo processado | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 1/6/2018        | 1/6/2018   | 1.00           | 1/9/2018        | 3.00    |
| Jay Norman          | 0,00              | 15/6/2018       | 15/6/2018  | 1.00           | 1/9/2018        | 2.00    |

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)
- [Acumular planos de licença e ausência](hr-leave-and-absence-accrue.md)
