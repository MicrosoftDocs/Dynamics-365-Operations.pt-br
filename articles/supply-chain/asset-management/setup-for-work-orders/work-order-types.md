---
title: Tipos de ordem de serviço
description: Este tópico explica os tipos de ordem de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6bdc9d226d8e1aa6960cac38b95b0245e46ee1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825581"
---
# <a name="work-order-types"></a><span data-ttu-id="932d9-103">Tipos de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="932d9-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="932d9-104">Os tipos de ordem de serviço são usados para categorizar ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="932d9-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="932d9-105">Por exemplo, você pode ter ordens de serviço relacionadas à manutenção preventiva ou manutenção corretiva.</span><span class="sxs-lookup"><span data-stu-id="932d9-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="932d9-106">Um tipo de ordem de serviço define uma afiliação com um modelo de ciclo de vida da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="932d9-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="932d9-107">Um modelo do ciclo de vida da ordem de serviço define os estados do ciclo de vida da ordem de serviço que podem ser definidos em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="932d9-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="932d9-108">(Exemplos dos estados de ciclo de vida da ordem de serviço incluem **Criado**, **Em andamento** e **Concluído**).</span><span class="sxs-lookup"><span data-stu-id="932d9-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="932d9-109">Para obter mais informações sobre os estados de ciclo de vida da ordem de serviço e as fases do projeto, consulte [Estados de ciclo de vida da ordem de serviço](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="932d9-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="932d9-110">Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Tipos de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="932d9-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="932d9-111">Selecione **Novo** para criar um tipo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="932d9-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="932d9-112">No campo **Tipo de ordem de serviço**, insira uma ID para o tipo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="932d9-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="932d9-113">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="932d9-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="932d9-114">No campo **Modelo de ciclo de vida da ordem de serviço**, selecione um modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="932d9-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="932d9-115">Defina a opção **Um funcionário de manutenção** como **Sim** se todos os trabalhos de ordem de serviço relacionados a uma ordem de serviço desse tipo devem ser agendados para o mesmo funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="932d9-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="932d9-116">No campo **Tipo de custo**, selecione **Corretivo**, **Preventivo** ou **Investimento**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="932d9-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="932d9-117">Todos os trabalhos da ordem de serviço em uma ordem de serviço devem ter o mesmo tipo de custo.</span><span class="sxs-lookup"><span data-stu-id="932d9-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="932d9-118">Na seção **Obrigatório**, defina as opções relevantes como **Sim** para especificar quais informações relacionadas a falha ou a tempo de inatividade de manutenção são adicionadas a uma ordem de serviço desse tipo.</span><span class="sxs-lookup"><span data-stu-id="932d9-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="932d9-119">As opções na seção **Obrigatório** estão relacionadas às opções na Guia Rápida **Validar** da página **Estados de ciclo de vida da ordem de serviço** (**Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Estados de ciclo de vida**).</span><span class="sxs-lookup"><span data-stu-id="932d9-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="932d9-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="932d9-120">Select **Save**.</span></span>

![Tipos de ordem de serviço](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]