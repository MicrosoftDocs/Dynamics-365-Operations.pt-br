---
title: Criar ordens de compra
description: "Este artigo descreve o processo e as opções quando você criar manualmente uma ordem de compra."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: fbf5337ac41ceae6e911c056db5226c8ed1cefb0
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="create-purchase-orders"></a>Criar ordens de compra

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Este artigo descreve o processo e as opções quando você criar manualmente uma ordem de compra.

Quando você cria uma ordem de compra (OC), informações gerais sobre a ordem inteira são especificadas no cabeçalho da OC e, em seguida, você adiciona uma ou mais linhas de OC. Este artigo descreve algumas das opções usadas com mais frequência que estão disponíveis.  

Você também pode criar POs copiando linhas de outro documento de ordem de compra ou uma ordem de venda. Nesse caso, você pode inverter o sinal do estoque, como você inverte o sinal em uma nota fiscal para indicar crédito.  

Embora você possa criar manualmente POs, elas geralmente são geradas de outros processos. As ordens podem ser criadas automaticamente com base em outros documentos, como requisições. Alternativamente, podem ser criados como parte do processo de planejamento mestre através das ordens de compra planejadas. Se usar contratos de compra, as ordens de compra podem ser criadas pela ação **Liberar ordem**. Existem também mais avançados métodos para criar automaticamente uma ordem de compra. Por exemplo, ordens podem ser criadas quando você usa a entrega ou direta cadeias de ordem intercompanhia.

## <a name="creating-a-purchase-order-header"></a>Criar o cabeçalho da ordem de compra
Quando você cria uma nova ordem de compra, uma caixa de diálogo será exibida, onde você pode inserir as informações mais comuns para o cabeçalho da ordem de compra. Quando você clica em **OK** para fechar a caixa de diálogo, a ordem é criada e, em seguida, você pode especificar informações adicionais no cabeçalho.  

O primeiro detalhe que você deve considerar ao criar uma ordem de compra é o tipo de ordem. O tipo **Ordem de compra** é usado com mais frequência. No entanto, se uma fatura de crédito for necessária, você pode usar o tipo **Ordem devolvida**.  

Você deve especificar o fornecedor no campo **Conta de fornecedor**. Para esse campo, você pode pesquisar sobre a conta ou o nome do fornecedor. Se um fornecedor oferece vários locais, mas usa uma conta de nota fiscal única, você pode selecionar essa conta de nota fiscal no campo **Conta de nota fiscal** e, em seguida, usá-lo com contas de fornecedores diferentes. Se for necessário criar uma ordem de compra para os produtos que não sejam ordenados repetidamente, você pode usar a opção **Fornecedor ocasional**. Essa opção cria automaticamente uma nova conta de fornecedor que está marcada como uma conta ocasional, para dar suporte a um processo de limpeza mais tarde para contas únicas do módulo **Contas a pagar**. Quando você selecionar uma conta de fornecedor, muitos campos no cabeçalho da ordem de compra herdam valores padrão a partir das informações que estão associadas com a conta do fornecedor. Por exemplo, o local de entrega padrão e o depósito são copiados a partir das informações do fornecedor. No entanto, você pode substituir esses valores padrão se destina a compra para outro local.  

Se o fornecedor tiver fornecido um número de referência para a ordem, você pode gravar essas informações no campo **Referência do fornecedor**. Para pedidos retornados, você deve especificar um valor no campo **RMA** para autorização do fornecedor para processar o retorno de referência.  

Se um contrato de compra estiver associado à ordem, você deve especificar essas informações no campo **Contrato de compra**.  

O cabeçalho da ordem de compra também contém informações sobre encargos que se aplicam a toda a ordem em vez de linhas individuais. Encargos podem ser adicionados automaticamente à ordem se encargos automáticos foram configurados para o fornecedor ou grupo de encargos do fornecedor. Você também pode adicionar manualmente encargos ao cabeçalho da ordem clicando em **Manter encargos** no painel de ação.

