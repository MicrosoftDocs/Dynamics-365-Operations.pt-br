---
title: Erro quando o diário Relatar como finalizado é postado
description: Quando posta o diário Relatar como finalizado, você recebe uma mensagem de erro que afirma que a quantidade pedido não pode ser reduzida.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 50a11aba46519a3a81c313aa1f685d45dcf35f64b50bc921d93968efab13b7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750921"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Erro quando o diário Relatar como finalizado é postado

Número da base de dados de conhecimento: 4612891

## <a name="symptoms"></a>Sintomas

Quando posta o diário **Relatar como finalizado**, um erro ocorre e você recebe a seguinte mensagem de erro:

> A quantidade encomendada não pode ser reduzida porque não há transações de estoque em aberto suficientes com status 'Encomendado'. Os itens são Comprados, Recebidos ou Registrados.

Este erro ocorre somente quando o campo **Quantidade incorreta** estiver definido na primeira linha do diário **Relatar como finalizado** e o campo **Quantidade correta** estiver definido na última linha. Se o campo **Quantidade incorreta** estiver definido na última linha, nenhum erro ocorre.

## <a name="resolution"></a>Resolução

Para evitar esse erro, abra a página **Parâmetros de controle de produção** e, na guia **Geral**, defina a opção **Aumentar qtde restante com qtde incorreta** como *Sim*.
