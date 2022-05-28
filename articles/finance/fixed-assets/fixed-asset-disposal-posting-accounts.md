---
title: Contas de lançamento de alienação de ativo fixo
description: Este tópico explica como configurar contas de lançamento de Contabilidade para descartar ativos.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8501bbb0fc47fb52e100d9086054db4831dae178
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720241"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Contas de lançamento de alienação de ativo fixo

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar contas de lançamento de Contabilidade ao descartar ativos.

Para configurar as contas de lançamento de Contabilidade para uso quando estiver descartando um ativo, selecione **Descarte - venda** e **Descarte - sucateamento** nas guias rápidas **Contas contábeis** na página **Perfis de lançamento de ativos fixos**.

Para ambos os tipos de transação (descarte de um ativo por venda ou sucateamento), a conta contábil é creditada no valor de descarte do ativo fixo. O débito é lançado em uma contrapartida, que pode ser, por exemplo, uma conta bancária. Caso um ativo fixo seja vendido para um cliente, a conta de cliente será usada em lugar da conta de compensação. Para obter mais informações, consulte a página [Descartar um ativo fixo como sucata](dispose-of-a-fixed-asset-as-scrap.md).

Clique em **Descarte** e em **Venda** ou **Sucateamento** e configure as contas detalhadas para estornar o valor líquido contábil do ativo fixo. Você também pode inserir informações nos campos **Lançar valor** e **Tipo de valor de venda** na página **Parâmetros de alienação**. 

A transação de alienação de um ativo em um grupo de valor baixo reduz o valor líquido contábil do grupo de valor baixo somente pelo valor alienado. Porém, quando a venda de um ativo excede o valor líquido contábil do grupo de valor baixo, o valor líquido contábil é reduzido a zero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
