---
title: "Conceitos de licença e ausência"
description: "Este tópico descreve os conceitos de licença e ausência e como os saldos de folgas são determinados."
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: pt-br
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a>Conceitos de licença e ausência

[!include[banner](../includes/banner.md)]

Os conceitos e termos descritos neste tópico podem ajudá-lo a determinar quando um funcionário pode ter folgas e como são calculados os saldos de tempo desse funcionário. Para obter mais informações sobre o gerenciamento de licenças e ausências, consulte [Gerenciamento de licenças e ausências](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Detalhes do plano de ausência

### <a name="start-date"></a>Data inicial

A data inicial é a data em que o processamento da competência começa. A data de início também serve como a data de aniversário usada para calcular valores postergados.

## <a name="accruals"></a>Competências

As competências determinam quando e com que frequência um funcionário tem direito a folgas. As políticas sobre quando as competências devem ser concedidas e a sobre a proporcionalidade são definidas na seção **Competências** durante configuração o plano de licença e ausência.

### <a name="accrual-frequency"></a>Frequência das competências

A frequência das competências define a frequência de folgas acumuladas ou concedidas. As opções a seguir estão disponíveis:

- Diariamente
- Semanalmente
- Quinzenalmente
- Duas vezes por mês
- Mensalmente
- Trimestralmente
- Duas vezes por ano
- Anualmente
- Nenhuma

### <a name="accrual-period-basis"></a>Base do período de competência

A base do período de competência determina a data que é usada para calcular os períodos de competência As opções a seguir estão disponíveis:

- **Data inicial do plano**
- **Data específica do funcionário** – quando essa opção for selecionada, o valor determinará a origem do valor da data inicial que é usado para calcular os períodos de competência. As opções a seguir estão disponíveis:

    - Personalizado
    - Data do aniversário de tempo de serviço
    - Data original de contratação
    - Aniversário de tempo de serviço
    - Data inicial ajustada do trabalhador
    - Data inicial do trabalhador

### <a name="accrual-award-date"></a>Data de concessão da competência

A data de concessão da competência determina quando um funcionário tem direito a folgas. As opções a seguir estão disponíveis:

- **Data do término do período de competência** – Será concedida ao funcionário folga no último dia do período de concessão.

    Para calcular o valor correto, o processo da competências deve incluir o período inteiro. Por exemplo, o período da competência vai de 1º de janeiro de 2018 até 31 de janeiro de 2018. Nesse caso, para que janeiro seja incluído, a competência deve ser executada a partir de 1º de fevereiro de 2018.

- **Data inicial do período de competência** – Será concedida ao funcionário folga no primeiro dia do período de concessão.

### <a name="accrual-policy-on-enrollment"></a>Política de competência no registro

A política de competência no registro define como a competência é calculada quando um funcionário é registrado no meio de um período de competência. As opções a seguir estão disponíveis:

- **Proporcional** – O intervalo de datas entre a data de registro e a data de início é usado para determinar a diferença em dias. Essa diferença será aplicada quando as competências são processadas.
- **Competência total** – O valor total da competência, com base na faixa, é concedido no primeiro processamento da competência.
- **Nenhuma competência** – Nenhuma competência será concedida até o próximo período de competência.

### <a name="accrual-policy-on-unenrollment"></a>Política de competência no cancelamento do registro

A política de competência no cancelamento do registro define como a competência é calculada quando o registro de um funcionário é cancelado no meio de um período de competência. As opções a seguir estão disponíveis:

- **Proporcional** – O intervalo de datas entre a data de registro e a data de início é usado para determinar a diferença em dias. Essa diferença será aplicada quando as competências são processadas.
- **Competência total** – O valor total da competência, com base na faixa, é concedido no primeiro processamento da competência.
- **Nenhuma competência** – Nenhuma competência será concedida até o próximo período de competência.

## <a name="accrual-schedule"></a>Agenda de competência

A agenda de competência determina como um funcionário acumulará as folgas e que valores ele acumulará e manterá. As faixas podem ser criadas para que as folgas sejam concedidas com base em níveis diferentes.

### <a name="months-of-service"></a>Meses de serviço

O valor **Meses de serviço** define o número mínimo de meses que os funcionários devem trabalhar para serem qualificados para acúmulo de folgas. Se não houver um número mínimo para os funcionários, defina o valor para **0**.

### <a name="hours-worked"></a>Horas trabalhadas

O valor **Horas trabalhadas** define o número mínimo de horas que os funcionários devem trabalhar por período de competência para terem direito ao acúmulo de folgas. Se não houver um número mínimo para os funcionários, defina o valor para **0**.

### <a name="accrual-amount"></a>Valor da competência

O valor da competência é o número de horas ou dias que os funcionários acumularão por período. O período se baseia na frequência de acumulação.

### <a name="minimum-balance"></a>Saldo mínimo

É possível usar um valor negativo para o saldo mínimo se os funcionários puderem solicitar mais licenças do aquelas a que têm direito.

### <a name="maximum-carry-forward"></a>Postergação máxima

O processo de competência ajustará os saldos de licença que excederem o saldo máximo de postergação no aniversário da data de início.

### <a name="grant-amount"></a>Valor concedido

O valor concedido é o número inicial de horas ou dias que é concedido aos funcionários quando se registram no plano de licença. O valor não é acumulado no cada período de competência.

## <a name="enrollments-and-balances"></a>Registros e saldos

### <a name="enrollment-date"></a>Data do registro

A data do registro determina quando um funcionário pode iniciar o acúmulo de folgas. Por exemplo, se um funcionário tiver se registrado em um plano de férias no 15 de junho de 2018, ela não pode acumular folgas antes do dia 15 de junho de 2018.

### <a name="current-balance"></a>Saldo atual

O saldo atual é o valor da licença disponível para as solicitações de folga. Esse valor inclui competências, solicitações aprovadas e ajustes até a data atual.

### <a name="current-balance-examples"></a>Exemplos de saldo atual

#### <a name="annual-plan"></a>Plano anual

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Data inicial do plano      | Término do período de competência |

As competências são processadas em 1º de janeiro de 2019 (1/1/2019), para que todo o período seja incluído.

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

As competências são processadas em 1º de maio de 2018 (1/5/2018), para que todo o período seja incluído.

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

As competências são processadas em 1º de maio de 2018 (1/5/2018), para que todo o período seja incluído.

**Resultados**

| Valor da competência | Saldo mínimo | Postergação máxima | Valor solicitado | Saldo atual (em 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

O saldo atual (7) = o valor acumulado (5 × 3) – o valor solicitado (8)

### <a name="forecasted-balance"></a>Saldo previsto

O *saldo previsto* é o valor da licença disponível em uma data futura. As competências e os ajustes de postergação são previstos até essa data.

Esta é a fórmula usada:

Saldo previsto na segunda-feira = saldo atual – solicitações + competências – ajuste de postergação

### <a name="forecasted-balance-examples"></a>Exemplos de saldo previsto

#### <a name="annual-plan"></a>Plano anual

**Configuração do plano**

| Data inicial do plano | Data do registro | Frequência das competências | Base do período de competência | Data de concessão da competência    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Data inicial do plano      | Término do período de competência |

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019), para que todo o período seja incluído.

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

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019), para que todo o período seja incluído.

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

As competências são processadas em 15 de fevereiro de 2019 (15/2/2019), para que todo o período seja incluído.

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
| Jeannette Nicholson | 0,00              | 1/6/2018        | 1/6/2018   | 1.00           | 1/9/2018        | 3,00    |
| Jay Norman          | 0,00              | 15/6/2018       | 15/6/2018  | 1.00           | 1/9/2018        | 2.00    |

