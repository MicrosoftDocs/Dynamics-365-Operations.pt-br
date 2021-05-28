---
title: Não é possível atualizar o custo unitário previsto ao importar registros de previsão de demanda
description: Quando você usa entidades de dados para importar registros de previsão de demanda, o preço de custo para registros existentes não atualiza para que continue correspondendo aos dados importados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026273"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="5424e-103">Não é possível atualizar o custo unitário previsto ao importar registros de previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="5424e-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="5424e-104">Número de KB: 4614109</span><span class="sxs-lookup"><span data-stu-id="5424e-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="5424e-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="5424e-105">Symptoms</span></span>

<span data-ttu-id="5424e-106">Quando você usa entidades de dados para importar registros de previsão de demanda, o valor do **Custo unitário previsto** para registros existentes não atualiza para que continue correspondendo aos dados importados.</span><span class="sxs-lookup"><span data-stu-id="5424e-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="5424e-107">Causa</span><span class="sxs-lookup"><span data-stu-id="5424e-107">Cause</span></span>

<span data-ttu-id="5424e-108">**Custo unitário previsto** é um campo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5424e-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="5424e-109">O valor se baseia no custo unitário do produto e não pode ser definido diretamente por meio da importação.</span><span class="sxs-lookup"><span data-stu-id="5424e-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="5424e-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="5424e-110">Resolution</span></span>

<span data-ttu-id="5424e-111">Como o campo é somente leitura, não é possível importar valores para ele.</span><span class="sxs-lookup"><span data-stu-id="5424e-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="5424e-112">O valor será calculado de acordo com a lógica comercial existente.</span><span class="sxs-lookup"><span data-stu-id="5424e-112">The value will be calculated according to the existing business logic.</span></span>
