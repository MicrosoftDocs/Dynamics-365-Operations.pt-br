---
title: Métodos de reabastecimento e modificação de quantidade
description: Este tópico fornece informações sobre os métodos de reabastecimento na Otimização de Planejamento. Também explica como a quantidade múltipla de ordens de um produto afeta o resultado.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19853bdb3c469dbfea3a3a0165a9cb5f47e73122cc695de3535a58f6e65e7933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759518"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Métodos de reabastecimento e modificação de quantidade

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações sobre os métodos de reabastecimento na Otimização de Planejamento. Também explica como a quantidade múltipla de ordens de um produto afeta o resultado.

Os métodos de reabastecimento também são conhecidos como métodos de cobertura e métodos de dimensionamento de lotes.

## <a name="coverage-codes"></a>Códigos de cobertura

A Otimização de Planejamento pode ser configurada para usar diversos métodos de reabastecimento. Os métodos de reabastecimento são as técnicas que o sistema usa para calcular os requisitos de um produto. Os métodos de reabastecimento são definidos por códigos de cobertura que você pode configurar no grupo de cobertura ou no produto.

Os seguintes códigos de cobertura podem ser usados na Otimização de Planejamento:

- **Período** - O método de reabastecimento combina toda a demanda de um período em uma ordem para o produto. A ordem será planejada para o primeiro dia do período e sua quantidade preencherá as requisições líquidas durante o período estabelecido. O período começa com a primeira a demanda do produto e abrange o tempo definido. O período seguinte começará com as requisições seguintes do produto. O código de cobertura *Período* é usado frequentemente para emissão de inventário não previsível, produtos sazonais ou produtos de alto custo. A ilustração a seguir mostra um exemplo.

    ![Exemplo de uso do Código de cobertura de período.](./media/coverage-code-period.png "Exemplo de uso do Código de cobertura de período")

- **Requisito** - No método de reabastecimento, o sistema cria uma ordem de compra, transferência ou produção planejada por requisição do produto. Este método é usado para produtos caros que têm demanda intermitente. O código de cobertura *Requisito* é usado frequentemente para produtos configuráveis ou cenários de produção por ordem. A ilustração a seguir mostra um exemplo.

    ![Exemplo de uso do Código de cobertura de requisito.](./media/coverage-code-requirement.png "Exemplo de uso do Código de cobertura de requisito")

- **Mín./Máx.** – O método de reabastecimento baseia-se no nível de inventário. Ele define o reabastecimento do inventário até um nível específico quando o nível previsto disponível estiver abaixo de um limite específico. A quantidade do reabastecimento será a diferença entre o nível máximo e o nível disponível previsto. O código de cobertura *Mín./Máx.* é frequentemente usado para sorteio de inventário previsível, corredores altos ou produtos mais baratos. A ilustração a seguir mostra um exemplo.

    ![Exemplo de uso do Código de cobertura Mín./Máx.](./media/coverage-code-min-max.png "Exemplo de uso do Código de cobertura Mín./Máx.")

- **Manual** - No método de reabastecimento, o sistema não sugere ordens de compra, transferência ou produção para o produto. Em vez disso, o planejador do produto é responsável pela criação dos pedidos necessários para a reposição do produto. O código de cobertura *Manual* é usado frequentemente para produtos para os quais as ordens planejadas geradas pelo sistema não são desejadas.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Impacto da quantidade de pedidos das configurações padrão do pedido

Na página **Configuração de ordem padrão** para um produto liberado, você pode especificar cada uma das seguintes configurações de quantidade nas FastTabs **Ordem de compra**, **Inventário** e **Ordem de vendas**. (A FastTab **Inventário** é usada tanto para ordens de transferência quanto para ordens de produção.)

- **Múltiplo** – As ordens planejadas serão múltiplos dessa quantidade.

    Por exemplo, se o campo **Múltiplo** for definido como *5*, uma ordem pode ser para uma quantidade de 5, 10, 15, 20, e assim por diante.

- **Quantidade mínima da ordem** – As ordens planejadas não serão inferiores ao valor especificado.

    Por exemplo, se o campo **Quantidade mínima da ordem** for definido como *10*, uma ordem planejada para uma quantidade de 10 itens será criada, mesmo que apenas quatro sejam necessários para atender à demanda.

- **Quantidade máxima da ordem** – As ordens planejadas não serão superiores ao valor especificado. Se a demanda for maior do que o valor **Quantidade máx. da ordem**, ordens planejadas de múltiplo serão criadas para atender essa demanda.

    Por exemplo, se o campo **Quantidade máx. da ordem** for definido como *100*, e a demanda for 450, quatro ordens planejadas para uma quantidade de 100 e uma ordem planejada para a quantidade de 50 serão criadas.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Exemplos de reabastecimentos que usam o código de cobertura Mín./Máx.

Se você não especificar um valor no campo **Múltiplo** para um produto na página de **Configuração de ordem padrão** e se você estiver usando o método de reabastecimento *Mín./Máx.*, a Otimização de Planejamento reabastecerá o inventário até um nível específico quando o nível disponível previsto estiver abaixo de um limite específico.

Se você definir uma quantidade múltipla para um produto, o método de reabastecimento *Mín./Máx.* mudará seu comportamento e considerará o valor **Múltiplo**.

Em outras palavras, a Otimização de Planejamento ainda reabastecerá o inventário até o nível máximo definido quando o nível previsto disponível for inferior ao nível mínimo definido. No entanto, a quantidade de reabastecimento deve ser um múltiplo do valor de **Múltiplo**.

Se a quantidade de reabastecimento (a diferença entre o nível máximo e o nível previsto disponível) não for um múltiplo da quantidade múltipla definida, a Otimização de Planejamento usará o primeiro valor possível que, juntamente com o nível previsto disponível, esteja abaixo do nível máximo. Se a soma for inferior ao nível mínimo, a Otimização de Planejamento utilizará o primeiro valor que, juntamente com o previsto disponível, estiver acima do nível máximo.

As seguintes subseções fornecem alguns exemplos que mostram como o resultado do método de reabastecimento *Mín./Máx.* é afetada pela quantidade múltipla da ordem para um produto.

### <a name="example-1"></a>Exemplo 1

Um produto tem a seguinte configuração:

- **Código de cobertura:** *Mín./Máx.*
- **Mínimo:** *15*
- **Máximo:** *22*
- **Múltiplo:** *0*

Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.

Quando o planejamento mestre é executado, uma ordem planejada para 12 itens é criada para reabastecer o inventário até a quantidade máxima.

### <a name="example-2"></a>Exemplo 2

Um produto tem a seguinte configuração:

- **Código de cobertura:** *Mín./Máx.*
- **Mínimo:** *15*
- **Máximo:** *22*
- **Múltiplo:** *5*

Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.

Quando o planejamento mestre é executado, uma ordem planejada para 10 itens é criada (porque 15 itens de reabastecimento mais 10 itens de inventário manual excederão a quantidade máxima).

### <a name="example-3"></a>Exemplo 3

Um produto tem a seguinte configuração:

- **Código de cobertura:** *Mín./Máx.*
- **Mínimo:** *21*
- **Máximo:** *24*
- **Múltiplo:** *5*

Há 10 itens de inventário disponível para o produto, e não há outra demanda ou oferta.

Quando o planejamento mestre é executado, a ordem planejada para 15 itens é criada (porque 10 itens de reabastecimento mais 10 itens de inventário manual serão inferiores que a quantidade mínima).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
