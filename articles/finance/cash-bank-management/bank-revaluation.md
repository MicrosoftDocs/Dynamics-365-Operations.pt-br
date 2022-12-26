---
title: Reavaliação de moeda estrangeira do banco
description: Este artigo fornece uma visão geral do processo de reavaliação bancária de moeda estrangeira. Ele inclui informações sobre a configuração, a execução do processo, os cálculos do processo e a reversão das transações de reavaliação.
author: angelad116
ms.date: 12/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2d5e8a36d3b4d44c9ad0454db94164adebf80997
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887250"
---
# <a name="bank-foreign-currency-revaluation"></a>Reavaliação de moeda estrangeira do banco

[!include [banner](../includes/banner.md)]


Este artigo fornece uma visão geral do processo de reavaliação bancária de moeda estrangeira. Ele explica como configurar e executar o processo e fornece informações sobre os cálculos do processo. Ele também explica a reversão das transações de reavaliação se a reversão for necessária.

Como parte de um fechamento, as convenções de contabilidade exigem que os saldos de contas bancárias em moedas estrangeiras sejam reavaliados usando diferentes tipos de taxa de câmbio (atual, histórico, médio e assim por diante). O recurso de reavaliação bancária de moeda estrangeira pode ser usado para reavaliar uma ou mais contas bancárias. O recurso também é um recurso global. Portanto, em uma única página, você pode reavaliar bancos em todas as entidades legais às quais você tem acesso.

> [!NOTE]
> Quando o processo de reavaliação é executado, o saldo em cada conta bancária que está lançado em uma moeda estrangeira será reavaliado. As transações de lucro não realizado ou transações perdidas criadas durante o processo de reavaliação são geradas pelo sistema. Duas transações poderão ser criadas, uma para a moeda contábil e uma para a moeda de relatório, se a moeda de relatório for relevante. Cada entrada contábil será lançada na conta de lucro ou de perda não realizada e na conta principal que estará sendo reavaliada.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparação para executar a reavaliação de moeda estrangeira

Para executar o processo de reavaliação, é necessária uma configuração adicional.

- Na página **Razão**, especifique o tipo de taxa de câmbio. Se um tipo de taxa de câmbio não estiver definido na conta principal, este tipo de taxa de câmbio será usado na reavaliação de moeda estrangeira.
- Na página **Razão**, especifique o lucro realizado, a perda realizada, o lucro não realizado e a perda não realizada para a reavaliação de moeda. As contas de lucro realizado e de perda realizada são usadas quando transações de Contas a receber e de Contas a pagar são liquidadas. As contas de lucro não realizado e de perda não realizada são usadas para reavaliar transações abertas e contas principais de contabilidade.
- Na página **Contas de reavaliação de moeda**, selecione diferentes contas de reavaliação de moeda para cada moeda e empresa. Se nenhuma conta for definida, as contas da página **Razão** serão usadas.
- Na página **Parâmetros de gerenciamento de caixa e bancos**, na guia **Número de sequências**, adicione uma sequência numérica para reavaliação de moeda estrangeira.


> [!NOTE]
> Se a sua entidade legal usar um código de país/região russo, polonês ou húngaro, você já poderá fazer a reavaliação de moeda estrangeira. Não será possível usar a reavaliação de moeda estrangeira que é usada por outros países ou regiões.

## <a name="process-foreign-currency-revaluation"></a>Processar uma reavaliação de moeda estrangeira

Depois de concluir a configuração, use a página **Reavaliação de moeda estrangeira** em Gerenciamento de caixa e bancos para reavaliar os saldos de uma ou mais contas bancárias em todas as entidades legais. Você pode executar o processo em tempo real ou agendá-lo para execução usando um lote.

A página **Reavaliação de moeda estrangeira** mostra o histórico de cada processo de reavaliação. Ela mostra quando o processo foi executado, quais critérios foram definidos e fornece um link para o comprovante que foi criado para a reavaliação. Ele também mostra se a reavaliação anterior foi revertida. Para executar o processo de reavaliação, selecione **Reavaliação de moeda estrangeira** no Painel de Ação para abrir a caixa de diálogo **Reavaliação de moeda estrangeira — Banco**.

