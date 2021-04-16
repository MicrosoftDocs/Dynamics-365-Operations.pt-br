---
title: Criar entradas de diário mensal em um lote
description: Este tópico explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 664001dd6e9da449dec65750da53d58bd27438b4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816019"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Criar entradas de diário mensal em um lote

[!include [banner](../includes/banner.md)]

Este tópico explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas. O processamento em lotes pode ser usado para criar entradas de diário a partir de vários agendamentos. Essas entradas de diário podem incluir pagamentos de arrendamento, amortização de passivos, amortização de ativos de direito de uso (DDU) e despesas de custo de execução. Você também pode usar o processamento em lotes para fazer o reconhecimento inicial de vários arrendamentos ao mesmo tempo ou para criar ajustes de transição para vários arrendamentos ao mesmo tempo.

Para configurar um trabalho em lotes ou para processar faturas de pagamento, depreciação ou juros para vários arrendamentos, acesse **Arrendamento de ativos \> Periódico \> Criação de jornal em lote**. Na caixa de diálogo exibida, é possível selecionar o agendamento a partir do qual as entradas de diário devem ser criadas. Você também pode especificar se o processo em lote deve ser executado para entidades, grupos de arrendamentos ou registros de arrendamento específicos.

> [!NOTE]
> Transações subsequentes, como agendamentos de amortização de passivos, pagamentos, depreciação e despesas, serão lançadas somente depois que o reconhecimento inicial dos arrendamentos correspondentes for lançado.
>
> As entradas de diário são criadas, mas não serão lançadas até que você selecione o comando **Executar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]