--- 
title: "Criar uma ordem de venda para um produto configurável"
description: "Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda."
author: YuyuScheller
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 646606237f593d24792a0ae072948f2e12782283
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Criar uma ordem de venda para um produto configurável

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda. Este exemplo usa o modelo do Palestrante D0006 na empresa de dados demo USMF. Normalmente, um processador de ordens de venda usa este procedimento.


## <a name="create-a-sales-order"></a>Criar uma ordem de venda
1. Clique em Consulta e processamento de ordem de venda.
2. Clique em Novo.
3. Clique Ordem de venda.
4. No campo da conta Cliente, selecione US-001. 
5. Clique em OK.
6. No campo Número do item, selecione D0006.
    * Para essa tarefa, você deve selecionar um produto configurável.  
7. Clique em Produtos e fornecimento.
8. Clique em Configurar linha.
    * Observe que o preço foi alterado, com base na configuração selecionada, e ela inclui o campo de cabo agora definido como Verdadeiro.  
    * Anote o preço padrão e as configurações que estão selecionadas para o período.  
9. Clique em Carregar modelo.
    * Esse exemplo mostra como é possível aplicar um modelo para selecionar uma configuração predefinida. Se você estiver usando este procedimento como um guia de tarefas e deseja consultar outros valores de atributo que estão disponíveis, clique no botão Desbloquear.  
10. Clique em OK.
11. Clique em OK.
12. Expanda a seção Detalhes da linha.
13. Clique na guia de Produto.
    * A configuração do item está listada agora nas dimensões do produto.  
14. Feche a página.

## <a name="select-the-product-configuration"></a>Selecione a configuração do produto


