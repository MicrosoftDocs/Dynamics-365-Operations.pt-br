---
title: Os pagamentos são automaticamente liquidados antes que as ordens sejam faturadas ou remetidas
description: Este artigo fornece orientação de solução de problemas que pode ser útil quando um pagamento é liquidado no portal Adyen imediatamente após uma ordem ser feita, mesmo que a ordem de venda não tenha sido faturada nem remetida.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c01a2fda54e198a43fa84ae83686fc1701958b6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890260"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Os pagamentos são automaticamente liquidados antes que as ordens sejam faturadas ou remetidas

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientação de solução de problemas que pode ser útil quando um pagamento é liquidado no portal Adyen imediatamente após uma ordem ser feita, mesmo que a ordem de venda não tenha sido faturada nem remetida.

## <a name="description"></a>descrição

Depois que uma ordem é colocada, o pagamento é imediatamente liquidado no portal Adyen, mesmo que a ordem de venda não tenha sido faturada nem remetida.

## <a name="resolution"></a>Resolução

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Configurar a captura manual de pagamentos de comércio eletrônico no portal de Adyen

Para configurar a captura manual de pagamentos de comércio eletrônico no portal de Adyen, siga estas etapas.

1. Entre no portal de Adyen.
1. No canto superior direito, selecione sua conta de comerciante para o canal de comércio eletrônico.
1. Na barra de navegação superior, selecione **Conta** e depois **Configurações**.
1. No campo **Atraso da Captura**, selecione **manual**.

    ![Configuração do Atraso de Captura no portal de Adyen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Recursos adicionais

[Captura de pagamento de Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector.md)

[Configurar o conector de pagamento da Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
