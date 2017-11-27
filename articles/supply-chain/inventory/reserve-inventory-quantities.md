---
title: Reservar quantidades do estoque
description: "Este tópico descreve as diferentes opções disponíveis para reservar estoque."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7c351618f4d710062dd8f369c5319cdce79f7339
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="reserve-inventory-quantities"></a>Reservar quantidades do estoque

[!include[banner](../includes/banner.md)]


Este tópico descreve as diferentes opções disponíveis para reservar estoque.

Você pode reservar automaticamente quantidades de estoque para uma ordem de venda específica. Isso significa que o estoque reservado não pode ser retirado do depósito para outras ordens, a menos que a reserva do estoque, ou parte dela, seja cancelada.

Há vários motivos para reservar o estoque:
-   Primeiro solicitado, primeiro entregue, o que significa que os clientes recebem os itens disponíveis na mesma sequência em que foram colocados em suas ordens.
-   A escassez de itens devido a um período longo ou desconhecido de entrega por parte do fornecedor. Talvez seja conveniente garantir que determinados clientes ou ordens recebam os primeiros itens disponíveis.
-   Determinados clientes e tipos de ordens têm prioridade de entrega.
-   Itens com números de série ou lote. Você pode marcar determinados itens que foram ou serão entregues para ordens específicas.
-   Itens solicitados especialmente, reservados para determinadas ordens.
-   Ordens de produção. Por exemplo, você pode marcar itens que são produzidos e ajustados para ordens específicas.

O estoque poderá ser reservado automaticamente quando uma nova linha de ordem for criada ou ser reservado manualmente nas ordens individuais. Também é possível reservar estoque em etapas diferentes no processo de produção. Apenas produtos em estoque podem ser reservados. Os serviços não podem ser reservados porque não há estoque disponível. Tanto o estoque físico disponível como o solicitado, mas ainda não recebido, podem ser reservados. Se for reservada uma quantidade superior à existente no estoque disponível, uma mensagem será exibida informando que não será possível reservar essa quantidade. Você poderá então optar por reservar a quantidade mesmo assim ou alterar a quantidade solicitada. A quantidade poderá ser reservada ou alterada. Se for reservada uma quantidade de itens superior à quantidade disponível, a escassez será coberta na próxima vez que os itens estiverem disponíveis para entrega.

## <a name="inventory-reservation-policies"></a>Políticas de reserva de estoque
Políticas de reserva de estoque estão definidas na página **Grupos de modelo do item**, na página **Parâmetros de gerenciamento de estoque e depósito** e na página **Parâmetros de produção**.
### <a name="policies-on-the-item-model-groups-page"></a>Políticas na página Grupos de modelo do item

A seção **Políticas de estoque** contém as seguintes políticas de reserva.
|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Política de reserva**  | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Controlado por data PEPS    | Se você selecionar a opção **Controlado por data PEPS**, a reserva de estoque será controlada por uma data de classificação, de acordo com o princípio PEPS. Lotes são reservados com base na data mais antiga de recebimento de itens, de acordo com o princípio PEPS (primeiro a entrar, primeiro a sair).                                                                                                                                                                                                                                                                       |
| Voltar a partir da data de remessa | Essa opção se tornará disponível apenas se você tiver selecionado a opção **Controlado por data PEPS**. Se você selecionar **Voltar a partir da data de remessa**, a reserva de estoque será feita a partir da data de remessa desejada, de acordo com o princípio UEPS (último a entrar, primeiro a sair). Se nenhum recebimento estiver disponível antes da data de remessa, será usada uma reserva PEPS.                                                                                                                                                                                                           |
| Reserva de venda de item  | Determina se a reserva de itens é manual ou automática. Se a reserva é automática, o estoque é reservado quando as linhas de ordem são criadas. É possível fazer reservas no nível de número de item para BOMs (opção **Automática**) ou para os elementos individuais de uma BOM (opção **Explosão**). O valor padrão de **Reserva de venda de item** pode ser herdado de **Parâmetros de contas a receber.** Nesta página, o valor é definido no campo **Reserva** da seção **Valores padrão de vendas** da guia **Geral**. |
| Seleção de mesmo lote    | A reserva de mesmo lote permite reservar estoque para uma linha de ordem de venda para um único lote de estoque. Se você deseja usar essa opção, deve também definir a opção **Consolidar necessidade** como **Sim**. Há configurações adicionais que são necessárias para o grupo de dimensões de rastreamento e o grupo de dimensões de armazenamento. Para obter mais informações, consulte [Reservando o mesmo lote para uma ordem de venda](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Consolidar necessidade | Essa opção é semelhante à opção **Seleção de mesmo lote** e consolida estoque reservado para linhas de ordem de venda em apenas uma necessidade.                                                                                                                                                                                                                                                                                                                                                                                      |
| Controlado por data FEFO    | Essa opção permite que você reserve lotes próximos de suas datas de vencimento ou de validade. Também é necessário definir o campo **Critérios de separação** para escolher **Data de vencimento** ou **Data de validade**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Exemplo para Controlado por data PEPS e Voltar a partir da data de remessa

Neste exemplo, o estoque disponível para o número de item A existe para três números de lote diferentes.
| Nº de itens | Nº do lote | Quantidade | Data             |
|-------------|--------------|----------|------------------|
| A           | 1000         | 5        | 2 de fevereiro de 2016 |
| A           | 1001         | 3        | 1 de janeiro, 2016  |
| A           | 1002         | 7        | 3 de março de 2016    |

Uma ordem de venda que deve ser reservada automaticamente e entregue em 4 de abril de 2016 reserva o seguinte lote:
-   Se ambas as caixas de seleção **Controlado por data PEPS** e **Voltar a partir da data de remessa** estiverem desmarcadas, o lote 1000 será reservado porque é o lote com o menor número.
-   Se a caixa de seleção **Controlado por data PEPS** estiver marcada e a caixa de seleção **Voltar a partir da data de remessa** estiver desmarcada, o lote 1001 será reservado porque é o lote com a primeira data de recebimento (PEPS).
-   Se ambas as caixas de seleção **Controlado por data PEPS** e **Voltar a partir da data de remessa** estiverem marcadas, o lote 1002 será reservado porque é o recebimento de lote mais próximo da data de remessa da ordem de venda.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Políticas na página Parâmetros de gerenciamento de estoque e depósito

Há duas opções relacionadas a reservas na página **Parâmetros de gerenciamento de estoque e depósito**:
-   A opção **Reservar itens encomendados** na guia **Geral** permite reservar recebimentos de itens solicitados para saídas de itens em Contas a receber, Gerenciamento de projetos e contabilidade e Controle de produção. Se você desmarcar esta opção, será possível reservar somente itens recebidos fisicamente. Se um item particular tiver sido configurado para aceitar estoque negativo, este campo não será importante.
-   A opção **Reservar itens automaticamente** na guia **Transporte** determina a configuração padrão se itens são automaticamente reservados para ordens de transferência. A configuração padrão pode ser substituída em ordens de transferência individuais.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Políticas de reserva de estoque na página Parâmetros de produção

O valor do campo **Reserva** na guia **Geral** da página **Parâmetros de produção** determina o ponto padrão no processo de produção em que o estoque deve ser reservado. Por exemplo, o estoque poderá ser reservado quando o trabalho for programado ou quando o trabalho começar.

