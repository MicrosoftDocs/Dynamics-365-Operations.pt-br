---
title: Contas de lançamento de aquisição de ativo fixo
description: Este artigo explica como configurar a contabilidade para lançar a aquisição de ativos.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d4c1b4de2e58b964bcf6ab07929897083f4c826
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822000"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Contas de lançamento de aquisição de ativo fixo

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar a contabilidade para lançar a aquisição de ativos.

As contas usadas para lançamento de aquisições de ativo fixo podem variar dependendo do método usado para a aquisição do ativo. Na página Perfis de lançamentos de ativo fixo, na guia Contas contábeis, selecione Aquisição e Ajuste de aquisição para configurar as contas de ativo fixo para lançamento no razão. 

Em diários e ordens de compra, a conta contábil normalmente é a conta de balanço, onde o valor de aquisição do novo ativo fixo é debitado. Essa conta não está exibida no diário e não pode ser substituída em transações. 

A contrapartida também é uma conta de balanço. No diário geral e no diário de ativos fixos, essa conta geralmente será a conta bancária usada para pagar pela aquisição do ativo. A contrapartida é uma conta padrão sugerida nos diários. Ela pode ser alterada no diário para qualquer outra conta a partir do plano de contas ou para uma conta de fornecedor, se o ativo fixo for comprado de um fornecedor. 

Quando Diário de fatura ou Ordens de compra em Contas a pagar são usados para aquisições de ativos fixos, a contrapartida para a transação de ativo fixo é substituída pela conta do fornecedor selecionada para a transação.

Para aquisições lançadas usando o Diário de estoque para ativos fixos em Contabilidade, o ativo fixo não será trazido de origens externas, mas transferido do estoque da própria empresa. Assim, a contrapartida é uma conta de saída de estoque para o item de estoque em Gerenciamento de estoque.

Para obter mais informações, consulte [Adquirir ativos por meio de compras](acquire-assets-procurement.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]