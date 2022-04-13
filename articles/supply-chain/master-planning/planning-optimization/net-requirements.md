---
title: Requisitos líquidos e informações de vinculação com a Otimização de Planejamento
description: Este tópico fornece informações sobre os requisitos líquidos e as informações de vinculação calculadas na Otimização do Planejamento.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: edfa6010074a4b04b3200115891723cd45871624
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468850"
---
# <a name="net-requirements-and-pegging-information-with-planning-optimization"></a>Requisitos líquidos e informações de vinculação com a Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Quando você executa o planejamento mestre na Otimização de Planejamento, é importante que você compreenda a saída deste recurso, a forma como o fornecimento existente cobre a demanda e por que um fornecimento específico foi gerado. Você pode usar a página **Requisitos líquidos** para compreender melhor os requisitos calculados que o planejamento mestre gera.

A página **Requisitos líquidos** mostra os requisitos líquidos que a Otimização de Planejamento calculou para o produto. Isso também mostra as configurações de cobertura que foram aplicadas durante a execução do planejamento mestre, um detalhamento dos requisitos totais por tipo de transação e informações sobre vinculação.

## <a name="open-the-net-requirements-page"></a>Abrir a página Requisitos líquidos

Você pode abrir a página **Requisitos líquidos** de uma das seguintes maneiras:

- Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**. Selecione ou abra um produto. Depois, no Painel de Ação, na guia **Plano**, no grupo **Requisito**, selecione **Requisitos líquidos**.
- Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**. Abra uma ordem de venda. Em seguida, na FastTab **Linhas da ordem de venda**, na barra de ferramentas, selecione **Produto e fornecimento \> Requisitos líquidas**.
- Acesse **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**. Selecione ou abra uma ordem planejada. Depois, no Painel de Ação, na guia **Exibir**, no grupo **Requisitos**, selecione **Perfil de requisito**.

## <a name="use-the-net-requirements-page"></a>Usar a página Requisitos líquidos

A página **Requisitos líquidos** consiste nas seções superior e inferior. O painel de ações desta página inclui um botão **Atualizar**. Quando este botão é selecionado, um menu de comandos é exibido.

### <a name="select-a-master-plan-to-view"></a>Selecionar um plano mestre a ser exibido

Antes de revisar os requisitos líquidos do produto, certifique-se de selecionar o plano mestre relevante no campo **Plano** na parte superior da página.

### <a name="upper-section"></a>Seção superior

A seção superior da página fornece as seguintes guias:

- **Visão geral** – Exibe os requisitos de itens das dimensões do produto.
- **Cobertura de item** – Exiba as configurações de cobertura usadas durante o cálculo dos requisitos.
- **Resumo** – Exiba um detalhamento dos totais de requisitos por tipo de transação.
- **Período** – exiba os recebimentos, as saídas e o estoque disponível projetado para cada período definido pelo modelo de período. Você também pode obter uma exibição gráfica do estoque disponível projetado.

### <a name="lower-section"></a>Seção inferior

A seção inferior da página fornece as seguintes guias:

- **Visão geral** – Exibe a lista de requisitos do produto que foram calculados durante a execução do planejamento mestre, juntamente com transações de saída e recebimento que correspondem aos requisitos. Por padrão, a lista é classificada por data da necessidade. Quando você seleciona um requisito, a FastTab **Vinculação** na seção inferior mostra a origem do requisito ou as transações que atendem ao requisito.
- **Geral** – exibe informações detalhadas sobre a necessidade selecionada.
- **Ação** – Exiba mensagens de ação para os requisitos.

### <a name="the-action-pane"></a>Painel de Ações

Os seguintes comandos estão disponíveis no Painel de Ações:

- **Atualizar \> Planejamento mestre** – Execute o planejamento mestre diretamente na página **Requisitos líquidos**.
- **Atualizar \> Planejamento de previsão** – Execute o planejamento de previsão diretamente na página **Requisitos líquidos**. A Otimização de Planejamento ainda não oferece suporte a essa operação.
- **Atualizar \> Plano de continuidade** – Execute o planejamento de continuidade diretamente na página **Requisitos líquidos**. A Otimização de Planejamento ainda não oferece suporte a essa operação.

## <a name="example-scenario"></a>Cenário de exemplo

Este exemplo mostra como as informações de vinculação são apresentadas na **página requisitos líquidos**.

