---
title: "Contas de lançamento de alienação de ativo fixo"
description: "Este artigo explica como configurar contas de lançamento de contabilidade para descartar ativos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0540ba30cb26abe274075deea80ca1e9cfc686f9
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a>Contas de lançamento de alienação de ativo fixo

[!include[banner](../includes/banner.md)]


Este artigo explica como configurar contas de lançamento de contabilidade para descartar ativos.

Na página Perfis de lançamentos de ativo fixo, na Guia Rápida Contas contábeis, selecione Descarte - Descarte de sucata para configurar lançamentos para o razão.

Para ambos os tipos de transação, a conta contábil é creditada no valor de alienação do ativo fixo. O débito é lançado em uma conta de baixa, que pode ser, por exemplo, uma conta bancária. Caso um ativo fixo seja vendido para um cliente, a conta de cliente será usada em lugar da conta de compensação.

Clique em Descarte e em Venda ou sucateamento e configure as contas detalhadas para estornar o valor líquido contábil do ativo fixo. Você também pode inserir informações nos campos Lançar valor e Tipo de valor de venda na página Parâmetros de alienação. 

A transação de alienação de um ativo em um grupo de valor baixo reduz o valor líquido contábil do grupo de valor baixo somente pelo valor alienado. Porém, quando a venda de um ativo for maior do que o valor líquido contábil do grupo de valor baixo, o valor líquido contábil é reduzido a zero.






