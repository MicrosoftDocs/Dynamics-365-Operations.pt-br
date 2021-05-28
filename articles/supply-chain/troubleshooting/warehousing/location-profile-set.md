---
title: O perfil de local desabilita inventário negativo, mas o inventário em mãos negativo é permitido
description: A opção Permitir inventário negativo para o perfil de local é definida como Não, mas o sistema ainda permite inventário em mãos negativo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026267"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="f2e42-103">O perfil de local desabilita inventário negativo, mas o inventário em mãos negativo é permitido</span><span class="sxs-lookup"><span data-stu-id="f2e42-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="f2e42-104">Número da base de dados de conhecimento: 4613622</span><span class="sxs-lookup"><span data-stu-id="f2e42-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="f2e42-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="f2e42-105">Symptoms</span></span>

<span data-ttu-id="f2e42-106">A opção **Permitir inventário negativo** para o perfil de local é definida como *Não*, mas o sistema ainda permite inventário em mãos negativo.</span><span class="sxs-lookup"><span data-stu-id="f2e42-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f2e42-107">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="f2e42-107">Example scenario</span></span>

<span data-ttu-id="f2e42-108">Para transações regulamentadas pelo governo, o sistema deve ser capaz de registrar inventário negativo para registrar perdas.</span><span class="sxs-lookup"><span data-stu-id="f2e42-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="f2e42-109">Você quer que um item seja capaz de mostrar inventário negativo, mas somente em locais designados, como tanques.</span><span class="sxs-lookup"><span data-stu-id="f2e42-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="f2e42-110">No entanto, se o grupo de modelo do item permitir inventário negativo, você verá que não importa se o local está definido para permitir inventário negativo.</span><span class="sxs-lookup"><span data-stu-id="f2e42-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="f2e42-111">Se o item estiver configurado para não permitir inventário negativo, não importa como o perfil de local está configurado.</span><span class="sxs-lookup"><span data-stu-id="f2e42-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="f2e42-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="f2e42-112">Resolution</span></span>

<span data-ttu-id="f2e42-113">A configuração **Permitir inventário negativo** no perfil de local aplica-se somente a processos de armazém, como retirada.</span><span class="sxs-lookup"><span data-stu-id="f2e42-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="f2e42-114">No entanto, os grupos de modelo de item que são definidos para permitir inventário negativo afetam todos os processos dos módulos Gerenciamento de inventário e Gerenciamento de armazém, e o perfil de local não substituirá essa configuração.</span><span class="sxs-lookup"><span data-stu-id="f2e42-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="f2e42-115">Você pode controlar se um armazém tem permissão para realizar inventário negativo.</span><span class="sxs-lookup"><span data-stu-id="f2e42-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="f2e42-116">Defina seus grupos de modelo de item para não permitir inventário físico negativo e defina somente o armazém relevante para permitir inventário negativo.</span><span class="sxs-lookup"><span data-stu-id="f2e42-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
