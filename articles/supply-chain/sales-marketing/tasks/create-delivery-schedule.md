---
title: Criar agenda de entrega
description: Este procedimento demonstra como criar uma agenda de entrega para ordem de venda.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7341ec21a89bf952e2fd21e9bebf7de65a1b2648
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421990"
---
# <a name="create-delivery-schedule"></a>Criar agenda de entrega

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como criar uma agenda de entrega para ordem de venda. Um plano de entrega é usado quando uma quantidade em uma ordem ou cotação for exigido para ser entregue em várias remessas. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="create-delivery-schedule"></a>Criar agenda de entrega
1. Ir para Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
4. Clique em OK.
5. No campo Número do item, insira ou selecione um valor.
6. No campo Quantidade, insira um número que é maior do que 1.
7. Clique em Linha da ordem de venda.
8. Clique em Agenda de entrega.
    * A página do plano de entrega é o local onde é possível especificar o número de remessas na qual a quantidade total da linha da ordem será enviado ao cliente.    
    * Por padrão, o sistema copia a quantidade total e outros detalhes de entrega das vendas originais de linha na primeira linha do plano de entrega. Neste exemplo, criaremos um plano para duas remessas, com a segunda data de remessa compensada em uma semana da primeira.  
9. No campo Quantidade, insira um número que faz parte da quantidade total.
10. Clique em Novo.
11. No campo Quantidade, insira a quantidade restante.
12. No campo Data de remessa solicitada, insira uma data a partir de uma data que seja uma semana depois da data da primeira linha de entrega.
    * As duas opções na conversão dos encargos FastTab controlam como deseja que os encargos devem ser distribuídos nas linhas do plano de entrega, uma vez que foram atribuídos à linha da ordem original. Se você selecionar valores brutos de impressão, o mesmo valor de encargo será copiado para cada linha. A opção Alocar à opção das linhas de entrega divide os encargos igualmente pelas linhas de entrega.  
    * Somente os encargos fixos podem ser divididos, enquanto os encargos variáveis ainda serão copiados para as linhas.  
13. Mova o cursor distante da segunda linha de entrega para atualizar a página.
    * Você pode controlar a quantidade total alocada para as linhas do plano de entrega olhando totais e os campos restantes. Quando a quantidade restante for zero, a quantidade total de linha original esteve alocada ao plano.   
14. Clique em OK.
    * A agenda de entrega agora foi copiada para as linhas da ordem.   
    * A linha da ordem original, conhecida como uma linha comercial, foi convertida em uma linha da ordem com várias entregas. São marcadas com um ícone distinto e atuam como um cabeçalho para as linhas de entrega.  
    * As duas novas linhas, referidas como linhas de entrega, compõem uma agenda de entrega. A ordem será processada nessas linhas e não na linha original. Se os documentos como guias de confirmações, listas de separação, guias de remessa ou notas fiscais forem impressos, apenas as linhas de entrega serão exibidas.   
    * As linhas de entrega podem ter datas de entrega diferentes, quantidades, modos de entrega e dimensões de armazenamento, como o site e o depósito. Entretanto, as dimensões do produto devem corresponder sempre àquela na linha comercial e não podem ser alteradas.  
15. No campo Quantidade, insira um número que é maior do que o atual.
16. Selecione a linha comercial para ver o efeito do recálculo de quantidade.
17. No Painel de Ação, clique em Separar e empacotar.
18. Clique em Postar guia de remessa.
19. Expanda a seção Parâmetros.
20. No campo Quantidade, selecione 'Tudo'.
    * Observe que a guia de remessa será criada para as duas linhas do plano de entrega e não a linha da ordem original.  
21. Selecione Sim no campo Imprimir guia de remessa.
22. Clique em OK.
23. Clique em Sim.
24. Feche a página.
