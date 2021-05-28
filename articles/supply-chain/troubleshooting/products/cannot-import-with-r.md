---
title: Não é possível importar um item usando a entidade de Produtos liberados V2
description: Não é possível importar um item usando a entidade de Produtos liberados V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026261"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="0bb26-103">Não é possível importar um item usando a entidade de Produtos liberados V2</span><span class="sxs-lookup"><span data-stu-id="0bb26-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="0bb26-104">Número de KB: 4611825</span><span class="sxs-lookup"><span data-stu-id="0bb26-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="0bb26-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="0bb26-105">Symptoms</span></span>

<span data-ttu-id="0bb26-106">Ao tentar importar um item usando a entidade *Produtos liberados V2*, você receberá uma mensagem de erro semelhante ao seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bb26-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="0bb26-107">Não é possível criar um registro em Itens - grupos de dimensão de rastreamento (EcoResTrackingDimensionGroupItem).</span><span class="sxs-lookup"><span data-stu-id="0bb26-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="0bb26-108">Número do item: 2040663, Lote.</span><span class="sxs-lookup"><span data-stu-id="0bb26-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="0bb26-109">O registro já existe.</span><span class="sxs-lookup"><span data-stu-id="0bb26-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="0bb26-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="0bb26-110">Resolution</span></span>

<span data-ttu-id="0bb26-111">Para importar novos produtos liberados, você deve usar a entidade *Criação de produto liberado V2*, em vez da entidade *Produtos liberados V2*.</span><span class="sxs-lookup"><span data-stu-id="0bb26-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
