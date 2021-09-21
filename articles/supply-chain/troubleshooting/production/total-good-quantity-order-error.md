---
title: Erro de quantidade total de mercadoria ao tentar encerrar uma ordem
description: Ao tentar finalizar uma ordem de produção e relatar como concluída, você poderá receber um erro de quantidade total de mercadoria. Esta página explica por que e como corrigir o problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475570"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Erro de Quantidade total sem erros ao tentar encerrar uma ordem de produção

## <a name="symptoms"></a>Sintomas

Ao tentar lançar um relatório como diário concluído em uma ordem de produção, você recebe a seguinte mensagem de erro:

> A quantidade total sem erros relatada como concluída da produção será %1. O feedback da última operação é de 0,00 no total.

## <a name="cause"></a>Causa

Esse problema ocorre se as quantidades que foram lançadas nas últimas operações estavam incorretas. Por exemplo, se a produção for iniciada, mas a quantidade que deve ser iniciada não for alocada, o diário de cartão de rota será lançado sem nenhuma linha. Para confirmar a situação, abra a ordem de produção e, no Painel de Ações, na guia **Exibir**, selecione **Cartão de roteiro**.

## <a name="resolution"></a>Resolução

É possível corrigir esse problema lançando diários adicionais para as operações para as quais os diários não foram lançados corretamente. Reinicie a ordem de produção e opte por lançar os diários adicionais. Essa ação não iniciará a ordem de produção, mas publicará os diários. O cartão de roteiro deve mostrar as quantidades que foram lançadas e você deve ser capaz de encerrar as ordens de produção com sucesso.
