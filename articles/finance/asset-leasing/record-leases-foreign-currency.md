---
title: Registrar arrendamentos em moedas estrangeiras
description: Este tópico explica como registrar arrendamentos em moedas diferentes da moeda contábil ou relatório.
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
ms.openlocfilehash: fd4d04ae7e89b8ce41ed745c643b8e736484789d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241481"
---
# <a name="record-leases-in-foreign-currencies"></a>Registrar arrendamentos em moedas estrangeiras

[!include [banner](../includes/banner.md)]

As contas de arrendamento de ativos para arrendamentos em moedas diferentes da moeda contábil ou da moeda organizacional são estabelecidas na página **Configuração do razão**. Todos os arrendamentos devem ser inseridos na moeda da transação. Em outras palavras, eles devem ser inseridos na moeda especificada no contrato de arrendamento. Este tópico explica como registrar arrendamentos em moedas diferentes da moeda contábil ou relatório.

Se você inserir um arrendamento em uma moeda estrangeira, o ativo de direito de uso (DDU) será depreciado na moeda contábil e na moeda do relatório. Essas moedas são configuradas na página **Configuração do razão**. Esse comportamento também é usado em Ativos fixos. Ao criar um arrendamento em uma moeda estrangeira, selecione a moeda da transação no campo **Moeda**.

A taxa de câmbio da moeda contábil é o valor padrão no campo **Taxa de câmbio da moeda contábil**. A taxa de câmbio da moeda de relatório é o valor padrão no campo **Taxa de câmbio da moeda de relatório**. Essas taxas de câmbio entraram em vigor na data de início do arrendamento. Os campos **Taxa de câmbio da moeda contábil** e **Taxa de câmbio da moeda de relatório** ficam na Guia Rápida **Informações de câmbio financeiras e de relatório**, na página **Detalhes do arrendamento**.

1. Marque a caixa de seleção **Taxa fixa** para substituir a taxa de câmbio inserida automaticamente e insira a nova taxa.
2. Nos outros campos, insira as informações necessárias para o arrendamento e selecione **Criar agendas**.
3. Na nova página **Detalhes do arrendamento** , selecione **Registros**.
4. Na página **Registro de arrendamento** , na guia **Informações de câmbio financeiras e de relatório**, verifique os valores dos campos **Ativo de direito de uso inicial da moeda contábil** e **Ativo de direito de uso inicial da moeda de relatório**. Cada um desses campos mostra o saldo de ativo DDU traduzido na moeda correspondente. Esses campos são atualizados sempre que você altera informações financeiras. Selecione **Criar agendas** antes de confirmar a agenda de pagamento.

    A entrada de diário de reconhecimento inicial registra o ativo DDU que usa as taxas de câmbio de moeda listadas no arrendamento. A entrada de diário também inclui os valores dos campos **Ativo de direito de uso inicial da moeda contábil** e **Ativo de direito de uso inicial da moeda de relatório**.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Medição subsequente para arrendamentos de moeda estrangeira

A agenda de depreciação mostra os valores de despesas de depreciação esperados na moeda do relatório, na moeda contábil e na moeda da transação.

Para exibir os saldos de ativo DDU e os valores de depreciação na moeda do relatório ou na moeda contábil, abra a página **Agenda de depreciação de ativos** e marque a caixa de seleção **Mostrar valores de moeda contábil** ou **Mostrar valores de moeda de relatório**.

Quando você cria as entradas do diário de despesas de depreciação em relação a um arrendamento indicado em uma moeda estrangeira, a entrada usa as taxas de câmbio listadas no arrendamento. Ele também usa os valores dos campos **Ativo de direito de uso inicial da moeda contábil** e **Ativo de direito de uso inicial da moeda de relatório**.

O valor da despesa de depreciação final pode ser calculado usando uma taxa de câmbio levemente diferente, de forma que o ativo DDU seja totalmente depreciado na moeda contábil e na moeda de relatório.

Se o arrendamento tiver sido reclassificado como **Arrendamento diferido**, o sistema limpará automaticamente as taxas de câmbio das moedas contábil e de relatório, caso já tenham sido definidas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]