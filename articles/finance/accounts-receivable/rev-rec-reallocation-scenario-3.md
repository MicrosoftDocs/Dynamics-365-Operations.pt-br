---
title: Realocação de reconhecimento de receita – cenário 3
description: Este tópico abrange um cenário de realocação em que uma nova linha é adicionada a uma ordem de venda existente faturada. Quando um novo item é adicionado a um contrato, ele pode ser adicionado a uma nova ordem de venda ou à ordem de venda existente.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4242be761ed170155b70211d99eb5018fb254071
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356164"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Realocação de reconhecimento de receita – cenário 3

[!include [banner](../includes/banner.md)]

Este tópico abrange um cenário de realocação em que uma nova linha é adicionada a uma ordem de venda existente faturada. Quando um novo item é adicionado a um contrato, ele pode ser adicionado a uma nova ordem de venda ou à ordem de venda existente. Este cenário também mostra o que ocorre quando Contas a receber é atualizado por causa da realocação.

Para este cenário, a opção **Lançar correções de fatura em Contas a receber** é definida como **Sim** na guia **Reconhecimento de receita** da página **Parâmetros da contabilidade** (**Reconhecimento de receita \> Configurar \> Parâmetros da contabilidade**).

[![Lançar correções de fatura na opção de Contas a receber definida como Sim.](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Uma ordem de venda é criada para o cliente US\_SI\_0003. O cliente está comprando um laptop (número de item S0012) e um plano de suporte (número de item S0008, "Serviço de Engenharia Sustentado"). A receita do laptop é reconhecida imediatamente. A receita do plano de suporte será adiada e reconhecida durante 12 meses, conforme definido pelo intervalo de datas no contrato.

[![Linhas de ordem de venda para o laptop e o plano de suporte.](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

A ordem de venda está confirmada. Como os dois itens estão configurados para alocação de preço de receita, o preço da receita é calculado quando a ordem de venda é confirmada. É possível exibir a receita que será reconhecida na página **Alocação de preço da receita** (na página **Ordem de venda**, no Painel de Ações, na guia **Gerenciar**, no grupo **Reconhecimento de receita**, selecione **Alocação de preço da receita**). A receita do laptop será lançada na Conta de receita no valor de US$ 1.008,01. A receita do plano de suporte será lançada na Conta de receita adiada no valor de US$ 190,99. A soma dos preços da receita deve ser igual à soma das linhas configuradas para capturar a alocação de preço da receita (US$ 1.199,00).

[![Página Alocação de preço da receita.](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

A ordem de venda está totalmente faturada. A ilustração a seguir mostra a entrada contábil lançada para a fatura.

[![Entrada contábil da ordem de venda totalmente faturada.](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

A agenda de reconhecimento de receita também é criada. Após algum tempo, dois dos meses reconheceram a receita do plano de suporte.

[![Página da agenda de reconhecimento de receita após dois meses.](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

Nesse momento, o cliente decide adicionar os serviços de instalação (número de item S0001). Esse item será adicionado à ordem de venda existente. O cliente é solicitado a confirmar que deseja modificar a ordem de venda totalmente fatura e seleciona **Sim**.

[![Ordem de venda após a linha de serviços de instalação ter sido adicionada.](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Se esse novo item for a única alteração no contrato do cliente, o processo de realocação poderá ser executado agora. Na ordem de venda, selecione **Realocar preço com novas linhas da ordem** para abrir a página **Realocar preço com novas linhas da ordem**. Selecione todas as linhas dessa ordem de venda e depois selecione **Atualizar realocação**. A coluna **Valor realocado** mostra o novo preço da receita de cada linha da ordem de venda.

[![Novos preços de receita na página Realocar o preço com novas linhas da ordem.](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Em seguida, selecione **Comprovante esperado** para exibir as entradas contábeis. Como a opção **Lançar correções da fatura em Contas a receber** está definida como **Sim** na página **Parâmetros de contabilidade**, essas entradas contábeis serão lançadas na Contabilidade por meio do documento de crédito e uma nova fatura será criada em Contas a receber.

[![Entradas contábeis na página Comprovante esperado.](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

Na página **Comprovante esperado**, as últimas quatro linhas estornam a entrada contábil original na fatura lançada. As cinco primeiras linhas são as novas entradas contábeis lançadas para a fatura. É importante compreender que uma nova fatura não é apresentada ao cliente. Após a realocação, o cliente ainda deve US$ 1.276,94, que é o valor que deve ser lançado em Contas a receber na nova entrada contábil. O imposto de compensação e a receita ou a receita adiada é igual a US$ 995,83 + US$ 188,69 + US$ 77,94 = US$ 1.262,46. O valor da receita ou da receita adiada foi alterado por causa da realocação. A diferença de -US$ 14,48 é lançada na Conta de compensação da receita da fatura parcial. Esse saldo será compensado quando a fatura for lançada para o novo item adicionado à ordem de venda.

Para concluir a realocação, selecione **Processar**. Uma data de lançamento é inserida. Depois que a realocação é concluída, a página **Alocação de preço da receita** mostra a realocação de preço dos três itens.

[![Realocação de preço dos três itens na página Alocação de preço da receita.](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

A agenda de reconhecimento da receita também foi atualizada, com base no novo preço de realocação da receita. Na ordem de venda, abra a página **Agenda de reconhecimento da receita**. Anteriormente, havia 13 linhas para o item S0008 (uma agenda de 12 meses foi atribuída a esse item). Agora há 39 linhas, as 13 linhas da agenda original, 13 linhas de estorno da agenda e 13 linhas baseadas no novo preço da receita.

[![Página Agenda de reconhecimento de receita atualizada com 39 linhas para o item S0008.](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Ao selecionar **Comprovante**, o diário de faturas mostra a entrada contábil original. Para exibir a entrada de estorno e a nova entrada contábil da ordem de venda, selecione **Ajustes da receita** no Painel de Ações e selecione **Comprovante**.

Em seguida, abra a página **Todos s clientes** (**Contas a receber \> Clientes \> Todos os clientes**), selecione o cliente **US\_SI\_0003** e depois **Transações**. A página **Transações do cliente** mostra a fatura original (000006), o documento de estorno (000006-1) e a nova fatura (000006-2). A fatura original e o documento de estorno são liquidados entre si e têm um saldo igual a zero (0). Exiba o comprovante de cada documento para ver o impacto na Contabilidade.

[![Fatura original, documento de estorno e nova fatura na página Transações do cliente.](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

A ordem de venda é faturada novamente para o item adicionado. A fatura total apresentada ao cliente é de US$ 300,00 + US$ 19,50 de imposto = US$ 319,50. A ilustração a seguir mostra a entrada contábil lançada.

[![Página de transações de comprovante com a entrada contábil lançada.](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Como a soma da receita e a venda é maior que US$ 319,50, a diferença é lançada para US$ 14,48. Esse valor compensa o saldo da conta de compensação da receita da fatura parcial. Esse saldo é atualizado na nova entrada contábil lançada após a realocação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]