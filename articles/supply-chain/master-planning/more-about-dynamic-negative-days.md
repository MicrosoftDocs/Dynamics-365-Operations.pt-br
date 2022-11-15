---
title: Dias negativos e dias negativos dinâmicos
description: Este artigo fornece informações sobre dias negativos e dias negativos dinâmicos, e como você pode usá-los em seus negócios.
author: t-benebo
ms.date: 05/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bcaaf46a0ddd84cded721c5d02d4a45cd4745114
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740348"
---
<!-- KFM: Split this up. non-dynamic for deprecated MP, and "dynamic" for new standard PO. -->

# <a name="negative-days-and-dynamic-negative-days"></a>Dias negativos e dias negativos dinâmicos

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre dias negativos e dias negativos dinâmicos, e como você pode usá-los em seus negócios. O *limite de tempo de dias negativos* representa o número de dias que você está disposto a esperar antes de solicitar um novo reabastecimento quando houver estoque negativo.

Neste artigo você obterá as seguintes informações:

- Como as ordens planejadas são criadas
- A correlação entre o limite de tempo de dias negativos e o prazo de entrega do item
- Como o limite de tempo de dias negativos dinâmico é calculado e como o prazo de entrega do item é fatorado no cálculo
- Como interpretar as [sugestões para melhorar o tempo de execução do planejamento de requisições de materiais (MRP) (planejamento mestre)](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx) relacionadas aos dias negativos

Este artigo usa três cenários hipotéticos para ajudá-lo a entender essas informações. A diferença entre os cenários é o ponto em que você obtém a demanda: antes, durante ou após o período do prazo de entrega do item.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Cenário 1: Você obtém demanda antes do período do prazo de entrega do item

Você pode obter demanda relativamente cedo no prazo de entrega do seu item ou pouco antes do início do período do prazo de entrega. Aqui está um exemplo deste cenário:

- O item DemoProduct tem um prazo de entrega de compra de seis dias.
- No dia zero (1º de janeiro), o nível de estoque do item DemoProduct é 0 (zero).
- No dia zero (1º de janeiro), você recebe uma ordem de vendas de uma quantidade 10 do item DemoProduct.
- No dia sete (8 de janeiro), há uma ordem de compra existente para uma quantidade 10 do item DemoProduct.

A ilustração a seguir mostra uma exibição gráfica deste cenário.

![Exibição gráfica do cenário 1.](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: os dias negativos são menores que o prazo de entrega do item

Se você definir os dias negativos como um número menor que o prazo de entrega do item, o MRP procurará recibos do item DemoProduct dentro do limite de tempo de dias negativos. Por não encontrar nenhum recebimento, o MRP cria uma ordem de compra planejada. Essa ordem planejada é exibida imediatamente por seis dias (o prazo de entrega). Portanto, ela chegará no dia 7 de janeiro. A ordem de compra existente recebe uma mensagem de ação **Cancelar**, porque a criação da nova ordem de compra planejada a tornou redundante.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso A do cenário 1.](./media/negative-days-2.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso A do cenário 1.](./media/negative-days-3.png)

Se você considera o desempenho do MRP e a tensão do plano, este caso não funcionará bem. O MRP deve criar uma nova ordem planejada e deve calcular atrasos e ações. Estas tarefas são demoradas. Esses casos também adicionam mais duas transações ao seu plano. Por outro lado, a ordem de venda é exibida por apenas seis dias, não sete.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: os dias negativos são maiores que o prazo de entrega do item

Para ajudar a melhorar o desempenho de MRP, você pode definir os dias negativos como um número que é maior que o lead time do item. Como você não pode obter o suprimento dentro do prazo de entrega deste cenário, pode procurar por recebimentos enquanto essa pesquisa fizer sentido. Embora o tempo de execução do MRP seja menor, você deve ficar atento a atrasos adicionais nas ordens.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: Corrige automaticamente o prazo de entrega do item para o limite de tempo de dias negativos

Para correlacionar automaticamente o prazo de entrega do item ao limite de tempo de dias negativos, use dias negativos dinâmicos. Para usar dias negativos dinâmicos, Acesse **Planejamento mestre \> Configuração \> Parâmetros de planejamento mestre** e, em seguida, na guia **Geral**, na seção **Cobertura**, defina a opção **Usar dias negativos dinâmicos** como **Sim**. O MRP procura recibos dentro do limite de tempo de dias negativos dinâmicos. Esse limite de tempo é calculado usando a seguinte fórmula:

