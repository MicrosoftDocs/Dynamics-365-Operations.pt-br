---
title: Itens fantasma
description: Este tópico descreve como o tipo de linha fantasma pode ser usado para as linhas de uma lista de materiais (BOM) e uma fórmula no Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5c9768381d35709611e4bec3d2b7793a4d896b34
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713236"
---
# <a name="phantom-items"></a>Itens fantasma

[!include [banner](../includes/banner.md)]

Este tópico descreve, em detalhes, como o tipo de linha fantasma pode ser usado para as linhas de uma lista de materiais (BOM) e uma fórmula.

Na figura 1, (a) é a BOM dos produtos H e peças F e G, e (b) é a planilha de roteiro dos produtos H e peça F.

![Figura 1: BOM de engenharia.](media/product-H-part-F.png)
*Figura 1: BOM de engenharia*

A figura 1 mostra um exemplo de uma estrutura de BOM em dois níveis. O produto finalizado H representa um produto para uma montagem de máquina. A montagem da máquina consiste em duas peças, uma unidade elétrica (F) que tem dois materiais (A e B) e um grupo de materiais de embalagem (G) que também tem dois materiais (C e D). Outro material (E) é usado durante a montagem geral da máquina.

A figura 1 representa a BOM de engenharia para o produto. H. Esta estrutura para fornece uma visão geral das peças e componentes da montagem geral da máquina. Entretanto, embora talvez os designers de produtos prefiram ver a BOM representada dessa maneira, é possível que essa estrutura não represente corretamente a maneira que máquina é criada no chão de fábrica.

Por exemplo, a BOM de engenharia na figura 1 indica que a unidade elétrica F é montada como uma parte separada em uma ordem de trabalho separada. Entretanto, no chão de fábrica, pode ser considerado melhor montar a unidade elétrica como parte da montagem geral da máquina, não como uma ordem de trabalho separada.

Essa BOM de engenharia também indica que a peça G é uma peça separada. Entretanto, nessa estrutura, a peça G não representa uma peça física, mas sim uma coleção de materiais de embalagem.

Portanto, apesar de uma BOM de engenharia agregar muito valor para a criação de um produto e a manutenção desse design, essa talvez não seja a maneira mais lógica de oferecer suporte ao processo de execução da fabricação do produto. Em contraste, uma BOM de fabricação representa a melhor maneira de criar um produto.

A figura 2 mostra como a é feita a transição da BOM de engenharia anterior para uma BOM de fabricação. Na figura 2, (a) é a BOM do produto H, e (b) é a planilha de roteiro do produto H.

![Figura 2: BOM de fabricação.](media/product-H-part-B.png)
*Figura 2: BOM de fabricação*

Nesta estrutura, você verá que não há uma noção de peças F e G, e os materiais em que essas peças consistem foram elevados para o próximo nível de BOM.

Diferentemente da BOM de engenharia, que tinha duas planilhas de operações, a BOM de fabricação tem apenas uma planilha de operações. A operação de embalagem que foi vinculada à peça G também foi elevada e agora faz parte da planilha de operações do produto. H. A montagem da unidade elétrica é a primeira operação. Essa ordem faz sentido, porque essa unidade é usada na operação seguinte, a montagem da máquina. A última operação é a operação de embalagem, que consume dois materiais de embalagem (C e D).

A transição entre a BOM de engenharia e a BOM de fabricação é habilitada por meio do tipo de linha fantasma da BOM. Como o termo “fantasma” já indica, as peças F e G desapareceram durante a transição entre os dois tipos de BOM. Neste exemplo, o tipo de linha fantasma será aplicado às linhas de BOM das peças F e G na BOM de engenharia. Quando uma ordem de produção ou de lote é criada, a BOM de engenharia é copiada na ordem de produção ou de lote. Em seguida, quando a ordem é estimada, ocorre a transição da BOM de engenharia para a BOM de fabricação, conforme mostrado na figura 2. Na planilha de operações da figura 2, os materiais de embalagem C e D são inseridos para a operação.

## <a name="multilevel-phantom-bom-structures"></a>Estruturas fantasma de BOM de vários níveis

O tipo de linha fantasma pode ser usado em estruturas de BOM de vários níveis, conforme mostrado na figura 3. Na figura 3, (a) é a BOM do produto G, e (b) é a planilha de roteiro das peças E e F e do produto G.

![Figura 3: BOM de engenharia peça G.](media/product-G.png)
*Figura 3: BOM de engenharia peça G*

A figura 4 mostra a BOM de fabricação e a planilha de roteiro resultantes se as linhas da BOM das peças E e F são configuradas para que o tipo de linha seja fantasma. Na figura 4, (a) é a BOM do produto G, e (b) é a planilha de roteiro do produto G.

![Figura 4: BOM de fabricação peça G.](media/product-G-route-sheet-G.png)
*Figura 4: BOM de fabricação peça G*

## <a name="phantom-and-route-network"></a>Rede de roteiro e fantasma

As BOMs fantasma também podem ser usadas para uma BOM com uma rede de roteiro. Em uma rede de roteiro, uma ou várias operações são executadas em paralelo. A figura 5 mostra um exemplo de uma rede de roteiro usada em uma BOM de vários níveis. Na figura 5, (a) é a BOM do produto G e peça F, e (b) é a planilha de roteiro do produto G e peça F, que tem uma rede de roteiro.

![Figura 5: BOM de engenharia peça G, rede de roteiro.](media/product-G-part-F.png)
*Figura 5: BOM de engenharia peça G, rede de roteiro*

Na figura 6, (a) é a BOM do produto G e peça F, e (b) é a planilha de roteiro do produto G e peça F.

![Figura 6: BOM de fabricação peça G, rede de roteiro.](media/product-G-part-F-with-route-sheet.png)
*Figura 6: BOM de fabricação peça G, rede de roteiro*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]