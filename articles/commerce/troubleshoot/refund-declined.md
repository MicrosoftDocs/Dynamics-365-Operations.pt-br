---
title: O reembolso em uma ordem de devolução foi recusado
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando um reembolso em uma ordem de devolução é recusado porque o cartão de crédito usado para faturamento difere do cartão usado durante a autorização do pagamento original.
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
ms.openlocfilehash: 99fd4b816b1a3a1fe3c2d1579be45b43fdc3d385
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020747"
---
# <a name="refund-on-a-return-order-is-declined"></a>O reembolso em uma ordem de devolução foi recusado

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando um reembolso em uma ordem de devolução é recusado porque o cartão de crédito usado para faturamento difere do cartão usado durante a autorização do pagamento original.

## <a name="description"></a>descrição

Um reembolso é recusado quando o cartão de crédito usado para faturar uma ordem de devolução difere do cartão usado durante a autorização do pagamento original. A seguinte mensagem de erro é exibida: "Alguns pagamentos não estão no status correto para lançamento. Valide novamente o status de todos os pagamentos antes de faturar."

Os detalhes de autorização de pagamento incluirão a seguinte mensagem de erro: "Falha no gateway SendRequest() de Adyen com o status 'InternalServerError'.22144; Resposta vazia retornada de Adyen.(22001);"

![Erro de reembolso recusado em uma ordem de devolução](media/refund-order-decline.jpg)

## <a name="resolution"></a>Resolução

### <a name="enable-blind-returns-in-adyen"></a>Habilitar devoluções cegas no Adyen

Para habilitar as devoluções cegas, siga as etapas em [Solucionar problemas do Conector de Pagamento do Dynamics 365 para problemas de Adyen](adyen-support.md) para contatar a equipe de suporte Adyen e solicitar que as devoluções cegas sejam habilitadas na sua conta de comerciante Adyen.

## <a name="additional-resources"></a>Recursos adicionais

[Conector de Pagamento do Dynamics 365 para Adyen](../dev-itpro/adyen-connector.md)

[Configurar o conector de pagamento da Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
