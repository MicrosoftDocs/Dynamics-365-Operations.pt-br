---
title: Promessa de ordem
description: Este artigo oferece informações sobre promessas de ordem. As promessas de ordem ajudam você a prometer, com segurança, datas de entrega aos clientes e lhe fornece flexibilidade para que possa atender a essas datas.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228255"
---
# <a name="order-promising"></a>Promessa de ordem

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre promessas de ordem. As promessas de ordem ajudam você a prometer, com segurança, datas de entrega aos clientes e lhe fornece flexibilidade para que possa atender a essas datas.

A promessa de pedido calcula as datas de entrega e recebimento mais próximas, e se baseia no método de controle de data de entrega e nos dias de transporte. Você pode escolher entre os métodos de controle de data de entrega seguintes:

- **Prazo de entrega das vendas**: prazo de entrega das vendas é o tempo entre a criação da ordem de venda e a remessa dos itens. O cálculo de data de entrega baseia-se em um número padrão de dias e não considera a disponibilidade de estoque, a demanda conhecida, ou o fornecimento planejado.
- **ATP (disponível para promessa)**: ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente em uma data específica. O cálculo de ATP inclui o estoque não confirmado, prazos de entrega, recebimentos planejados, e saídas.
- **Margem de saída + ATP**: a data de remessa é igual a data de ATP acrescida da margem de saída do item. A margem de saída é o tempo necessário para preparar os itens para remessa.
- **CTP (capacidade de comprometimento)**: a disponibilidade é calculada com o detalhamento. Se você estiver usando a otimização de planejamento, o método de controle da data de entrega do *CTP* não estará disponível e, se for selecionado, causará um erro quando o cálculo for executado. Para obter mais informações sobre como configurar e usar a opção CTP, consulte a opção [Calcular datas de entrega das ordens de venda usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP para otimização de planejamento**: use o cálculo do CTP fornecido pela otimização do planejamento. Essa opção não tem efeito se você estiver usando o mecanismo de planejamento mestre integrado. Para obter mais informações sobre como configurar e usar a opção CTP, consulte a opção [Calcular datas de entrega das ordens de venda usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Quando uma ordem de venda for atualizada, as informações de promessa da ordem serão atualizadas somente se a data de promessa da ordem existente não puder ser atendida, conforme ilustrado nos exemplos a seguir:
>
> - **Exemplo 1**: a data de promessa da ordem atual é 20 de julho mas, devido à quantidade crescente, você não poderá entregar até 25 de julho. Como a data atual não pode mais ser atendida, a promessa da ordem é disparada.
> - **Exemplo 2**: a data de promessa do pedido atual é 20 de julho, mas, devido à quantidade reduzida, agora é possível entregar em 15 de julho. No entanto, como a data atual ainda pode ser cumprida, a promessa do pedido não é disparada e 20 de julho permanece sendo a data de promessa do pedido.

## <a name="atp-calculations"></a>Cálculos de ATP

A quantidade de ATP é calculada usando o método “ATP cumulativo com leitura prévia”. A principal vantagem desse cálculo de ATP é que ele pode lidar com casos nos quais a soma de saídas entre recebimentos é maior do que o último recebimento (por exemplo, quando se faz necessário usar uma quantidade de um recebimento anterior para atender a uma necessidade). O método de cálculo “ATP cumulativo com leitura prévia” inclui todas as saídas até que a quantidade cumulativa para receber exceda a quantidade cumulativa para emissão. Sendo assim, esse método de cálculo de ATP avalia se qualquer quantidade de um período anterior pode ser usada em um período posterior.

A quantidade ATP é o saldo de estoque não confirmado no primeiro período. Geralmente, ela é calculada para cada período no qual um recebimento é planejado. O programa calcula o período ATP em dias e calcula a data atual como a primeira data para a quantidade ATP. No primeiro período, ATP inclui o estoque disponível menos ordens de cliente que estão vencidas ou atrasadas.

O ATP é calculado através da seguinte fórmula:

ATP = ATP do período anterior + Recibos do período atual – Problemas do período atual – Quantidade líquida de saída para cada período futuro até que o período em que a soma de recibos de todos os períodos futuros, até e incluindo o período futuro, seja maior que a soma de saídas, até e incluindo o período futuro.

Observe que o cálculo de ATP não inclui informações sobre data de vencimento e além do limite de tempo ATP que o sistema espera quando qualquer quantidade pode ser prometida.

Quando não houver mais saídas ou emissões a serem consideradas, a quantidade ATP para as seguintes datas é a mesma que a última quantidade ATP calculada.

Se nem todas as dimensões usadas para um item forem fornecidas quando a verificação de ATP for concluída, estas ainda podem ser especificadas na saída e nos recebimentos. Nesse caso, no cálculo ATP, os recebimentos e saídas devem ser agregados para as dimensões existentes para reduzir o número de linhas de recebimentos e de saída usadas no cálculo ATP.

A quantidade ATP que é mostrada é sempre maior ou igual a 0 (zero). Se o cálculo retornar uma quantidade ATP negativa (por exemplo, se a quantidade prometida anteriormente exceder a quantidade disponível), a quantidade é definida automaticamente como 0.

### <a name="example"></a>Exemplo

O campo **Limite de tempo de demanda retroativa ATP** controla o recuo no tempo para procurar por ordens de demanda atrasadas ou saídas de estoque. O campo **Limite de tempo de fornecimento retroativo ATP** controla o recuo no tempo para procurar por ordens de fornecimento atrasadas ou recebimentos de estoque. Por exemplo, se as ordens que estão vencidas somente em sete dias precisarem ser considerados no cálculo ATP, os campos devem ser definidos como **7**.

Os campos **Tempo de deslocamento de demanda atrasada ATP** e **Tempo de deslocamento de fornecimento atrasado ATP** controlam quando a demanda ou fornecimento atrasados serão considerados no cálculo de ATP. Por exemplo, se a demanda e fornecimento atrasados precisarem ser considerados no cálculo de ATP depois de amanhã, ambos os campos devem ser definidos como **2**. Um valor de **2** significa que a quantidade de um item em uma ordem de compra atrasada que deve ser considerada no cálculo de ATP será vista como disponível dois dias após a data atual.

Para o exemplo a seguir, **7** é inserido nos campos **Limite de tempo de demanda retroativa ATP** e **Limite de tempo de fornecimento retroativo ATP**, e **1** é inserido nos campos **Tempo de deslocamento de demanda atrasada ATP** e **Tempo de deslocamento de fornecimento atrasado ATP**.

Uma ordem de compra de 200 peças de um produto que devia ser recebida três dias atrás ainda não foi recebida. Sendo assim, uma linha de ordem de venda de 75 peças do mesmo produto que devia ser enviada ontem não foi enviada.

O cliente liga e solicita 150 peças do mesmo produto. Ao verificar a disponibilidade do produto, você descobre que há outra ordem de compra de 100 peças do produto que será entregue 10 dias depois.

Crie uma linha de ordem de venda para o produto e insira **150** como quantidade.

Como o método de controle da data de entrega é ATP, os dados ATP são calculados para localizar a data de remessa mais próxima. Com base nas configurações, são consideradas ordem de compra e ordem de venda que estão atrasadas e a quantidade ATP resultante para a data atual é 0. Amanhã, quando a ordem de compra atrasada tiver que ser recebida, a quantidade ATP é calculada como mais de 0 (nesse caso, calculada como 125). Entretanto, em 10 dias, quando a ordem de compra adicional de 100 peças tiver que ser recebida, a quantidade ATP se tornará mais de 150.

Portanto, a data de remessa é definida para 10 dias, a contar de hoje, com base no cálculo ATP. Sendo assim, você informa ao cliente que a quantidade solicitada pode ser entregue em 10 dias, a contar de hoje.

## <a name="ctp-calculations"></a>Cálculos de CTP

A funcionalidade CTP permite que você forneça as datas reais de clientes para quando puder prometer bens específicos. Para cada linha de venda, você pode fornecer uma data que considera o estoque disponível existente, a capacidade da produção e os tempos de transporte.

O CTP estende a funcionalidade ATP considerando as informações sobre capacidade. Enquanto ATP considera apenas a disponibilidade de materiais e pressupõe recursos de capacidade infinitas, o CTP considera a disponibilidade de materiais e capacidade. Portanto, ele fornece uma imagem mais realista sobre a possibilidade da demanda ser cumprida em um determinado período.

A opção CTP comporta-se um pouco diferente dependendo do mecanismo de planejamento mestre que você está usando (otimização de planejamento ou o mecanismo integrado). O CTP para otimização de planejamento atualmente oferece suporte somente a um subconjunto de cenários do CTP para os quais o mecanismo integrado oferece suporte.

Para obter informações detalhadas sobre como configurar e usar a opção CTP para cada mecanismo, consulte a opção [Calcular datas de entrega das ordens de venda usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
