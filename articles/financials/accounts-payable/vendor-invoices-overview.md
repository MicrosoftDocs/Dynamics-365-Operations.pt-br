---
title: "Visão geral das faturas de fornecedor"
description: "Este artigo fornece informações gerais sobre notas fiscais de fornecedor. As notas fiscais de fornecedor são solicitações para pagamento dos produtos e serviços recebidos. As notas fiscais do fornecedor podem representar uma conta para serviços em andamento, ou podem se basear em ordens de compra para itens específicos e serviços."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5ff988d669f8a2328530425482f6e045cf4537c7
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-invoices-overview"></a>Visão geral das faturas de fornecedor

[!include[banner](../includes/banner.md)]


Este artigo fornece informações gerais sobre notas fiscais de fornecedor. As notas fiscais de fornecedor são solicitações para pagamento dos produtos e serviços recebidos. As notas fiscais do fornecedor podem representar uma conta para serviços em andamento, ou podem se basear em ordens de compra para itens específicos e serviços. 

<a name="vendor-invoices"></a>Faturas de fornecedor
---------------

Uma fatura de fornecedor de uma ordem de compra é uma fatura que é gerada quando produtos ou serviços são recebidos de acordo com uma ordem de compra que foi criada com um fornecedor. A fatura do fornecedor contém um cabeçalho e uma ou mais linhas para itens ou serviços. Uma fatura do fornecedor completa o ciclo da ordem de compra para a nota fiscal do fornecedor. 

Embora algumas faturas de fornecedor estejam associadas a uma ordem de compra, as faturas de fornecedor também podem conter linhas que não correspondem às linhas da ordem de compra. Você também pode criar faturas de fornecedor que não estão associadas com qualquer ordem de compra. Essas faturas de fornecedor podem representar serviços em andamento, como uma conta de serviço público, e não é necessário fazer referência a uma ordem de compra ao adicioná-las. 

Há várias formas de inserir uma fatura de fornecedor:

-   O registro de fatura do fornecedor permite que você insira rapidamente faturas que não fazem referência a uma ordem de compra, para que você possa acumular a despesa. Ao usar o diário de aprovação de fatura do fornecedor, você pode selecionar essas faturas e publicá-las no saldo do fornecedor para reverter a provisão.
-   O diário de faturas de fornecedor permite inserir rapidamente faturas que não fazem referência a uma ordem de compra, em uma única etapa.
-   Junto com o grupo de faturas de fornecedor, o registro de fatura de fornecedor permite inserir rapidamente faturas para aumentar a despesa. Você pode abrir as ordens de compra associadas ao lançar a fatura com base na conta de despesas.
-   As páginas **Faturas de fornecedor em aberto** e **Faturas de fornecedor pendentes** permitem criar faturas de fornecedor a partir de ordens de compra confirmadas.

A discussão a seguir fornece mais informações sobre como usar a página **Faturas de fornecedor em aberto** ou **Faturas de fornecedor pendentes** para criar uma fatura de fornecedor a partir de uma ordem de compra.

## <a name="understanding-invoice-line-quantities"></a>Entendendo as quantidades da linha da fatura
Ao abrir uma fatura de fornecedor de uma ordem de compra relacionada, as linhas de fatura são criadas a partir da ordem de compra. Por padrão, as quantidades são tiradas da quantidade de recebimento de produtos. No entanto, você pode usar qualquer um dos seguintes comportamentos padrão:

-   **Quantidade de recebimento atual** – Use esta opção para remessas parciais. O valor padrão no campo **Quantidade** é tirado do campo **Quantidade de recebimento atual** na ordem de compra.
-   **Quantidade encomendada** – Use esta opção para remessas completas. O valor padrão no campo **Quantidade** é tirado do campo **Quantidade encomendada** na ordem de compra.
-   **Quantidade registrada** – Use esta opção se o item exigir registro, conforme especificado na página **Grupos de modelos de item**. O valor padrão no campo **Quantidade** é a quantidade de atualização física que foi registrada.
-   **Quantidade de recebimento de produtos** – Use esta opção se um recebimento de produtos já tiver sido recebido para a ordem. O valor padrão no campo **Quantidade** é tirado da quantidade total dos recebimentos de produtos disponíveis.
-   **Quantidade e serviços registrados** – Use esta opção se as quantidades foram registradas em diários de chegada para os itens em estoque ou itens que não estão armazenados. Esta opção também inclui serviços, independente do fato de os serviços estarem registrados ou não.

