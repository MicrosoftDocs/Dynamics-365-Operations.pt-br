--- 
title: " Criar ordens de call center"
description: Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f702690f72b3e299f6c2744da326a23d5753eb5d
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-call-center-orders"></a> Criar ordens de call center

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente. Este procedimento usa a empresa de dados de demonstração USRT e destina-se ao funcionário de ordens de venda. Pré-requisitos: O usuário que conclui o procedimento é configurado como usuário do call center e o catálogo semestral da Fabrikam é publicado com pelo menos um código fonte nele.

1. Vá para Varejo e comércio > Clientes > SAC.
2. No campo Texto da pesquisa, insira os critérios de pesquisa para pesquisar o cliente.
    * Para este procedimento de exemplo, digite 'Karen' e pressione tab.  
3. Clique em Pesquisar.
    * Uma vez que há somente uma cliente chamada Karen nos dados de demonstração, eles serão automaticamente selecionados.  
4. Clique em Nova ordem de venda.
5. Expanda ou recolha a seção do Cabeçalho de ordem de venda.
6. Selecione o código fonte para o catálogo.
    * Se não houver nenhum Código fonte ativo, você pode fechar o Campo de origem e ignorar essa etapa.  
7. Clique em Adicionar linha.
8. No campo número do item, digite o termo de pesquisa do item.
    * Para este procedimento de exemplo, insira um número de item parcial de '8111' e pressione tab. Isso fará surgir a janela de pesquisa de itens.  
9. Selecionar o produto para ser adicionado à ordem de venda
10. Insira a quantidade de vendas.
11. Clique em Criar.
12. Clique em Concluir para capturar o pagamento do cliente.
13. Clique em Adicionar.
    * A opção Adicionar link está na guia Pagamentos. Expanda a guia Pagamentos se ela estiver recolhida.  
14. Selecione o método de pagamento.
    * Para este procedimento, selecione o método de pagamento à vista.  
15. Feche a página.
16. Insira o valor.
    * Para este procedimento, insira um valor igual ao saldo da ordem que pode ser visto na página Resumo da ordem de venda, à esquerda do campo de valor. Isto permitirá que você conclua a ordem como totalmente paga.  
17. Clique em OK.
18. Clique em Enviar.


