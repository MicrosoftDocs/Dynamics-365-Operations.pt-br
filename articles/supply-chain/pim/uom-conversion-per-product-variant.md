---
title: Conversão de unidade de medida por grade de produto
description: Este tópico explica como configurar conversões de unidade de medida para grades do produto. Ele iInclui um exemplo da instalação.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: eaa20f9a8f145fa8d44bfe77cc85f4dc565c2d27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841494"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversão de unidade de medida por grade de produto

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar conversões de unidade de medida para várias grades do produto.

Em vez de criar vários produtos individuais que devem ser mantidos, você pode usar variantes de produto para criar variações de um único produto. Por exemplo, uma grade de produto pode ser uma camiseta de um determinado tamanho e cor.

Anteriormente, as conversões de unidades podiam ser configuradas somente no produto mestre. Portanto, todas as grades de produto tinham as mesmas regras de conversão de unidades. No entanto, quando o recurso *Conversões de unidade de medida para variantes de produto* são ativadas, se suas camisas forem vendidas em caixas e o número de camisas que podem ser embaladas em uma caixa depender do tamanho das camisetas, você poderá configurar conversões de unidade entre os tamanhos de camisa diferentes e as caixas usadas para a embalagem.

## <a name="turn-on-the-feature-in-your-system"></a>Ative o recurso no seu sistema

Se você ainda não tiver visto esse recurso no sistema, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Conversões de unidade de medida para variantes de produtos*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurar um produto para a conversão de unidade por grade

Grades de produto só podem ser criadas para produtos que são produtos mestre. Para obter mais informações, consulte [Criar um produto mestre](tasks/create-product-master.md). O recurso *Conversões de unidade de medida para variantes de produto* não estão disponíveis para os produtos que estão configurados para processos de peso variável.

Para configurar um produto mestre para oferecer suporte à conversão de unidades por grade, siga estas etapas.

1. Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.
1. Crie ou abra um produto mestre para ir para a **Página detalhes do produto**.
1. Defina a opção **Habilitar conversões de unidade de medida** como *Sim*.
1. No Painel de Ações, na guia **Produto**, no grupo **Configuração**, selecione **Conversões de unidade**.
1. A página **Conversões de unidade** é aberta. Selecione uma das guias a seguir:

    - **Conversões entre classes** – Selecione esta guia para converter entre as unidades que pertencem à mesma classe de unidade.
    - **Conversões entre classes** – Selecione esta guia para converter entre as unidades que pertencem à classes de unidade diferentes.

1. Selecione **Novo** para adicionar uma nova conversão de unidade.
1. Defina o campo **Criar conversão para** como um dos seguintes valores:

    - **Produto** – Se você selecionar esse valor, você pode configurar uma conversão de unidade para os produtos mestres. Essa conversão de unidade será usada como um fallback para todas as grades de produto para as quais nenhuma conversão de unidade é definida.
    - **Grade de produto** – Se você selecionar esse valor, você pode configurar uma conversão de unidade para uma grade de produto específica. Use o campo **Grade do produto** para selecionar a grade.

    ![Adicionando uma nova conversão de unidades](media/uom-new-conversion.png "Adicionando uma nova conversão de unidades")

1. Use os outros campos fornecidos para configurar a conversão de unidades.
1. Selecione **OK** para salvar a nova conversão de unidades.

> [!TIP]
> Você pode abrir a página **Conversões de unidade** para um produto ou uma grade de produto em qualquer uma das páginas a seguir:
> 
> - Detalhes do produto
> - Detalhes de produtos liberados
> - Grades de produtos liberadas

## <a name="example-scenario"></a>Cenário de exemplo

Nesse cenário, uma empresa vende camisetas nos tamanhos pequeno, médio, grande e extra grande. A camiseta é definida como um produto; os diferentes tamanhos são definidos como grades desse produto. As camisas estão embaladas nas caixas. Para tamanhos pequenos, médios e grandes, pode haver cinco camisas em cada caixa. No entanto, para o tamanho extra-grande, há espaço para apenas quatro camisas em cada caixa.

A empresa deseja rastrear as diferentes grades das camisetas na unidade em *Peças* mas está vendendo as camisetas na unidade *Caixas*. Para tamanhos pequenos, médios e grandes, a conversão entre a unidade de estoque e a unidade de vendas é de 1 caixa = 5 peças. Para tamanho extra-grande, a conversão é 1 caixa = 4 peças.

1. Na página **Detalhes de produto lançados** do produto **Camisa**, abra a página **Conversões de unidade**.
1. Na página **Conversões de unidades**, configure a conversão de unidades a seguir para a grade de produtos liberados **Extra Grande**.

    | Campo                 | Configuração                 |
    |-----------------------|-------------------------|
    | Criar conversão para | Grade de produto         |
    | Grade de produto       | Camiseta: : extra grande: : |
    | De unidade             | Caixas                   |
    | Fator                | 4                       |
    | Para unidade               | Peças                  |

1. Como as grades de produto **Pequeno**, **Médio** e **Grande** têm a mesma conversão de unidade entre unidades *Caixa* e *Peças*, você pode definir a conversão de unidade a seguir para elas no produto mestre.

    | Campo                 | Configuração |
    |-----------------------|---------|
    | Criar conversão para | Produto |
    | Produto               | Camiseta |
    | De unidade             | Caixas   |
    | Fator                | 5       |
    | Para unidade               | Partes  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Usando o Excel para atualizar as conversões de unidade

Se um produto tiver muitas grades de produto com diferentes conversões de unidade, é uma boa ideia exportar as conversões de unidade para uma pasta de trabalho do Microsoft Excel, atualizá-las e publicá-las novamente no Dynamics 365 Supply Chain Management.

Para exportar conversões de unidade para o Excel, na página **Conversões de unidade**, no Painel de Ações, selecione **Abrir em Microsoft Office**.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar unidade de medida](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]