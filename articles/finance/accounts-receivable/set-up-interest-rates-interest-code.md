---
title: Configurar taxas de juros para um código de juros
description: Os códigos de juros contêm configurações que determinam quando os juros são cobrados e como são calculados em contas vencidas.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1169a397dfdd32f728a09e2ad279842edc289c19
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971619"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a>Configurar taxas de juros para um código de juros

[!include [banner](../includes/banner.md)]

Os códigos de juros contêm configurações que determinam quando os juros são cobrados e como são calculados em contas vencidas.

Você pode configurar um único código de juros e aplicá-lo a vários perfis de lançamentos do cliente, códigos de cobrança ou às linhas da fatura específicas. Quando os detalhes do código de juros são alterados, todos os recursos que usam o código implementarão automaticamente as alterações nas novas transações. Para cada código de juros, você pode configurar dois tipos de taxas:
-   Taxas para ganhos de juros − Representam a receita recebida pela alteração de juros em faturas ou notas de juros.
-   Pagamentos de taxas de juros - Representam um custo pago por jutos sobre notas de crédito.

Ambas as taxas podem existir ao mesmo tempo e no mesmo código de juros. As taxas de juros podem ser baseadas em três tipos de cálculo:
-   Juros por porcentagem.
-   Juros por valor.
-   Juros pelo intervalo, o que resulta em uma única porcentagem ou valor.

Quando um código de juros é usado para calcular os juros, uma nota de juros separada é criada para cada taxa de juros em vigor durante o período em que o pagamento tiver excedido a data de vencimento da transação. Use a guia **Ganhos** na página **Código de juros** para configurar taxas de juros para os juros que você ganha ao cobrar juros. Use a guia **Pagamentos** para configurar as taxas de juros para os juros que você paga.

## <a name="interest-rates-based-on-a-percentage"></a>Taxas de juros com base em um porcentagem
Você pode configurar taxas de juros para calcular um percentual especificado.

- O valor dos juros se aplica a todas as moedas.
- Os limites do valor de juros opcional podem ser inseridos.
- <strong>Porcentagem</strong> é selecionado** <strong>no campo **Calcular juros com base em</strong> na página <strong>Configurar Códigos de juros</strong>.

Por exemplo, para configurar um código de juros que avalie 5% de juros para cada dois meses, se o pagamento da fatura exceder a data de vencimento da transação, digite 2 no campo **Calcular juros a cada** e selecione **Mês**.

## <a name="interest-rates-based-on-amounts"></a>Taxas de juros baseadas em valores
Você pode configurar taxas de juros que calculam um valor por moeda específico.
- Um valor de juros é especificado para cada moeda no código de juros.
- Os limites do valor de juros opcional podem ser inseridos.
- **Valor** é selecionado no campo **Calcular juros com base em** na página **Configurar códigos de juros**.

Por exemplo, para configurar um código de juros que avalie juros de 25,00 para cada 20 dias que o pagamento da fatura excede a data de vencimento da transação, insira 20 no campo **Calcular juros a cada** e selecione **Dia**.

## <a name="interest-rates-based-on-ranges"></a>Taxas de juros baseadas em intervalos
Você pode configurar taxas de juros que varia de acordo com o valor vencido, o número de dias ou de meses que o valor está atrasado.
-   Você pode usar a guia **Salário por moeda** para definir configurações específicas de juros para cada moeda. Esse também é o local onde você definirá o intervalo.
-   Use o botão **Intervalos** para adicionar as linhas que representam os intervalos que deseja configurar. O valor **De** representa o início do intervalo e o número **Valor dos juros** representa uma porcentagem ou valor, dependendo da seleção no campo **Calcular juros com base em** da página **Configurar códigos de juros**.

## <a name="example-1-interest-by-range--amount"></a>Exemplo 1: Juros por intervalo = valor
Você configura um código de juros que avalia juros uma vez a cada três meses que o pagamento da fatura ultrapassar a data de vencimento da transação. Você deseja basear o cálculo de um valor dos juros em porcentagem, de acordo com o valor de nível dos intervalos. O valor dos juros será 1 por cento para valores da fatura de até 1.000,00, 2 por cento para valores de 1.001,00 para 5.000,00, e 3 por cento para os valores superiores a 5.000,00. Configure os valores do campo código de juros como a seguir.

| **Nome do campo**                  | **Valor do campo** |
|---------------------------------|-----------------|
| **Código de juros**               | 3M%ByAmt        |
| **Calcular juros a cada**    | 3/Mês         |
| **Juros por intervalo**           | Valor          |
| **Calcular juros baseados em** | Porcentagem      |

Configure as informações do intervalo conforme as informações a seguir.

| **Do valor** | **Valor dos juros** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |


## <a name="example-2-interest-by-range--days"></a>Exemplo 2: Juros por intervalo = Dias
--------------------------------------------------

Você configura um código de juros que avalia juros uma vez a cada 15 dias que o pagamento da fatura ultrapassar a data de vencimento da transação. Você deseja basear o cálculo de um valor dos juros em valor, de acordo com os intervalos de dia de nível. O valor dos juros será 10,00 para 15 dias durante os primeiros 60 dias, 15,00 para 15 dias durante os dias 61 a 90 e 20,00 para 15 dias do dia 91 e os dias seguintes. Configure os valores do campo código de juros como a seguir.

| **Nome do campo**                  | **Valor do campo** |
|---------------------------------|-----------------|
| **Código de juros**               | 15DAmtXDay      |
| **Calcular juros a cada**    | 15/Dia          |
| **Juros por intervalo**           | Dias            |
| **Calcular juros baseados em** | Valor          |

Configure as informações do intervalo conforme as informações a seguir.

| **Do valor** | **Valor dos juros** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |


## <a name="example-3-interest-by-range--months"></a>Exemplo 3: Juros por intervalo = Meses
----------------------------------------------------

Você configura um código de juros que avalia juros uma vez a cada mês que o pagamento da fatura ultrapassar a data de vencimento da transação. Você deseja basear o cálculo de um valor dos juros em porcentagem, de acordo com o mês de nível dos intervalos. O valor dos juros será 1,5 por cento por mês para os três primeiros meses vencidos, 2,0 por cento por mês para os três meses seguintes, e 2,5 por cento por mês para cada mês além dos seis primeiros meses. Configure os valores do campo código de juros como a seguir.

| **Nome do campo**                  | **Valor do campo** |
|---------------------------------|-----------------|
| **Código de juros**               | 1M%ByMth        |
| **Calcular juros a cada**    | 1/mês         |
| **Juros por intervalo**           | Meses          |
| **Calcular juros baseados em** | Porcentagem      |

Configure as informações do intervalo conforme as informações a seguir.

| **Do valor** | **Valor dos juros** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Novas versões
Os códigos de juros possuem data efetiva. Se desejar alterar a taxa de juros, você pode criar uma **nova versão** que entrará em vigor a partir de uma data futura.

Para exibir versões diferentes, você pode usar a opção de menu **A partir da data** para selecionar a data de fechamento. Você também pode selecionar **Exibir todos os registros** para exibir todos os códigos de juros na página.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]