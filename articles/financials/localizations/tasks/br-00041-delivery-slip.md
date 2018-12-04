--- 
title: Guias de entrega (Brasil)
description: "Você pode lançar uma guia de entrega para uma ordem de venda com várias linhas de ordem de venda com um código CFOP (Código Fiscal de Operações e Prestações)."
author: sndray
manager: AnnBe
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 853d9d45defe386997e8d887d4efe85759a22450
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="delivery-slips-brazil"></a>Guias de entrega (Brasil)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Você pode lançar uma guia de entrega para uma ordem de venda com várias linhas de ordem de venda com um código CFOP (Código Fiscal de Operações e Prestações). Para cada linha de ordem de venda, você deve especificar o código CFOP que tem um código CFOP de entrega atribuído a ele. Uma guia de entrega é usada quando o cliente para o qual você entrega itens difere do cliente que é faturado. (Ou seja, a conta do cliente e a conta da fatura diferem.) As guias de entrega são lançadas em ordem cronológica. É preciso anexar referências fiscais a guias de entrega antes de lançá-las. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
4. Clique em OK.
5. No campo Linhas ou cabeçalho, selecione uma opção.
6. No campo Conta de fatura, insira ou selecione um valor.
    * Selecione o cliente que encomendou mercadorias.  
7. No campo Linhas ou cabeçalho, selecione uma opção.
8. Clique em Adicionar linha.
9. Na lista, marque a linha selecionada.
10. No campo Número do item, insira ou selecione um valor.
11. No campo Quantidade, insira um número.
12. No campo Local, insira ou selecione um valor.
13. No campo Depósito, insira ou selecione um valor.
14. No campo CFOP, insira ou selecione um valor.
    * Os códigos de CFOP disponíveis dependem do estabelecimento fiscal do site, tipo de ordem, tipo de operação, localização do cliente e endereço de entrega do cliente.  
15. Expanda a seção Detalhes da linha.
16. Clique na guia Configuração.
17. No campo Grupo de imposto do item de entrega, insira ou selecione um valor.
    * Insira o grupo de impostos sobre vendas do item para a nota fiscal de entrega.  
18. No campo Grupo de imposto de entrega, insira ou selecione um valor.
    * Insira o grupo de impostos sobre vendas para a nota fiscal de entrega.  
19. Clique em Salvar.
20. No Painel de Ação, clique em Separar e empacotar.
21. Clique em Guia de entrega.
22. Clique em Referência fiscal.
23. No campo Modelo do documento, insira ou selecione um valor.
24. No campo Chave de acesso, digite um valor.
    * Insira a chave de acesso da NF-e que foi emitida pelo cliente que encomendou mercadoria e ao qual as vendas devem ser faturadas.  
25. No campo Data, insira uma data.
26. No campo Direção, selecione uma opção.
27. No campo Conta, insira ou selecione um valor.
    * Selecione a conta do cliente que gerou a nota fiscal.  
28. Clique em Salvar.
29. Feche a página.
30. Clique em OK.
31. Clique em OK.
32. Feche a página.
33. Feche a página.
34. Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.
35. Clique em OK.


