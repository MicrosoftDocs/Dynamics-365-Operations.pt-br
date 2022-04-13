---
title: Criar um plano de materiais para coprodutos
description: O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27bba54db915b7ccc31fda43a00a8c9435493e07
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469523"
---
# <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos

[!include [banner](../../includes/banner.md)]

O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula. A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.

## <a name="create-requirement-for-a-co-product"></a>Criar requisito para um coproduto

1. Acesse **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
1. Selecione **Novo**.
1. Selecione **Ordem de venda**.
1. No campo **Conta de cliente**, digite um valor.
    * Exemplo: US-001  
1. Selecione **OK**.
1. No campo **Número de item**, digite um valor.
    * Exemplo: P6003  
1. No campo **Quantidade.**, insira um número
    * Exemplo: 50000  
1. Selecione **Salvar**.

## <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos

1. Feche a página.
1. Feche a página.
1. Selecione **Planejamento mestre**.
1. No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.
1. Na lista, selecione o link na linha selecionada.
    * Exemplo: Plano Mestre  
1. Selecione **Executar**.
1. Expanda ou recolha a seção **Registros a serem incluídos**.
1. Selecione **Filtro**.
1. Na lista, selecione a linha para **Campo** = *Número do item*.
1. No campo **Critérios**, digite um valor.
    * Exemplo: P6003  
1. Selecione **OK**.
1. Selecione **OK**.
1. Selecione **Ordens planejadas**.
1. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo **Número do item** com um valor de 'P6000'.
    * Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.  
1. Na lista, marque a linha selecionada.
    * Selecione uma das linhas retornadas pelo filtro.  
1. Na lista, selecione o link na linha selecionada.
1. Expanda a seção **Vinculação**.
1. Na lista, selecione o link na linha selecionada.
    * A ordem planejada está vinculada a ordem de venda para o coproduto.  
1. Feche a página.

## <a name="create-a-second-requirement-for-a-co-product"></a>Crie um segundo requisito para um coproduto

1. Acesse **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
1. Selecione **Novo**.
1. Selecione **Ordem de venda**.
1. No campo **Conta de cliente**, digite um valor.
    * Exemplo: US-001  
1. Selecione **OK**.
1. No campo **Número de item**, digite um valor.
    * Exemplo: P6003  
1. No campo **Quantidade.**, insira um número
    * Exemplo: 50000  
1. Selecione **Salvar**.

## <a name="create-a-second-material-plan-for-co-products"></a>Crie um segundo plano de materiais para coprodutos

1. No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.
2. Na lista, selecione o link na linha selecionada.
    * Exemplo: Plano Mestre  
3. Selecione **Executar**.
4. Expanda ou recolha a seção **Registros a serem incluídos**.
5. Selecione **Filtro**.
6. Na lista, selecione a linha para **Campo** = *Número do item*.
7. No campo *Critérios*, digite um valor.
    * Exemplo: P6003  
8. Selecione **OK**.
9. Selecione **OK**.
10. Selecione **Ordens planejadas**.
11. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo **Número do item** com um valor de 'P6000'.
    * Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.  
12. Na lista, marque a linha selecionada.
    * Selecione uma das linhas retornadas pelo filtro.  
13. Na lista, selecione o link na linha selecionada.
14. Expanda ou recolha a seção **Vinculação**.
15. Na lista, selecione o link na linha selecionada.
    * A ordem planejada está vinculada a ordem de venda para o coproduto.  
16. Feche a página.
17. Selecione **Planejamento mestre**.
18. Acesse **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**.
19. Selecione *Não* no campo **Desabilitar todos os processos de planejamento**.
20. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]