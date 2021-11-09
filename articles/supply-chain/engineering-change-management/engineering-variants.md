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
ms.openlocfilehash: e24bceac9457212ecaafda876d19ba62df049371
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7471827"
---
# <a name="generate-variants-for-engineering-products"></a>Gerar grades para produtos de engenharia

[!include [banner](../includes/banner.md)]

Este tópico descreve como gerar grades para produtos de engenharia.

## <a name="turn-on-variant-generation-for-engineering-products"></a>Ativar a geração de grades para produtos de engenharia

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de alteração de engenharia*
- **Nome do recurso:** *Geração de grades para produtos de engenharia*

> [!IMPORTANT]
> O recurso *Geração de grade para produtos de engenharia* ficará visível no seu sistema somente depois que você habilitar a chave de configuração *Gerenciamento de alterações de engenharia* . Para obter instruções, consulte [Visão geral do gerenciamento de alteração de engenharia](product-engineering-overview.md).

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
1. Feche a página e, em seguida, selecione **Grades de produtos liberadas**. Observe que a primeira grade criada (azul V-1) é exibida.
1. No Painel de Ações, na guia **Grade de produto**, selecione **Sugestões de grades**.
1. Na caixa de diálogo **Sugestões de grade** , siga uma destas etapas:

    - Na parte superior da caixa de diálogo, há uma seção para cada dimensão disponível. Para cada dimensão, marque a caixa de seleção de cada valor para o qual você deseja gerar uma sugestão de grade e, em seguida, selecione **Sugerir** na barra de ferramentas. As sugestões relevantes são adicionadas à seção **Grades sugeridas**.
    - Selecione **Sugerir tudo** na barra de ferramentas para gerar sugestões de grade para todas as combinações disponíveis de valores de dimensão. As sugestões são adicionadas à seção **Grades sugeridas**.

1. Na seção **Grades sugeridas**, marque a caixa de seleção de cada grade que deseja criar. Em seguida, selecione **Criar** para gerar e liberar as grades selecionadas para a empresa de engenharia. As seguintes condições se aplicam:

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
