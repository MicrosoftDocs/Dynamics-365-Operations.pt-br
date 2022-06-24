---
title: Criar entradas de diário mensal em um lote
description: Este artigo explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fb5c65b0a2c982171fa0ae88141d92c2f1ead6ac
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894983"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Criar entradas de diário mensal em um lote

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Este artigo explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas. O processamento em lotes pode ser usado para criar entradas de diário a partir de vários agendamentos. Essas entradas de diário podem incluir pagamentos de arrendamento, amortização de passivos, amortização de ativos de direito de uso (DDU) e despesas de custo de execução. Você também pode usar o processamento em lotes para fazer o reconhecimento inicial de vários arrendamentos ao mesmo tempo ou para criar ajustes de transição para vários arrendamentos ao mesmo tempo.

Para configurar um trabalho em lotes ou para processar faturas de pagamento, depreciação ou juros para vários arrendamentos, acesse **Arrendamento de ativos \> Periódico \> Criação de jornal em lote**. Na caixa de diálogo exibida, é possível selecionar o agendamento a partir do qual as entradas de diário devem ser criadas. Você também pode especificar se o processo em lote deve ser executado para entidades, grupos de arrendamentos ou registros de arrendamento específicos.

> [!NOTE]
> Transações subsequentes, como agendamentos de amortização de passivos, pagamentos, depreciação e despesas, serão lançadas somente depois que o reconhecimento inicial dos arrendamentos correspondentes for lançado.
>
> As entradas de diário são criadas, mas não serão lançadas até que você selecione o comando **Executar**.

Para lançar o diário de reconhecimento inicial em uma data diferente da data de início de arrendamento, selecione **Atribuindo data de lançamento de reconhecimento inicial**. Um campo de **Data** que permite especificar a data de lançamento correta.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
