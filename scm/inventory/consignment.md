---
title: "Consignação"
description: "Este tópico explica como usar os processos de estoque de entrada de consignação."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchVendorPortalConfirmedOrders
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: d9dcdd63649d6dbff96efe2eec7cad34025ab2ee
ms.lasthandoff: 03/31/2017


---

# <a name="consignment"></a>Consignação

Este tópico explica como usar os processos de estoque de entrada de consignação.

Estoque em consignação é o estoque a que pertence a um fornecedor, mas está armazenado em seu site. Quando estiver pronto para consumir ou usar o estoque, você obterá sobre a propriedade de estoque. Esse tópico contém informações sobre como recebidas fisicamente no estoque disponível de possuído sem criar transações de contabilização, como iniciar um processo de produção no estoque de possuído pode ser fisicamente reservado. e como alterar a propriedade de matérias-primas para processar o consumo como parte do processo de ordem de produção. Há também quaisquer informações sobre como monitorar fornecedores podem o consumo do estoque usando a interface de colaboração de fornecedor. Para obter informações sobre como habilitar e configurar processos de entrada de consignação, [Configuração de consignação](set-up-consignment.md).

## <a name="overview-of-the-consignment-process"></a>Visão geral do processo de consignação
Neste cenário de exemplo, a empresa USMF tem um acordo de consignação com fornecedores US-104 da matéria-prima M9211CI.

1.  Uma ordem de reabastecimento de consignação é criada manualmente por alguém em USMF, com base em demanda prevista. A ordem é criada para o fornecedor US-104 e uma linha será adicionada para o item MS9211CI.
2.  O fornecedor recebe informado sobre a entrega esperada. Isso pode ocorrer de três formas:
    -   Alguém que trabalha na USMF envia as informações da ordem ao fornecedor.
    -   O fornecedor pode monitorar o esperado estoque disponível usando a interface de colaboração de fornecedor.
    -   Alguém que trabalha na USMF filtra os dados na página **Estoque disponível** para mostrar apenas os registros do fornecedor US-104, cujo status de recebimento é **Encomendado**, e envia essa informação ao fornecedor.

3.  O estoque for entregue de US-104 a USMF.
4.  Quando o material em USMF chega, a ordem de reabastecimento de consignação é atualizada a um recebimento de produtos. Apenas as quantidades físicas de estoque de possuído são registradas. Nenhuma transação de contabilidade criadas, como inventários pertence ainda por fornecedor.
5.  As atualizações dos monitores de fornecedor para auditoria estoque disponível usando a página **Estoque em consignação disponível**.
6.  Agora que o estoque físico está disponível, o processo de produção o estoque de reserva possuído e iniciar a ordem de produção para mercadorias concluídas que estejam prestes a consumir a matéria-prima M9211CI.
7.  O proprietário de matérias-primas reservados que estejam prestes a ser consumidas em produção de hoje é alterado de US-104 a USMF. Isso é feito usando um diário de alteração de propriedade do estoque. Este processo criar ordens de compra a que **Origem** o campo foi definido **Consignação**.
8.  O fornecedor monitora o consumo (alteração de propriedade) na página **Bens recebidos de estoque de consignação** e emite uma fatura com base nos contratos entre as duas empresas.
9.  O processo de produção consume a matéria-prima via lista de separação da produção. A reserva física é atualizada automaticamente para refletir o estoque será possuído disponível por USMF.
10. A fatura de US-104 é processada em ordens de compra a que são gerados quando o diário da alteração de propriedade do estoque foi processado. O pagamento é feito ao fornecedor US-104 de estoque que foi consumido.

É USMF processos periódicos adicionais:

-   O movimento físico de estoque de possuído entre depósitos diferentes é processado usando um diário de transferência.
-   O estoque físico é atualizado disponível usando um diário** Contagem de item **. A contagem pode ser usada por fornecedor para atualizar o estoque disponível, se tiverem permissão para isso.

O fornecedor, US-104, pode monitorar as atualizações com a página **Estoque em consignação disponível**.

## <a name="consignment-replenishment-orders"></a>Ordens de reabastecimento de consignação
Uma ordem de reabastecimento de consignação é um documento utilizado para pedir e controlar de quantidades de produtos de um fornecedor tem entregue dentro de um determinado intervalo de datas criar transações de estoque encomendadas. Geralmente, isso será baseado na previsão e a demanda real de produto específico. O estoque que está prestes a ser recebida na ordem de reabastecimento de consignação restante a propriedade do fornecedor. Apenas uma posse de produto à atualização física do recebimento é registrada e portanto nenhuma atualização da transação da contabilização ocorre. A dimensão **Proprietário** usada para separar as informações sobre a qual a ação pertence por fornecedor e que pertence por entidade legal de recebimento. As linhas de ordem de reabastecimento de remessa têm ** ordem aberta ** status como a quantidade total das linhas não foi recebida ou não foi cancelada. Quando a quantidade total foi recebida ou cancelada, o status será alterado para concluído. ** ** O estoque físico disponível relacionado a uma ordem de reabastecimento de consignação pode ser registrado por meio de um processo de registro assim como um processo de atualização do recebimento de produtos. O registro pode ser criado como parte do processo de entrada de item manualmente ou atualizando as linhas. Quando o processo de atualização do recebimento de produtos é usado, é feito um registro no diário do recebimento de produtos, que pode ser usado para confirmar o recebimento de mercadorias a fornecedores. 

[remessa-reabastecimento- ordem![(]. /media/consignment-replenishment-order.png)](. /media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Diário de alteração de propriedade de estoque
O processo de alteração do proprietário do inventário do fornecedor para receber a entidade legal é feito usando um diário de alteração de proprietário de Estoque. Nenhuma transação de estoque foi criada para o diário. Apenas as transações de estoque criadas são aquelas relacionadas a um diário lançado. Onde o jornal foi lançado:

-   O estoque de possuído é emitido usando **Alteração de propriedade** uma referência com um status **Vendido**.
-   O estoque disponível é recebido pela entidade legal que o consome usando uma transação de estoque atualizada de recebimento de produto na ordem de compra. Isso define o status da ordem **Recebido**. Ordens de compra usada para a consignação tiver **Origem** definido ao campo **Consignação**.

Não é possível atualizar a quantidade nas linhas de ordem de consignação de compra depois que a ordem foi criada. 

[estoque-propriedade-alteração- diário do![(]. /media/inventory-ownership-change-journal.png)](. /media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Colaboração de fornecedor em processos de consignação
A interface de colaboração de fornecedor tiver três páginas relacionadas o processo de entrada de consignação:

-   ** Ordens de compra ** ** que consomem o estoque ** de remessa - ordem de compra detalhado mostra informações relacionadas à alteração de propriedade do processo de remessa.
-   **Bens recebidos de estoque de consignação** - Mostra informações sobre os itens e as quantidades que têm os recebimentos de produtos atualizados durante a propriedade alteram o processo.
-   **Estoque disponível de consignação** - Mostra informações sobre os itens de consignação que são esperadas, entregar e os itens que estão fisicamente disponíveis no site de cliente.



