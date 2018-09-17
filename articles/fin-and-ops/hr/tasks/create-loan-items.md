--- 
title: "Criar itens de empréstimo"
description: "Os itens de empréstimo são registros que ajudam a manter o controle dos itens físicos, como telefones ou computadores, que sua empresa empresta aos trabalhadores."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cef1f9b2e3d202d7eea3a967fa8a6c371c6ac3a5
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-loan-items"></a>Criar itens de empréstimo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Os itens de empréstimo são registros que ajudam a manter o controle dos itens físicos, como telefones ou computadores, que sua empresa empresta aos trabalhadores. Cada item físico deve ter um item de empréstimo correspondente. Cada registro de item de empréstimo deve descrever o que está sendo emprestado, quem é a pessoa responsável pelo empréstimo e o número de dias que o item poderá ficar emprestado. Você pode criar vários itens de empréstimo, como chaves, cartões de acesso ou uniformes, ao mesmo tempo. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-loan-types"></a>Criar Tipos de empréstimo
1. Vá para Recursos humanos > Trabalhadores > Itens de empréstimo > Tipos de empréstimo.
2. Clique em Novo.
3. No campo Tipo de empréstimo, digite um valor.
4. No campo Descrição, digite um valor.
5. Insira o número de dias de atraso permitidos para os itens atribuídos a este tipo de empréstimo. 
6. Clique em Salvar.
7. Feche a página.
8. Atualize a página.

## <a name="create-loan-items"></a>Criar Itens de empréstimo
1. Vá para Recursos humanos > Trabalhadores > Itens de empréstimo > Itens de empréstimo.
2. Clique em Criar itens de empréstimo.
3. Em Quantidade. insira um número.
4. No campo Descrição, digite um valor.
5. No campo Tipo de empréstimo, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. Insira o número de dias pelos quais o item pode ser emprestado.
    * O valor padrão do campo Devolução planejada na página de Equipamento emprestado é calculado como a data atual mais esse número.  
9. No campo Pessoa responsável, clique no botão suspenso para abrir a pesquisa.
10. Clique em Selecionar.
11. No campo Valor inicial, insira um número.
12. No campo Intervalo, insira um número.
13. No campo Formato, digite um valor.
    * Por exemplo, se o número de início por um item de empréstimo 10, insira dois símbolos de números no campo Formato.  
14. Clique em OK.
15. Atualize a página.


