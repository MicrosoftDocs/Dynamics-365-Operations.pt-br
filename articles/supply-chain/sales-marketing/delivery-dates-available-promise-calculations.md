---
title: Promessa de ordem
description: Este artigo oferece informações sobre promessas de ordem. As promessas de ordem ajudam você a prometer, com segurança, datas de entrega aos clientes e lhe fornece flexibilidade para que possa atender a essas datas.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78b81431d44ea5f85676b6999eece1330d3101a4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210036"
---
# <a name="order-promising"></a>Promessa de ordem

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre promessas de ordem. As promessas de ordem ajudam você a prometer, com segurança, datas de entrega aos clientes e lhe fornece flexibilidade para que possa atender a essas datas.

A promessa da ordem calcula as datas de entrega e recebimento mais próximas, e se baseia no método de controle de data de entrega e nos dias de transporte. Você pode escolher entre quatro métodos controle de data de entrega:

-   **Prazo de entrega das vendas** – Prazo de entrega das vendas é o tempo entre a criação da ordem de venda e a remessa dos itens. O cálculo de data de entrega baseia-se em um número padrão de dias, e não considera a disponibilidade de estoque, a demanda conhecida, ou o fornecimento planejado.
-   **ATP (disponível para promessa)** – ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente em uma data específica. O cálculo de ATP inclui o estoque não confirmado, prazos de entrega, recebimentos planejados, e saídas.
-   **Margem de saída + ATP**– A data de remessa é igual a data de ATP mais a margem de saída do item. A margem de saída é o tempo necessário para preparar os itens para remessa.
-   **CTP (capacidade de comprometimento)**– A disponibilidade é calculada com o detalhamento.

## <a name="atp-calculations"></a>Cálculos de ATP
A quantidade de ATP é calculada usando o método “ATP cumulativo com look-ahead”. A principal vantagem desse cálculo de ATP é que ele pode lidar com casos nos quais a soma de saídas entre recebimentos é maior do que o último recebimento (por exemplo, quando se faz necessário usar uma quantidade de um recebimento anterior para atender a uma necessidade). O método de cálculo “ATP cumulativo com look-ahead” inclui todas as saídas até que a quantidade cumulativa para receber exceda a quantidade cumulativa para emissão. Sendo assim, esse método de cálculo de ATP avalia se qualquer quantidade de um período anterior pode ser usada em um período posterior.  

A quantidade ATP é o saldo de estoque não confirmado no primeiro período. Geralmente, ela é calculada para cada período no qual um recebimento é planejado. O programa calcula o período ATP em dias e calcula a data atual como a primeira data para a quantidade ATP. No primeiro período, ATP inclui o estoque disponível menos ordens de cliente que estão vencidas ou atrasadas.  

O ATP é calculado através da seguinte fórmula:  

ATP = ATP do período anterior + Recibos do período atual – Problemas do período atual – Quantidade líquida de saída para cada período futuro até que o período em que a soma de recibos de todos os períodos futuros, até e incluindo o período futuro, seja maior que a soma de saídas, até e incluindo o período futuro.  

Quando não houver mais saídas ou emissões a serem consideradas, a quantidade ATP para as seguintes datas é a mesma que a última quantidade ATP calculada.  

Se nem todas as dimensões usadas para um item forem fornecidas quando a verificação de ATP for concluída, estas ainda podem ser especificadas na saída e nos recebimentos. Nesse caso, no cálculo ATP, os recebimentos e saídas devem ser agregados para as dimensões existentes para reduzir o número de linhas de recebimentos e de saída usadas no cálculo ATP.  

A quantidade ATP que é mostrada é sempre maior ou igual a 0 (zero). Se o cálculo retornar uma quantidade ATP negativa (por exemplo, se a quantidade prometida anteriormente exceder a quantidade disponível), o programa define automaticamente a quantidade para **0**.

### <a name="example"></a>Exemplo

O campo **Limite de tempo de demanda retroativa ATP** controla o recuo no tempo para procurar por ordens de demanda atrasadas ou saídas de estoque. O campo **Limite de tempo de fornecimento retroativo ATP** controla o recuo no tempo para procurar por ordens de fornecimento atrasadas ou recebimentos de estoque. Por exemplo, se as ordens que estão vencidas somente em sete dias precisarem ser considerados no cálculo ATP, os campos devem ser definidos como **7**.  

Os campos **Tempo de deslocamento de demanda atrasada ATP** e **Tempo de deslocamento de fornecimento atrasado ATP** controlam quando a demanda ou fornecimento atrasados serão considerados no cálculo de ATP. Por exemplo, se a demanda e fornecimento atrasados precisarem ser considerados no cálculo de ATP depois de amanhã, ambos os campos devem ser definidos como **2**. Um valor de **2** significa que a quantidade de um item em uma ordem de compra atrasada que deve ser considerada no cálculo de ATP será vista como disponível dois dias após a data atual.  

Para o exemplo a seguir, **7** é inserido nos campos **Limite de tempo de demanda retroativa ATP** e **Limite de tempo de fornecimento retroativo ATP**, e **1** é inserido nos campos **Tempo de deslocamento de demanda atrasada ATP** e **Tempo de deslocamento de fornecimento atrasado ATP**.  

Uma ordem de compra de 200 peças de um produto que devia ser recebida três dias atrás ainda não foi recebida. Sendo assim, uma linha de ordem de venda de 75 peças do mesmo produto que devia ser enviada ontem não foi enviada.  

O cliente liga e solicita 150 peças do mesmo produto. Ao verificar a disponibilidade do produto, você descobre que há outra ordem de compra de 100 peças do produto que será entregue 10 dias depois.  

Crie uma linha de ordem de venda para o produto e insira **150** como quantidade.  

Como o método de controle da data de entrega é ATP, os dados ATP são calculados para localizar a data de remessa mais próxima possível. Com base nas configurações, são consideradas ordem de compra e ordem de venda que estão atrasadas e a quantidade ATP resultante para a data atual é 0. Amanhã, quando a ordem de compra atrasada tiver que ser recebida, a quantidade ATP é calculada como mais de 0 (nesse caso, calculada como 125). Entretanto, em 10 dias, quando a ordem de compra adicional de 100 peças tiver que ser recebida, a quantidade ATP se tornará mais de 150.  

Portanto, a data de remessa é definida para 10 dias, a contar de hoje, com base no cálculo ATP. Sendo assim, você informa ao cliente que a quantidade solicitada pode ser entregue em 10 dias, a contar de hoje.



