---
title: Criar transações de imposto em documentos
description: Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11e006e41f467a594521dfc601f46b4d1b492ce5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440435"
---
# <a name="create-sales-tax-transactions-on-documents"></a>Criar transações de imposto em documentos

[!include [banner](../../includes/banner.md)]

Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento. Esses padrões derivam dos dados mestre, mas podem ser alterados manualmente, se necessário. Os impostos sobre vendas calculado podem ser feitos em um nível de linha e do documento. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a receber > Ordens > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em OK.
7. Na lista, marque a linha selecionada.
8. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
9. Na lista, clique no link na linha selecionada.
10. No campo Preço unitário, insira um número.
11. Expandir ou recolher a seção Detalhes de linha.
12. Clique na guia Configuração.
13. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
14. Na lista, localize e selecione o registro desejado.
15. Na lista, clique no link na linha selecionada.
16. Clique em Financeiros.
17. Clique em Impostos.
18. Clique em OK.
19. Clique em Adicionar linha.
20. Na lista, marque a linha selecionada.
21. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
22. Na lista, localize e selecione o registro desejado.
23. Na lista, clique no link na linha selecionada.
24. No campo Preço unitário, insira um número.
25. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
26. Na lista, localize e selecione o registro desejado.
27. Na lista, clique no link na linha selecionada.
28. No Painel de Ação, clique em Vender.
29. Clique em Impostos.
30. Clique em OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]