## <a name="adding-purchase-order-lines"></a>Adicionar linhas de ordem de compra
POs podem ser de produtos físicos ou de serviços. Uma configuração no grupo de modelos de estoque determina se um número de item em particular se aplica a um produto ou serviço. Geralmente, o item é comprado é especificado por um número de item. No entanto, se a ordem for por produtos ou serviços que são consumidos diretamente, você também pode especificar o item por meio de uma categoria de compras.  

Linhas da OC contêm vários campos, mas muitos desses campos têm um valor padrão ou um valor que é herdado do cabeçalho da ordem. Campos adicionais são definidos quando você selecionar um produto ou serviço. Os campos são geralmente definidos manualmente e incluem os campos para o número do item, quantidade e data de entrega solicitada. Informações sobre o preço unitário e descontos também são muito importantes, mas os valores desses campos geralmente são determinados pelos contratos comerciais ou contratos de compra.  

Quando você selecionar um produto, você pode pesquisar em todo ou parte do nome do produto, em vez de usar o número do item. Se o produto tiver diversas variantes, como tamanhos diferentes, você pode ver uma visão geral sobre as variantes disponíveis usando a função **Adicionar linhas** ou usando a pesquisa que está disponível no campo **Número de variante**.  

Em geral, você terá que especificar várias dimensões para o item que está selecionado em cada linha de ordem de compra. As dimensões que devem ser especificadas dependem dos grupos de dimensões que foram atribuídos para a definição de produtos mestre. Por exemplo, você frequentemente precisa especificar um local e um depósito para indicar o local em que o produto deve ser entregue. Identificar variantes de produto, especificando um número de variante ou inserindo valores para uma ou mais dimensões do produto, como cor, tamanho, configuração ou estilo. Dimensões, como o número de série e de lote de rastreamento permite identificar de forma exclusiva cada lote de estoque. Depois que você tiver criado uma ordem, você pode capturar os valores de dimensão na ordem usando a ação **Registro**. Por exemplo, você solicitou uma quantidade de cinco partes de um item. Posteriormente, você registra que três dessas partes será preta, e duas delas serão azuis. Essa abordagem é uma alternativa para capturar as informações de dimensão durante o registro de entrada.  

Você pode verificar os detalhes sobre o status da transação de estoque de produtos em estoque. Por exemplo, convém verificar o estoque para ajudá-lo a decidir quanto à ordem. Como alternativa, convém rever o status de estoque de uma quantidade encomendada para ver se o registro de entrada ocorreu.  

Uma linha de OC está sendo usada para devolver um produto ao fornecedor que terá uma quantidade negativa. Você pode selecionar um lote específico para retornar usando a ação **Reserva**.  

Às vezes, convém dividir a quantidade que foi encomendada, para que diferentes partes sejam entregues em datas diferentes. Você pode configurar essas entregas usando a ação **Agenda de entrega**, que está disponível no menu **Linha da ordem de compra** na exibição de **Linhas**.  

Encargos podem ser adicionados automaticamente à linhas da PO, se encargos automáticos foram configurados para o fornecedor ou grupo de encargos do fornecedor, e para o item ou grupo de encargos do item. No entanto, geralmente, encargos são adicionados manualmente no nível da linha da ordem. Para adicionar um encargo, abra a página **Manter encargos** usando a ação **Manter encargos** sobre o menu **Finanças** na exibição **Linhas**. A vantagem de adicionar encargos diretamente no nível da linha da ordem é que o encargo pode ser alocado como um custo de estoque. Para definir os códigos de encargo ao custo do produto de conta, use a opção de débito **Item**. Esses tipos de encargos devem ser alocados do cabeçalho da ordem de compra para as linhas antes que a ordem possa ser confirmada. Por exemplo, você talvez queira alocar encargos com base na quantidade em cada linha. A categoria de custo também afeta como os encargos serão contabilizados. Por exemplo, encargos fixos especificam um valor fixo e porcentagem de encargos calculados como uma porcentagem do valor líquido para a linha da ordem. POs podem ser atribuídos a uma carga e a carga pode incluir uma estimativa da despesa esperada para o custo de transporte. Você pode alocar essa despesa de carga antes das linhas de ordem de compra.

