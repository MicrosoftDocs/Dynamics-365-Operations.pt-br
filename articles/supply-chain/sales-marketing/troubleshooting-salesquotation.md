---
title: Solucionar problemas de cotações de venda
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834313"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="1251b-103">Solucionar problemas de cotações de venda</span><span class="sxs-lookup"><span data-stu-id="1251b-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="1251b-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.</span><span class="sxs-lookup"><span data-stu-id="1251b-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="1251b-105">Não consigo alterar a quantidade de venda de uma cotação de venda para um item de serviço.</span><span class="sxs-lookup"><span data-stu-id="1251b-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1251b-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="1251b-106">Issue description</span></span>

<span data-ttu-id="1251b-107">Se você tentar definir uma quantidade de venda (**campo SalesQty**) para um item do tipo *Serviço* em uma linha da cotação de venda, você receberá a seguinte mensagem: "Atualização não permitida para o campo Quantidade".</span><span class="sxs-lookup"><span data-stu-id="1251b-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1251b-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="1251b-108">Issue resolution</span></span>

<span data-ttu-id="1251b-109">Não é possível definir uma quantidade de venda para produtos que são itens de serviço.</span><span class="sxs-lookup"><span data-stu-id="1251b-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="1251b-110">Por exemplo, se você oferece um serviço para instalar um item, não faz sentido registrar uma quantidade porque não há um item físico.</span><span class="sxs-lookup"><span data-stu-id="1251b-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="1251b-111">Há apenas um serviço.</span><span class="sxs-lookup"><span data-stu-id="1251b-111">There is only a service.</span></span>

