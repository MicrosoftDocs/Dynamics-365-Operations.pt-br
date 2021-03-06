---
title: Exibir resultados da automação de fatura de fornecedor (versão preliminar)
description: Este tópico explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 872ec404da0cce41c4ea0f882a3fa8af56316ce3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837216"
---
# <a name="view-vendor-invoice-automation-results"></a>Exibir resultados da automação de fatura de fornecedor

[!include [banner](../includes/banner.md)]

Este tópico explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado. Os detalhes do histórico de automação são mantidos para cada fatura de fornecedor importada. Dependendo dos processos comerciais que você automatizou, a página **Faturas de fornecedor pendentes** mostra o **Status de correspondência automática de recibo** e o **Status de envio para fluxo de trabalho automatizado**. Você pode exibir os detalhes e fazer um plano para focar nas faturas que falharam em uma etapa automatizada. Em seguida, depois de corrigir o problema, você poderá retomar o processo automatizado para a fatura importada.

Para poder editar uma fatura que foi enviada, você deve pausar o processamento automatizado. Se uma fatura no processo de envio para fluxo de trabalho automatizado precisar ser pausada, defina o campo **Incluir no processamento automatizado** como **Não** na página **Faturas do fornecedor**. A automação não será executada até que a opção **Incluir no processamento automatizado** seja definida como **Sim**. Uma fatura pode ser pausada da automação adicional, se ainda não estiver no sistema do fluxo de trabalho e não for usada pelo processo automatizado.

Se uma fatura importada estiver sujeita ao processo de envio para o fluxo de trabalho, você poderá exibir seu valor de **Status de automação** na página **Faturas do fornecedor**. Os seguintes status são rastreados:

- **Incluído** – os processos automatizados definidos na página **Parâmetros de contas a pagar** estão sendo executados corretamente, mas ainda não foram preenchidos.
- **Pausado** – os processos automatizados definidos na página **Parâmetros de contas a pagar** foram executados, mas pelo menos uma etapa no processo falhou. O status **Pausado** também é aplicado se o campo **Incluir no processamento automatizado** estiver definido como **Não**. Você pode exibir as falhas selecionando o botão **Exibir resultados mais recentes**.
- **No fluxo de trabalho** – a fatura importada foi enviada para o sistema de fluxo de trabalho, seja pelo processo de envio para fluxo de trabalho automatizado ou manualmente.
- **Fluxo de trabalho concluído** – o processo de fluxo de trabalho foi concluído para a fatura importada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]