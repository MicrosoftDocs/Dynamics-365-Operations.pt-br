--- 
title: "Manter BOM para um modelo de configuração de produtos"
description: "Executar este procedimento exige um modelo de configuração de produto existente."
author: ShylaThompson
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c017d7719ac6af43b0c8a162080bb753587df030
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Manter BOM para um modelo de configuração de produtos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Executar este procedimento exige um modelo de configuração de produto existente. O modelo de alto-falante avançado na empresa de demonstração USMF é usado para criar este procedimento.


## <a name="add-a-bom-line"></a>Adicione uma linha da BOM
1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, localize e selecione o PDV desejado.
    * Selecione o alto-falante avançado para este procedimento.  
4. Na lista, clique no link na linha selecionada.
5. Expandir a seção Linhas de BOM.
6. Clique em Adicionar.
7. No campo Nome, digite um valor.
8. No campo Descrição, digite um valor.
9. Clique em Salvar.

## <a name="add-bom-line-details"></a>Adicione Detalhes da linha de BOM
1. Clique em Detalhes da linha de BOM.
2. No campo Número do item, insira ou selecione um valor.
    * Por exemplo, você pode selecionar o item M0055.  
    * Para cada propriedade da linha da BOM, você pode selecionar se ela tem um valor fixo ou está mapeada a um atributo.  
3. Marque a caixa de seleção Definir.
4. Selecione Sim no campo Cálculo.
    * Definindo a propriedade Cálculo como Sim garante que a linha da BOM seja incluída em cálculos de custo.  
5. Clique na guia Configuração.
6. Marque a caixa de seleção Definir.
7. No campo Quantidade, insira um número.
    * O campo Quantidade determina a quantidade do item que será incluída na BOM. Pode ser um candidato óbvio para um mapeamento de atributos.  
8. Clique na guia Dimensão.
    * Verifique qualquer uma das dimensões do produto estão ativas, e consequentemente deve ter um valor ou um atributo atribuído.  
9. Clique em OK.


