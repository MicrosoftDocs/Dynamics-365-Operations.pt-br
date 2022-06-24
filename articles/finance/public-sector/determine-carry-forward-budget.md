---
title: Atualizar o orçamento postergado após reduções em ordens de compra e faturas
description: Este artigo descreve como controlar o que acontece com o orçamento postergado quando as ordens de compra são canceladas ou reduzidas, e quando as faturas são reduzidas.
author: TaylorVH
ms.date: 02/11/2022
ms.topic: article
ms.search.form: LedgerFund
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2022-02-01
ms.openlocfilehash: 7f0ef0ffdf697609e811f754b4378b1f7a81c494
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897948"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Atualizar o orçamento postergado após reduções em ordens de compra e faturas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo descreve como controlar o que acontece com o orçamento postergado quando as ordens de compra são canceladas ou reduzidas, e quando as faturas são reduzidas.

Para obter informações sobre o processamento do exercício de ordens de compra, consulte [Processamento do exercício de ordens de compra](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Ativar ou desativar reduções de orçamento postergadas para variações de fatura

O sistema sempre pode atualizar o orçamento postergado quando uma ordem de compra é cancelada ou reduzida. No entanto, se você desejar atualizar o orçamento postergado quando uma fatura for reduzida, você ative o recurso *Reduzir orçamento postergado quando uma fatura em uma ordem de compra for reduzida com uma variação*. Os administradores podem ativar este recurso procurando-o no espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Cancelamentos e reduções de ordens de compra

Independentemente de o recurso *Reduzir orçamento postergado quando uma fatura em uma ordem de compra for reduzida com uma variação* ser ativado, o orçamento postergado será atualizado quando uma ordem de compra qualificada for cancelada ou reduzida. Você pode definir cada fundo de contabilidade para responder de uma das seguintes maneiras:

- Preservar o orçamento postergado como ele foi criado.
- Ajuste automaticamente o orçamento postergado para remover o valor cancelado ou reduzido.

Somente linhas de ordem de compra com distribuições que incluem um fundo estão disponíveis para o ajuste de orçamento automático. O ajuste de orçamento automático ocorre quando a ordem de compra é finalizada ou uma redução de ordem de compra é confirmada.

## <a name="invoice-reductions"></a>Reduções de fatura

Quando o recurso *Reduzir orçamento postergado quando uma fatura em uma ordem de compra for reduzida com uma variação* for ativado, você poderá especificar se cada fundo deve reduzir o orçamento postergado quando uma fatura é reduzida, além de quando uma ordem de compra é reduzida ou cancelada. A fatura deve ser para uma ordem de compra com orçamento postergado. As reduções incluem variações de preço, variações de encargo e variações de imposto. Quando uma ordem de compra postergada é reduzida durante o faturamento, uma variação é criada. Quando a fatura for lançada, o ônus da ordem de compra será reduzido pelo valor da variação. O recurso também criará o ajuste de orçamento automático para o valor da variação.

Quando o recurso *Reduzir orçamento postergado quando uma fatura em uma ordem de compra for reduzida com uma variação* estiver desativado, o orçamento postergado não será reduzido neste cenário. Portanto, o orçamento postergado restante para o valor da variação é deixado de lado.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Configurar as opções de orçamento postergado para cada fundo

Siga estas etapas para cada fundo de contabilidade que deve ser capaz de reduzir o orçamento postergado quando uma ordem de compra ou fatura é reduzida.

1. Vá para **Contabilidade \> Plano de contas \> Fundos \> Fundos**.
1. Selecione o fundo a ser configurado.
1. Em **Processamento do exercício da ordem de compra**, verifique se a opção **Substituir opção de exercício selecionada** está definida como *Sim*.
1. Em **Status de orçamento postergado**, defina o campo **Reaplicar o orçamento quando um ordem de compra postergada for cancelada ou reduzida** conforme necessário. As configurações têm efeitos um pouco diferentes, dependendo se o recurso *Reduzir orçamento postergado quando uma fatura em uma ordem de compra for reduzida com uma variação* está ativado no sistema.

    - Quando o recurso está desativado, o sistema reage somente a ordens de compra canceladas ou reduzidas. As configurações de opção funcionam da seguinte maneira:

        - *Não* – o sistema cria uma entrada de registro de orçamento para o saldo restante de ordens de compra que foram canceladas ou reduzidas.
        - *Sim* – o sistema permite que as ordens de compra sejam canceladas ou reduzidas, mas não cria uma entrada de registro de orçamento. O orçamento postergado permanece disponível para consumo por outros documentos.

    - Quando o recurso está ativado, o sistema reage a variações de fatura e a ordens de compra canceladas ou reduzidas. As configurações de opção funcionam da seguinte maneira:

        - *Não* – para variações de fatura, o sistema cria uma entrada de registro de orçamento na ordem de compra para o valor de redução da variação. Para ordens de compra canceladas ou reduzidas, essa configuração tem o mesmo efeito que quando o recurso está desativado.
        - *Sim* – para variações de fatura, o sistema permite a redução da fatura, mas não cria uma entrada de registro de orçamento. O orçamento postergado permanece disponível para consumo por outros documentos. Para ordens de compra canceladas ou reduzidas, essa configuração tem o mesmo efeito que quando o recurso está desativado.

## <a name="additional-resources"></a>Recursos adicionais

- [Processamento do exercício de ordens de compra](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Manter reservas de orçamento geral](general-budget-reservation-tasks.md)
- [Fundos no setor público](funds-public-sector.md)
- [Configurar um fundo para o setor público](tasks/set-up-fund-public-sector.md)
