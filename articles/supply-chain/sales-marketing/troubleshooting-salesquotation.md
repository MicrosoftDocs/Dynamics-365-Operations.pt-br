---
title: Solucionar problemas de cotações de venda
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 09529ba729170be7281e2ae04008d3ba4a58e060
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824741"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="32375-103">Solucionar problemas de cotações de venda</span><span class="sxs-lookup"><span data-stu-id="32375-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="32375-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.</span><span class="sxs-lookup"><span data-stu-id="32375-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="32375-105">Não consigo alterar a quantidade de venda de uma cotação de venda para um item de serviço.</span><span class="sxs-lookup"><span data-stu-id="32375-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="32375-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="32375-106">Issue description</span></span>

<span data-ttu-id="32375-107">Se você tentar definir uma quantidade de venda (**campo SalesQty**) para um item do tipo *Serviço* em uma linha da cotação de venda, você receberá a seguinte mensagem: "Atualização não permitida para o campo Quantidade".</span><span class="sxs-lookup"><span data-stu-id="32375-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="32375-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="32375-108">Issue resolution</span></span>

<span data-ttu-id="32375-109">Não é possível definir uma quantidade de venda para produtos que são itens de serviço.</span><span class="sxs-lookup"><span data-stu-id="32375-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="32375-110">Por exemplo, se você oferece um serviço para instalar um item, não faz sentido registrar uma quantidade porque não há um item físico.</span><span class="sxs-lookup"><span data-stu-id="32375-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="32375-111">Há apenas um serviço.</span><span class="sxs-lookup"><span data-stu-id="32375-111">There is only a service.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]