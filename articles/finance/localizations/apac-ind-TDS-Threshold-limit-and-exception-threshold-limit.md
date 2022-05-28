---
title: Limite e limite de exceção
description: Este tópico descreve o limite e os limites de exceção para Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7fa7d871fdf25f29b003a68cacd9fc0d487dce5b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726006"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Limite e limite de exceção

[!include [banner](../includes/banner.md)]

Este tópico descreve o limite e os limites de exceção para Imposto Deduzido na Origem (TDS). O TDS em faturas e pagamentos é sempre calculado considerando-se o limite de limite e o limite de exceção definidos para os componentes de imposto TDS na página **Componentes de imposto retido na fonte**. Os componentes de imposto de TDS são anexados a códigos de imposto de TDS, incluídos nos grupos de impostos de TDS. Os grupos de impostos de TDS estão associados a fornecedores e clientes para calcular TDS no nível de fatura ou de pagamento.

O TDS é calculado se o valor de uma transação ou as transações cumulativas lançadas com um grupo de TDS específico para um fornecedor exceder o limite especificado na página **Componentes de imposto retido na fonte**. O TDS não será calculado até que o valor cumulativo da transação exceda o limite especificado.

Se um limite de exceção for especificado juntamente com o limite para um componente de TDS, o TDS é calculado quando um valor de transação específico excede o limite de exceção, mesmo que o valor da transação cumulativa não exceda o limite especificado.

### <a name="example"></a>Exemplo
Um componente de imposto chamado TDS é configurado e anexado ao grupo de impostos TDS chamado Prestador de serviço. O limite foi definido como 50.000 e o limite de exceção foi definido como 20.000 para o componente de imposto TDS. O prestador de serviço do grupo TDS é definido como o grupo de TDS padrão para o fornecedor 1.

Uma fatura de compra 001 é lançada para o fornecedor 1 para 10000. O TDS não é calculado para a fatura porque o valor da fatura não ultrapassou o limite ou limite de exceção. Uma fatura de compra 002 é lançada para o fornecedor 1 para 25.000. O TDS é calculado para a fatura porque o valor da fatura não ultrapassou o limite de exceção. Uma fatura de compra 003 é lançada para o Fornecedor 1 para 20.000. O TDS é calculado para a fatura porque o valor total da fatura das três faturas emitidas para o fornecedor ultrapassou o limite. O TDS é calculado em todas as faturas que são emitidas para o fornecedor no qual o TDS não foi calculado anteriormente. Portanto, o TDS é calculado em 30.000, que é o valor total das faturas 001 e 003.

O limite e o limite de exceção não são considerados para o cálculo do TDS se a caixa de seleção **Esquecer limite** for selecionada para códigos de imposto de TDS no grupo de TDS que está anexado à transação. O limite não será usado nos códigos de imposto de TDS do grupo de TDS para o qual a caixa de seleção **Esquecer limite** se destina.

Se a caixa de seleção **Esquecer limite** for marcada para um grupo de TDS específico para algumas faturas, mas não selecionado para outras faturas que foram criadas para um fornecedor/cliente específico, o cálculo de TDS sem negligenciar o limite de algumas faturas pode ocorrer considerando o valor cumulativo em todas as faturas no qual o TDS não foi calculado anteriormente.

Por exemplo, o limite é 25000. As seguintes faturas são criadas para o Fornecedor A.

- Fatura 1 – 2.000 – (caixa de seleção **Esquecer limite** não selecionada): TDS não calculado.

- Fatura 2 – 4.000 – (caixa de seleção **Esquecer limite** selecionada): TDS calculado em 4.000.

- Fatura 2 – 3.000 – (caixa de seleção **Esquecer limite** não marcada): o TDS é calculado como o valor cumulativo da fatura, ou seja, 27.000 (20.000 + 4.000 + 3.000) excedeu o limite. O TDS é calculado com base no valor cumulativo das faturas nas quais o TDS não foi calculado anteriormente, ou seja, 23.000 (20000 + 3000).
