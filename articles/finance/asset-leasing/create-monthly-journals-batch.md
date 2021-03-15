---
title: Criar entradas de diário mensal em um lote
description: Este tópico explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas.
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
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971319"
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