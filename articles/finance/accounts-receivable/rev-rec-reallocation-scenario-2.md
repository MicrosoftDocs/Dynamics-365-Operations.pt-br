---
title: Realocação de reconhecimento de receita – cenário 2
description: Este tópico aborda um cenário de realocação em que duas ordens de venda são inseridas e o cliente adiciona um item ao contrato depois que a primeira ordem de venda foi faturada. Quando um novo item é adicionado a um contrato, ele pode ser adicionado a uma nova ordem de venda ou à ordem de venda existente.
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
ms.openlocfilehash: 1fe195f171e8e343e9ce01b2ca0d4980d193a6fd3d9aa6f95efed66a29aa7d6d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770680"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Realocação de reconhecimento de receita – cenário 2

[!include [banner](../includes/banner.md)]

Este tópico aborda um cenário de realocação em que duas ordens de venda são inseridas e o cliente adiciona um item ao contrato depois que a primeira ordem de venda foi faturada. Quando um novo item é adicionado a um contrato, ele pode ser adicionado a uma nova ordem de venda ou à ordem de venda existente.

Para este cenário, a opção **Lançar correções de fatura em Contas a receber** é definida como **Não** na guia **Reconhecimento de receita** da página **Parâmetros da contabilidade** (**Reconhecimento de receita \> Configurar \> Parâmetros da contabilidade**).

