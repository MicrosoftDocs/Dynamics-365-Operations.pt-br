---
title: O reembolso em uma ordem de devolução foi recusado
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando um reembolso em uma ordem de devolução é recusado porque o cartão de crédito usado para faturamento difere do cartão usado durante a autorização do pagamento original.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585201"
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
