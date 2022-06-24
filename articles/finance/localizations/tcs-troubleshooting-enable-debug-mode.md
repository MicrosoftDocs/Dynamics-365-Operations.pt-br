---
title: Habilitar modo de depuração no serviço de Cálculo de Imposto
description: Este artigo explica como habilitar o modo de depuração no serviço Cálculo de Imposto para investigar problemas.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 2bb381939ebe32cb51caf730cdd441557d83a4c0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887767"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Habilitar modo de depuração no serviço de Cálculo de Imposto

[!include [banner](../includes/banner.md)]

Este artigo explica como habilitar o modo de depuração no serviço Cálculo de Imposto para investigar problemas.

1. Adicione **&debug=vs%2CconfirmExit&** à URL do AOS (Servidor de Objetos de Aplicativo) e, em seguida, atualize a página.
2. Quando você seleciona **Impostos** para calcular o imposto, um arquivo de texto chamado **TaxServiceTroubleshootingLog.txt** é aberto. O arquivo **TaxServiceTroubleshootingLog.txt** contém **TaxableDocument** e o parâmetro de cálculo. Esses resultados são retornados do serviço de imposto e das informações de exceção para a solução de problemas.

## <a name="sample"></a>Exemplo

```json
===============================Tax service calculation input JSON:=====================================
{
    "TaxableDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Transaction Line ID": "5816,68719677391",
            ...
            }
        ],
        "Transaction Header ID": "2022,68719506302",
        ...
        }
    ]
    },
    "Parameter": {
    "ContinueOnErrors": true,
    ...
    },
    "Adjustment": {
    "Lines": {}
    }
}
===========================Tax service calculation result JSON:=================================
{
    "taxDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Tax Codes": {
                ...
            }
        ],
        "Measures": {
            "List Code": "EUTrade"
        },
        "Tax Registration ID": null,
        "Transaction Header ID": "2022,68719506302",
        "Errors": null
        }
    ]
    },
    "solutionId": "b51e0025-cbbe-4d37-bf0b-90d7be4f214d|1",
    "isPartialSuccess": false
}
=============================CorrelationId:==============================
"21f3a8a1-ee9a-477b-b44e-b8ec79e74d16"
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
