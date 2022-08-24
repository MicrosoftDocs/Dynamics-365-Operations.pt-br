---
title: Habilite o tipo de taxa de câmbio do imposto retido na fonte global e a configuração do tipo de data
description: Este artigo explica como habilitar a configuração global do tipo de taxa de câmbio e tipo de data da moeda do imposto retido na fonte.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 41f12a33651c14439f3a59c5c2f2d34019dada2d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229950"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Habilite o tipo de taxa de câmbio do imposto retido na fonte global e a configuração do tipo de data

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Este artigo explica como habilitar a configuração global do tipo de taxa de câmbio e tipo de data da moeda do imposto retido na fonte. Agora você pode selecionar um tipo de taxa de câmbio dedicada e um tipo de data de cálculo da taxa de câmbio para a moeda do imposto retido na fonte. Essas seleções determinam a taxa de câmbio de moeda estrangeira usada para calcular o valor do imposto retido na fonte na moeda do imposto retido na fonte, nas transações de pagamento.

Esta funcionalidade está disponível na versões 10.0.29 do Microsoft Dynamics 365 Finance e posterior.

1. Acesse **Imposto** \> **Configuração** \> **Parâmetros** \> **Parâmetros gerais de contabilidade**.
2. Na guia **Imposto retido na fonte**, defina a opção **Habilitar moeda de imposto retido na fonte avançado** como **Sim**.
3. No campo **Tipo de taxa de câmbio**, selecione um tipo de taxa de câmbio para a moeda do imposto retido na fonte.
4. No campo **Tipo de data de cálculo**, selecione um tipo de data de cálculo que determine a taxa de câmbio da moeda do imposto retido na fonte:

    - **Data do pagamento** – determine a taxa de câmbio com base na data de lançamento do diário de pagamentos.
    - **Data da fatura** – determine a taxa de câmbio com base na data da fatura do diário de faturas. Se a data da fatura do comprovante estiver em branco, será usada a data de lançamento da fatura. 
    - **Data do documento**  – determine a taxa de câmbio com base na data do documento do diário de pagamentos. Se a data do documento estiver em branco, será usada a data de pagamento.

5. Selecione **Salvar**.

Se a moeda da transação for diferente da moeda do imposto retido na fonte definida no código do imposto retido na fonte, o valor na moeda do imposto retido na fonte será calculado a partir da moeda da transação, com base nas configurações anteriores, e será registrado nas transações do imposto retido na fonte lançado.
