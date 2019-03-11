---
title: Completar instalação básica de um produto mestre lançado
description: Este procedimento mostra como concluir a configuração mínima necessária antes que o produto mestre possa ser usado em versões de Listas de Materiais.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "354773"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Completar instalação básica de um produto mestre lançado

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como concluir a configuração mínima necessária antes que o produto mestre possa ser usado em versões de Listas de Materiais.

Este é o terceiro procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione o produto mestre que você liberou no segundo procedimento. Esse produto mestre foi criado com a tecnologia de configuração baseada em dimensão.  
3. No Painel de Ação, clique em Produto.
4. Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.
5. No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
    * O grupo dimensões de armazenamento determina quais dimensões de armazenamento são usadas na transação do produto. Selecione Local para esse procedimento.  
7. Na lista, clique no link na linha selecionada.
8. No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
    * O grupo dimensões de rastreamento determina quais dimensões de rastreamento são usadas na transação do produto. Selecione Nenhum para esse procedimento.  
10. Na lista, clique no link na linha selecionada.
11. Clique em OK.
12. Na lista, clique no link na linha selecionada.
13. Clique em Editar.
    * Abra o formulário Detalhes do produto liberado para continuar a tarefa de configuração.  
14. No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.
15. Na lista, localize e selecione o PDV desejado.
    * Os grupos de modelo de item contêm configurações que determinam como os itens são controlados e processados em recebimentos e saídas. Eles também determinam como o consumo de itens é calculado. Selecione PEPS para esse procedimento.  
16. Na lista, clique no link na linha selecionada.
17. Expandir ou recolher a seção Gerenciar custos.
18. No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.
19. Na lista, localize e selecione o PDV desejado.
    * Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos. Selecione CarAudio para esse procedimento.  
20. Na lista, clique no link na linha selecionada.
21. No Painel de Ação, clique em Plano.
22. Clique em Configurações de ordem padrão.
23. No campo Tipo de ordem padrão, selecione uma opção.
    * Selecione Produção para especificar que a opção padrão de fornecimento para esse produto mestre é produzi-lo.  
24. Feche a página.
25. Feche o formulário Detalhes do produto liberado.

