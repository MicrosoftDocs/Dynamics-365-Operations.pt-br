---
title: Disponibilidade de estoque em gravação dupla
description: Este tópico fornece informações sobre a disponibilidade de verificação de estoque em gravação dupla.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426973"
---
# <a name="inventory-availability"></a>Disponibilidade de estoque

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto aos formulários **Cotações**, **Ordens** ou **Faturas** em aplicativos baseados em modelo no Dynamics 365. Por exemplo, a verificação de estoque e a determinação de uma data de atendimento é uma tarefa fundamental no [processo de pagamento à vista](dual-write-prospect-to-cash.md). Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado. Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.

## <a name="on-hand-inventory"></a>Estoque disponível 

No cabeçalho dos formulários **Cotações**, **Ordens** ou **Faturas** no Dynamics 365 Sales, foi adicionado um novo botão **Estoque disponível**. Quando você clica no botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível. Ele retorna as informações de estoque do Dynamics 365 Supply Chain Management e mostra as mesmas informações do [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md). As informações incluem estas quantidades:

- **Quantidade Disponível**
- **Quantidade Disponível Reservada**
- **Quantidade Disponível**
- **Quantidade da Ordem**
- **Quantidade na Ordem**
- **Quantidade Encomendada Reservada**
- **Quantidade Disponível Total**

## <a name="atp-information"></a>Informações sobre ATP

Em itens de linha dos formulários **Cotações**, **Ordens** ou **Faturas** no Dynamics 365 Sales, foi adicionado um novo botão **Informações ATP**. Quando você clica no botão, uma caixa de diálogo é exibida e você pode especificar a empresa, produto, site do estoque, depósito de estoque e quantidade da ordem. Ele retorna as **informações ATP** do Supply Chain Management e mostra as configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). As informações incluem a **Quantidade ATP**, a **Quantidade de recebimento**, **Quantidade de saída** e **Quantidade disponível**.
