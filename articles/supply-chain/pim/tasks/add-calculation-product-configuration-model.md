---
title: Adicionar um cálculo a um modelo de configuração de produto
description: Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9754c46010e7bbdb2edef0d6e68162f344bb1257
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570402"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="ec7ac-103">Adicionar um cálculo a um modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="ec7ac-103">Add a calculation to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec7ac-104">Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="ec7ac-105">Ele mostra como você pode criar uma expressão lógica usando o operador “If” para definir uma altura do alto-falante como 10 para alto-falantes brancos, e 15 para todos os outros acabamentos de gabinetes.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="ec7ac-106">O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="ec7ac-107">Adicionar um cálculo</span><span class="sxs-lookup"><span data-stu-id="ec7ac-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="ec7ac-108">Criar expressão de cálculo</span><span class="sxs-lookup"><span data-stu-id="ec7ac-108">Create calculation expression</span></span>
1. <span data-ttu-id="ec7ac-109">Clique em Editar expressão.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-109">Click Edit expression.</span></span>
2. <span data-ttu-id="ec7ac-110">No campo de ConstraintBody, insira 'If[CabinetFinish=="White", 10, 15]'.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="ec7ac-111">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-111">Click Validate.</span></span>
4. <span data-ttu-id="ec7ac-112">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-112">Click Close.</span></span>
5. <span data-ttu-id="ec7ac-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ec7ac-113">Click OK.</span></span>

