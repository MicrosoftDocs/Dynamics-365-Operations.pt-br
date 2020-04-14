---
title: Criar uma ordem de venda para um produto configurável
description: Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cafd6e01800b55f316179c481aaa110b2cbcbc80
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150024"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Criar uma ordem de venda para um produto configurável

[!include [banner](../../includes/banner.md)]

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

