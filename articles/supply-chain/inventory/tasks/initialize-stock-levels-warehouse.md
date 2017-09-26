---
title: "Inicializar níveis de estoque no depósito"
description: "Esse procedimento mostra como obter o estoque disponível atualizado manualmente usando um diário de movimentação de estoque."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 953125ae6e9d669bd13a3344c9f679747af6ff93
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# Inicializar níveis de estoque no depósito

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento mostra como obter o estoque disponível atualizado manualmente usando um diário de movimentação de estoque. (Também é possível atualizar o estoque disponível importando transações em entidades de dados.) Você pode executar esse guia na empresa de dados de demonstração USMF na qual estão disponíveis todos os pré-requisitos, como nome do diário, configuração do item, perfis de lançamento e contas. Esse guia sugere valores específicos para o item e as dimensões que são usados. Se selecionar um item diferente, você talvez precise inserir valores para diferentes dimensões.

1. Vá para Gerenciamento de estoque > Entradas de diário > Itens > Movimento.
2. Clique em Novo.
3. No campo Nome, clique no botão suspenso para abrir a pesquisa.
4. Selecione IMov.
    * É uma boa prática usar modelos de nomes de diários diferentes para fins comerciais diferentes.  
5. Na lista, clique no link na linha selecionada.
6. No campo Contrapartida, especifique os valores '140200'.
    * Essa contrapartida será a conta padrão nas linhas do diário. É possível substituir o padrão para atribuir contrapartidas diferentes por linha.  
7. Clique em OK.
8. Clique em Novo.
9. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
10. Selecione o item A0001.
11. Na lista, clique no link na linha selecionada.
12. Clique na guia Dimensões de estoque.
13. No campo Local, clique no botão suspenso para abrir a pesquisa.
14. Selecione site 1.
15. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
16. Selecione depósito 13.
17. Na lista, clique no link na linha selecionada.
18. No campo Localização, clique no botão suspenso para abrir a pesquisa.
19. Selecione localização 13.
20. No campo Quantidade, insira um número.
21. Clique em Salvar.
22. Clique em Lançar.
23. Marque ou desmarque a caixa de seleção Transferir todos os erros de lançamento para um novo diário.
    * Se essa opção for habilitada, qualquer linha que não puder ser lançada será copiada em um novo diário. Você pode usar as informações no log para corrigir os problemas e relançar as linhas.  
24. Clique em OK.
25. Feche a página.
26. Feche a página.

