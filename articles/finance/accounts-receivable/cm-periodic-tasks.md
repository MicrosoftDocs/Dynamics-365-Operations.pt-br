---
title: Tarefas periódicas de gerenciamento de crédito
description: Este tópico descreve as tarefas periódicas que são necessárias no processo de gerenciamento dos limites de crédito de clientes.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f6b04c28c0f7b5e4d58d464ad45d42478cde4e0ffb584e5afa43c99ebaed7166
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724006"
---
# <a name="periodic-credit-management-tasks"></a>Tarefas periódicas de gerenciamento de crédito

[!include [banner](../includes/banner.md)]

Este tópico descreve as tarefas periódicas que são necessárias no processo de gerenciamento dos limites de crédito de clientes.

## <a name="update-risk-scores"></a>Atualizar pontuações de risco

À medida que as empresas evoluem e as circunstâncias mudam, os riscos de crédito de um determinado cliente também podem mudar. Para ajudar a manter os limites de crédito adequados para seus clientes, periodicamente você deve revisar os critérios de cada pontuação de risco e atualizar as pontuações de cada cliente. É possível atualizar as pontuações a seguir usando a página **Atualizar pontuações de risco** (**Crédito e cobranças \> Tarefas periódicas \> Gerenciamento de crédito \> Atualizar pontuações de risco**). Todos os cálculos definidos pelo usuário também são processados.

- **Média de dias de pagamento** – Esta pontuação é o número médio de dias que um cliente leva para pagar as faturas.
- **Cliente desde** – Esta pontuação representa o número de anos que um cliente é cliente da sua organização.
- **Na empresa desde** – Esta pontuação é o número de anos durante os quais o cliente está na empresa. Ela usa o valor do campo **Início do negócio** na página **Clientes**.
- **Vendas diárias pendentes** – Esta pontuação se baseia no saldo de contas a receber, na receita de vendas e no número de dias do período de 12 meses anterior.
- **Saldo médio** – Esta pontuação se baseia no saldo de contas a receber do período de 12 meses anterior.
- **Grupo de gerenciamento de crédito**, **Status da conta** e **País** – Estas pontuações usam informações do cliente.

## <a name="update-customer-balance-statistics"></a>Atualizar estatísticas de saldo de cliente

Você pode executar o processo **Atualizar estatísticas de saldo de cliente** para atualizar o cálculo de estatísticas de saldo mostrado na página **Consulta de estatísticas de saldo**. Essas informações são usadas para calcular as pontuações de risco e os valores que são mostrados nos Quadro de Fatos de estatísticas da página **Cliente**.

Quando você executa o processo, ele atualiza as estatísticas de saldo de um único cliente. Para configurar um trabalho em lotes para executar o processo para vários clientes, você pode usar a página **Calcular estatísticas de saldo** (**Gerenciamento de crédito \> Tarefas periódicas \> Calcular estatísticas de saldo**).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]