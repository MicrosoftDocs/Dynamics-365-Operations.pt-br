--- 
title: Dados-chave de fatura no sistema de AP usando grupo de faturas
description: "Esta guia da tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Dados-chave de fatura no sistema de AP usando grupo de faturas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guia da tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais.  Use o grupo de notas fiscais para fazer a correspondência da nota fiscal para uma ordem de compra e finalizar as despesas na página da nota fiscal do fornecedor.


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Vá para Contas a pagar > Ordens de compra > Ordens de compra.
2. Clique em Novo para criar uma ordem de compra.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. Selecione o fornecedor na lista. Por exemplo, fornecedor 1001.
5. Clique em OK.
6. No campo Número do item, clique no botão suspenso para abrir a pesquisa.
7. Localizar o número de item de serviço na lista. Por exemplo, selecione S0001.
8. Clique no número de item e o selecione.
    * O total líquido é 75,00.  Esse é o valor que esperaremos na nota fiscal.  
9. No painel de ação, clique em Compra.
10. Clique em Confirmar.

## <a name="create-and-post-and-invoice"></a>Criar e lançar e faturar
1. Vá para Contas a pagar > Faturas > Registro de fatura.
2. Clique em Novo.
3. Abra a busca para selecionar o nome do registro de fatura que você deseja usar.
4. Selecione o nome do registro de fatura que você deseja usar.
5. Clique em em Linhas para abrir o registro e para inserir linhas de despesa.
6. Na busca, selecione um fornecedor. Por exemplo, clique em vendor 1001.
7. No campo Fatura, insira o número da fatura.
8. No campo Descrição, digite um valor.
9. No campo Crédito, insira um número.
10. No campo Ordem de compra, clique no botão suspenso para abrir a pesquisa.
11. Selecione a ordem de compra que você criou anteriormente.
12. No campo Aprovado por, clique no botão suspenso para abrir a pesquisa.
13. Realce um aprovador e clique em selecionar para selecionar o aprovador.
14. Clique em Lançar.
15. Feche o formulário.
16. Feche o formulário.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Abra uma fatura do grupo e corresponda-a a ordem de compra para concluir o processo de fatura
1. Vá para Contas a pagar > Faturas > Grupo de fatura.
2. Clique em Ordem de compra para criar uma fatura de fornecedor da fatura no grupo.
3. Selecione a fatura que você deseja revisar.
4. Clique no status de correspondência de atualização para concluir a correspondência.
5. No painel de ação, clique em Opções.
6. Clique em Alterar exibição.
7. Clique em Exibição de grade.
8. Clique em Lançar.
9. Feche o formulário.
10. Vá para Contas a pagar > Fornecedores > Fornecedores.
11. Selecione o fornecedor que estava na ordem de compra. Por exemplo, selecione fornecedor 1001.
12. Na lista, clique no link na linha selecionada.
13. No painel de ação, clique em Fornecedor.
14. Clique em Transações.
15. Selecione a nota fiscal que você criou.
    * O acúmulo de registro de nota fiscal foi estornada e lançada na conta de despesas apropriada.  