Se a entidade legal utiliza a conciliação de faturas, você pode exibir os resultados da conciliação de quantidade na coluna **Conciliação de quantidade de recebimento de produtos**. Você também pode usar o comando do menu **Detalhes de conciliação** na guia **Revisão** para exibir os resultados da conciliação de quantidade.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Adicionar uma linha que não estava na ordem de compra
Você pode adicionar uma nova linha que não estava na ordem de compra para a fatura do fornecedor. Você deve selecionar um número de item ou categoria de suprimento. Você pode adicionar quantidades, preços e valores na linha. A linha será incluída somente nas políticas de conciliação para os totais de fatura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Enviando uma fatura de fornecedor para revisão
Sua organização pode usar os fluxos de trabalho para gerenciar o processo de revisão para faturas de fornecedores. A revisão de fluxo de trabalho poderá ser necessária para o cabeçalho ou a linha da fatura, ou ambos. Os controles do fluxo de trabalho se aplicam ao cabeçalho ou linha, dependendo de onde o foco estiver ao clicar no controle. Em vez do botão **Lançar**, você verá o botão **Enviar** que você pode usar para enviar a fatura de fornecedor com o processo de revisão.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Conciliando faturas de fornecedor com os recebimentos de produtos
Você pode inserir e salvar informações para as faturas de fornecedores e pode conciliar linhas de fatura a linhas de recebimento de produtos. Você também pode conciliar quantidades parciais para uma linha. 

Você pode criar uma fatura de fornecedor com base nos itens de linha de recebimento de produtos que até a data, mesmo que todos os itens de determinada ordem de compra ainda não tenham sido recebidos. Por exemplo, é possível usar esta opção se um fornecedor enviar uma fatura por mês cobrindo todas as entregas enviadas pelo fornecedor durante esse mês. Cada recebimento de produtos representa uma entrega parcial ou completa dos itens da ordem de compra. 

Quando você lança a fatura, a **Quantidade a faturar** de cada item é atualizada com o total das quantidades recebidas dos recebimentos de produtos selecionados. Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de compra for 0 (zero), o status da ordem de compra é alterado para **Faturado**. Se a quantidade **A faturar** for diferente de 0, o status da ordem de compra permanece inalterado, e faturas adicionais podem ser inseridas para ela.

Esta opção pressupõe que pelo menos um recebimento de produtos tenha sido lançado para a ordem de compra. A fatura de fornecedor baseia-se nesses recebimentos de produtos e reflete suas quantidades. As informações financeiras da nota fiscal baseiam-se nas que são inseridas quando você lança essa nota.

Para saber mais, consulte [Registrar fatura de fornecedor e corresponder com a quantidade recebida](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="working-with-multiple-invoices"></a>Trabalhando com diversas faturas

Você pode trabalhar com várias faturas e lançá-las ao mesmo tempo. Se você precisar criar várias faturas, use a página **Faturas de fornecedor pendentes**. Se você precisar lançar e imprimir várias faturas de fornecedor, use a página do diário de aprovação de faturas. Se você estiver usando o diário de aprovação de fatura, pelo menos um recebimento de produtos deve ser lançado para a ordem de compra, e uma fatura para a ordem de compra deve ser lançada em um registro de fatura. As informações financeiras para a nota fiscal vêm da nota fiscal que foi lançada no registro.


Para obter mais informações, consulte: 

 - [Configurar políticas de fatura de fornecedores](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md) 

 - [Dados-chave de fatura em contas a pagar usando uma fatura de fornecedor](tasks/key-invoice-data-ap-system-vendor-invoice.md)
 
 - [Dados-chave de fatura em contas a pagar usando um diário de aprovações](tasks/key-invoice-data-into-ap-system-approval-journal.md)
  
 - [Dados-chave de fatura no sistema de AP usando grupo de faturas](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
 
 - [Registrar uma fatura de fornecedor no diário de faturas](tasks/record-vendor-invoice-invoice-journal.md)


