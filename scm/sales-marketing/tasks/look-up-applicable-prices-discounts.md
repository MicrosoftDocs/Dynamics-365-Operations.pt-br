--- 
title: "Pesquisar preços e descontos aplicáveis"
description: "Este procedimento mostra como encontrar o preço e/ou desconto para um produto que é válido no momento para um cliente específico, sem criar uma ordem de venda."
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
ms.openlocfilehash: ecfe2ad4dbba74cb067628b63abaf780bcf0680e
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="look-up-applicable-prices-and-discounts"></a>Pesquisar preços e descontos aplicáveis

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como encontrar o preço e/ou desconto para um produto que é válido no momento para um cliente específico, sem criar uma ordem de venda. O procedimento aborda um exemplo específico, e você precisa seguir o exemplo utilizando a empresa de demonstração USMF para selecionar os valores necessários.


## <a name="find-the-applicable-price"></a>Localizar o preço aplicável
1. Vá para Vendas e marketing > Preços e descontos > Encontrar preços.
2. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o cliente US-001.
4. Na lista, clique no link na linha selecionada.
5. No campo Número do item, digite 'T0004'.
    * Por padrão, o campo Quantidade está definido como 1. No entanto, se você souber o tamanho da ordem que o cliente pretende realizar para o produto em questão, insira este valor no lugar. Essa informação é relevante se os contratos comerciais com o cliente tem divisões de quantidade, ou seja, o preço do produto depende da quantidade mínima comprada.  
6. No campo Data, insira uma data para quando o cliente espera fazer um pedido. 
    * A data pode ser a data de hoje ou qualquer data futura.  
    * O sistema agora retorna o preço que é válido para o produto selecionado quando comprado pelo cliente selecionado na data selecionada com uma quantidade especificada. Neste exemplo, se o cliente US-001 comprou 1 unidade do produto T0004 hoje, seria cobrado do cliente 350 CAD por unidade Esse preço é obtido de um contrato comercial existente e ativo com o cliente.      Outros campos na página fornecem mais detalhes sobre o preço e o custo do produto (se configurado no produto mestre), e a lucratividade calculada.  
    * Se a opção Exibir variantes do produto relacionadas estiver selecionada, significa que existem contratos comerciais adicionais para variantes do produto.  
7. Clique na caixa de seleção Exibir variantes do produto relacionadas.
    * Uma lista das variantes do produto é exibida, com informação sobre suas dimensões.  
8. Na lista, marque a linha que representa a cor Branca.
    * Note que o preço do produto agora é diferente daquele exibido anteriormente quando não era especificado por dimensão.  
9. Clique em Exibir preços de venda.
    * A página Preços (venda) exibe todos os contratos comerciais aplicáveis ao produto, incluindo suas variantes.  
10. Feche a página.

## <a name="find-the-applicable-discount"></a>Localizar o desconto aplicável
    * Verifique se o campo Conta de cliente contém o número de cliente US-001    
1. No campo Número do item, digite 'T0012'.
    * Verifique se o campo Quantidade está definido como 1.  
    * Os seguintes detalhes de definição de preços mostrados para o produto T0012 vêm de um ou mais contratos comerciais: O preço unitário é 1.000 CAD e a porcentagem de desconto é 5.  
2. Defina a quantidade como '20'.
    * A quantidade da ordem aumentada faz com que o desconto de linha que será oferecido ao cliente mude de 5 para 7 por cento.  
    * O Valor líquido é calculado com base no preço unitário, desconto e na quantidade total.  
3. Clique em Exibir desconto de linha.
    * Existem dois contratos de linha de desconto para o produto T0012, especificando um desconto de 5 por cento para uma quantidade de linha de ordem de 1 a 10, e 7 por cento para quantidades de ordem acima de 10. Observe que os descontos estão aplicados a um grupo de produtos, neste exemplo, Grupo código 01, do qual o produto T0012 é membro.  
4. Feche a página.


