---
title: Ciclo de vida da ordem de lotes da criação ao início
description: Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac0ce1d3267df917a6ba8ed9dd8cc72168c79936d53600776972c2e5f4f16857
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745541"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Ciclo de vida da ordem de lotes da criação ao início

[!include [banner](../../includes/banner.md)]

Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.

A partir da criação, da estimativa de custo e em um agendamento de trabalho de produção até o início real de uma ordem de lote.



A empresa de dados demo usada para criar este procedimento é USMF. 



Os pré-requisitos para executar o procedimento com outro conjunto de dados são um produto liberado com uma fórmula ativa e a versão de roteiro.


## <a name="create-a-batch-order"></a>Criar uma ordem de lotes
1. Acesse Todas as ordens de produção.
2. Clique em Nova ordem de lote.
3. No campo Número do item, insira ou selecione um valor.
4. Clique em Criar.
5. Use o Filtro Rápido para filtrar o campo Produção com o valor 'b'.

## <a name="view-production-formula-and-expected-co-products"></a>Exiba a fórmula de produção e os coprodutos previstos
1. No Painel de Ação, clique em Ordem de produção.
2. Clique em Fórmula.
3. Feche a página.
4. Clique em Co-produtos.
5. Feche a página.

## <a name="estimate-the-batch-order"></a>Estime a ordem de lote
1. Clique em Estimar.
2. Clique em OK.
3. No Painel de Ação, clique em Gerenciar custos.
4. Clique em Exibir detalhes do cálculo.
5. Feche a página.

## <a name="release-the-batch-order"></a>Libere a ordem de lote
1. No Painel de Ação, clique em Ordem de produção.
2. Clique em Liberar.
3. Clique em OK.

## <a name="schedule-production-jobs"></a>Agende os trabalhos de produção
1. No Painel de Ação, clique em Agenda.
2. Clique em Agendar trabalhos.
3. Selecione Não no campo Capacidade finita.
4. Selecione Não no campo Material finito.
5. Clique em OK.
6. No Painel de Ação, clique em Ordem de produção.
7. Clique em Todos os trabalhos.
8. Feche a página.

## <a name="start-the-batch-order"></a>Inicie a ordem de lote
1. Clique em Iniciar.
2. Clique na guia Geral.
3. Selecione Não no campo Lançar lista de separação agora.
4. Clique em OK.
5. No Painel de Ação, clique em Exibir.
6. Clique em Lista de separação.
7. Na lista, clique no link na linha selecionada.
8. Feche a página.
9. Feche a página.
10. Clique em Cartão de roteiro.
11. Na lista, clique no link na linha selecionada.
12. Feche a página.
13. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]