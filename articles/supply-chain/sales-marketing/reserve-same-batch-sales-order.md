---
title: Reservar o mesmo lote para uma ordem de venda
description: Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fb1f9e017de71d01fbf7a05b579d68b702aa7c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001490"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reservar o mesmo lote para uma ordem de venda

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque.

A reserva de mesmo lote permite reservar estoque para uma linha de ordem de venda para um único lote de estoque. Por exemplo, um cliente que encomende papel de parede pode solicitar que a ordem inteira seja atendida pelo mesmo lote a fim de evitar diferenças entre os rolos. Para configurar um produto para usar a mesma reserva de lote, as configurações a seguir devem estar ativas no grupo de modelos de item, no grupo de dimensões de rastreamento e no grupo de dimensões de armazenamento atribuídos ao produto:

- **Grupos de modelos de itens** – o grupo de modelos de itens deve ter os campos **Seleção de mesmo lote** e **Consolidar necessidade** selecionados no grupo de campos **Reserva** para políticas de estoque.
- **Grupos de dimensões de rastreamento** – o grupo de dimensões de rastreamento deve ter o campo **Plano de cobertura por dimensão** selecionado para o número do lote.
- **Grupos de dimensões de armazenamento** – o grupo de dimensões de armazenamento deve ter o campo **Plano de cobertura por dimensão** selecionado para **Local** e **Depósito**.

Ao reservar estoque para um produto em uma linha da ordem de venda configurada para a seleção de mesmo lote, o sistema tenta reservar a quantidade encomendada em um único lote de estoque. Qualquer requisito específico do atributo de lote também será considerado. Se a quantidade não puder ser preenchida de um único lote, a página **Conflito de reserva de mesmo lote** será exibida. Essa página descreve os problemas e também as ações que você pode executar para proceder com a reserva. As seguintes condições podem impedir que o lote seja reservado:

- O código de disposição do lote tem **Bloquear reserva** da venda sinalizado como **Bloqueado**.
- O lote expirou com base na data de vencimento e nos dias comercializáveis aplicáveis do cliente. O item ainda poderá ser considerado para reserva se o grupo de modelos de item for controlado pela data FEFO (primeiro a vencer, primeiro a sair) e se a data de validade for selecionada como critério de separação.
- O lote não tem dias restantes de validade suficientes com base na data de vencimento e na data de validade, mais os dias comercializáveis do cliente.

Para itens associados a um grupo de dimensões de armazenamento com **Usar processos de gerenciamento de depósito** habilitado, é possível reservar números de lote específicos usando uma hierarquia de reserva com a dimensão de estoque de número de lote definida acima da dimensão de localização. A página **Reserva de lote** para linhas de ordem de venda e transferência também permite selecionar e reservar várias linhas com base nos números de lote disponíveis. Para obter mais informações sobre o que fazer se você estiver usando uma hierarquia de reserva que tenha a dimensão do número do lote abaixo do local, consulte [Política flexível de reserva de dimensão no nível de depósito](../warehousing/flexible-warehouse-level-dimension-reservation.md).
