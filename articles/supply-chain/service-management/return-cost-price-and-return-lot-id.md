---
title: "Devolução do preço de custo e do ID do lote"
description: "Talvez você queira que o custo dos produtos devolvidos seja igual ao custo dos produtos no momento em que você os vende ao cliente. Você pode fazer isso usando **Retornar a ID de lote**."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: aeba56128ab6c9ab7d244bdf153faba8e96069d6
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="return-cost-price-and-return-lot-id"></a>Devolução do preço de custo e do ID do lote        

[!include [banner](../includes/banner.md)]



O custo dos produtos que foram devolvidos ao estoque é calculado usando o custo atual dos produtos. No entanto, talvez você queira que o custo dos produtos devolvidos seja igual ao custo dos produtos no momento em que você os vende ao cliente. Você pode fazer isso usando o campo **Devolver ID de lote** na Guia Rápida **Detalhes da linha** no formulário **Ordem de venda**.

Por exemplo, considere o cenário a seguir. Você fatura um cliente. Em seguida, o cliente lhe devolve os produtos entregues. Você devolve os produtos ao estoque. Nesse caso, quando você credita o cliente pelos produtos devolvidos, o custo desses produtos é calculado usando o custo atual dos produtos. No entanto, se você usar o campo **ID do lote devolvido**, o custo dos produtos devolvidos é calculado usando o custo na fatura da venda original ao cliente.

Para usar um custo diferente do custo atual para devoluções de um cliente, use um dos métodos a seguir.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Método 1: Inserir manualmente o preço de custo de devolução

Por padrão, quando você adiciona itens a uma ordem de devolução, os itens foram devolvidos ao estoque no preço de custo atual. Para especificar outro preço de custo de devolução, sigas estas etapas.

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.

2.  No **Painel de Ação**, no grupo **Novo**, clique em **Ordem de retorno**.

3.  No formulário **Criar ordem de devolução**, selecione uma conta de cliente e clique em **OK**.

4.  No formulário **Ordem de devolução - Número RMA: %1, %2**, selecione um item e insira uma quantidade negativa no campo **Quantidade**.

5.  Clique na Guia Rápida **Detalhes da linha**.

6.  Na guia **Geral**, insira um valor no campo **Preço de custo de devolução**. Esse valor é usado quando os bens forem devolvidos para o estoque. Se você não inserir um valor, o preço de custo atual será usado quando os bens forem devolvidos ao estoque.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Método 2: Gerar automaticamente o preço de custo com base na linha da fatura do cliente

Esse é o método preferido a ser usado para criar linhas de devolução. Para usar o custo dos produtos no momento em que você vendeu os produtos ao cliente, crie uma ordem de devolução e especifique uma linha de venda para devolução.

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.

2.  No **Painel de Ação**, no grupo **Novo**, clique em **Ordem de retorno**.

3.  No formulário **Criar ordem de devolução**, selecione uma conta de cliente e clique em **OK**.

4.  No formulário **Ordem de devolução - Número RMA: %1, %2**, no **Painel de Ação**, clique em **Encontrar ordem de vendas**.

5.  No formulário **Localizar ordem de venda**, selecione a linha de fatura para devolução e clique em **OK**.
    
    Na Guia Rápida **Detalhes de linha**, na guia **Geral**, o campo **Devolver ID de lote** exibe o valor da linha de venda original. Além disso, o campo **Preço de custo de devolução** exibe o valor do custo da linha de venda original.

## <a name="cost-calculation-example"></a>Exemplo de cálculo de custo

Quando você usa o campo **ID do lote devolvido** em uma linha da ordem de devolução para especificar o preço de custo da devolução, o custo na linha da ordem de devolução será usado. Se você executar a funcionalidade de fechamento ou recálculo do estoque, os custos serão ajustados na linha de venda original. Os custos na linha da ordem de devolução são ajustados automaticamente para refletir o mesmo custo por peça.

1.  Crie e libere um produto denominado Teste. No formulário **Detalhes do produto liberado**, especifique as seguintes informações:
    
    1.  Na Guia Rápida **Gerenciar custos**, no campo **Grupo de item**, selecione o grupo **Peças**.
    
    2.  Na Guia Rápida **Geral**, no campo **Grupo de modelo do item**, selecione **DEF**.
    
    3.  Na Guia Rápida **Compra**, no campo **Preço**, digite 10,00 como o preço de custo do item.
    
    4.  No **Painel de Ação**, clique em **Grupos de dimensões**. No campo **Grupo de dimensões de armazenamento**, selecione **Apenas site e depósito**. No campo **Grupo de dimensões de rastreamento**, selecione **Nenhuma dimensão de rastreamento ativa**.

2.  Crie uma ordem de compra para 10 peças do item Teste a 6,00 cada peça e lance uma fatura para a ordem de compra.
    
    Crie uma segunda ordem de compra para 10 peças do item Teste a 8,00 cada peça e lance uma fatura para a ordem de compra.

3.  Lance uma fatura para uma ordem de venda para vender cinco peças do item Teste.
    
    Nesse caso, a linha da ordem de venda é orçada a 35,00 (5 peças \* custo médio por peça de 7,00).

4.  Crie uma ordem de devolução para o cliente. No formulário **Localizar ordem de venda**, selecione a linha de fatura para devolução e clique em **OK**.

5.  No formulário **Ordem de devolução - Número RMA: %1, %2**, verifique se uma ordem de devolução foi gerada para devolução do item Teste. A quantidade da ordem de devolução é definida como -5,00.
    
    O campo **Devolver ID de lote** exibe um ID de lote. Essa ID de lote é extraída da ordem de venda original do item que foi vendido ao cliente. O campo **Preço de custo de devolução** exibe o preço do custo da linha de venda original.

6.  Registre o recebimento dos itens devolvidos.

7.  Lance uma guia de remessa para os itens devolvidos.

8.  Lance uma fatura para a ordem de devolução. Na página de listagem **Todas as ordens de venda**, selecione uma ordem de venda para a qual **Ordem devolvida** é o tipo de ordem.

9.  Abra o formulário **Transações de estoque**. Verifique se a devolução foi orçada a 7,00 por peça usando o valor no campo **Preço de custo de devolução**, para um total de 35,00 no campo **Valor de custo**. Você pode abrir o formulário **Transações de estoque** a partir do formulário **Ordem de devolução - Número RMA: %1, %2**. Na grade **Linhas**, clique em **Estoque** \> **Transações**.

10. No Gerenciamento de estoque e depósito, use o formulário **Fechamento e ajuste** para executar o procedimento **3. Fechar**.
    
    Essa ação ajusta o custo na linha de venda original que foi orçado a -35,00 (5 peças \* 7,00) para -30,00 (5 peças \* 6,00). Isso porque o grupo de modelos de estoque usa o processo FIFO (primeiro a entrar, primeiro a sair) e 6,00 por peça é o custo FIFO a partir da primeira ordem de compra. Além disso, a ação ajusta o custo na linha de venda de devolução para corresponder ao custo por peça na linha de venda original. Portanto, o custo da linha de devolução é ajustado de 35,00 para 30,00.





