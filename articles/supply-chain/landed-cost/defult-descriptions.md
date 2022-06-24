---
title: Descrições padrão da contabilidade
description: As descrições padrão podem ser usadas para atualizar o campo Descrição em lançamentos de comprovantes na contabilidade.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7020c39dd599be047e07caa391d6d4c69c426328
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889538"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Descrições padrão da contabilidade

[!include [banner](../../includes/banner.md)]

As descrições padrão podem ser usadas para atualizar o campo **Descrição** em lançamentos de comprovantes na contabilidade. Essa funcionalidade foi aprimorada para trabalhar com custo de entrega.

Para configurar descrições padrão para lançamentos contábeis, acesse **Administração organizacional \> Configuração \> Descrições padrão**.

A tabela a seguir lista os novos valores que foram adicionados ao campo **Descrição** na página **Descrições padrão** para dar suporte ao custo de entrega.

| Tipo de descrição | Observação |
|---|---|
| Custos de importação – acumulação de custos | Quando uma fatura de ordem de compra é lançada, uma acumulação de custo é processada para estimar custos de viagens. As descrições padrão podem ser especificadas para adicionar o número da viagem à descrição. Use *%4* para o número de remessa. |
| Importar avaliação de custo – Ordem de mercadorias em trânsito | Se você estiver usando o processamento em trânsito, a fatura da ordem de compra será lançada e as mercadorias serão lançadas em uma conta de mercadorias em trânsito. As descrições padrão podem ser especificadas para adicionar o número da ordem em trânsito à descrição. Use *%4* para o número da ordem em trânsito. |
| Estoque - fechar - ajuste | Quando a fatura de contas a pagar (AP) é processada para um custo de viagem, um ajuste de estoque é processado para estimar os custos de viagens. As descrições padrão podem ser especificadas para adicionar o número da viagem à descrição. Use *%4* para o número de remessa. |

Para obter mais informações sobre como trabalhar com a página **Descrições padrão**, consulte [Configurar descrições padrão para lançamento automático](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
