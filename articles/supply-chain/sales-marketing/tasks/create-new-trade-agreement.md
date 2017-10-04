--- 
title: Criar um novo contrato comercial
description: "Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
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
ms.openlocfilehash: 1178c7a5db129801f83afa8b4caf9357ccf76b71
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-trade-agreement"></a>Criar um novo contrato comercial

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando seus próprios dados, antes de iniciar esse guia será preciso ter certeza de que um Nome de diário de contratos comerciais existe onde a Relação padrão está definida como 'Preços (vendas)'.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Criar e lançar um novo diário de contratos comerciais.
1. Vá para Vendas e marketing > Preços e descontos > Diários de contratos comerciais.
2. Clique em Novo.
3. No campo Nome, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em Linhas.
7. No campo Código da conta, selecione 'Tabela'.
    * Neste exemplo, você está atualizando o preço para um cliente específico, o que significa quem você precisa selecionar Tabela. Se você estava atualizando o preço da lista de produtos, você deve selecionar Todos, de modo que o novo preço seja válido para todos os clientes. Se você estava diferenciando preços entre diferentes segmentos de clientes, então você deve selecionar Grupo. Para selecionar Grupo, é necessário configurar Grupos de preços ao cliente.  
8. No campo Seleção de conta, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
10. No campo Código do item, selecione 'Tabela'.
    * Quando você está inserindo um contrato comercial do tipo 'Preço (vendas)', você deve selecionar apenas 'Tabela' no campo de código do item. Isso ocorre porque um preço é um valor absoluto e não pode ser o mesmo para todos os produtos ou para um grupo de produtos.  
11. No campo Relação do item, clique no botão suspenso para abrir a pesquisa.
12. Na lista, selecione o produto que deseja incluir no contrato.
    * Faça uma nota dos produtos que você selecionou.  
13. Na lista, clique no link na linha selecionada.
14. No campo De, insira uma quantidade mínima.
    * Se o cliente tem que solicitar uma quantidade mínima antes de se qualificar para o novo preço, então você precisa especificar essa quantidade aqui.  
    * Insira um valor no campo Para para especificar a quantidade máxima acima da qual o preço do contrato não será válido. Se você oferece preços e descontos com base em múltiplas divisões de quantidade, então especifique cada faixa de quantidade como um par de quantidade mínima e máxima nos campos 'De' e 'Para', respectivamente.  
15. No campo Valor em moeda, insira um preço.
16. No campo A partir da data, insira uma data a partir da qual esse contrato será válido.
17. Clique em Salvar.
18. Clique em Validar.
19. Clique em Validar as linhas selecionadas.
20. Clique em OK.
21. Clique em Lançar.
22. Clique em OK.

## <a name="view-trade-agreements-for-a-product"></a>Exibir contratos comerciais para um produto
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, localize e selecione o produto cujo preço você acabou de atualizar.
3. No Painel de Ação, clique em Vender.
4. Clique em Exibir contratos comerciais.
    * Revise os detalhes do contrato comercial de preço que acabou de criar.    
5. Feche a página.

