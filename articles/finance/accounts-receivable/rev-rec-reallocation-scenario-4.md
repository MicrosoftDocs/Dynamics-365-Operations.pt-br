---
title: Realocação de reconhecimento de receita – cenário 4
description: Este artigo abrange um cenário de realocação em que uma linha é removida de uma ordem de venda existente faturada parcialmente. Este cenário gera o mesmo resultado, independentemente da linha ter sido removida da ordem de venda ou definida como status cancelado.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 06e6322ff55259b5c59d570b73199591ab46c767
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891656"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Realocação de reconhecimento de receita – cenário 4

[!include [banner](../includes/banner.md)]

Este artigo abrange um cenário de realocação em que uma linha é removida de uma ordem de venda existente faturada parcialmente. Este cenário gera o mesmo resultado, independentemente da linha ter sido removida da ordem de venda ou definida como status cancelado.

Para este cenário, a opção **Lançar correções de fatura em Contas a receber** é definida como **Não** na guia **Reconhecimento de receita** da página **Parâmetros da contabilidade** (**Reconhecimento de receita \> Configurar \> Parâmetros da contabilidade**).

[![Lançar correções de fatura na opção de Contas a receber definida como Não.](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Uma ordem de venda é criada para o cliente US\_SI\_0003. O cliente está comprando um laptop (número de item S0012), serviços de instalação (número de item S0001) e um plano de suporte para o laptop (número de item S0008, "Serviço de Engenharia Sustentado"). A receita do laptop e dos serviços de instalação é reconhecida imediatamente. A receita do plano de suporte será adiada e reconhecida durante 12 meses, conforme definido pelo intervalo de datas no contrato.

[![Linhas de ordem de venda para o laptop, serviços de instalação e o plano de suporte.](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

A ordem de venda está confirmada. Como os três itens estão configurados para alocação de preço de receita, o preço da receita é calculado quando a ordem de venda é confirmada. É possível exibir a receita que será reconhecida na página **Alocação de preço da receita** (na página **Ordem de venda**, no Painel de Ações, na guia **Gerenciar**, no grupo **Reconhecimento de receita**, selecione **Alocação de preço da receita**). A receita do laptop será lançada na Conta de receita no valor de $995,84. A receita dos serviços de instalação também será lançada na Conta de receita no valor de US$ 314,47. A receita do plano de suporte será lançada na Conta de receita adiada no valor de US$ 188,69. A soma dos preços da receita deve ser igual à soma das linhas configuradas para capturar a alocação de preço da receita (US$ 1.499,00).

[![Página Alocação de preço da receita.](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

A fatura é emitida ao cliente pelo laptop e pelo plano de suporte, mas não pelos serviços de instalação. A ilustração a seguir mostra a entrada contábil lançada para a fatura.

[![Entrada contábil da ordem de venda faturada.](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

A entrada contábil lança US$ 1.276,94 em Contas a receber. No entanto, como essa fatura é parcial, a receita ou receita adiada mais o imposto não será igual ao valor de Contas a receber. A diferença de -US$ 14,47 é lançada na Conta de compensação da receita da fatura parcial.

A agenda de reconhecimento de receita também é criada.

[![Página Agenda de reconhecimento de receita da fatura parcial.](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

Subsequentemente, o cliente decide não comprar os serviços de instalação. Portanto, essa linha será removida da ordem de venda. Observe que a ordem de venda não pode ser confirmada novamente, pois somente as linhas faturadas permanecem nela.

[![Ordem de venda após a linha de serviços de instalação ter sido removida.](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Embora a ordem de venda não possa ser confirmada, ela pode ser realocada. Na ordem de venda, selecione **Realocar preço com novas linhas da ordem** para abrir a página **Realocar preço com novas linhas da ordem**. Selecione as duas linhas restantes da ordem de venda e selecione **Atualizar realocação**. A coluna **Valor realocado** mostra o novo preço da receita de cada linha restante da ordem de venda.

[![Novos preços de receita na página Realocar o preço com novas linhas da ordem.](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Em seguida, selecione **Comprovante esperado** para exibir as entradas contábeis.

[![Entradas contábeis na página Comprovante esperado.](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

Na página **Comprovante esperado**, as últimas cinco linhas estornam a entrada contábil original na fatura lançada. As quatro primeiras linhas são as novas entradas contábeis lançadas para a fatura. É importante compreender que uma nova fatura não é apresentada ao cliente. Após a realocação, o cliente ainda deve US$ 1.276,94, que é o valor que deve ser lançado em Contas a receber na nova entrada contábil. A nova receita ou receita adiada mais imposto é igual a US$ 1.276,94. Portanto, você não precisa lançar na Conta de compensação da receita da fatura parcial.

Para concluir a realocação, selecione **Processar**. Uma data de lançamento é inserida. Depois que a realocação é concluída, a página **Alocação de preço da receita** mostra a realocação de preço dos dois itens restantes.

[![Realocação de preço dos itens restantes na página Alocação de preço da receita.](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

A agenda de reconhecimento da receita também foi atualizada, com base no novo preço de realocação da receita. Na ordem de venda, abra a página **Agenda de reconhecimento da receita**. Anteriormente, havia 13 linhas para o item S0008 (uma agenda de 12 meses foi atribuída a esse item). Agora há 39 linhas, as 13 linhas da agenda original, 13 linhas de estorno da agenda e 13 linhas baseadas no novo preço da receita.

[![Página Agenda de reconhecimento de receita atualizada com 39 linhas para o item S0008.](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Ao selecionar **Comprovante**, o diário de faturas mostra a entrada contábil original. Para exibir a entrada de estorno e a nova entrada contábil da ordem de venda, selecione **Ajustes da receita** no Painel de Ações e selecione **Comprovante**.

Em seguida, abra a página **Todos s clientes** (**Contas a receber \> Clientes \> Todos os clientes**), selecione o cliente **US\_SI\_0003** e depois **Transações**. A página **Transações do cliente** mostra somente a fatura original (000008), junto com a entrada contábil original. Como a opção **Lançar correções da fatura em Contas a receber** está definida como **Não** na página **Parâmetros da contabilidade**, somente a Contabilidade será atualizada. Portanto, as entradas de estorno e contábeis atualizadas não são mostradas. Observe que as transações de ajuste de receita criadas no [cenário 3](rev-rec-reallocation-scenario-3.md) são mostradas.

[![Entrada contábil original na página Transações do cliente.](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
