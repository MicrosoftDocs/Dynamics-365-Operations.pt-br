---
title: Visão geral de ordem de compra
description: Este artigo fornece informações gerais sobre as ordens de compra (POs) e links para artigos adicionais que estão relacionados aos diversos estágios que passa de uma OC.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, PurchConfirmationRequestJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "93083"
- intro-internal
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7c3666cfcc6db19f7144448d9eb435af43140f45e3291fc914adb0ee9f96831
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718939"
---
# <a name="purchase-order-overview"></a>Visão geral de ordem de compra

[!include [banner](../includes/banner.md)]

Este artigo fornece informações gerais sobre as ordens de compra (POs) e links para artigos adicionais que estão relacionados aos diversos estágios que passa de uma OC.

Uma ordem de compra (OC) é um documento que representa um contrato com um fornecedor para comprar mercadorias ou serviços. O documento também ajuda a manter o controle dos recebimentos de produtos que são feitos em direção a ordem e, posteriormente, estatísticas de notas fiscais de fornecedor que o fornecedor cobra em direção a ordem.  

A página **Ordens de compra** contém uma visão geral das ordens disponíveis e permite que você modifique as ordens. Ao abrir um pedido de compra, você pode selecionar a exibição **Cabeçalho**, que contém informações que são especificadas somente uma vez para cada ordem de compra, como os detalhes do fornecedor. Como alternativa, você pode selecionar a exibição **Linhas**, onde você pode modificar linhas de ordem. Normalmente, você alternará entre essas duas exibições conforme altera as OCs. Encargos não estão relacionados diretamente a página **Ordens de compra**, mas são acessados nos menus no cabeçalho e nas linhas de ordem.  

Há vários relatórios onde você pode exibir informações sobre POs, guias de remessa e notas fiscais de fornecedor. Esses relatórios são encontrados nos módulos **Aquisição e fornecimento** e **Contas a pagar**.  

Os espaços de trabalho **Preparação da ordem de compra** e **Recebimento e acompanhamento da ordem de compra** permitem que você exiba listas de POs em vários estados para o qual você progrediu. Eles também fornecem um resumo das ações que devem ser seguidas. O espaço de trabalho **Preparação da ordem de compra** se concentra na criação de ordem de compra e revisão, processamento do pedido e até a aprovação e confirmação com o fornecedor. O espaço de trabalho **Recebimento e acompanhamento da ordem de compra** tem como foco processamento do recebimento de materiais ou serviços contra OCs. Inclui as listas que oferecem informações sobre os recebimentos vencidos ou que vencerão futuramente por conta de entrega do fornecedor. Estes espaços de trabalho não são usados para executar as atividades de recebimento relacionadas feitas no depósito. Essas atividades são executadas usando páginas nos módulos **Gerenciamento de estoque** e **Gerenciamento de depósito**. Processamento de faturas do fornecedor deve ser feito usando o espaço de trabalho **Entrada de fatura de fornecedor** e pagamentos devem ser feitos usando o espaço de trabalho **Pagamentos de fornecedor**.  

Os artigos a seguir fornecem uma visão geral sobre os vários estágios pelos quais uma OC passa por:

-   [Criar ordens de compra](purchase-order-creation.md)
-   [Aprovar e confirmar ordens de compra](purchase-order-approval-confirmation.md)
-   [​Recebimento de produtos contra ordens de compra​](product-receipt-against-purchase-orders.md)
-   [​Visão geral de faturas de fornecedor​](../../finance/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Tipos de ordens de compra
Existem três tipos de ordens de compra. Quando você cria uma OC, você deve especificar o tipo. Você pode configurar um tipo de ordem padrão para novas ordens na página **Parâmetros de compras**.

| Tipo de OC        | Descrição                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Diário        | Use este tipo para criar uma ordem de venda. Este tipo não afeta as quantidades em estoque ou gera transações de estoque. As linhas do diário da OC não estão incluídas no planejamento mestre.                                                                                                       |
| Ordem de Compra | Use este tipo para criar POs quando as ordens são confirmadas com um fornecedor, e quando os pedidos são processados por meio de recebimento e faturamento antes de o pagamento ser feito ao fornecedor. Esse tipo de ordem de compra é o mais comum.                                                                          |
| Ordem devolvida | Use este tipo na devolução de mercadorias ao fornecedor. Esse tipo de ordem exige que você especifique o número de autorização de material de devolução (ADM) que o fornecedor dá a você. Especificar o número RMA na guia **Geral** do pedido de compra. As linhas da ordem devem ter quantidades negativas. |

## <a name="purchase-order-statuses"></a>Status da ordem de compra
POs incluem vários campos de status que indicam o progresso da ordem. Todos esses campos são visíveis na exibição **Cabeçalho** da ordem e alguns deles também são visíveis na visão geral de grade de todas as ordens. O campo **Status** mostram o status para as quantidades da ordem. Os valores a seguir estão disponíveis:

-   **Abrir ordem** – Ordens foram criadas e as quantidades estão em ordem.
-   **Recebida** – Algumas das quantidades foram recebidas, mas ainda não foram faturadas.
-   **Faturado** – A quantidade total da ordem foi faturada. **Observação:** se um pedido foi *parcialmente* faturado, nem **recebido** status nem **faturado** status é apropriado. Portanto, a ordem terá um status **Abrir ordem**.
-   **Cancelado** – Uma ordem foi confirmada mas cancelada mais tarde. Portanto, este status indica que não existem mais as quantidades abertas na ordem.

O campo **Status de documentos** ajuda a verificar rapidamente o progresso da ordem em termos de documentos que foram processados. Ele mostra o status do documento mais recente que foi concluído para a ordem. Os valores a seguir estão disponíveis:

-   **Nenhum** – Nenhum documento foi processado para o pedido ainda.
-   **Consulta de compra** – Uma consulta de compra foi gerada e a ordem está aguardando comentários do fornecedor.
-   **Ordem de compra** – Confirmação foi processada na ordem.
-   **Recebimento de produtos** – Produto foi processado na ordem de recebimento de produtos.
-   **Fatura** – Uma nota fiscal foi levada em consideração com a ordem.

O campo **Status de aprovação** é usado quando uma ordem de compra passa por um processo de revisão ou fluxo de trabalho. Os valores a seguir estão disponíveis:

-   **Rascunho**, **Em revisão**, e **Rejeitado** – Esses status são usados somente quando é usado um fluxo de trabalho de aprovação para o pedido de compra.
-   **Aprovado** – Este status é atribuído às ordens que tenham concluído a aprovação de fluxo de trabalho. As ordens criadas sem usar um fluxo de trabalho de aprovação recebem um status de **Aprovado** imediatamente.
-   **Na revisão externa** – este status é usado em cenários onde a consulta de compra é enviada ao fornecedor, para que o fornecedor possa confirmar termos do pedido de compra. Este status também é usado no processo iniciado pela ação **Solicitação de confirmação**. Para esse processo, o fornecedor deve confirmar termos da PO conectando-se ao seu sistema e registrando se ele confirma ou rejeita o pedido.
-   **Confirmado** – este status é atribuído depois que a ordem foi confirmada. Normalmente, esse status é o último status de aprovação é atribuído a uma encomenda.


## <a name="additional-resources"></a>Recursos adicionais

[Criar ordens de compra](purchase-order-creation.md)

[Aprovar e confirmar ordens de compra](purchase-order-approval-confirmation.md)

[​Recebimento de produtos contra ordens de compra​](product-receipt-against-purchase-orders.md)

[​Visão geral de faturas de fornecedor​](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]