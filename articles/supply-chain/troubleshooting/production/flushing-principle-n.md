---
title: Configurações do princípio de liberação em linhas de BOM não são respeitadas
description: Configurações do princípio de liberação em linhas de lista de materiais (BOM) não são respeitadas.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026271"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Configurações do princípio de liberação em linhas de BOM não são respeitadas

Número da base de dados de conhecimento: 4612725

## <a name="symptoms"></a>Sintomas

Este problema ocorre quando o campo **Consumo automático da BOM** na guia **Atualização automática** da página **Parâmetros de controle de produção** estiver definido como *Princípio de liberação*. Esta configuração indica que todas as linhas de BOM (lista de materiais) devem ser consumidas automaticamente quando um pedido de compra é recebido. Se o campo **Princípio de liberação** nas linhas da BOM estiver definido explicitamente como *Manual*, você pode esperar que as linhas da BOM não sejam consumidas automaticamente. No entanto, quando esse problema ocorre, as linhas da BOM em que o campo **Princípio de liberação** estiver definido explicitamente como *Manual*, as linhas da BOM são consumidas automaticamente mesmo assim.

## <a name="resolution"></a>Resolução

Se esse problema ocorrer, seus parâmetros de controle de produção podem estar configurados para substituir a configuração **Princípio de liberação** nas linhas da BOM. Na página **Parâmetros de controle de produção**, na guia **Atualização automática**, verifique o valor do campo **Consumo automático da BOM**. Se ele estiver definido como *Sempre*, o sistema ignorará a configuração **Princípio de liberação** em todas as linhas da BOM e sempre liberará as linhas. Para fazer o sistema respeitar a configuração **Princípio de liberação** nas linhas da BOM, mude o valor do campo **Consumo automático da BOM** para *Princípio de liberação*.
