---
title: Criar um modelo de fatura de texto livre
description: Este procedimento demonstra como criar um modelo de fatura de texto livre.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8281de3cb336d9392a6a97f98e51a2a139a384c5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440217"
---
# <a name="create-a-free-text-invoice-template"></a>Criar um modelo de fatura de texto livre

[!include [banner](../includes/banner.md)]

Para este passo a passo, use a empresa de demonstração USMF. Este procedimento é direcionado para o usuário responsável por gerenciar e processar faturas A/R.

## <a name="create-a-template"></a>Criar um modelo

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

## <a name="save-a-free-text-invoice-as-a-template"></a>Salvar uma fatura de texto livre como modelo
Você também pode salvar uma fatura de texto livre existente como um modelo. Quando selecionar Salvar no modelo na guia Fatura, forneça um nome e uma descrição para o modelo. Se um modelo com o nome já existir, uma notificação de que um modelo com esse nome já existe será exibida. Você ainda poderá clicar em OK para substituí-lo. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]