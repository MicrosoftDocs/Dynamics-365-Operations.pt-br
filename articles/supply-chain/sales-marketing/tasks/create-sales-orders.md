---
title: Criar ordens de venda
description: Este procedimento mostra como criar uma ordem de venda.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bb4c7a542106161f8bc1b8db0976c24faebf907
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974801"
---
# <a name="create-sales-orders"></a>Criar ordens de venda

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma ordem de venda. Você pode usar o procedimento na empresa USMF de dados de demonstração. As ordens de venda são desenvolvidos tipicamente por um processador de ordens de venda. 

## <a name="enter-sales-order-header-details"></a>Insira detalhes do cabeçalho da ordem de venda
1. Vá para **Painel de navegação > Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Selecione **Novo**.
3. No campo **Conta do cliente**, selecione o botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro do cliente.
    - Por exemplo, selecione o número do cliente US-004.  
5. Selecione **OK**.

## <a name="enter-sales-order-line-details"></a>Insira detalhes da linha da ordem de venda
    
Os bens vendidos pela sua organização podem vir em grades diferenciadas por dimensões, como a configuração, cor, o tamanho e o estilo. Além disso, os produtos podem ser configurados para usar dimensões de armazenamento, incluindo o site, depósito e palete, bem como as dimensões de rastreamento, como números de lote e de série. Quando essas dimensões são atribuídas, você deve selecionar os valores das dimensões na linha da ordem. Para aumentar a eficiência de entrada de ordem, você pode adicionar os respectivos campos de dimensão para a grade da ordem.
    
1. Na seção **Linhas de ordem de venda**, selecione a **Linha da ordem de venda**.
2. Selecione **Dimensões**.
    
    Por exemplo, selecione a cor, o site e o depósito dimensões. As dimensões selecionadas aqui aparecerão na grade de ordem de venda. Se desejar que as seleções persistam, defina a opção **Salvar configuração** como Sim.
    
3. Selecione **OK**.
4. No campo **Número do item**, selecione o botão suspenso para abrir a pesquisa.
5. Para este exemplo, selecione número de item T0004.
    - Se o item for parte de uma categoria de vendas, o nome do item será exibido automaticamente no campo da categoria de vendas.  
    - Se os campos de dimensão de produto já contém um valor, isso ocorre porque o valor é copiado do registro do produto no qual é definido como uma dimensão de produto padrão. Você pode alterar o valor padrão a qualquer momento.   
6. No campo **Cor**, selecione o botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. No campo **Quantidade.**, insira um número
    - Se o item for vendido em unidades diferentes dos itens comprados, quando gerado e armazenado, e uma unidade de medida de vendas for definida no registro do produto, esse valor será mostrado no campo **Unidade**. É possível alterar o valor a qualquer momento.   
    - Se o campo **Site** já tiver um valor, o valor foi copiado do cabeçalho da ordem ou das configurações de ordem associadas ao produto. É possível alterar o valor a qualquer momento. Se o campo estiver vazio, selecione um valor.   
    - Se o campo **Preço unitário** já tiver um valor, o valor foi copiado do contrato comercial válido ou de registro do produto. (O preço unitário também pode se originar de um contrato de venda, mas o processo para criar ordens de venda a partir dos contratos de venda é diferente do exibido aqui.) Se o campo estiver vazio, insira um valor.   
    - O campo **Desconto** contém um valor de desconto por unidade de produto. Para calcular o valor total do desconto de linha, o valor do desconto é multiplicado pela quantidade de linhas. Se o campo **Desconto** já tiver um valor, o valor foi copiado do contrato comercial válido. Se o campo estiver vazio, e você desejar atribuir ao cliente um desconto de linha, insira um valor.  
    - O campo **Percentual de desconto** contém um valor percentual para o qual o valor bruto da linha total deve ser reduzido.  Se o campo **Percentual de desconto** já contém um valor, ele foi copiado de um contrato comercial válido. Se o campo estiver vazio, e você desejar atribuir ao cliente um desconto de linha, insira um valor. 
    - O campo de valor **Líquido** contém um valor calculado com base na quantidade e no preço unitário da linha ajustado por descontos.  Você pode substituir o valor calculado por outro.  

## <a name="review-the-order-totals"></a>Rever os totais da ordem
1. No **Painel de Ação**, selecione **Ordem de venda**.
2. Selecione **Totais**.
    
    A página **Totais** exibe detalhes sobre a ordem inteira. Isso inclui o valor do subtotal, que é a soma de todos os descontos de linha dos valores líquidos ajustados para os descontos eventuais de linha, o valor total da nota fiscal, que é um valor de subtotal ajustado para desconto, encargos diversos, impostos sobre vendas e eventuais nível de fórmula, situação de limite de crédito do cliente, etc. O valor da nota fiscal é o valor que aparecerá no documento da nota fiscal do cliente.  
    
3. Selecione **OK**.
