---
title: Criar um orçamento original e depois reverter entradas de orçamento preliminar no setor público
description: Quando você cria uma entrada de orçamento original e usa o modelo de orçamento e os valores de dimensão que contêm valores de orçamento preliminar, os valores de orçamento preliminar podem ser revertidos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32d89216d49a743729de8910f738276cbddcd8bb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440443"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>Criar um orçamento original e depois reverter entradas de orçamento preliminar no setor público

[!include [banner](../../includes/banner.md)]

Quando você cria uma entrada de orçamento original e usa o modelo de orçamento e os valores de dimensão que contêm valores de orçamento preliminar, os valores de orçamento preliminar podem ser revertidos. Este procedimento foi criado usando os dados da empresa de demonstração PSUS na partição do setor público.

1. Vá para Orçamento > Entradas de registro de orçamento.
2. Clique em Novo.
3. No campo Modelo de orçamento, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. No campo Orçamento, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique em Orçamento original.
7. Clique em Salvar.
8. Clique em Adicionar linha.
9. Opcionais: Se quiser alterar a data de em um cabeçalho, insira uma nova data. Esta data determina o período fiscal no qual o orçamento será registrado.
10. No campo Estrutura de conta, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o registro desejado.
12. No campo Valores de dimensão, especifique os valores desejados.
13. No campo Valor, insira um número.
14. No campo Moeda, clique no botão suspenso para abrir a pesquisa.
15. Na lista, clique no link na linha selecionada.
16. Clique em Salvar.
17. Clique em Atualizar saldos de orçamentos.
    * Opcionais: Você pode selecionar a opção Reverter orçamento preliminar. Observe que você pode reverter todas as entradas de orçamento preliminar, ou somente as entradas de orçamento preliminar com o código de orçamento que você especificar.  
    * Para fazer seleções opcionais, clique no ícone Desbloquear na parte superior da página.  
18. Clique em Atualizar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]