---
title: Contas de lançamento de alienação de ativos fixos
description: Este tópico explica como configurar contas de lançamento de contabilidade para descartar ativos.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d1d6a3dc6348e64bcf247544bc7b56c5314db4c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826849"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Contas de lançamento de alienação de ativos fixos

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar contas de lançamento de contabilidade para descartar ativos.

Na página Perfis de lançamentos de ativo fixo, na Guia Rápida Contas contábeis, selecione Descarte - Descarte de sucata para configurar lançamentos para o razão.

Para ambos os tipos de transação, a conta contábil é creditada no valor de alienação do ativo fixo. O débito é lançado em uma conta de baixa, que pode ser, por exemplo, uma conta bancária. Caso um ativo fixo seja vendido para um cliente, a conta de cliente será usada em lugar da conta de compensação.

Clique em Descarte e em Venda ou sucateamento e configure as contas detalhadas para estornar o valor líquido contábil do ativo fixo. Você também pode inserir informações nos campos Lançar valor e Tipo de valor de venda na página Parâmetros de alienação. 

A transação de alienação de um ativo em um grupo de valor baixo reduz o valor líquido contábil do grupo de valor baixo somente pelo valor alienado. Porém, quando a venda de um ativo excede o valor líquido contábil do grupo de valor baixo, o valor líquido contábil é reduzido a zero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]