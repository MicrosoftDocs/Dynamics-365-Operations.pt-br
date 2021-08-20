---
title: Descrições padrão da contabilidade
description: As descrições padrão podem ser usadas para atualizar o campo Descrição em lançamentos de comprovantes na contabilidade.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c68d0ae43ee2350225a0a0e32578f300b8faebe18aa575a5f737a49fd4c0c1a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736710"
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
