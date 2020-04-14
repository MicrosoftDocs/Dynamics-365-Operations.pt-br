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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139912"
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

