---
title: Ativos de entrada e saída
description: Este tópico explica como registrar ativos de entrada e saída em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a7239bf5f8e53e61c4259abbcbf2ff740f4cef55
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422242"
---
# <a name="inbound-and-outbound-assets"></a>Ativos de entrada e saída

[!include [banner](../../includes/banner.md)]

 

Se a empresa faz trabalhos de reparo ou trabalhos de manutenção em ativos que são recebidos de outros locais ou clientes, o Gerenciamento de Ativos pode rastrear ativos de entrada que estão sendo enviados à sua empresa e ativos saída que estão sendo devolvidos.

> [!NOTE]
> Se quiser usar os estados do ciclo de vida de entrada e saída para gerenciar ativos recebidos e devolvidos, configure os estados do ciclo de vida de solicitação de manutenção e os modelos de ciclo de vida para dar suporte a essas ações. Para obter mais informações, consulte [Solicitações de manutenção](../setup-for-maintenance-requests/requests.md).

A configuração do Gerenciamento de Ativos determina se você pode trabalhar com ativos de entrada e saída.

## <a name="register-assets-as-inbound"></a>Registre ativos como entrada

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Solicitações manutenção de ativos**.
2. Selecione a solicitação de manutenção.
3. Selecione **Atualizar estado de solicitação de manutenção**.
4. Selecione **Entrada** (ou outro estado do ciclo de vida que você criou para ativos de entrada) e **OK**.

![Registre ativos como entrada](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Registre ativos de entrada como recebido

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Entrada/saída** \> **Ativos de entrada**.
2. Selecione o ativo ou a solicitação de manutenção.
3. Selecione **Receber ativos**.
4. No campo **Recebido**, insira a data e a hora. Em seguida, selecione **OK**. O registro é removido da página de lista **Ativos de entrada**.

![Registre ativos de entrada como recebido](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Registre ativos como saída

Quando terminar o trabalho de manutenção ou de reparo, você pode registrar o ativo como devolvido.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Solicitações manutenção de ativos**.
2. Selecione a solicitação de manutenção.
3. Selecione **Atualizar estado de solicitação de manutenção**.
4. Selecione **Saída** (ou outro estado do ciclo de vida que você criou para ativos de saída) e **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Registre ativos de saída como entregue

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Entrada/saída** \> **Ativos de saída**.
2. Selecione o ativo ou a solicitação de manutenção.
3. Selecione **Entregar ativos**.
4. No campo **Entregue**, insira a data e a hora. Em seguida, selecione **OK**. O registro é removido da página de lista **Ativos de saída**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]