O campo **Data da reavaliação** define a data de fechamento para o cálculo do saldo em moeda estrangeira que será reavaliado. A soma de todas as transações bancárias que ocorreram até essa data será reavaliada.

O campo **Data da taxa de câmbio** define a data da taxa de câmbio que será usada para reavaliar os saldo de moeda. Por exemplo, você pode reavaliar os saldos a partir de 31 de janeiro, mas usar a taxa de câmbio definida para 1º de fevereiro.

O processo de reavaliação pode ser executado para uma ou mais entidades legais. A pesquisa exibe somente as entidades legais às quais você tem acesso. Selecione as entidades legais para as quais você deseja selecionar as contas bancárias qualificadas para reavaliação de moeda estrangeira. Todas as contas bancárias para essas entidades legais serão exibidas na grade.

Defina a opção **Visualizar antes do lançamento** como **Sim** se quiser revisar os resultados da reavaliação antes de lançá-la. A reavaliação de moeda estrangeira tem uma visualização que pode ser lançada. Não é necessário executar o processo de reavaliação novamente. Você pode exportar os resultados na visualização para o Microsoft Excel para manter o histórico como os valores foram calculados. Não é possível usar o processamento em lotes se você deseja visualizar os resultados da reavaliação.

Selecione **OK** para processar a reavaliação de moeda estrangeira. Um registro será criado para controlar o histórico de cada execução. Um registro separado será criado para cada entidade legal e nível de lançamento.

## <a name="calculate-unrealized-gainloss"></a>Calcule lucros/perdas não realizado

Em Gerenciamento de caixa e bancos, a moeda do banco é considerada como a moeda base e não é reavaliada. O saldo da conta bancária na moeda contábil é reavaliado usando as taxas de câmbio entre a moeda do banco e a moeda contábil na **Data da taxa de câmbio**. O saldo da conta bancária na moeda de relatório também é reavaliado usando as taxas de câmbio entre a moeda do banco e a moeda de relatório na **Data da taxa de câmbio**.

Uma transação será criada para a diferença entre o saldo da conta bancária e o novo saldo que é calculado para a moeda contábil. Outra transação será criada para a diferença entre o saldo da conta bancária e o novo saldo que é calculado para a moeda de relatório. As entradas dessas transações são marcadas como reconciliadas. 

Nenhuma entrada será feita para a moeda contábil se a moeda do banco corresponder à moeda contábil. Da mesma forma, nenhuma entrada será feita para a moeda de relatório se a moeda do banco corresponder à moeda de relatório.

A transação de reavaliação de moeda estrangeira também é dividida entre as dimensões que são encontradas nas transações bancárias. A divisão é baseada no saldo de cada dimensão. Por exemplo, o saldo bancário total é de 10.000, mas o saldo da unidade de negócios 001 é de 4.000, enquanto o saldo da unidade de negócios 002 é de 6.000. Nesse caso, 40% do valor da reavaliação será lançado na conta de reavaliação que tem a unidade de negócios 001 e 60% será lançado na conta de reavaliação que tem a unidade de negócios 002. Se a estrutura de conta não incluir uma unidade de negócios, o valor total será lançado na conta de reavaliação.

## <a name="reverse-foreign-currency-revaluation"></a>Estornar reavaliação de moeda estrangeira

Se for necessário reverter a transação de reavaliação, selecione o botão **Reverter transação** na página **Reavaliação de moeda estrangeira**. Um novo registro histórico de reavaliação de moeda estrangeira será criado para manter a trilha de auditoria histórica de quando a reavaliação ocorreu ou foi revertida.

Para reverter várias reavaliações, você deverá reverter a reavaliação mais atual primeiro. Depois, continue a reverter as reavaliações mais antigas por ordem de data. É possível processar novas reavaliações para os períodos que foram revertidos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
