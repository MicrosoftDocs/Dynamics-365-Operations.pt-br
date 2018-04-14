--- 
title: Criar um modelo de fatura de texto livre
description: "Este registro usa a empresa de dados de demonstração USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice-template"></a>Criar um modelo de fatura de texto livre

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este registro usa a empresa de dados de demonstração USMF. O registro é direcionado para o usuário responsável por gerenciar e processar faturas A/R.

1. Vá para Contas a receber > Faturas > Faturas recorrentes > Modelos de fatura de texto livre.
    * Use este formulário para criar modelos de fatura de texto livre que podem incluir linhas da fatura, encargos, um modelo de distribuição contábil e informações da conta contábil.  
2. Clique em 'Novo' para criar um novo modelo de fatura de texto livre.
3. No campo Nome de modelo, digite um valor.
    * Especialmente 'Nome do modelo' identifica um modelo de fatura de texto livre. Nenhum do dois modelos pode ter o mesmo 'Nome do modelo'.  
4. No campo Descrição, insira uma descrição do modelo.
5. Expanda a guia nas linhas da nota fiscal.
6. No campo Descrição, insira uma descrição da linha de fatura.
7. No campo Conta principal, selecione uma conta de receita.
    * Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.  
8. No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.
    * O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.  
9. Na lista, clique no link na linha selecionada.
10. No campo Grupo de taxa de item, selecione o grupo de impostos de item para a linha de fatura atual.
11. Na lista, clique no link na linha selecionada.
12. No campo Preço de unidade, insira ou exiba o preço por unidade para a linha de fatura
    * Esse valor é multiplicado pelo campo Quantidade para determinar o valor da linha da fatura.  
13. Adicione uma nova linha ao modelo de fatura de texto livre.
14. No campo Descrição, insira uma descrição da linha de fatura.
15. No campo Conta principal, selecione uma conta de receita.
    * Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.  
16. No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.
    * O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.  
17. Na lista, clique no link na linha selecionada.
18. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
    * O grupo de impostos do item para a linha de fatura atual.  
19. Na lista, clique no link na linha selecionada.
20. Insira ou exiba o número de unidades da linha da fatura
    * Esse número é multiplicado pelo valor no campo Preço unitário para determinar o valor da linha da fatura.  
21. Insira ou exiba o preço unitário para a linha de fatura. 
    * Esse valor é multiplicado pelo valor no campo Quantidade para determinar o valor da linha da fatura.  
22. Exiba e modifique as distribuições contábeis para uma linha individual e todas as linhas descendentes.
    * As distribuições contábeis definem como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre.  
23. Atualizar as distribuições contábeis para a linha de fatura selecionada.
24. Clique em Fechar.


