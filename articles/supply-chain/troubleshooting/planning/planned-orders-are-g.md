---
title: O planejamento principal gera pedidos planejados para produtos fantasmas
description: Pedidos planejados são gerados para produtos fantasmas depois que o planejamento principal é executado.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026276"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="6eb32-103">O planejamento principal gera pedidos planejados para produtos fantasmas</span><span class="sxs-lookup"><span data-stu-id="6eb32-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="6eb32-104">Número da base de dados de conhecimento: 4614729</span><span class="sxs-lookup"><span data-stu-id="6eb32-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="6eb32-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="6eb32-105">Symptoms</span></span>

<span data-ttu-id="6eb32-106">Pedidos planejados são gerados para produtos fantasmas depois que o planejamento principal é executado.</span><span class="sxs-lookup"><span data-stu-id="6eb32-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="6eb32-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="6eb32-107">Resolution</span></span>

<span data-ttu-id="6eb32-108">A configuração da opção **Fantasma** para produtos liberados determina o tipo de linha padrão na lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="6eb32-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="6eb32-109">Quando a opção **Fantasma** for definida como *Sim*, o sistema ainda criará pedidos planejados para o item, mas a opção **Requisito derivado diretamente** para cada pedido planejado será definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="6eb32-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="6eb32-110">Portanto, o pedido de produção planejado não pode ser realizado por si só.</span><span class="sxs-lookup"><span data-stu-id="6eb32-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="6eb32-111">Em vez disso, ele sempre será incluído automaticamente quando o pedido de produto principal for firmado.</span><span class="sxs-lookup"><span data-stu-id="6eb32-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="6eb32-112">Além disso, as linhas da BOM do pedido fantasma planejado serão incluídas na BOM do pedido de produção principal.</span><span class="sxs-lookup"><span data-stu-id="6eb32-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