## <a name="purchase-order-actions"></a>Ações da ordem de compra
Depois de adicionar o cabeçalho e as linhas para a ordem de compra, você geralmente deve concluir etapas adicionais antes que a ordem esteja pronta para ser confirmada. Como tantas opções estão disponíveis, talvez seja útil usar [Pesquisa de ação](/dynamics365/unified-operations/fin-and-ops/get-started/action-search) para localizar o item de menu relevantes.  

Você pode configurar produtos na ordem para que eles tenham itens suplementares. Itens suplementares são produtos que devem ou podem ser comprados em conjunto com outros produtos. Produtos suplementares podem ser adicionados gratuitamente como os que acompanham os produtos ou você poderá optar por adicioná-los à ordem ou não. Você pode revisar os itens suplementares após cada linha de ordem adicionada. No entanto, você provavelmente achará mais conveniente revisar e adicionar itens suplementares relevantes para todas as linhas da ordem, usando a página **Itens suplementares**, que pode ser aberta no painel de ação.  

Descontos em geral são adicionados às linhas conforme eles são criados. No entanto, alguns descontos se aplicam a toda a ordem:

-   A ação **Desconto Total** calcula uma porcentagem de desconto total que é aplicada a ordem inteira. Não confunda este desconto com a porcentagem de desconto à vista. Descontos são aplicados quando a fatura é paga e eles dependem de liquidação de pagamento de uma determinada data.
-   Se se aplica um desconto de várias linhas, você deve usar a ação **Desconto combinado** para calcular e atribuí-lo à ordem. Descontos combinados são descontos que podem ser oferecidos se uma combinação de produtos da ordem exceder um limite de conjunto. Apenas poucas empresas usam esse tipo de desconto.

Encargos que possuem um código de encargo que usa o tipo **Item** de débito que deve ser atribuído ao nível de linha antes que a ordem possa ser confirmada. Talvez seja conveniente atribuir esses encargos no nível do cabeçalho da ordem, para que você possa especificar o valor total dos encargos. No entanto, nesse caso, o encargo deve ser alocado para cada linha antes que a ordem possa ser confirmada. Você pode usar a ação **Alocar encargos** para dividir os valores de encargos atribuídos no nível do cabeçalho para as linhas da ordem. Encargos podem ser divididos de acordo com o valor líquido de cada linha, de acordo com a quantidade que foi encomendada ou uniformemente entre as linhas da ordem. Depois que você tiver alocado encargos para as linhas, o encargo será removido do cabeçalho da ordem.  

POs podem ser configurados para exigir que fundos de orçamento sejam alocados para a ordem antes que possa ser processado. Nesse caso, você pode usar a ação **Verificação de orçamento** para alocar o orçamento.  

Talvez seja necessário atrasar a conclusão de uma ordem de compra. Por exemplo, você pode requerer informações adicionais sobre produtos ou serviços, ou talvez você precise obter autorização para o gasto. Há várias maneiras de reter um pedido. Por exemplo, você pode esperar para confirmar a ordem. Como alternativa, se estiver sendo usado um fluxo de trabalho de gerenciamento de alterações, não envie o pedido de aprovação. Se você deve bloquear todos os pedidos para um determinado fornecedor, você também pode marcar o fornecedor como **Em espera** para processamento no mestre de fornecedor. Também há circunstâncias que podem impedir que o pedido esteja sendo processado. Por exemplo, o processamento poderá ser impedido se foram excedidos os limites de crédito ou se for necessário fundos de orçamento que não estão disponíveis.

<a name="see-also"></a>Consulte também
--------

[Visão geral de ordem de compra](purchase-order-overview.md)

[Confirmação e aprovação da ordem de compra](purchase-order-approval-confirmation.md)

[Recebimento de produtos contra ordens de compra](product-receipt-against-purchase-orders.md)

[Visão geral de faturas de fornecedor](/dynamics365/unified-operations/financials/accounts-payable/vendor-invoices-overview)




