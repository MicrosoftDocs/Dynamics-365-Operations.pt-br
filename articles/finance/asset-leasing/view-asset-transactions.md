---
title: Exibir transações de passivos, ativos e despesas
description: Este tópico explica como exibir transações para um ativo arrendado. Essas transações incluem transações de responsabilidade com arrendamento e transações de despesa de execução que foram lançadas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 76c7eff17df92b01317544112099e391fd05d105
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995359"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Exibir transações de passivos, ativos e despesas

[!include [banner](../includes/banner.md)]

Este tópico explica como exibir transações para um ativo arrendado. Essas transações incluem transações de responsabilidade com arrendamento e transações de despesa de execução que foram lançadas. Os valores de transporte do ativo passivo e de direito de uso (DDU) são usados em vários relatórios. Eles também são usados para calcular os valores de ajuste.

## <a name="liability-transactions"></a>Transações de passivo

Para exibir as transações de responsabilidade com arrendamento, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros anexados ao registro de arrendamento. Depois que um reconhecimento inicial, uma fatura ou um diário de juros tiver sido lançado, selecione **Transações de passivo**.

A página **Transações de passivo** mostra as transações que aumentam ou diminuem a responsabilidade com arrendamento. Os valores negativos nesta página representam transações de crédito no aplicativo padrão. As competências de juros são mostradas como valores negativos e aumentam a responsabilidade com arrendamento total. Os ajustes de arrendamento são mostrados como valores positivos ou negativos, dependendo da natureza e do impacto do registro de arrendamento. O saldo total líquido atual da responsabilidade com arrendamento para o arrendamento selecionado é mostrado no canto inferior esquerdo da página.

## <a name="asset-transactions"></a>Transações de ativo

Para exibir as transações de ativo, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros de arrendamento anexados ao registro de arrendamento. Em seguida, selecione **Transações de ativo**.

A página **Transação de ativo** mostra as transações que aumentam ou diminuem as contas de ativo de arrendamento e depreciação acumulada. Os débitos são mostrados como valores positivos, e os créditos são mostrados como valores negativos, como na página **Transações de passivo**. O reconhecimento inicial lançado e a próxima depreciação acumulada são mostrados no canto inferior esquerdo da página como o saldo do ativo. 

## <a name="expenses-transactions"></a>Transações de despesas

Para exibir as transações de despesas de ativo, selecione um arrendamento na página **Resumo do arrendamento** e, em seguida, selecione **Registros** para abrir os registros de arrendamento anexados ao registro de arrendamento. Em seguida, selecione **Transações de despesa**.

A página **Transações de despesa** mostra todas as despesas que foram lançadas em relação ao arrendamento, como despesas de juros, despesas de depreciação e qualquer custo de execução.
