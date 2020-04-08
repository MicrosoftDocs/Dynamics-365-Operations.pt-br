---
title: Diretivas de instalação do trabalho de depósito (solicitação de emprego, maio de 2016)
description: Os processos de depósito nem sempre incluem o trabalho do depósito.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca54cceb83425c43b5d124cd6d11be0cdef4d63a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145907"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>Diretivas de instalação do trabalho de depósito (solicitação de emprego, maio de 2016)

[!include [banner](../../includes/banner.md)]

Os processos de depósito nem sempre incluem o trabalho do depósito. Ao definir uma diretiva de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o separar as mercadorias concluídas para um conjunto de produtos em locais específicos. A empresa de dados demo USMF foi usada para criar este registro. Essa guia da tarefa requer o aplicativo do Dynamics AX 7.0.1 ou posterior.

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

