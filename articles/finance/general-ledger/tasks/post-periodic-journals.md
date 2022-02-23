---
title: Lançar diários periódicos
description: Os diários periódicos são as vezes chamados diários de devolução porque o valor, o texto, e outras informações são repetidos toda vez que o diário periódico é recuperado.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99d157e82f8451e2c8f0bc7946ba30ca48e99add
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968495"
---
# <a name="post-periodic-journals"></a>Lançar diários periódicos

[!include [banner](../../includes/banner.md)]

Os diários periódicos são as vezes chamados diários de devolução porque o valor, o texto, e outras informações são repetidos toda vez que o diário periódico é recuperado. Quando você cria o diário periódico, você especifica o intervalo do período para a recorrência, como dias ou meses. Essa guia da tarefa criará um diário periódico com uma recorrência mensal.

1. Acesse **Painel de Navegação > Módulos > Contabilidade > Tarefas periódicas > Diários periódicos**.
2. Clique em **Novo**.
3. No campo **Nome**, insira ou selecione um valor.
4. Na lista, clique no link na linha selecionada.
5. No campo **Descrição**, digite um valor. A descrição será o nome do diário periódico quando recuperada posteriormente e isso garantirá atribuir um nome relevante.
6. No **Painel de ação**, clique em **Linhas**. Um diário periódico incluirá normalmente várias linhas do diário. essa guia de tarefa no entanto adicionará apenas uma linha.
7. No campo **Data**, insira uma data. O campo **Data** contém a data de lançamento da próxima transferência para o diário. Para os diários que serão recuperados cada mês na qual recomenda-se usar a data do mês em que será lançado, normalmente a primeira e a última data do período. É possível deixar o campo Data e inserir uma data quando o diário for recuperado, usando o campo vazio de data. O campo é atualizado automaticamente para a próxima data de devolução em que as transações são recuperadas. 
8. No campo **Conta**, especifique os valores desejados.
9. No campo **Descrição**, selecione um valor.
10. Feche a página.
11. No campo **Débito**, insira um número.
12. No campo **Contrapartida**, especifique os valores desejados.
13. No campo **Unidade**, selecione "Meses".
14. No campo **Número de unidades**, insira "1".
15. No campo **Última data**, insira uma data. Inserir a última data do período anterior evitará que o diário de devolução seja criado por engano no período inicial incorreto. A última data será atualizada posteriormente cada vez que o diário periódico for recuperado. 
16. Clique em **Salvar**.
17. Vá até **Painel de Navegação > Módulos > Contabilidade > Entradas de diário > Diários gerais**.
18. Clique em **Novo**.
19. No campo **Nome**, insira ou selecione um valor.
20. Na lista, localize e selecione o PDV desejado.
21. Na lista, clique no link na linha selecionada.
22. No campo **Descrição**, digite um valor.
23. No **Painel de ação**, clique em **Linhas**.
24. No **Painel de Ações**, clique em **Diário do período**.
25. Clique em **Recuperar diário**.
26. No campo **Data final**, insira uma data. A opção **Até a data** serve como a data de fechamento para as linhas de comprovante periódicas. Com base na configuração de recorrência, a Última data e Até data da mesma linha podem ser incluídas mais de uma vez no diário resultante. Até data é atualizado automaticamente com base na data da sessão de vezes em que a linha periódica foi transferida para um diário. 
27. No campo **Número de diário periódico**, insira ou selecione um valor.
28. Na lista, clique no link na linha selecionada.
29. Clique em **OK**. O diário do período pode então ser revisto aprovado ou lançado, dependendo do requisito e da configuração.   