### <a name="prerequisites"></a>Pré-requisitos

Antes de trabalhar com o cenário, os seguintes pré-requisitos devem ser atendidos:

1. Você deve trabalhar em um sistema no qual os dados de exemplo padrão estão disponíveis, e deve definir a entidade legal para *USMF*.
2. Este exemplo usa o produto *1000*, que é parte dos dados de exemplo do USMF. Verifique se o produto está disponível e se está configurado da seguinte maneira:

    - **Tipo de ordem padrão:** *Ordem de compra*
    - **Estoque disponível:** *10,00*

3. Crie uma ordem de venda para uma quantidade de *25,00* e preço unitário de *1000*. Use as dimensões de armazenamento nas quais o estoque disponível está localizado.
4. Executar o planejamento mestre para o planejamento mestre de *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Revisar os requisitos calculados

Em seguida, você abrirá a página **Requisitos líquidos** do produto *1000* para analisar como os requisitos calculados correspondem uns aos outros.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto que tem um valor de **Número de item** igual a *1000*.
1. No Painel de Ação, na guia **Plano**, no grupo **Requisito**, selecione **Requisitos líquidos**.
1. Na página **Requisitos líquidos**, defina o campo **Plano** como *DynPlan*.
1. Na guia **Visão geral** na parte inferior da página, verifique se os seguintes requisitos estão listados como linhas na grade.

    | Demonstrativo | Quantidade de requisitos | Acumulado |
    |---|---|---|
    | Disponível | 10,00 | 10,00 |
    | Ordens de Compra Planejadas | 15.00 | 25.00 |
    | Ordem de Venda | -25,00 | (Em branco) |

    > [!NOTE]
    > O campo **Quantidade do requisito** representa a quantidade total necessária para o requisito (se o valor for negativo) ou fornecimento (se o valor for positivo). O campo **Acumulado** representa a quantidade total de recebimento e de saída que é acumulada até o período selecionado.

1. Selecione a linha requisito *Disponível* e, em seguida, na FastTab **Vinculação**, revise os requisitos que são cobertos por este fornecimento. A linha a seguir deve aparecer lá.

    | Demonstrativo | Quantidade de requisitos | Quantidade coberta |
    |---|---|---|
    | Ordem de Venda | -25,00 | -10,00 |

    O estoque disponível existente cobre parcialmente a demanda que vem da ordem de venda.

    ![Informações sobre vinculação para o estoque disponível](media/pegging-on-hand.png "Informações sobre vinculação para o estoque disponível")

1. Selecione a linha requisito *Ordens de compra planejadas* e, em seguida, na FastTab **Vinculação**, revise os requisitos que são cobertos por este fornecimento. A linha a seguir deve aparecer lá.

    | Demonstrativo | Quantidade de requisitos | Quantidade coberta |
    |---|---|---|
    | Ordem de Venda | -25,00 | -15,00 |

    Como a ordem de venda já foi parcialmente coberta, o sistema cria uma ordem de compra planejada para a quantidade não revelada restante.

    ![Informações sobre vinculação para a ordem de compra planejada](media/pegging-planned-purchase-order.png "Informações sobre vinculação para a ordem de compra planejada")

1. Selecione a linha requisito *Ordem de venda* e, em seguida, na FastTab **Vinculação**, revise os requisitos que cobram esta demanda. A linha a seguir deve aparecer lá.

    | Demonstrativo | Quantidade de requisitos | Quantidade coberta |
    |---|---|---|
    | Disponível | 10,00 | 10,00 |
    | Ordens de Compra Planejadas | 15.00 | 15.00 |

    ![Informações sobre vinculação para a ordem de venda](media/pegging-planned-purchase-order.png "Informações sobre vinculação para a ordem de venda")

> [!NOTE]
> Como a Otimização de Planejamento ainda não oferece suporte a alguns recursos, os tipos de requisitos *Estoque de segurança* e *Lote expirado* não são incluídos na página **Requisitos líquidos**. Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).
>
> Se você estiver usando o mecanismo de planejamento mestre interno, os produtos controlados por lote serão aceitos. Para produtos controlados por lote, o estoque disponível expirado é mostrado na página **Requisitos líquidos**, mas não é vinculado com requisitos de demanda. As linhas disponíveis e vencidas deste tipo, são mostradas como linhas de requisitos de *Lote expirado* na página **Requisitos líquidos**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
