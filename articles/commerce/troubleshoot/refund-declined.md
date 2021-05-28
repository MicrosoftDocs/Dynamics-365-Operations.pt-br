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
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="9721f-103">O reembolso em uma ordem de devolução foi recusado</span><span class="sxs-lookup"><span data-stu-id="9721f-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9721f-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando um reembolso em uma ordem de devolução é recusado porque o cartão de crédito usado para faturamento difere do cartão usado durante a autorização do pagamento original.</span><span class="sxs-lookup"><span data-stu-id="9721f-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="9721f-105">descrição</span><span class="sxs-lookup"><span data-stu-id="9721f-105">Description</span></span>

<span data-ttu-id="9721f-106">Um reembolso é recusado quando o cartão de crédito usado para faturar uma ordem de devolução difere do cartão usado durante a autorização do pagamento original.</span><span class="sxs-lookup"><span data-stu-id="9721f-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="9721f-107">A seguinte mensagem de erro é exibida: "Alguns pagamentos não estão no status correto para lançamento.</span><span class="sxs-lookup"><span data-stu-id="9721f-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="9721f-108">Valide novamente o status de todos os pagamentos antes de faturar."</span><span class="sxs-lookup"><span data-stu-id="9721f-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="9721f-109">Os detalhes de autorização de pagamento incluirão a seguinte mensagem de erro: "Falha no gateway SendRequest() de Adyen com o status 'InternalServerError'.22144; Resposta vazia retornada de Adyen.(22001);"</span><span class="sxs-lookup"><span data-stu-id="9721f-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Erro de reembolso recusado em uma ordem de devolução](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="9721f-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="9721f-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="9721f-112">Habilitar devoluções cegas no Adyen</span><span class="sxs-lookup"><span data-stu-id="9721f-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="9721f-113">Para habilitar as devoluções cegas, siga as etapas em [Solucionar problemas do Conector de Pagamento do Dynamics 365 para problemas de Adyen](adyen-support.md) para contatar a equipe de suporte Adyen e solicitar que as devoluções cegas sejam habilitadas na sua conta de comerciante Adyen.</span><span class="sxs-lookup"><span data-stu-id="9721f-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9721f-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9721f-114">Additional resources</span></span>

[<span data-ttu-id="9721f-115">Conector de Pagamento do Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="9721f-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="9721f-116">Configurar o conector de pagamento da Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9721f-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
