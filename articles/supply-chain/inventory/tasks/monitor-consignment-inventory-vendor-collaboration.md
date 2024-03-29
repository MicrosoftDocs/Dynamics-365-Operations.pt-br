---
title: Monitorar o estoque de consignação usando a colaboração de fornecedor
description: Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0d194728805cd1eee741069538352b497867981
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571824"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Monitorar o estoque de consignação usando a colaboração de fornecedor

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente. Também é possível monitorar o consumo de estoque quando o cliente tem a propriedade do estoque. Você pode usar este procedimento na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Exibir estoque consumido
1. Acesse Colaboração do fornecedor > Estoque de consignação > Produtos recebidos de estoque de consignação.
    * A lista mostra as linhas do recebimento de produtos geradas quando a propriedade do estoque foi alterada de remessa do fornecedor para o cliente. Pode ser necessário rolar à direita para consultar as quantidades e outras informações. Você pode usar informações nesta lista para gerar notas fiscais para o cliente. Você também pode exportar dados para o Microsoft Excel.   
2. Clique em Visualizar ordem de compra.
3. Expanda a seção Detalhes da linha.
    * A linha é marcada como a remessa e, na seção do cabeçalho que mostra a ordem de compra tiver um status de recebimento.  
4. Feche a página.

## <a name="view-on-hand-inventory"></a>Exibir estoque disponível
1. Acesse Colaboração do fornecedor > Estoque de consignação > Estoque de consignação disponível.
    * Disponível a página de remessa de estoque mostra o estoque que você possui em depósito de cliente. Você pode mostrar dimensões adicionais, como o site e o depósito, clique na guia dimensões de exibição.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]