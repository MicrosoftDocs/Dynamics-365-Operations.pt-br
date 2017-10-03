--- 
title: Criar um plano de materiais para coprodutos
description: "O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4eb36b0de53f40f882950628d55d6ac08ac5fdde
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos

[!include[task guide banner](../../includes/task-guide-banner.md)]

O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula. A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.


## <a name="create-requirement-for-a-co-product"></a>Criar requisito para um coproduto
1. Ir para o painel Padrão.
2. Clique em Consulta e processamento de ordem de venda.
3. Clique em Novo.
4. Clique Ordem de venda.
5. No campo Conta de cliente, insira um valor.
    * Exemplo: US-001  
6. Clique em OK.
7. No campo Número de item, digite um valor.
    * Exemplo: P6003  
8. No campo Quantidade, insira um número.
    * Exemplo: 50000  
9. Clique em Salvar.

## <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos
1. Clique em Planejamento mestre.
2. No campo Plano, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
    * Exemplo: Plano Mestre  
4. Clique em Executar.
5. Expanda ou recolha a seção de Registros a serem incluídos.
6. Clique em Filtro.
7. Na lista, selecione a linha para Campo = Número do item.
8. No campo Critérios, digite um valor.
    * Exemplo: P6003  
9. Clique em OK.
10. Clique em OK.
11. Clique em Ordens planejadas.
12. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Número do item com um valor de 'P6000'.
    * Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.  
13. Na lista, marque a linha selecionada.
    * Selecione uma das linhas retornadas pelo filtro.  
14. Na lista, clique no link na linha selecionada.
15. Expandir ou recolher a seção Vinculação.
16. Na lista, clique no link na linha selecionada.
    * A ordem planejada está vinculada a ordem de venda para o coproduto.  
17. Feche a página.


