--- 
title: Criar ordens de venda
description: Este procedimento mostra como criar uma ordem de venda.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 62276765e1cc76b2328a7b5b57bd18593d93e4ab
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-sales-orders"></a>Criar ordens de venda

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma ordem de venda. Você pode usar o procedimento na empresa USMF de dados de demonstração. As ordens de venda são desenvolvidos tipicamente por um processador de ordens de venda. 




## <a name="enter-sales-order-header-details"></a>Insira detalhes do cabeçalho da ordem de venda
1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro do cliente.
    * Por exemplo, selecione o número do cliente US-004.  
5. Na lista, clique no link na linha selecionada.
6. Clique em OK.

## <a name="enter-sales-order-line-details"></a>Insira detalhes da linha da ordem de venda
    * Os bens vendidos pela sua organização podem vir em grades diferenciadas por dimensões, como a configuração, cor, o tamanho e o estilo. Além disso, os produtos podem ser configurados para usar dimensões de armazenamento, como o site, depósito, a paleta e as dimensões de racking, como o números de lote e de série. Quando essas dimensões são atribuídas, você deve selecionar os valores das dimensões na linha da ordem. Para aumentar a eficiência de entrada de ordem, você pode adicionar os respectivos campos de dimensão para a grade da ordem.  
1. Clique em Linha da ordem de venda.
2. Clique em Dimensões.
    * Por exemplo, selecione a cor, o site e o depósito dimensões. As dimensões selecionadas aqui aparecerão na grade de ordem de venda. Se desejar que as seleções persistam, defina a opção de configuração salva em Sim.   
3. Clique em OK.
4. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
5. Para este exemplo, selecione número de item T0004.
6. Na lista, clique no link na linha selecionada.
    * Se o item for parte de uma categoria de vendas, o nome do item será exibido automaticamente no campo da categoria de vendas.  
    * Se os campos de dimensão de produto já contém um valor, isso ocorre porque o valor é copiado do registro do produto no qual é definido como uma dimensão de produto padrão. Você pode alterar o valor padrão a qualquer momento.   
7. No campo Cor, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o registro desejado.
9. Na lista, clique no link na linha selecionada.
10. No campo Quantidade, insira um número.
    * Se o item for vendido em unidades diferentes dos itens comprados, quando gerado e armazenado, e uma unidade de medida de vendas é definida no registro do produto, esse valor será mostrado no campo unidade. É possível alterar o valor a qualquer momento.   
    * Se o campo do site já contém um valor, o valor esteve copiado do cabeçalho da ordem ou encomendado no formulário associado com o produto. É possível alterar o valor a qualquer momento. Se o campo estiver vazio, selecione um valor.   
    * Se o campo de preço unitário já contém um valor, o valor esteve copiado do contrato comercial válido ou de registro do produto. (O preço unitário também pode se originar de um contrato de venda, mas o processo para criar ordens de venda a partir dos contratos de venda é diferente do exibido aqui.) Se o campo estiver vazio, insira um valor.   
    * O campo Desconto contém um valor de desconto por unidade do produto. Para calcular o valor total do desconto de linha, o valor do desconto é multiplicado pela quantidade de linhas.    Se o campo Desconto já contém um valor, o valor esteve copiado do contrato comercial válido. Se o campo estiver vazio, e você desejar atribuir ao cliente um desconto de linha, insira um valor.  
    * O campo Percentual de desconto contém um valor percentual para o qual a linha total do valor bruto deve ser reduzida.  Se o campo Percentual de desconto já contém um valor, ele esteve copiado do contrato comercial válido. Se o campo estiver vazio, e você desejar atribuir ao cliente um desconto de linha, insira um valor.  
    * O campo Valor líquido contém um valor calculado com base na quantidade na unidade da linha e ajustado ao preço por descontos.  Você pode substituir o valor calculado por outro.  

## <a name="review-the-order-totals"></a>Rever os totais da ordem
1. No Painel de Ação, clique em Ordem de venda.
2. Clique em Totais.
    * A página Totais exibe os detalhes sobre a ordem inteira. Isso inclui o valor do subtotal, que é a soma de todos os descontos de linha dos valores líquidos ajustados para os descontos eventuais de linha, o valor total da nota fiscal, que é um valor de subtotal ajustado para desconto, encargos diversos, impostos sobre vendas e eventuais nível de fórmula, situação de limite de crédito do cliente, etc.  O valor da nota fiscal é o valor que aparecerá no documento da nota fiscal do cliente.  
3. Clique em OK.


