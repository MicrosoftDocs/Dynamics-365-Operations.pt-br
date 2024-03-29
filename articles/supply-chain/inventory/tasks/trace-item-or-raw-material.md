---
title: Rastrear um item ou uma matéria-prima
description: Este procedimento demonstra como usar o rastreamento de itens para identificar onde itens ou matérias-primas foram usados ou estão sendo usados.
author: yufeihuang
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c01cabf32542798f70720ab0db7d055fc54cf345
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575815"
---
# <a name="trace-an-item-or-raw-material"></a>Rastrear um item ou uma matéria-prima

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como usar o rastreamento de itens para identificar onde itens ou matérias-primas foram usados ou estão sendo usados. Com esse procedimento, você pode identificar um item, rastreá-lo até sua origem e encaminhá-lo por meio da produção e venda do produto finalizado. O processo pode ser usado para investigar os clientes impactados, as ordens de venda afetadas etc. Este procedimento usa a empresa de dados de demonstração USP2.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Rastrear um item regressivamente usando um número de lote conhecido
1. No **Painel de navegação**, acesse **Módulos > Gerenciamento de estoque > Consultas e relatórios > Dimensões de rastreamento > Rastreamento de item**.
2. No campo **Número do item**, selecione 'P9100'.
3. Na lista, clique no link na linha selecionada.
4. No campo **Avançar ou recuar**, selecione 'Recuar'.
5. No campo **Número do lote**, selecione 'as-12-344-01'.
6. Na lista, clique no link na linha selecionada.
7. Clique em **OK**.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identificar um item, rastreá-lo progressivamente e fazer uma análise

O nó superior da árvore representa a quantidade disponível do item e lote selecionados. Você precisa expandir os nós da árvore para localizar o item onde o rastreamento deve ser executado.   
1. Na árvore, expanda "os nós descrito abaixo e selecione o último nó".
    
    Expanda: 'P9100 / 1 / 10 / como-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Separado ● Ordem de venda 000072 ● 12/22/2015 ● -1 keg ● -4.00 gal ● Local=1, Depósito=10, Número do lote=as-12-344-01  \P9100 ● Produção B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Local=1,Depósito=10, Número de lote=as-12-344-01 ● Coprodutos: P9101' e então selecione esse nó.     
2. Na árvore, expanda "o nó descrito abaixo e selecione aquele nó".
    
    A partir do nó que você acabou de selecionar, expanda "M9103 ● Linha de produção B-000050 ● 12/9/2015 ● -160,00 libras ● Tamanho=70, Cor=OK, Local=1, Depósito=10, Número de lote=App01" e então selecione o nó.  
3. Clique em **Rastreamento a partir do nó**.
4. Clique em **Encaminhar**.
5. No **Painel de Ação**, clique em **Rastreamento**.
    
    Há várias opções de rastreamento que fornecem informações sobre os clientes afetados por item que está sendo rastreado, e para ordens de venda relacionadas ao item que foram e não foram enviadas.   
6. Clique em **Clientes**.
7. Feche a página.
8. No **Painel de Ação**, clique em **Rastreamento**.
9. Clique em **Ordens de venda remetidas**.
10. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]