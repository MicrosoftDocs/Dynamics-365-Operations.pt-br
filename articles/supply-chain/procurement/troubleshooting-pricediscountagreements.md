---
title: Solucionar problemas de preços, descontos, contratos e descontos
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com preços, descontos, contratos e descontos.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2ccc1d52b83f9319af1c6336c1876c795c70028a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908510"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Solucionar problemas de preços, descontos, contratos e descontos

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com preços, descontos, contratos e descontos.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>Não consigo vincular um contrato de compra a uma linha da ordem de compra após a criação da ordem de compra.

Um contrato de compra deve ser associado a uma ordem de compra quando a ordem de compra for criada. Caso contrário, as linhas da ordem de compra não podem ser associadas a linhas do contrato de compra.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Que verificação dispara a mensagem "Atualizar preços e descontos inseridos manualmente ou documento externo"?

Ao alterar a data de remessa, você pode receber uma mensagem que declara, "Atualizar preços e descontos inseridos manualmente ou documento externo." Você recebe esta mensagem porque, se a data de remessa for alterada, um contrato comercial ou de venda diferente poderá ser disparado e provocar uma alteração de preço. Uma alteração na data de remessa também pode afetar agendas de depósito e outras informações relacionadas.

A mensagem é disparada sempre que qualquer uma das datas ou outros parâmetros são alterados. A finalidade da mensagem é verificar se você está ciente de alterações de preço que podem ocorrer devido a essas alterações.

A mensagem é o prompt de avaliação do contrato comercial (TAE). Para obter uma descrição completa, consulte [Políticas de avaliação de contrato comercial](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Um recibo de ordem de compra não inclui todos os encargos.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Na página **Parâmetros de compras**, na guia **Entrega**, certifique-se de que a opção **Gerar encargos no recibo do produto** está definida como *Sim*.
1. Crie uma ordem de compra que inclui encargos.
1. Confirme uma ordem de compra.
1. Receba a ordem de compra.
1. Examine o total do recibo e compare-o com o total esperado.
1. Observe que nem todos os encargos estão incluídos no recebimento da ordem de compra.

### <a name="issue-resolution"></a>Resolução do problema

A resolução depende da forma como os encargos diversos foram configurados. Para obter informações sobre como configurar encargos diversos de acordo com suas necessidades, consulte a seguinte postagem de blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>Os preços e descontos do contrato comercial não são aplicados a linhas de ordem de compra ou de venda que são importadas por meio do gerenciamento de dados.

### <a name="issue-description"></a>Descrição do problema

Os contratos comerciais que não são aplicados a linhas de ordem de compra ou de venda não são aplicados a linhas que são importadas por meio do gerenciamento de dados. No entanto, os mesmos contratos comerciais são aplicados a linhas de ordem de compra ou de venda que são criadas manualmente.

### <a name="reason-for-the-issue"></a>Motivo do problema

Se as linhas da ordem de compra que são importadas por meio do gerenciamento de dados já incluírem informações de preço, o contrato comercial não será reavaliado para essas linhas. Por exemplo, se **Porcentagem de desconto de linha** ou qualquer um dos valores de preço e desconto for definido para uma linha, os contratos comerciais não serão pesquisados para essa linha.

### <a name="issue-workaround"></a>Solução alternativa do problema

Esse comportamento é esperado e é semelhante para ordens de venda e ordens de compra.

Para solucionar o problema, importe as linhas da ordem de compra sem definir as informações de preço. Os contratos comerciais serão aplicados, e as linhas da ordem de compra serão atualizadas com base nos contratos comerciais definidos.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Um desconto de fornecedor não é acumulado com base em faturas.

### <a name="issue-description"></a>Descrição do problema

Se as faturas lançadas tiverem datas de conclusão diferentes, essas faturas serão refletidas em descontos de fornecedor que são gerados a partir delas.

### <a name="issue-resolution"></a>Resolução do problema

Por design, a data de conclusão não é considerada quando o desconto do fornecedor é calculado. Considere a personalização do sistema para que a data de conclusão e a relação com a fatura sejam mais aparentes em relação ao desconto real do fornecedor.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Os preços unitários das ordens de compra não são calculados com base na conversão de unidades.

### <a name="issue-description"></a>Descrição do problema

Quando uma unidade é alterada em uma ordem de compra, os preços do contrato comercial não são recalculados de acordo com as definições de conversão de unidades.

### <a name="issue-resolution"></a>Resolução do problema

Os preços sempre obtidos de contratos comerciais (ou outras configurações de preço no sistema, como contratos de venda ou preços de item), e são definidos para uma unidade.

Se a unidade for alterada em uma linha da ordem, o sistema procurará um preço para a nova unidade e aplicará esse preço. Se nenhum preço for encontrado para a unidade, o sistema não aplicará um preço. A conversão de unidades não pode ser usada para recalcular o preço em outra unidade. Teoricamente, o preço de uma caixa de dez pode não ser igual a dez vezes o preço de uma caixa.

### <a name="issue-workaround"></a>Solução alternativa do problema

Uma forma de solucionar esse problema é verificar se há contratos comerciais para as unidades esperadas que serão usadas nas linhas da ordem para o item.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Os problemas de conversão de moeda ocorrem com os contratos comerciais.

Os preços do contrato comercial não são recalculados, de acordo com a moeda, quando a moeda é diferente em uma ordem de compra.

O recurso *Moeda genérica* permite definir preços e descontos em apenas uma moeda. Em seguida, você pode converter para outras moedas, conforme necessário. Além disso, após a conversão ser concluída, o recurso pode aplicar o arredondamento inteligente automaticamente.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Quando abro a página de Contrato de compra em um modo de exibição de linha, não consigo personalizar a página adicionando o campo Unidade de preço na visão geral da linha.

Alguns campos compartilhados na estrutura do contrato não podem ser incluídos nas personalizações. Essa limitação ocorre por causa do modelo de dados implementado. Portanto, não é possível personalizar o campo **Unidade de preço**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>O limite máximo de um contrato de compra não é efetivo em uma requisição de compra.

### <a name="issue-description"></a>Descrição do problema

Quando uma requisição de compra estiver vinculada a um contrato de compra, o limite máximo do contrato de compra não será efetivo na requisição de compra. As informações de preço padrão são inseridas corretamente, mas mais do que o limite máximo do contrato de compra pode ser solicitado na requisição de compra.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é esperado. Como as requisições nem sempre são aprovadas, uma quantidade ou um valor não deve ser reservado no contrato de compra. Portanto, você não atenderá ao limite máximo do contrato de compra.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>Os contratos comerciais podem ser criados a partir de RFQs rejeitadas. Portanto, o sistema não impede que os diários de contratos comerciais sejam criados se a linha da RFQ não tiver sido aceita.

Você pode criar contratos comerciais para qualquer resposta para uma solicitação de cotação (RFQ), independentemente de elas terem sido aceitas ou rejeitadas. Para obter informações, consulte [Visão geral de solicitações de cotação (RFQs)](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]