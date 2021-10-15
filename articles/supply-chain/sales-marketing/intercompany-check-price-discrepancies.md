---
title: Verificar as discrepâncias de preço da ordem intercompanhia
description: Este tópico explica como verificar as discrepâncias de preço da ordem intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f9a0ba4980f8acf56d84dc865094b405b7402ad5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548093"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Verificar as discrepâncias de preço da ordem intercompanhia

[!include [banner](../../includes/banner.md)]

Você pode usar este procedimento para verificar se há discrepâncias de preço em ordens intercompanhia.

1. Acesse **Compras e fornecimento \> Periódico \> Limpeza \> Verificar discrepâncias no preço da ordem intercompanhia**.
1. Configure um trabalho em lotes, se necessário, e selecione **OK** para verificar os preços e descontos de ordens de venda e ordens de compra intercompanhia. Caso contrário, selecione **Cancelar** para fechar a página sem executar a verificação.

    > [!TIP]
    > Caso haja problemas de sincronização ou com os preços, eles serão listados em uma mensagem informativa que será exibida. Você pode imprimir a mensagem informativa para referência.

1. Na mensagem informativa, selecione a linha relevante para abrir a ordem na entidade legal atual. Abra a ordem na entidade legal relacionada ao selecionar **Intercompanhia** e, em seguida, **Ordem de compra intercompanhia** ou **Ordem de venda intercompanhia**.

    > [!NOTE]
    > Para permitir uma atualização da ordem intercompanhia:
    >
    > 1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
    > 1. No Painel de Ações, selecione a guia **Geral** e, em seguida, selecione **Intercompanhia**.
    > 1. Na página **Intercompanhia**, selecione **Políticas de ordem de compra** ou **Políticas de ordem de venda**.
    > 1. Selecione **Permitir edição de preços** e **Permitir edição de descontos** em ambas as áreas.

1. Abra a ordem intercompanhia relevante onde você deseja manter o preço.
1. Para cada linha da ordem, altere o campo **Preço unitário** da linha e mude novamente para o valor original. Altere o campo **Desconto** para a linha para a frente e para trás, e altere os campos **Encargos em compras** ou **Encargos em vendas** relevantes para a frente e para trás. Mudar os valores dessa forma desencadeia uma sincronização de preços, descontos e encargos dessa linha de ordem intercompanhia para a linha de ordem intercompanhia a que ela faz referência para que elas sejam alinhadas automaticamente.

    > [!NOTE]
    > Essa sincronização só será válida se a ordem de venda intercompanhia não tiver sido faturada. Caso a ordem de venda intercompanhia tenha sido lançada na fatura e um diário de faturas de cliente tiver sido criado, as mudanças deverão ser executadas diretamente nas linhas de ordem de compra intercompanhia pela definição dos preços, descontos e encargos iguais ao do diário de faturas de cliente intercompanhia. Se isso não for feito, a ordem de compra intercompanhia não poderá ser lançada na fatura porque haverá uma diferença no total da ordem.

1. Repita o procedimento até que todas as ordens de compra e venda sejam sincronizadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
