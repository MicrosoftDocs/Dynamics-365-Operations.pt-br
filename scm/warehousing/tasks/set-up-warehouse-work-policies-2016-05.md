--- 
title: "Configurar políticas de trabalho de depósito "
description: "Os processos de depósito nem sempre incluem o trabalho do depósito."
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 5db1c99833276a92467ed57b7be51b0ebaa74d83
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-warehouse-work-policies"></a>Configurar políticas de trabalho de depósito  

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os processos de depósito nem sempre incluem o trabalho do depósito. Ao definir uma diretiva de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o separar as mercadorias concluídas para um conjunto de produtos em locais específicos. A empresa de dados demo USMF foi usada para criar este registro. Essa guia da tarefa requer a aplicação 7.0.1 do Dynamics AX ou posterior.

1. Vá para Gerenciamento de depósito > Configuração > Políticas de trabalho.
2. Clique em Novo.
3. No campo Nome de política de trabalho, digite "Sem trabalhos ausentes".
4. Clique em Salvar.
5. Clique em Adicionar.
6. Na lista, marque a linha selecionada.
7. No campo Tipo de ordem de trabalho, selecione as mercadorias “Concluiu mercadorias dadas”.
8. Clique em Adicionar.
9. Na lista, marque a linha selecionada.
10. No campo Tipo de ordem de trabalho, selecione "Coproduto e subproduto cedido".
11. Expanda a seção Localizações de estoque.
12. Clique em Adicionar.
13. Na lista, marque a linha selecionada.
14. Na lista Depósito, insira "51".
15. No campo Local, insira ou selecione "001".
16. Expanda a seção Produtos.
17. No campo Seleção do produto, selecione "Selecionado".
18. Clique em Adicionar.
19. Na lista, marque a linha selecionada.
20. No campo Número do item, insira ou selecione "L0101".
21. Clique em Salvar.


