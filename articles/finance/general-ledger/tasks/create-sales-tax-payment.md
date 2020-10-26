---
title: Criar um pagamento de imposto
description: Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e41217d26239cf704709d1d48666c382e1e2e824
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985699"
---
# <a name="create-a-sales-tax-payment"></a>Criar um pagamento de imposto

[!include [banner](../../includes/banner.md)]

Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.

1. Vá para Imposto > Declarações > Imposto > Liquidar e lançar imposto.
2. No campo Período de liquidação, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo De data, insira uma data.
    * Se a opção Incluir correções não estiver marcada na página Parâmetros da contabilidade, o pagamento pode ser processado para várias versões. O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos. As últimas correções estabelecerão as transações de imposto sobre vendas que foram lançadas depois que a versão original foi criada.   
5. No campo Transação, insira uma data.
6. Clique em OK.

