---
title: Criar um plano de materiais para coprodutos
description: O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920720"
---
# <a name="create-a-material-plan-for-co-products"></a>Criar um plano de materiais para coprodutos

[!include [banner](../../includes/banner.md)]

O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula. A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.

## <a name="create-requirement-for-a-co-product"></a>Criar requisito para um coproduto

1. Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
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

1. Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
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
18. Vá para **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**.
19. Selecione *Não* no campo **Desabilitar todos os processos de planejamento**.
20. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]