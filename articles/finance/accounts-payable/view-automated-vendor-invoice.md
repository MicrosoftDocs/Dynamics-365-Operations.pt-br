---
title: Exibir resultados da automação de fatura de fornecedor (versão preliminar)
description: Este artigo explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd9b74d2ed34399aff455563504c296a5a25a874
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895157"
---
# <a name="view-vendor-invoice-automation-results"></a>Exibir resultados da automação de fatura de fornecedor

[!include [banner](../includes/banner.md)]

Este artigo explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado. Os detalhes do histórico de automação são mantidos para cada fatura de fornecedor importada. Dependendo dos processos comerciais que você automatizou, a página **Faturas de fornecedor pendentes** mostra o **Status de correspondência automática de recibo** e o **Status de envio para fluxo de trabalho automatizado**. Você pode exibir os detalhes e fazer um plano para focar nas faturas que falharam em uma etapa automatizada. Em seguida, depois de corrigir o problema, você poderá retomar o processo automatizado para a fatura importada.

Para poder editar uma fatura que foi enviada, você deve pausar o processamento automatizado. Se uma fatura no processo de envio para fluxo de trabalho automatizado precisar ser pausada, defina o campo **Incluir no processamento automatizado** como **Não** na página **Faturas do fornecedor**. A automação não será executada até que a opção **Incluir no processamento automatizado** seja definida como **Sim**. Uma fatura pode ser pausada da automação adicional, se ainda não estiver no sistema do fluxo de trabalho e não for usada pelo processo automatizado.

Se uma fatura importada estiver sujeita ao processo de envio para o fluxo de trabalho, você poderá exibir seu valor de **Status de automação** na página **Faturas do fornecedor**. Os seguintes status são rastreados:

- **Incluído** – os processos automatizados definidos na página **Parâmetros de contas a pagar** estão sendo executados corretamente, mas ainda não foram preenchidos.
- **Pausado** – os processos automatizados definidos na página **Parâmetros de contas a pagar** foram executados, mas pelo menos uma etapa no processo falhou. O status **Pausado** também é aplicado se o campo **Incluir no processamento automatizado** estiver definido como **Não**. Você pode exibir as falhas selecionando o botão **Exibir resultados mais recentes**.
- **No fluxo de trabalho** – a fatura importada foi enviada para o sistema de fluxo de trabalho, seja pelo processo de envio para fluxo de trabalho automatizado ou manualmente.
- **Fluxo de trabalho concluído** – o processo de fluxo de trabalho foi concluído para a fatura importada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