[![Lançar correções de fatura na opção de Contas a receber definida como Não.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Uma ordem de venda é criada para o cliente US\_SI\_0003. O cliente está comprando serviços de instalação (número de item S0001) e um plano de suporte para o laptop (número de item S0008), mas ainda não selecionou o laptop. A receita dos serviços de instalação serão adiadas até a data em que o laptop for comprado. A receita do plano de suporte será adiada e reconhecida durante 12 meses, conforme definido pelo intervalo de datas no contrato.

[![Linhas de ordem de venda para serviços de instalação e o plano de suporte.](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

A ordem de venda está confirmada. Como os dois itens estão configurados para alocação de preço de receita, o preço da receita é calculado quando a ordem de venda é confirmada. É possível exibir a receita que será reconhecida na página **Alocação de preço da receita** (na página **Ordem de venda**, no Painel de Ações, na guia **Gerenciar**, no grupo **Reconhecimento de receita**, selecione **Alocação de preço da receita**). A receita dos serviços de instalação será lançada na Conta de receita adiada no valor de US$ 250,00. A receita do plano de suporte também será lançada na Conta de receita adiada, no valor de US$ 150,00. A soma dos preços da receita deve ser igual à soma das linhas configuradas para capturar a alocação de preço da receita (US$ 400,00).

[![Página Alocação de preço da receita.](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

A ordem de venda está totalmente faturada. A ilustração a seguir mostra a entrada contábil lançada para a fatura.

[![Entrada contábil da ordem de venda totalmente faturada.](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

A agenda de reconhecimento da receita também é criada, mas nenhuma receita é reconhecida.

[![Página Agenda de reconhecimento de receita.](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Alguns dias depois, o cliente seleciona um laptop. Uma segunda ordem de venda é inserida para o cliente.

[![Linha da ordem de venda para o laptop.](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

A segunda ordem de venda está confirmada. Como essa ordem de venda contém apenas uma linha, a alocação de preço da receita não é executada ao confirmar a ordem de venda. A alocação de preço da receita ocorre somente se houver um ou mais itens exclusivos, e se esses itens forem configurados para a alocação de preço da receita.

Se essa nova ordem de venda for a única alteração no contrato do cliente, o processo de realocação poderá ser executado agora. Em uma das duas ordens de venda, selecione **Realocar preço com novas linhas da ordem** para abrir a página **Realocar preço com novas linhas da ordem**. Como alternativa, acesse **Reconhecimento de receita \> Tarefas periódicas \> Realocar preço com novas linhas da ordem**. Selecione as duas ordens de venda e as linhas correspondentes dela e depois selecione **Atualizar realocação**. A coluna **Valor realocado** mostra o novo preço da receita de cada linha da ordem de venda.

[![Novos preços de receita na página Realocar o preço com novas linhas da ordem.](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Em seguida, selecione **Comprovante esperado** para exibir as entradas contábeis que serão lançadas somente na Contabilidade. Como a opção **Lançar correções da fatura em Contas a receber** está definida como **Não** na página **Parâmetros da contabilidade**, nada será alterado em Contas a receber quando a realocação for processada.

[![Entradas contábeis na página Comprovante esperado.](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

Na página **Comprovante esperado**, as últimas três linhas estornam a entrada contábil original na fatura lançada. As quatro primeiras linhas constituem a nova entrada contábil lançada para a fatura. É importante compreender que uma nova fatura não é apresentada ao cliente. Após a realocação, o cliente ainda deve US$ 426,00, que é o valor que deve ser lançado em Contas a receber na nova entrada contábil. O imposto de compensação e a receita adiada é igual a US$ 188,69 + US$ 314,48 + US$ 26,00 = US$ 529,17. O valor da receita adiada foi alterado por causa da realocação. A diferença de US$ 103,17 é lançada na Conta de compensação da receita da fatura parcial. Esse saldo será compensado quando a fatura for lançada para a segunda ordem de venda que foi incluída na realocação.

Para concluir a realocação, selecione **Processar**. Você será solicitado a fornecer uma data de lançamento, mesmo que nada seja lançado. Depois que a realocação for concluída, a página **Alocação de preço da receita** de cada ordem de venda exibirá a alocação de preços de todos os itens nas duas ordens de venda. Em outras palavras, a página **Alocação de preço da receita** de cada ordem de venda incluirá um item que não existe nessa ordem de venda, pois faz parte do mesmo contrato, mas em uma ordem de venda diferente.

> [!TIP]
> Para fornecer um contexto sobre o motivo pelo qual esses itens adicionais são mostrados, você pode adicionar outras colunas à grade, como **ID de realocação** e **Ordem de venda**.
> 
> [![Colunas adicionais na página Alocações de preço de receita.](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

Na ordem de venda 00036, a agenda de reconhecimento de receita também foi atualizada, com base no novo preço de realocação da receita. Nessa ordem de venda, abra a página **Agenda de reconhecimento da receita**. Anteriormente, havia 13 linhas para o item S0008 (uma agenda de 12 meses foi atribuída a esse item). Agora há 39 linhas, as 13 linhas da agenda original, 13 linhas de estorno da agenda e 13 linhas baseadas no novo preço da receita.

[![Página Agenda de reconhecimento de receita atualizada com 39 linhas para o item S0008.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Da mesma forma, havia duas linhas para o item S0001, mas agora há seis.

[![Página Agenda de reconhecimento de receita atualizada com seis linhas para o item S0001.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Ao selecionar **Comprovante** na ordem de venda 000036, o diário de faturas mostra a entrada contábil original. Para exibir a entrada de estorno e a nova entrada contábil da ordem de venda, selecione **Ajustes da receita** no Painel de Ações e selecione **Comprovante**.

[![Ordem de venda 000036.](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Em seguida, abra a página **Todos s clientes** (**Contas a receber \> Clientes \> Todos os clientes**), selecione o cliente **US\_SI\_0003** e depois **Transações**. A fatura aberta da ordem de venda 000036 será exibida. Se você selecionar o comprovante, verá a entrada contábil original, não a nova entrada contábil da realocação. A entrada de estorno e a nova entrada contábil não podem ser exibidas em Contas a receber.

A segunda ordem de venda já está faturada. A fatura total apresentada ao cliente é de US$ 1.099,00 + US$ 71,44 de imposto = US$ 1.170,44. A ilustração a seguir mostra a entrada contábil lançada.

[![Página de transações de comprovante com a entrada contábil lançada.](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Como a soma da receita e a venda é maior que US$ 1.170,44, a diferença é lançada para -US$ 130,17. Esse valor compensa o saldo da conta de compensação da receita da fatura parcial. Esse saldo é lançado na nova entrada contábil após a realocação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]