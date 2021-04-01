---
title: Criar um pagamento de imposto
description: O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9523ef75953bdca36f509f596c51c08b12b3fdb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254454"
---
# <a name="create-a-sales-tax-payment"></a>Criar um pagamento de imposto

[!include [banner](../../includes/banner.md)]

O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.

1. Vá para **Imposto > Declarações > Imposto > Liquidar e lançar imposto**.
2. No campo **Período de liquidação**, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo **Data inicial**, insira uma data.
    * Se você não selecionar **Incluir correções** na página **Parâmetros da contabilidade**, a liquidação pode ser processada para várias versões. O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos. As últimas correções estabelecerão as transações de imposto que foram lançadas depois que a versão original foi criada.   
5. No campo **Data de transação**, insira uma data.
6. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]