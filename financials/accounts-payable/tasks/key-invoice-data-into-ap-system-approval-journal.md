--- 
title: "Dados-chave de fatura em contas a pagar usando um diário de aprovações"
description: "Este guia de tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais e usar no diário de aprovações para atualizar as contas de despesas."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d7cf810f1d8eabb9989fdd858585afcdf2e9574b
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Dados-chave de fatura em contas a pagar usando um diário de aprovações

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais e usar no diário de aprovações para atualizar as contas de despesas.


## <a name="create-and-post-and-invoice"></a>Criar e lançar e faturar
1. Ir para Contas a pagar > Faturas > Registro de fatura.
2. Clique em Novo.
3. Selecione o nome do registro de fatura que você deseja usar.
4. Na lista, clique no link na linha selecionada.
5. Clique em em Linhas para abrir o registro e para inserir linhas de despesa.
6. Selecione um fornecedor. Por exemplo, digite ou selecione US-104
7. No campo Fatura, digite um valor.
8. No campo Descrição, digite um valor.
9. No campo Crédito, insira um número.
10. No campo Aprovado por, clique no botão suspenso para abrir a pesquisa.
11. Realce um aprovador e clique em selecionar para selecionar o aprovador.
12. Clique em Lançar.
13. Feche a página.
14. Feche a página.

## <a name="approve-an-invoice"></a>Aprovar uma fatura
1. Ir para Contas a pagar > Faturas > Aprovação de fatura.
2. Clique em Novo.
3. Selecione o nome do diário de aprovação de fatura que você deseja usar.
4. Na lista, clique no link na linha selecionada.
5. Clique em Linhas para exibir uma página na qual você possa selecionar as notas fiscais que deseja aprovar.
6. Selecione comprovantes de localização para exibir todas as notas fiscais que estão prontas para aprovação.
7. Marque a nota fiscal que você criou.
8. Clique em Selecionar.
    * Os comprovantes que tiver selecionado acima são movidos para esta lista depois que você os seleciona.  
9. Clique em OK.
10. Clique no campo do número de conta para adicionar uma conta de despesas na nota fiscal.
11. Insira um número de conta e desmarque o campo. Por exemplo, insira 600120.
12. Clique em Lançar.
13. Clique no comprovante para exibir as entradas que foram lançadas.
    * A nota fiscal durante a conta de aprovação é revertida e substituída pela conta de despesa real.  