Limite de tempo de dias negativos dinâmicos = Prazo de entrega da compra + Limite de tempo de dias negativos + (Data atual – Data da necessidade)

(Se o tipo de ordem padrão do item DemoProduct for **Produção** ou **Transferência**, o prazo de entrega será **estoque**.)

Quando dias negativos dinâmicos são usados, o limite de tempo que o MRP analisa para recebimentos agora é 6 + 2 + 0 = 8 dias. O MRP encontra a ordem de compra existente e a relaciona a ele. Nenhuma ordem planejada nova é criada. Portanto, o tempo de execução do MRP é mais curto. A ilustração a seguir mostra a necessidade líquida para o item DemoProduct.

![Necessidades líquidas para o caso C do cenário 1.](./media/negative-days-4.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso C do cenário 1.](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: Usar somente dias negativos dinâmicos

Se você definir os dias negativos como **0** (zero) e usar somente o limite de tempo de dias negativos dinâmicos, o limite de tempo de dias negativos dinâmicos será 6 + 0 + 0 = 6 dias. Nesse caso, o resultado será o mesmo que o resultado caso A deste cenário. O MRP deve criar uma nova ordem planejada e deve calcular atrasos e ações. Estas tarefas são demoradas e também podem ser frustrantes. Você também terá mais duas transações para processar. Como a demanda não pode ser atendida no prazo do item chegar, esse caso adiciona complicações desnecessárias ao seu plano.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso D do cenário 1.](./media/negative-days-6.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso D do cenário 1.](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: Use os dois dias negativos que são mais do que o prazo de entrega do item e o limite de tempo de dias negativos dinâmicos

Se você definir os dias negativos como um número que é maior que o prazo de entrega do item e também usar o limite de tempo de dias negativos dinâmicos, o limite de tempo de dias negativos dinâmico será 6 + 6 + 0 = 12 dias. Essa abordagem pode produzir um limite de tempo muito longo no qual o MRP deve procurar resultados. Para obter informações sobre como o caso E está relacionado a uma situação em que você define os dias negativos como um limite de tempo longo, consulte a seção [Conclusão](#conclusion) deste artigo.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Cenário 2: Você obtém demanda durante o período do prazo de entrega do item

Você pode obter demanda em algum momento durante o prazo de entrega de seu item. Aqui está um exemplo deste cenário:

- O item DemoProduct tem um prazo de entrega de compra de seis dias. 
- No dia zero (1º de janeiro), o nível de estoque do item DemoProduct é 0 (zero).
- No quarto dia (5 de janeiro), que está dentro do prazo de entrega do item, você recebe uma ordem de venda com uma quantidade 10 do item do DemoProduct.
- No sétimo dia (8 de janeiro), há uma ordem de compra com uma quantidade 10 do item do DemoProduct.

A ilustração a seguir mostra uma exibição gráfica deste cenário.

![Exibição gráfica do cenário 2.](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: os dias negativos são menores que o prazo de entrega do item

Se você definir os dias negativos como um número menor que o prazo de entrega do item, o MRP procurará recibos do item DemoProduct dentro do limite de tempo de dias negativos. Como não encontra nenhum recebimento, o MRP cria uma nova ordem de compra planejada que usa a data atual como a data da ordem. Essa ordem planejada é exibida imediatamente por seis dias (o prazo de entrega). Portanto, ela chegará no dia 7 de janeiro. A ordem de compra existente recebe uma mensagem de ação **Cancelar**, porque a criação da nova ordem de compra planejada a tornou redundante.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso A do cenário 2.](./media/negative-days-9.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso A do cenário 2.](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: os dias negativos são maiores que o prazo de entrega do item

Esse caso é semelhante ao caso B do cenário 1. Se você definir os dias negativos como um número maior que o prazo de entrega do item, não receberá uma nova ordem planejada. A ordem de venda será anexada à ordem de compra existente.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: Corrige automaticamente o prazo de entrega do item para o limite de tempo de dias negativos

Este caso é semelhante ao caso C do cenário 1 porque os dias negativos dinâmicos funcionam tão bem como neste caso. O limite de tempo de dias negativos dinâmicos agora é 6 + 2 – 4 = 4 dias. Se você usar esta abordagem, o MRP localizará a ordem de compra existente e anexará a ordem de compra a ela. Como nenhuma nova ordem planejada é criada, o tempo de execução do MRP será menor.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso C do cenário 2.](./media/negative-days-11.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso C do cenário 2.](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: Usar somente dias negativos dinâmicos

Se você definir os dias negativos como **0** (zero) e usar somente o limite de tempo de dias negativos dinâmicos, o limite de tempo de dias negativos dinâmicos agora será 6 + 0 - 4 = 2 dias. Nesse caso, o resultado será o mesmo que o resultado caso A deste cenário. Para obter uma exibição gráfica do que ocorre, consulte o caso A deste cenário.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: Use os dois dias negativos que são mais do que o prazo de entrega do item e o limite de tempo de dias negativos dinâmicos

Se você definir os dias negativos como um número que é maior que o prazo de entrega do item e também usar o limite de tempo de dias negativos dinâmicos, o limite de tempo de dias negativos dinâmico será 6 + 6 - 4 = 8 dias. Essa abordagem pode produzir um limite de tempo muito longo no qual o MRP deve procurar resultados. Para obter informações sobre como o caso E está relacionado a uma situação em que você define os dias negativos como um limite de tempo longo, consulte a seção [Conclusão](#conclusion) deste artigo.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Cenário 3: Você obtém demanda depois do período do prazo de entrega do item

Você pode obter demanda depois do período do prazo de entrega do item. Aqui está um exemplo deste cenário:

- O item DemoProduct tem um prazo de entrega de compra de seis dias.
- No dia zero (1º de janeiro), o estoque do item DemoProduct é 0 (zero).
- No sétimo dia (8 de janeiro), que está fora do prazo de entrega do item, você recebe uma ordem de venda com uma quantidade 10 do item do DemoProduct.
- No décimo dia (11 de janeiro), há uma ordem de compra com uma quantidade 10 do item do DemoProduct.

A ilustração a seguir mostra uma exibição gráfica deste cenário.

![Exibição gráfica do cenário 3.](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: os dias negativos são menores que o prazo de entrega do item

Se você definir os dias negativos como um número inferior ao prazo de entrega do item, o MRP verifica dois dias antes da data da necessidade da ordem de venda. Como ele não encontra nada, o MRP cria uma ordem de compra planejada em 2 de janeiro. Essa ordem de compra planejada será enviada em tempo de atender à demanda de ordem de venda. A ordem de compra existente receberá uma mensagem de ação **Cancelar** , pois não será necessária.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso A do cenário 3.](./media/negative-days-14.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso A do cenário 3.](./media/negative-days-15.png)

> [!NOTE]
> Na captura de tela anterior, a data da necessidade da ordem de compra é 12 de janeiro. Como essa captura de tela foi obtida em 2015, quando o dia 11 de janeiro foi um domingo, o MRP transferiu a data da necessidade para o próximo dia útil, que foi segunda-feira, 12 de janeiro. No entanto, a ordem de compra tem uma data de entrega de 11 de janeiro.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: os dias negativos são maiores que o prazo de entrega do item

Se você definir os dias negativos como um número maior que o prazo de entrega do item, não receberá uma nova ordem planejada. A ordem de venda será vinculada à ordem de compra existente. Portanto, a ordem de venda ficará atrasada. Se criar uma ordem planejada, você poderá enviar a ordem de venda no prazo.

A ilustração a seguir mostra uma captura de tela deste caso.

![Captura de tela do caso B do cenário 3.](./media/negative-days-16.png)

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso B do cenário 3.](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: Corrige automaticamente o prazo de entrega do item para o limite de tempo de dias negativos

Este caso é semelhante ao caso C do cenário 1 porque os dias negativos dinâmicos funcionam tão bem quanto, se não melhor, que no caso B para esse cenário.

O limite de tempo de dias negativos dinâmicos agora é 6 + 2 – 7 = 1 dia. Porém, nesse caso, o sistema ainda considera o prazo de entrega de dias negativos (2), porque o MRP considera o valor máximo entre o prazo de entrega de dias negativos e o prazo de entrega de dias negativos dinâmicos. Portanto, o resultado neste caso será igual ao resultado do caso A deste cenário.

A ilustração a seguir mostra uma exibição gráfica do que ocorre neste caso.

![Exibição gráfica do caso C do cenário 3.](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: Usar somente dias negativos dinâmicos

Se você definir os dias negativos como **0** (zero) e usar somente o limite de tempo de dias negativos dinâmicos, o limite de tempo de dias negativos dinâmicos agora será 6 + 0 - 7 = -1 dia. Nesse caso, o sistema ainda considera o prazo de entrega de dias negativo (2). Portanto, o resultado neste caso será igual ao resultado do caso A deste cenário e tem todos os mesmos inconvenientes. Para obter uma exibição gráfica do que ocorre, consulte o caso A do cenário 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: Use os dois dias negativos que são mais do que o prazo de entrega do item e o limite de tempo de dias negativos dinâmicos

Este caso é igual ao caso E dos cenários 1 e 2. Basicamente terá os mesmos e inconvenientes e benefícios.

## <a name="conclusion"></a>Conclusão

Como os três cenários mostram neste artigo, é aconselhável definir os dias negativos como um número que seja maior do que o prazo de entrega de itens no grupo de cobertura. Também é recomendável usar somente dias negativos dinâmicos e definir os dias negativos como o número de dias que você está disposto a esperar antes de solicitar um novo reabastecimento quando tiver um estoque negativo (em outras palavras, o número de dias que você está disposto a atrasar ainda mais a demanda). Além disso, os itens no mesmo grupo de cobertura devem ter prazos de entrega semelhantes.

Se você definir os dias negativos como **0** (zero) e não usar dias negativos dinâmicos, o MRP sempre criará uma nova ordem planejada para atender à demanda. Nessa situação, é importante que você trabalhe com mensagens de ação para assegurar que você não empilha o estoque.

Talvez você queira definir os dias negativos como um intervalo de tempo longo e, em seguida, trabalhar com as mensagens de ação. Esta abordagem gera bons resultados de planejamento, mas também é um pouco mais lenta. Pode ser mais difícil analisar porque você deve analisar e aplicar as mensagens de ação. Este é um exemplo:

- O item DemoProduct tem um prazo de entrega de compra de seis dias.
- No dia zero (1º de janeiro), o estoque do item DemoProduct é 0 (zero).
- No dia zero (1º de janeiro), você recebe uma ordem de vendas de uma quantidade 10 do item DemoProduct.
- No dia nove (1º de janeiro), você recebe uma ordem de vendas de uma quantidade 10 do item DemoProduct.
- No dia onze (12 de janeiro), há uma ordem de compra com uma quantidade 10 do item do DemoProduct.
- Os dias negativos são definidos como **20**, que é muito mais que o prazo de entrega do item.

A ilustração a seguir mostra uma exibição gráfica do que ocorre.

![Revisão gráfica do exemplo.](./media/negative-days-19.png)

O MRP produz os seguintes resultados.

![Exemplo de resultados 1.](./media/negative-days-20.png)

Na captura de tela anterior, a data da necessidade da ordem de venda é 9 de janeiro, em vez de 10 de janeiro. Como essa captura de tela foi obtida em 2015, quando o dia 10 de janeiro foi um sábado, a data da solicitação da ordem deveria ser o dia útil anterior, que era sexta-feira, 9 de janeiro.

O MRP cria uma ordem de compra planejada para atender à demanda que é solicitada pela primeira ordem de venda, mas também recomenda cancelar a ordem planejada, pois é possível antecipar a ordem de compra existente e aumentar a quantidade dela.

Os resultados não estão errados, mas o tempo de execução do MRP pode ser maior, porque o MRP deve criar todos os atrasos e sugestões. Além disso, o planejador pode precisar de mais tempo para entender os resultados do MRP. Mais importante ainda, nesse caso, é essencial que o planejador entenda e use as mensagens de ação.

Se você reduzir os dias negativos para um número mais próximo do prazo de entrega do item e usar dias negativos dinâmicos, o MRP produzirá os seguintes resultados.

![Exemplo de resultados 2.](./media/negative-days-21.png)

O MRP criará uma ordem planejada anexada à primeira ordem de venda. Então, como esperado, a segunda ordem de venda será vinculada à ordem de venda existente, com base na configuração de dias negativos. Esse resultado do planejamento também está correto e o tempo de execução do MRP pode ser menor. Nesse caso, não é essencial que você entenda e saiba como trabalhar com as mensagens de ação.

Para ajudar a garantir que os valores corretos sejam inseridos para os seus negócios, você deve pensar em termos de funcionalidade e tempo de execução do MRP. Portanto, podem ocorrer tentativas e erros para determinar os valores ideais.

## <a name="see-also"></a>Consulte também

Para mais discussão, veja a postagem de blog original [More about (dynamic) negative days (Mais informações sobre dias negativos (dinâmicos))](/archive/blogs/axmfg/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
