--- 
title: Emitir notas fiscais para fornecedores (Brasil)
description: "Você pode criar e lançar faturas de fornecedor em nome dos fornecedores que não são contribuintes."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
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
ms.openlocfilehash: 82de46c4e9b03aa15fdfad189cc55925eb40281a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="issue-fiscal-documents-for-vendors-brazil"></a>Emitir notas fiscais para fornecedores (Brasil)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Você pode criar e lançar faturas de fornecedor em nome dos fornecedores que não são contribuintes. Você deve atribuir um estabelecimento fiscal a um site. Você também deve configurar um tipo de documento fiscal para as ordens de compra que você criar e lançar no nome de fornecedores que não são contribuintes. Antes de criar e lançar faturas de fornecedores no nome de fornecedores que não são contribuintes, é necessário especificar o fornecedor como fornecedor que não é contribuinte. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Contas a pagar > Fornecedores > Todos os fornecedores.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Expanda a seção Informações fiscais.
5. Clique em Editar.
6. Selecione Sim no campo Gerar nota fiscal recebida.
    * Marque esta opção para indicar que o fornecedor é um não contribuinte.  
7. Selecione Sim no campo Uso e consumo.
8. Selecione Não no campo Contribuinte do ICMS.
9. Clique em Salvar.
10. Feche a página.
11. Feche a página.
12. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
13. Clique em Novo.
14. No campo Conta de fornecedor, insira ou selecione um valor.
    * Selecione uma conta de fornecedor que é classificada como não contribuinte.  
15. Clique em OK.
16. No campo Número do item, insira ou selecione um valor.
17. No campo CFOP, insira ou selecione um valor.
18. No campo Local, insira ou selecione um valor.
19. No campo Depósito, insira ou selecione um valor.
20. No campo Quantidade, insira um número.
21. Clique em Salvar.
22. No Painel de Ação, clique em Compra.
23. Clique em Confirmar.
24. Feche a página.
25. Feche a página.
26. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
27. Na lista, clique no link na linha selecionada.
28. No Painel de Ação, clique em Fatura.
29. Clique em Fatura.
30. Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.
31. No campo Quantidade padrão para linhas, selecione uma opção.
32. Clique em OK.
33. Clique em Lançar.
34. Feche a página.
35. Feche a página.
36. Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.
37. Clique em OK.


