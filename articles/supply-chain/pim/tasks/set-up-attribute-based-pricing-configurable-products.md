--- 
title: "Configurar definição de preços com base no atributo para os produtos configuráveis"
description: "Este procedimento mostra como configurar preços baseados em atributos."
author: YuyuScheller
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Configurar definição de preços com base no atributo para os produtos configuráveis

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar preços baseados em atributos. Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos. Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF. Normalmente, um gerente de produto usa este procedimento.


## <a name="create-a-new-price-model"></a>Criar um novo modelo de preço
1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, selecione a linha do Palestrante avançado, mas não clique no link do nome.
4. No Painel de Ação, clique em Modelo.
5. Clique em Modelos de preço.
6. Clique em Novo.
7. No campo Nome do modelo de preço, digite um valor.
    * Use um nome que torne o modelo de fácil identificação.  
8. No campo Descrição, digite um valor.
9. Clique em Salvar.

## <a name="add-price-elements"></a>Adicionar Elementos de preço
1. Clique em Editar.
    * Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço. Você também pode adicionar os preços em moedas diferentes.  
2. No campo Expressão de preço base, digite um valor.
    * Por exemplo, digite 100.   Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.  
3. Clique em Adicionar.
4. No campo Nome, digite ‘Rosewood’.
    * O nome de expressão de preço ajuda a identificar qual elemento de preço representa. Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.  
5. Clique em Editar condição.
    * Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.  
6. No campo de ConstraintBody, insira 'CabinetFinish=="Rosewood"'.
7. Clique em OK.
8. No campo Expressão, digite um valor.
    * Por exemplo, digite 50.  
9. Feche a página.
10. Feche a página.


