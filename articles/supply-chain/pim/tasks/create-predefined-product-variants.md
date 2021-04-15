---
title: Criar grades de produtos predefinidas
description: Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8340d295ffd072c95d9b174507ef4203131c8165
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809341"
---
# <a name="create-predefined-product-variants"></a>Criar grades de produtos predefinidas

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]