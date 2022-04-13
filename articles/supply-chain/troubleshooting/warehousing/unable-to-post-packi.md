---
title: Não é possível lançar uma guia de remessa para uma linha de ordem de venda interrompida
description: Você não pode lançar uma guia de remessa para uma linha de ordem de venda interrompida
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462843"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Não é possível lançar uma guia de remessa para uma linha de ordem de venda interrompida

Código de erro: SYS13203

## <a name="symptoms"></a>Sintomas

Ao tentar lançar uma guia de remessa para uma carga, o sistema exibe a seguinte mensagem de erro:

> Não é possível lançar a guia de remessa ao interromper uma linha da ordem de venda após a confirmação de que a quantidade da remessa de saída A não pode ser separada.

## <a name="cause"></a>Causa

Uma ou mais linhas de ordem de venda relacionadas podem ser interrompidas, o que significa que o sistema impedirá o processamento dessa ordem de venda. Entre outras coisas, isso significa que o sistema não lançará uma guia de remessa para a ordem.

Por exemplo, um usuário pode ter decidido interromper uma ou mais linhas da ordem porque o cliente cancelou sua ordem. No entanto, se a remessa de saída tiver sido confirmada, a remessa que contém a ordem de venda já deve ter saído fisicamente do depósito, o que significa que a interrupção das linhas da ordem de venda não terá nenhum efeito. Como não é mais possível interromper fisicamente a remessa, sugerimos que você cancele a interrupção das linhas para que possa lançar a guia de remessa. Em seguida, será necessário tratar a ordem cancelada como uma devolução.

## <a name="resolution"></a>Resolução

Para poder lançar a guia de remessa, verifique se nenhuma das linhas da ordem de venda relevantes foi interrompida seguindo as etapas abaixo.

1. Acesse **Todas as ordens de venda \> Vendas e marketing \> Todas as ordens de venda**.
1. Localize e abra a ordem de venda com problemas.
1. Na Guia Rápida **Linhas de ordem de venda**, selecione uma linha da ordem de venda.
1. Na FastTab **Detalhes da linha**, abra a guia **Geral** e verifique se o campo **Interrompido** está definido como *Não*.
1. Continue trabalhando até que todas as linhas de venda relevantes não sejam mais interrompidas.
1. Tente lançar novamente a guia de remessa para a ordem de venda ou carga.
