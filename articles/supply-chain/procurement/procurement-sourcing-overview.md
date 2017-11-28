---
title: "Visão geral de Compras"
description: "Este artigo oferece uma visão geral da funcionalidade que está disponível no módulo Aquisição e fornecimento."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0692518afc5c8b385773dad3c44dc4e3c978362b
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-and-sourcing-overview"></a>Visão geral de Compras

[!include[banner](../includes/banner.md)]


Este artigo oferece uma visão geral da funcionalidade que está disponível no módulo Aquisição e fornecimento.

A aquisição e o fornecimento abrangem todas as etapas, desde a identificação da necessidade de produtos e serviços até a aquisição do produto, o recebimento, o faturamento e o processamento do pagamento a fornecedores. Os processos de aquisição podem ser configurados de acordo com as necessidades dos negócios, por meio da definição de políticas e fluxos de trabalho.

## <a name="identifying-a-need-for-product-and-services"></a>Identificando a necessidade de produtos e serviços
A necessidade de produtos ou serviços pode ser decorrente de *requisições*, por exemplo, quando um funcionário requer um produto. Os *catálogos de produtos* podem ser configurados para orientar a seleção de produtos disponíveis, ou podem ser feitas solicitações de produtos que ainda não estão disponíveis no catálogo, permitindo ao departamento de compras considerar como o produto pode ser fornecido.  

Os *limites de gastos* podem ser utilizados para restringir os gastos da requisição e o *fluxo de trabalho de compras* inclui a opção de exigir aprovação antes que ocorra um pedido. Também é possível especificar a alocação de fundos de orçamento, se necessário.  
  
O departamento de aquisição identifica fornecedores para produtos e serviços necessários, e isso pode envolver o envio de uma *solicitação de cotação* a vários fornecedores potenciais. É possível compartilhar as especificações do produto que está sendo solicitado, e os fornecedores potenciais podem verificar se são capazes de fornecer um produto em conformidade com as especificações. Os fornecedores fazem as ofertas, que são analisadas pelo departamento de compras antes que eles escolham de qual fornecedor desejam comprar.  

As ordens de compra incluem uma opção para enviar uma *consulta de compra* ao fornecedor como uma alternativa para um processo de solicitação de cotação mais abrangente. A consulta de compra pode ser usada para estabelecer condições como preços, descontos e data de entrega do pedido. Se os fornecedores forem configurados para usar o portal do **Fornecedor**, a funcionalidade de consulta de compra será desabilitada. Em vez disso, a ordem é compartilhada no portal do**Fornecedor** e, quando uma *solicitação de confirmação* é enviada, o fornecedor pode confirmar diretamente o pedido.  

Os *catálogos do fornecedor* podem ser usados para coletar informações sobre a variedade de produtos que os fornecedores podem prover. Os fornecedores podem publicar seus próprios catálogos, tornando-os mais fácil de serem atualizados. É possível anexar uma *lista de fornecedores aprovados* a um produto. Isso pode ajudar a orientar a seleção de fornecedores quando novas ordens de compra forem abertas e evitar o uso de fornecedores não desejados.

## <a name="procurement"></a>Compras
As *ordens de compra* podem ser criadas de diversas maneiras:

-   Como um resultado de planejamento mestre que identificou uma demanda exigisse que uma compra. Este processo gera ordens de compra planejadas e, quando eles são liberados, ordens de compra são geradas.
-   Pelo processamento de requisições de compra que resultam em aquisições.
-   Pelo processamento de contratos de compra, nos quais as ordens de compra são criadas como ordens liberadas dos contratos. Isso é comumente usado quando os contratos de compra são utilizados para representar ordens amplas.
-   Manualmente, quando a ordem de compra criada não está baseada em outro documento.

As ordens de compra configuradas com *fluxos de trabalho de aprovação de compra* exigem aprovação para que sejam registradas como aprovadas; isso é necessário para que a ordem possa ser processada posteriormente.  

As ordens de compra são *confirmadas* para representar que um contrato foi estabelecido com o fornecedor. A ordem de compra, então, avançará gradualmente pelos diferentes estágios até ser finalmente faturada ou cancelada.  

Quando você cria uma ordem de compra, muitos dos campos são previamente preenchidos com valores baseados, por padrão, nas informações do fornecedor armazenadas na página **Fornecedores**. Isso significa que há um número limitado de campos que você precisa preencher na ordem de compra, embora você tenha a opção de substituir os valores padrão.

### <a name="prices-and-discounts"></a>Preços e descontos

