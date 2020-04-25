---
title: Criar um produto lançado para uma única empresa
description: Este procedimento demonstra como criar um único produto lançado no contexto de uma unidade legal única.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 371157aee389694d349ec4fe51af0d9bfbf08cb7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213234"
---
# <a name="create-a-released-product-for-a-single-company"></a>Criar um produto lançado para uma única empresa

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como criar um único produto lançado no contexto de uma unidade legal única. Depois que o produto lançado é criado, ele está imediatamente disponível somente nessa unidade. Você pode explorar esse procedimento na empresa de dados demonstrativos USMF. Esta tarefa é executada geralmente por um designer de produto.


## <a name="create-a-released-product"></a>Crie um produto lançado
1. Vá para Produtos liberados.
2. Clique em Novo.
3. No campo Número do produto, digite um valor.
    * Se um número de produto não é inserido automaticamente no campo Número do produto, digite um número de produto exclusivo. Essa etapa só é necessária se nenhuma sequência numérica foi definida para números de produto.  
4. No campo Nome do produto, digite um valor.
    * O padrão do Nome do produto é o nome de pesquisa. Se necessário, você pode selecionar para alterar o nome de pesquisa.  
5. No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.
    * Os grupos de modelos de item contêm configurações que determinam como os itens são controlados e manuseados em recebimentos e saídas. As configurações também determinam como o consumo de itens é calculado.  
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.
    * Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos com base nas características do item. Por exemplo, para gerenciar como as informações são postadas nas contas principais, você pode criar uma série de grupos de itens diferentes associados a contas principais específicas. Isso permite que você acompanhe o valor de estoque de itens em estágios diferentes.  
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.
    * As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque. Por exemplo, uma dimensão de armazenamento pode ser Local e Depósito.  
12. Na lista, localize e selecione o PDV desejado.
13. Na lista, clique no link na linha selecionada.
14. No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.
    * O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto. Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.  
15. Na lista, localize e selecione o PDV desejado.
16. Na lista, clique no link na linha selecionada.
17. No campo Unidade de estoque, clique no botão suspenso para abrir a pesquisa.
    * A unidade de estoque determina como o produto é quantificado quando é armazenado no estoque.  
18. Na lista, localize e selecione o PDV desejado.
19. Na lista, clique no link na linha selecionada.
20. No campo Unidade de compra, clique no botão suspenso para abrir a pesquisa.
    * A unidade de compra determina como o produto é quantificado quando é comprado de um fornecedor.  
21. Na lista, localize e selecione o PDV desejado.
22. Na lista, clique no link na linha selecionada.
23. No campo Unidade de vendas, clique no botão suspenso para abrir a pesquisa.
    * A unidade de vendas determina como o produto é quantificado quando é vendido a um cliente.  
24. Na lista, localize e selecione o PDV desejado.
25. Na lista, clique no link na linha selecionada.
26. No campo Unidade BOM, clique no botão suspenso para abrir a pesquisa.
    * A unidade BOM determina como o produto é quantificado quando é incluso numa Lista de Materiais (BOM).  
27. Na lista, localize e selecione o PDV desejado.
28. Na lista, clique no link na linha selecionada.
29. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
    * O grupo de impostos sobre vendas do item no grupo de tributação de vendas determina como o imposto sobre as vendas é calculado para cada item.  
30. Na lista, localize e selecione o PDV desejado.
31. Na lista, clique no link na linha selecionada.
32. No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.
    * O grupo de impostos sobre vendas do item no grupo de tributação de compras determina como o imposto sobre as compras é calculado para cada item.  
33. Na lista, localize e selecione o PDV desejado.
34. Na lista, clique no link na linha selecionada.
35. Clique em OK.

## <a name="add-product-characteristics"></a>Adicione características do produto.
1. Expandir ou recolher a seção Gerenciar estoque.
2. No campo Peso líquido, insira um número.
3. No campo Tara, insira um número.
4. No campo Profundidade bruta, insira um número.
5. No campo Largura bruta, insira um número.
6. No campo Altura bruta, insira um número.
7. No campo Volume, insira um número.

## <a name="add-financial-dimensions"></a>Adicione dimensões financeiras
1. Expanda ou recolha a seção Dimensões financeiras.
2. No campo Unidade de Negócios, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo Centro de Custo, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Departamento, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o registro desejado.
10. Na lista, clique no link na linha selecionada.
11. No campo Grupo de Item, clique no botão suspenso para abrir a pesquisa.
12. Na lista, localize e selecione o registro desejado.
13. Na lista, clique no link na linha selecionada.

