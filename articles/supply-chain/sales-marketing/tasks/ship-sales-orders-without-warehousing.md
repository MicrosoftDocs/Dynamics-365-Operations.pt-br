--- 
title: Enviar ordens de venda sem armazenamento
description: "Este guia demonstra como atualizar uma ordem de venda quando produtos são enviados ao cliente."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3f1b9dd4b99bcbcc6cfbc5cfd8e3271fa80c628c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="ship-sales-orders-without-warehousing"></a>Enviar ordens de venda sem armazenamento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia demonstra como atualizar uma ordem de venda quando produtos são enviados ao cliente. Este guia é aplicável ao fluxo de realizações que não está definido para o gerenciamento de depósito (sem armazenamento básico ou avançado) e, portanto, não requer separação de produtos que serão registrados antes da remessa. Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração. Em ambos os casos, antes de começar esta tarefa, crie uma ordem de venda para um produto inventariado com uma quantidade maior que 1. Para evitar um erro de lançamento, você precisa verificar se a quantidade disponível do produto no site e o depósito que você selecionou na ordem abrangem a quantidade da ordem.


## <a name="post-packing-slip-for-an-order"></a>Lançar guia de remessa para uma ordem
1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Na lista, localize e selecione a ordem que você criou para essa tarefa.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em Separar e empacotar.
5. Clique em Postar guia de remessa.
6. Expanda e recolha a seção Parâmetros.
7. No campo Quantidade, selecione 'Tudo'.
    * Outras opções incluem Entregar agora e Separado. Se a linha da ordem estiver pronta para ser parcialmente remetida e o campo Entregar agora na linha da ordem contiver uma quantidade, você selecionará Entregar agora. Se o fluxo de realizações da sua organização incluir a separação como um processo à parte que é gerenciado por e registrado com uma lista de separação, você selecionará Separado.  
    * Verifique se a opção Lançamento está definida como Sim.  
8. Defina a opção Imprimir guia de remessa como Sim.
    * A guia Visão geral contém uma lista de guias de remessa que serão geradas nesse lançamento. Se estiver remetendo uma ordem individual, normalmente haverá uma guia de remessa. No entanto, se as linhas dessa ordem estiverem prontas para ser enviadas de sites diferentes, o lançamento será automaticamente dividido no número apropriado de documentos. Essa é uma condição obrigatória que não pode ser alterada. De modo semelhante, o lançamento também será dividido em vários documentos se as linhas da ordem estiverem prontas para ser enviadas a endereços de entrega diferentes, e a política de envio é definida para requerer divisão.  
9. Na guia Linhas, selecione a linha para a linha de ordem que será remetida.
10. No campo Atualizar, insira um número menor que a quantidade original.
11. Clique em OK.
12. Clique em Sim.
13. Feche a página.
14. No Painel de Ação, clique em Opções.
15. Clique em Alterar exibição.
16. Clique em Exibição do cabeçalho.
    * Se todas as linhas na ordem foram completamente enviadas, o status da ordem muda de Aberto para Entregue.  
    * Neste exemplo, a linha da ordem foi remetida parcialmente. É por isso que o status da ordem permanece Aberto.     
    * Se o campo Status do documento estiver definido como Guia de remessa, é porque pelo menos uma das linhas da ordem foi enviada.  
17. No Painel de Ação, clique em Geral.
18. Clique em Quantidade da linha.
19. Feche a página.
20. No Painel de Ação, clique em Separar e empacotar.
21. Clique em Guia de remessa.
    * A página Diário de guias de remessa contém todos os documentos de guia de remessa que foram gerados para sua ordem. Você pode revisar os detalhes de cada documento e imprimi-los, se desejar.  


