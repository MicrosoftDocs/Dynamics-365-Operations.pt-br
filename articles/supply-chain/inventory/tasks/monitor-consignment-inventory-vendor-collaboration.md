---
title: Monitorar o estoque de consignação usando a colaboração de fornecedor
description: Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente.
author: sherry-zheng
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: chuzheng
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92e397c12b9f605d1c864ce053477090ed8c1700
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839262"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Monitorar o estoque de consignação usando a colaboração de fornecedor

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente. Também é possível monitorar o consumo de estoque quando o cliente tem a propriedade do estoque. Você pode usar este procedimento na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Exibir estoque consumido
1. Vá para Colaboração do fornecedor > Estoque de consignação > Produtos recebidos de estoque de consignação.
    * A lista mostra as linhas do recebimento de produtos geradas quando a propriedade do estoque foi alterada de remessa do fornecedor para o cliente. Pode ser necessário rolar à direita para consultar as quantidades e outras informações. Você pode usar informações nesta lista para gerar notas fiscais para o cliente. Você também pode exportar dados para o Microsoft Excel.   
2. Clique em Visualizar ordem de compra.
3. Expanda a seção Detalhes da linha.
    * A linha é marcada como a remessa e, na seção do cabeçalho que mostra a ordem de compra tiver um status de recebimento.  
4. Feche a página.

## <a name="view-on-hand-inventory"></a>Exibir estoque disponível
1. Vá para Colaboração do fornecedor > Estoque de consignação > Estoque de consignação disponível.
    * Disponível a página de remessa de estoque mostra o estoque que você possui em depósito de cliente. Você pode mostrar dimensões adicionais, como o site e o depósito, clique na guia dimensões de exibição.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]