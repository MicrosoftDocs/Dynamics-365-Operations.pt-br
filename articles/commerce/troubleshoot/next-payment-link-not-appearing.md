---
title: A opção Salvar para o próximo pagamento não aparece
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção Salvar para o próximo pagamento não aparecer no método de pagamento na página de finalização de compra de um site de comércio eletrônico.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018425"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="8f471-103">A opção "Salvar para o próximo pagamento" não aparece</span><span class="sxs-lookup"><span data-stu-id="8f471-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8f471-104">Este tópico fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção **Salvar para o próximo pagamento** não aparecer no **Método de pagamento** na página de finalização de compra de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8f471-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="8f471-105">descrição</span><span class="sxs-lookup"><span data-stu-id="8f471-105">Description</span></span>

<span data-ttu-id="8f471-106">A caixa de seleção **Salvar para o próximo pagamento** não aparece na seção **Método de pagamento** em uma página de finalização de compra de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8f471-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="8f471-107">A ilustração a seguir mostra um exemplo de uma página de finalização de compra que inclui a caixa de seleção **Salvar para meu próximo pagamento**.</span><span class="sxs-lookup"><span data-stu-id="8f471-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Caixa de seleção Salvar para meu próximo pagamento no módulo de Pagamento](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="8f471-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="8f471-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="8f471-110">Verifique se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="8f471-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="8f471-111">Para verificar se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8f471-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8f471-112">Vá para **Varejo e Comércio \> Canais \> Lojas Online**.</span><span class="sxs-lookup"><span data-stu-id="8f471-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="8f471-113">Selecione a loja online.</span><span class="sxs-lookup"><span data-stu-id="8f471-113">Select the online store.</span></span>
1. <span data-ttu-id="8f471-114">Na guia rápida **Contas de pagamento**, verifique se o campo **Permitir salvar informações de pagamento no comércio eletrônico** está definido como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="8f471-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Campo Permitir salvar informações de pagamento no comércio eletrônico na matriz do Commerce](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="8f471-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8f471-116">Additional resources</span></span>

[<span data-ttu-id="8f471-117">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="8f471-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="8f471-118">Salvando meios de pagamento online com o conector para Adyen</span><span class="sxs-lookup"><span data-stu-id="8f471-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
