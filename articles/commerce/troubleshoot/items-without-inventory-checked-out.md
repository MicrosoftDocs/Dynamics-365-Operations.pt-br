---
title: Pode ocorrer a finalização da compra para itens sem estoque
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585193"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Pode ocorrer a finalização da compra para itens sem estoque

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.

## <a name="description"></a>descrição

Os usuários podem adicionar um item ao seu carrinho, mesmo que não haja estoque disponível na loja e, em seguida, prosseguir para a página de finalização da compra.

## <a name="resolution"></a>Resolução

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Habilitar a propriedade Mostrar Erros de Estoque Insuficiente no construtor de sites do Commerce

Para ativar a propriedade **Mostrar Erros de Estoque Insuficiente** no construtor de sites do Commerce, siga estas etapas.

1. Selecione o site no qual você está trabalhando.
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Selecione **CartPage** para abri-la.
1. Selecione o slot **Carrinho 1**, selecione **Editar** e, no painel Propriedades, marque a caixa de seleção **Mostrar Erros de Estoque Insuficiente**.
1. Salve e publique a página.

## <a name="additional-resources"></a>Recursos adicionais

[Aplicar configurações de estoque](../inventory-settings.md)

[Calcular disponibilidade de estoque para canais de varejo](../calculated-inventory-retail-channels.md)

[Configurar buffers de estoque e níveis de estoque](../inventory-buffers-levels.md)