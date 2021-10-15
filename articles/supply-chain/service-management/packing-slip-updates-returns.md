---
title: Atualizações de guia de remessa para devoluções
description: Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f586537aa2d4cb47b0e55e76e401ea6852e1d60
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580375"
---
# <a name="packing-slip-updates-for-returns"></a>Atualizações de guia de remessa para devoluções  

[!include [banner](../includes/banner.md)]


Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada. Assim como o processo de atualização da fatura é a atualização da transação financeira, o processo de atualização da guia de remessa é a atualização física do registro do estoque, o que significa que ele efetua as alterações no estoque. No caso de devoluções, as etapas atribuídas à ação de disposição são implementadas durante a atualização da guia de remessa.

A atualização da guia de remessa pode ser processada no diário de entrada de itens ou na ordem de devolução.

Como parte do processo de lançamento da guia de remessa, o número de referência da guia de remessa dos documentos de remessa do cliente pode ser associado opcionalmente às linhas de ordem. Essa associação é opcional e serve somente como referência. Ela não cria nenhuma atualização transacional.

Se nem todos os itens de devolução esperados foram recebidos, você deverá incluir somente a quantidade recebida na atualização da guia de remessa. Deixe os itens restantes na ordem até que o resto da remessa de devolução seja recebida.

Se um item for devolvido da quarentena para o departamento de Remessa e Recebimento, como quando o inspetor de quarentena não sabe onde deve armazenar o item no estoque, a guia de remessa correspondente deverá ser atualizada de forma a registrar corretamente e agir no código de disposição especificado como resultado da quarentena.

Ao atualizar uma guia de remessa de um item devolvido que é de um contrato de venda, o compromisso do contrato de venda para esse item é atualizado automaticamente de modo a refletir as alterações na quantidade ou no valor. 

## <a name="see-also"></a>Consulte também

[Executar atualizações de fatura para devoluções](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]