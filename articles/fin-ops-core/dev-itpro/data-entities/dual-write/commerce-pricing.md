---
title: Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales
description: Este tópico descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: 364cc5adf0358ffa952750149ad31d62cbd35e87
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751425"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="ca492-103">Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="ca492-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca492-104">Este tópico descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ca492-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="ca492-105">O mecanismo de definição de preços do Dynamics 365 Commerce oferece suporte à maioria dos cenários de precificação de business-to-consumer (B2C), como definição de preços no nível de armazenamento, definição de preços com base em fidelidade e afiliação, descontos de compra combinada, descontos de quantidade e descontos de limite.</span><span class="sxs-lookup"><span data-stu-id="ca492-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="ca492-106">O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem.</span><span class="sxs-lookup"><span data-stu-id="ca492-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="ca492-107">Ao usar a [gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), você tem três opções para as necessidades de definição de preços.</span><span class="sxs-lookup"><span data-stu-id="ca492-107">When you use [dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), you have three options for your pricing needs.</span></span> <span data-ttu-id="ca492-108">Você pode usar a precificação estática que vem da lista de preços no Dynamics 365 Sales, o mecanismo de precificação no Dynamics 365 Supply Chain Management ou o mecanismo de precificação no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca492-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ca492-109">Entre essas opções, o mecanismo de precificação comercial é mais adequado para os cenários B2C.</span><span class="sxs-lookup"><span data-stu-id="ca492-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="ca492-110">Usar o mecanismo de precificação comercial em Vendas</span><span class="sxs-lookup"><span data-stu-id="ca492-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="ca492-111">No momento, o mecanismo de precificação comercial pode ser usado somente para a criação de cotações nas Vendas.</span><span class="sxs-lookup"><span data-stu-id="ca492-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="ca492-112">A integração da ordem de venda com o mecanismo de precificação comercial ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ca492-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="ca492-113">Quando os usuários iniciarem uma cotação nas Vendas, a estrutura de gravação dupla copiará os detalhes da cotação para o Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca492-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="ca492-114">As alterações nas linhas de cotação existentes ou em quaisquer linhas de cotação adicionadas recentemente nas vendas são copiadas para o Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca492-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="ca492-115">Quando os usuários desejarem usar o mecanismo de precificação do Commerce para calcular o preço da cotação, eles poderão selecionar **Cotação de preços** para atualizar os preços da cotação, com base no mecanismo de precificação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca492-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="ca492-116">Os preços são atualizados automaticamente no Sales and Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca492-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca492-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ca492-117">Prerequisites</span></span>

- <span data-ttu-id="ca492-118">Antes de usar o mecanismo de precificação do Commerce no Sales, você deve seguir as etapas do [Cliente potencial com pagamento à vista em gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span><span class="sxs-lookup"><span data-stu-id="ca492-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span></span>
- <span data-ttu-id="ca492-119">Você deve desativar a avaliação do contrato comercial para a entrada manual seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ca492-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="ca492-120">No ambiente do Commerce, vá para **Contas a receber \> Configuração \> parâmetros de Contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="ca492-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="ca492-121">Na guia **Preços**, na guia rápida **Avaliação de contrato comercial**, desmarque a caixa de seleção **Entrada manual**.</span><span class="sxs-lookup"><span data-stu-id="ca492-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca492-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ca492-122">Additional resources</span></span>

[<span data-ttu-id="ca492-123">Cliente potencial com pagamento à vista em gravação dupla</span><span class="sxs-lookup"><span data-stu-id="ca492-123">Prospect-to-cash in dual-write</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]