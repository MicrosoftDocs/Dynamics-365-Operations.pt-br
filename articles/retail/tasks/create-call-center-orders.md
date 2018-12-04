--- 
title: Criar ordens de call center
description: Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: b2e986df1e089ef2a394d0e9d9236d39f2726c77
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="create-call-center-orders"></a>Criar ordens de call center

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


