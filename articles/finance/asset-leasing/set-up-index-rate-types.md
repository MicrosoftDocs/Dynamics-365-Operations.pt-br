---
title: Configurar taxas indexadas
description: Este tópico explica como configurar taxas indexadas. As taxas indexadas são necessárias se a sua organização associa os valores de pagamento de arrendamento a um conjunto de taxas indexadas.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880951"
---
# <a name="set-up-index-rates"></a>Configurar taxas indexadas

[!include [banner](../includes/banner.md)]

Se os pagamentos de arrendamento dependerem de um índice, os tipos de taxa indexada poderão ser adicionados e mantidos no sistema. Para reavaliar os pagamentos de arrendamento da página **Tipo de taxa indexada**, o processo de reavaliação de taxa indexada usa a taxa indexada mais recente a partir da data de reavaliação.

Para adicionar tipos de taxa indexada e taxas indexada, siga estas etapas.

1. Vá para **Arrendamento de ativo \> Configuração \> Tipo de taxa indexada**.
2. Selecione **Novo**.
3. Nos campos apropriados, insira o tipo de taxa e o nome da taxa indexada.
4. Para adicionar um novo valor de taxa indexada, selecione o tipo de taxa indexada e selecione **Adicionar**.
5. Selecione a data de início efetiva da taxa e selecione o valor da taxa.

Você deve selecionar **Diferença de valor de taxa indexada** ou **Valor de taxa indexada** como o método de taxa indexada.

- Selecione o método **Diferença de valor de taxa indexada** para calcular um novo pagamento de arrendamento, com base na diferença entre a taxa indexada na data de início e a taxa indexada mais recente. A taxa indexada é definida no campo **Taxa indexada (%)**.
- Selecione o método **Valor de taxa indexada** para calcular o pagamento do arrendamento usando a porcentagem especificada no campo **Taxa indexada (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
