---
title: Pode ocorrer a finalização da compra para itens sem estoque
description: Este artigo fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 3bc924e44077886b942e19b25a84f0f1d4298c13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282725"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Pode ocorrer a finalização da compra para itens sem estoque

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.

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
