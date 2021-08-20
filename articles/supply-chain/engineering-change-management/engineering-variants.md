---
title: Gerar grades para produtos de engenharia
description: Este tópico descreve como gerar grades para produtos de engenharia
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 57eda6a833df6ff8e91c006bbc5096554eff6c503a8b7ba2bd0b13e2f8e98f56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766137"
---
# <a name="generate-variants-for-engineering-products"></a>Gerar grades para produtos de engenharia

[!include [banner](../includes/banner.md)]

Este tópico descreve como gerar grades para produtos de engenharia.

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Gerar uma ou mais variantes novas de um produto de engenharia

Você pode criar uma ou mais variantes novas de um produto sem copiar informações de um produto existente. Isso é útil quando você precisa criar mais de uma variante de produto ao mesmo tempo.

O procedimento a seguir fornece um exemplo de como criar várias grades que incluem a dimensão de cor.

1. Abra a página **Produtos liberados** (por exemplo, Acesse a **Gerenciamento de engenharia de alterações \> Comum \> Produtos liberados**).
1. No Painel de Ações, abra a guia **Produto** e, no grupo **Novo**, selecione **Produto de engenharia**.
1. A caixa de diálogo **Novo produto** será aberta. Selecione a **Categoria de engenharia** apropriada.
1. Se a categoria de engenharia selecionada incluir dimensões de grade, você poderá definir valores para elas agora. Neste exemplo, se a categoria tiver uma dimensão de **Cor**, você poderá defini-la como *Azul*.
1. Faça outras configurações, conforme necessário. Selecione **OK** para criar o produto.
1. O produto e a grade de V-1 azul são criados e o novo produto é aberto.
1. Adicione uma BOM (lista de materiais) e um roteiro para a grade, conforme necessário.
1. No Painel de Ações, abra a guia **Produto**, no grupo **Produto mestre**, selecione **Dimensões do produto**.
1. A página **Dimensões do produto** é aberta. Esta página inclui uma guia para cada dimensão disponível. Em cada guia, adicione uma linha para cada valor que terá suporte para cada dimensão relevante. (Neste exemplo, você pode adicionar linhas na guia **Cor** para *Branco*, *Amarelo* e *Verde*).
1. Feche a página e selecione **Variantes de produtos liberados**. Observe que a primeira grade criada (V-1 branco) é exibida.
1. Selecione **Sugestões de variações**.
1. O sistema sugere variantes com os valores de cor criados (por exemplo, V-1 branco, V-1 amarelo e verde V-1).
1. Selecione as variantes sugeridas e selecione **OK** para liberar as variantes para a empresa de engenharia. As seguintes condições se aplicam: 
    - Nenhuma das variantes criadas terá uma BOM ou um roteiro.
    - Os atributos dessas variantes serão padronizados a partir da categoria de engenharia e não serão copiados da variante anterior.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Gerar uma grade como uma cópia de outra grade de produto

Você pode criar uma variante de um produto com base em outra grade de produto. A BOM (lista de materiais) e o roteiro da grade do produto de origem são copiados para a nova grade. Isso pode ser útil para produtos de fabricação dedicados que se beneficiem da criação da BOM com base em uma BOM inicial e manter o controle das alterações da grade anterior. Para manter o rastreamento, o sistema registra que grade foi copiada para criar uma nova cópia.

O procedimento a seguir fornece um exemplo de como criar uma nova grade que inclui a dimensão de cor criando uma cópia de uma grade existente

1. Abra a página **Produtos liberados** (por exemplo, Acesse a **Gerenciamento de engenharia de alterações \> Comum \> Produtos liberados**).
1. No Painel de Ações, abra a guia **Produto** e, no grupo **Novo**, selecione **Produto de engenharia**.
1. A caixa de diálogo **Novo produto** será aberta. Selecione a **Categoria de engenharia** apropriada.
1. Se a categoria de engenharia selecionada incluir dimensões de grade, você poderá definir valores para elas agora. Neste exemplo, se a categoria tiver uma dimensão de **Cor**, você poderá defini-la como *Azul*.
1. Faça outras configurações, conforme necessário. Selecione **OK** para criar o produto.
1. O produto e a grade de V-1 azul são criados e o novo produto é aberto.
1. Adicione uma BOM (lista de materiais) e um roteiro para a grade conforme necessário.
1. Adicione atributos à grade de produto conforme necessário.
1. Adicione a grade de produto azul V-1 a uma ordem de alteração de engenharia.
1. Defina **Impacto** como *Nova grade*.
1. Selecione o novo valor de cor (por exemplo, *Branco*). As seguintes condições se aplicam: 
    - A nova grade tem uma BOM e um roteiro que foram copiados da grade anterior.
    - A nova grade tem os atributos copiados da grade anterior.
1. Aprove a ordem de alteração.
1. Processe a ordem de alteração. Depois que a ordem for processada, a nova grade V-1 será criada e liberada para a empresa de engenharia.
