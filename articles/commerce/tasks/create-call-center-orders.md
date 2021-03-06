---
title: Criar ordens de call center
description: Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8dc9e19ecd6b835569ba80563bce33134895cb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791646"
---
# <a name="create-call-center-orders"></a>Criar ordens de call center

[!include [banner](../includes/banner.md)]

Este procedimento orienta como pesquisar um cliente, criar uma nova ordem, pesquisar por um produto e coletar os pagamentos do cliente. Este procedimento usa a empresa de dados de demonstração USRT e destina-se ao funcionário de ordens de venda. Pré-requisitos: O usuário que conclui o procedimento é configurado como usuário do call center e o catálogo semestral da Fabrikam é publicado com pelo menos um código fonte nele.

1. Vá para **Retail e Commerce \> Clientes \> Customer service**.
2. Para **Texto da Pesquisa**, insira os critérios de pesquisa para pesquisar o cliente.
    * Para este procedimento de exemplo, insira "Karen" e selecione **Tab**.  
3. Selecione Pesquisar.
    * Uma vez que há somente uma cliente chamada "Karen" nos dados de demonstração, o resultado será automaticamente selecionado.  
4. Selecione **Nova ordem de venda**.
5. Expanda ou recolha a seção de cabeçalho **Ordem de venda**.
6. Selecione o código fonte para o catálogo.
    * Se não houver nenhum código fonte ativo, você poderá ignorar esta etapa.  
7. Selecione **Adicionar linha**.
8. Para **Número do item**, insira o termo de pesquisa do item.
    * Para este procedimento de exemplo, insira um número de item parcial de '8111' e pressione tab. Essa ação fará surgir a janela de pesquisa de itens.  
9. Selecione o produto a ser adicionado à ordem de venda.
10. Insira a quantidade de vendas.
11. Selecione **Criar**.
12. Selecione **Concluir** para capturar o pagamento do cliente.
13. Selecione **Adicionar**.
    * A opção Adicionar link está na guia Pagamentos. Expanda a guia Pagamentos se ela estiver recolhida.  
14. Selecione o método de pagamento.
    * Para este procedimento, selecione o método de pagamento à vista.  
15. Feche a página.
16. Insira o valor.
    * Para este procedimento, insira um valor igual ao saldo da ordem que pode ser visto na página Resumo da ordem de venda, à esquerda do campo de valor. Essa ação permitirá que você conclua a ordem como totalmente paga.  
17. Selecione **OK**.
18. Selecione **Enviar**.

## <a name="additional-resources"></a>Recursos adicionais

[Personalizar emails transacionais por modo de entrega](../customize-email-delivery-mode.md)

[Alterar modo de entrega no PDV](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]