Os preços e descontos incluem informações sobre preços, descontos e as condições de reembolso que eles oferecem. Os preços e os descontos podem ser representados como *contratos* *comerciais*. Os contratos comerciais representam listas de preços de fornecedor com preços ou descontos e têm um conjunto de datas específico para o qual o contrato é válido. Os preços e descontos podem ser negociados e representados em *contratos de compra* com condições como compromisso de compra de volumes ou valores monetários específicos como uma precondição para os termos negociados. Os *contratos de reembolso* podem ser criados com os fornecedores, quando a aquisição de produtos ou grupos de produtos podem acionar um reembolso do fornecedor, dependendo do valor ou do volume da compra.

### <a name="delivery-options"></a>Opções de entrega

Há opções diferentes para o processo de entrega associado a uma ordem de compra. Os produtos encomendados podem ser divididos em agendas de *entrega*, em que as partes da quantidade encomendada podem ser planejadas para entrega em datas diferentes. A entrega também pode incluir *entrega direta* iniciada a partir de uma ordem de venda, o que automatiza a geração da guia de remessa na ordem de venda ao mesmo tempo em que o recebimento de produtos é registrado na ordem de compra. As ordens de compra também podem ser parte de uma cadeia de *ordem intercompanhia*, também conhecida como ordens de compra intercompanhia, em que os produtos são solicitados a partir de uma ordem de venda intercompanhia correspondente. Nesse caso, algumas etapas são automatizadas entre as duas ordens intercompanhia relacionadas.

### <a name="supplementary-items"></a>Itens suplementares

Os produtos podem ser configurados para incluir *itens suplementares*. Isso tem como objetivo propor produtos relacionados ao produto que está sendo solicitado. Os produtos adicionais podem ser obrigatórios ou opcionais. Em alguns casos, os itens suplementares podem ser adicionados como produtos gratuitos que acompanham a compra de outros produtos.

### <a name="purchase-order-charges"></a>Encargos da ordem de compra

Os encargos podem ser atribuídos à ordem de compra. Isso pode ocorrer automaticamente por meio da configuração de encargos automáticos ou da adição manual dos encargos. Os encargos podem ser atribuídos à ordem no nível do cabeçalho ou no nível da linha da ordem. A contabilização de encargos pode ser configurada de diversas maneiras. Por exemplo, você pode configurar um encargo para ser contabilizado como um custo de produto. Se você fizer isso, os encargos deverão ser atribuídos no nível da linha da ordem para que a ordem possa ser confirmada. Existe uma opção para alocar os encargos do cabeçalho da ordem para as linhas.

## <a name="product-receipt-and-invoicing"></a>Recebimento e faturamento de produtos
As ordens de compra que incluem produtos físicos normalmente exigem um *registro de entrada* para entrarem em um depósito. Em seguida, um *recebimento de produto* é registrado para a ordem. As ordens de compra com produtos que preenchem requisições podem ser configuradas para que o funcionário que solicitou os produtos também precise fornecer uma *confirmação de recebimento*.  

Algumas ordens de compra incluem produtos que são serviços ou outros produtos não físicos, quando o recebimento em depósito não é necessário. Produtos podem ser criados como serviços ou as *categorias de aquisição* podem ser usadas diretamente na ordem de compra dessas ordens. Com essas ordens, a contabilidade do recebimento de produtos é ignorada algumas vezes, e a ordem é faturada diretamente. Alternativamente, o registro de recebimento de produto é feito na ordem de compra sem nenhum registro anterior de entrada.  

O recebimento de produtos pode resultar em consumo automático para uma finalidade específica. Isso inclui consumo implícito com entrega direta, consumo para um projeto ou contabilização do produto como um ativo fixo.  

Quando as *faturas do fornecedor* chegam do fornecedor, elas podem ser registradas primeiramente no *registro de fatura*, independentemente da ordem de compra, e depois ser aprovadas como um registro com base na ordem de compra. O registro da fatura do fornecedor com a ordem de compra inclui a correspondência do recebimento de produto com a fatura.  

As *distribuições contábeis* podem ser especificadas na ordem de compra para descrever como a contabilidade deverá ser feita no razão e também podem definir como a alocação de fundos de orçamento será obtida quando for incluída na configuração.  

As ordens de compra faturadas registrarão o passivo na conta do fornecedor em contas a pagar, no qual o *paga**mento do fornecedor* pode ser processado.

## <a name="vendor-performance"></a>Desempenho do fornecedor
O suporte ao desempenho e à revisão da compra é feito por meio de *relatórios de aquisição e contas a pagar,* que inclui a análise de gastos e a análise de desempenho do fornecedor.




