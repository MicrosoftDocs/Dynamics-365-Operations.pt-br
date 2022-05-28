---
title: Criar transações de imposto em documentos
description: Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20a021ae4f713a74bdd565cc1470e5d95efc8b71
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735601"
---
# <a name="create-sales-tax-transactions-on-documents"></a>Criar transações de imposto em documentos

[!include [banner](../../includes/banner.md)]

Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento. Esses padrões derivam dos dados mestre, mas podem ser alterados manualmente, se necessário. Os impostos sobre vendas calculado podem ser feitos em um nível de linha e do documento. Esta tarefa usa a empresa de demonstração USMF.

1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Clique em **Novo**.
3. No campo **Conta do cliente**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em **OK**.
7. Na lista, marque a linha selecionada.
8. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
9. Na lista, clique no link na linha selecionada.
10. No campo **Preço unitário**, insira um número.
11. Expanda ou recolha a seção **Detalhes da linha**.
12. Clique na guia **Configuração**.
13. No campo **Grupo de impostos do item**, clique no botão suspenso para abrir a pesquisa.
14. Na lista, localize e selecione o registro desejado.
15. Na lista, clique no link na linha selecionada.
16. Clique em **Financeiros**.
17. Clique em **Impostos**.
18. Clique em **OK**.
19. Clique em **Adicionar linha**.
20. Na lista, marque a linha selecionada.
21. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
22. Na lista, localize e selecione o registro desejado.
23. Na lista, clique no link na linha selecionada.
24. No campo **Preço unitário**, insira um número.
25. No campo **Grupo de impostos do item**, clique no botão suspenso para abrir a pesquisa.
26. Na lista, localize e selecione o registro desejado.
27. Na lista, clique no link na linha selecionada.
28. No Painel de Ações, clique em **Vender**.
29. Clique em **Impostos**.
30. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
