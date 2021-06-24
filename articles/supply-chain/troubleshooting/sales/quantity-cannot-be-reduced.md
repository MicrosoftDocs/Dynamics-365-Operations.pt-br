---
title: A quantidade não pode ser reduzida quando uma ordem de venda for cancelada
description: A quantidade não pode ser reduzida quando uma ordem de venda for cancelada.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230827"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>A quantidade não pode ser reduzida quando uma ordem de venda for cancelada

Código de erro: SYS138831

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> A quantidade não pode ser reduzida. O número de transações de inventário na ordem é baixo demais porque a quantidade ou parte dela é referenciada por uma ordem de saída ou uma ordem de produção ou é marcada contra outras transações.

## <a name="cause"></a>Causa

Se o trabalho estiver associado a uma ordem de venda, não será possível cancelar a ordem de venda até que o trabalho seja cancelado e revertido. Esse requisito se aplica mesmo que o trabalho associado à ordem de venda seja fechado.

## <a name="resolution"></a>Resolução

Para solucionar esse problema, conclua as seguintes tarefas:

1. Cancele o trabalho aberto.
1. Excluir a carga.
1. Reduza a quantidade selecionada.

### <a name="cancel-open-work"></a>Cancelar o trabalho aberto

Siga estas etapas para cancelar o trabalho aberto.

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

### <a name="delete-the-load"></a>Excluir a carga

Para excluir uma carga, siga estas etapas.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Abra a ordem de venda relevante.
1. Na FastTab **Linhas da ordem de venda**, selecione **Armazém \> Detalhes do trabalho**.
1. Na página **Trabalho**, no Painel de Ações, na guia **Trabalho**, no grupo **Trabalho**, selecione **Cancelar trabalho**.
1. Certifique-se de que o campo **Status do trabalho** está definido como *Cancelado*.
1. Feche a página **Trabalho**.
1. Na página de detalhes da ordem de venda, na FastTab **Linhas da ordem de venda**, selecione **Armazém \> Detalhes da carga**.
1. No Painel de Ações, selecione **Excluir**.
1. Selecione **Sim** para confirmar que você deseja excluir a carga.
1. Feche a página **Carga**.

### <a name="reduce-the-picked-quantity"></a>Reduzir a quantidade selecionada

Após todo o trabalho ter sido cancelado, siga estas etapas para reduzir a quantidade selecionada.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Abra a ordem de venda relevante.
1. Na FastTab **Linhas da ordem de venda**, selecione **Atualizar linha \> Selecionar** na barra de ferramentas.
1. Na página **Selecionar**, na seção **Transações**, selecione a linha em que o campo **Status da emissão** está definido como *Selecionado*.
1. Na seção **Transações**, selecione **Adicionar linha de seleção** na barra de ferramentas.
1. Na seção **Linhas de seleção**, selecione **Confirmar seleção de todos** na barra de ferramentas.
1. Feche a página **Selecionar**.
1. Na página de detalhes de ordem de venda, no Painel de Ações, na guia **Ordem de vendas**, no grupo **Manter**, selecione **Cancelar**.
1. Selecione **Sim** para confirmar que você deseja cancelar a ordem de venda.
