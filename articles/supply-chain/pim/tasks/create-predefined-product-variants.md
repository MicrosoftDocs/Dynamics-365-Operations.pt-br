--- 
title: Criar grades de produtos predefinidas
description: "Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c49d25004b19084276404cf887188e89200afa32
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-predefined-product-variants"></a>Criar grades de produtos predefinidas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto. A empresa de demonstração usada para criar este procedimento é USMF.


## <a name="create-a-product-master"></a>Criar um produto mestre
1. Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos mestres.
2. Clique em Novo.
3. No campo Número do produto, digite um valor.
    * Inserir um número de produto manualmente é apenas obrigatório se nenhuma sequência numérica foi configurada para o campo número do produto. Ou seja, ignore essa etapa se a sequência numérica foi definida para o campo.  
4. No campo Nome do produto, digite um valor.
5. No campo Grupo de dimensões de produto, insira ou selecione um valor.
    * Selecione o grupo de dimensões do produto SizeCol (Tamanho e cor).  
6. Clique em OK.

## <a name="add-product-dimensions"></a>Adicionar dimensões do produto
1. Clique em Dimensões de produto.
    * Este exemplo a seguir mostra como inserir manualmente as dimensões do produto. Você pode escolher para selecionar um tamanho, cores ou estilos para o grupo que inclui os valores de dimensão de produto que deseja usar.  
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Tamanho, insira ou selecione um valor.
5. No campo Nome, digite um valor.
6. Clique em Novo.
7. Na lista, marque a linha selecionada.
8. No campo Tamanho, insira ou selecione um valor.
9. No campo Nome, digite um valor.
10. Clique na guia Cores.
11. Clique em Novo.
12. Na lista, marque a linha selecionada.
13. No campo Cor, insira ou selecione um valor.
14. No campo Nome, digite um valor.
15. Clique em Novo.
16. Na lista, marque a linha selecionada.
17. No campo Cor, insira ou selecione um valor.
18. No campo Nome, digite um valor.
19. Clique em Salvar.
20. Feche a página.

## <a name="generate-product-variants"></a>Gerar grades de produtos
1. Clique em Grades de produtos.
2. Clique em Sugestões de grade.
3. Clique em Selecionar tudo.
    * Neste exemplo, todas as grades possíveis são selecionadas. Se somente um subconjunto de possíveis combinações de dimensões do produto for usado para criar grades, você pode selecionar as entradas individuais.  
4. Clique em Criar.
    * Você pode gerar descrições de todas as grades com base na combinação de valores de dimensão de produto. As descrições são opcionais.  
5. Clique em Salvar.


