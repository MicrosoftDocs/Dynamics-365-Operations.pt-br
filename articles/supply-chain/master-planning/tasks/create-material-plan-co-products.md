---
title: Criar um plano de materiais para coprodutos
description: O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5915dca3af0650883ef5c90dbc50332af5be6cbd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209665"
---
# <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos

[!include [banner](../../includes/banner.md)]

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
1. Feche a página.
2. Feche a página.
3. Clique em Planejamento mestre.
4. No campo Plano, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
    * Exemplo: Plano Mestre  
6. Clique em Executar.
7. Expanda ou recolha a seção de Registros a serem incluídos.
8. Clique em Filtro.
9. Na lista, selecione a linha para Campo = Número do item.
10. No campo Critérios, digite um valor.
    * Exemplo: P6003  
11. Clique em OK.
12. Clique em OK.
13. Clique em Ordens planejadas.
14. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Número do item com um valor de 'P6000'.
    * Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.  
15. Na lista, marque a linha selecionada.
    * Selecione uma das linhas retornadas pelo filtro.  
16. Na lista, clique no link na linha selecionada.
17. Expandir ou recolher a seção Vinculação.
18. Na lista, clique no link na linha selecionada.
    * A ordem planejada está vinculada a ordem de venda para o coproduto.  
19. Feche a página.

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
1. No campo Plano, clique no botão suspenso para abrir a pesquisa.
2. Na lista, clique no link na linha selecionada.
    * Exemplo: Plano Mestre  
3. Clique em Executar.
4. Expanda ou recolha a seção de Registros a serem incluídos.
5. Clique em Filtro.
6. Na lista, selecione a linha para Campo = Número do item.
7. No campo Critérios, digite um valor.
    * Exemplo: P6003  
8. Clique em OK.
9. Clique em OK.
10. Clique em Ordens planejadas.
11. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Número do item com um valor de 'P6000'.
    * Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.  
12. Na lista, marque a linha selecionada.
    * Selecione uma das linhas retornadas pelo filtro.  
13. Na lista, clique no link na linha selecionada.
14. Expandir ou recolher a seção Vinculação.
15. Na lista, clique no link na linha selecionada.
    * A ordem planejada está vinculada a ordem de venda para o coproduto.  
16. Feche a página.
17. Clique em Planejamento mestre.
18. Vá para Planejamento mestre > Configurar > Parâmetros de planejamento mestre.
19. Selecione Não no campo Desabilitar todos os processos de planejamento.
20. Feche a página.

