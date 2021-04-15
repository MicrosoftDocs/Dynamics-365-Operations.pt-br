---
title: Local de saída de produção
description: Este tópico descreve a hierarquia usada para identificar o local de saída de produção.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 48b68c36718fa42b7f80e3ffe1f54b7efbbee8bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814623"
---
# <a name="production-output-location"></a><span data-ttu-id="b0aa9-103">Local de saída de produção</span><span class="sxs-lookup"><span data-stu-id="b0aa9-103">Production output location</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0aa9-104">Este tópico descreve a hierarquia usada para identificar o local de saída de produção.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="b0aa9-105">O local de saída de produção é o primeiro local onde uma mercadoria concluída é armazenada depois de produzida.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="b0aa9-106">Geralmente, esse local é próximo ao processo de produção que gera a mercadoria concluída.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="b0aa9-107">O local de saída de produção é usado como armazenamento intermediário do material antes que ele seja movido para a área de remessa, um local de armazenamento, um local de entrada de produção para um processo de produção downstream e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="b0aa9-108">Um local de saída de produção padrão é definido quando as mercadorias concluídas são relatadas em uma ordem de produção ou em uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="b0aa9-109">A hierarquia a seguir é usada para identificar este local de saída:</span><span class="sxs-lookup"><span data-stu-id="b0aa9-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="b0aa9-110">Use o local de saída definido no cabeçalho da ordem de produção ou da ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="b0aa9-111">Se não houver um local ali, use o local de saída definido no recurso usado pela última operação definida no roteiro de produção.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="b0aa9-112">Se não houver um local ali, use o local de saída definido no grupo de recursos usado pelo recurso na última operação definida no roteiro de produção.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="b0aa9-113">Se não houver uma localização ali, use o local de saída definido no depósito definido na ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="b0aa9-114">Um local de saída de produção padrão é definido apenas para os produtos configurados usando os processos avançados de depósito.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="b0aa9-115">Quando esse tipo de item for relatado como concluída, será criado o trabalho de depósito do tipo **Mercadorias concluídas armazenadas** ou **Co-produto e subproduto armazenados**.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="b0aa9-116">Esse tipo de trabalho usa o local de saída de produção como o local de separação.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="b0aa9-117">O local de armazenamento é determinado pelas diretivas de local.</span><span class="sxs-lookup"><span data-stu-id="b0aa9-117">The put-away location is determined by the location directives.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]