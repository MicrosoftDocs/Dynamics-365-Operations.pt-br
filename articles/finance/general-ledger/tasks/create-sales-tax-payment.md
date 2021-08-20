---
title: Criar um pagamento de imposto
description: O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c0b6c67a547e42ab4d7b7ba9f456a29c6b3d22e491e3a8ad0481a0144491087
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763157"
---
# <a name="create-a-sales-tax-payment"></a>Criar um pagamento de imposto

[!include [banner](../../includes/banner.md)]

O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.

1. Acesse **Imposto > Declarações > Imposto > Liquidar e lançar imposto**.
2. No campo **Período de liquidação**, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo **Data inicial**, insira uma data.
    * Se você não selecionar **Incluir correções** na página **Parâmetros da contabilidade**, a liquidação pode ser processada para várias versões. O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos. As últimas correções estabelecerão as transações de imposto que foram lançadas depois que a versão original foi criada.   
5. No campo **Data de transação**, insira uma data.
6. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]