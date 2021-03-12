---
title: Criar uma classe de trabalho
description: Este procedimento mostra como configurar uma classe de trabalho.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0e06cd5fc6dc27f79eb39bbd78932a166e9d442
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977204"
---
# <a name="create-a-work-class"></a><span data-ttu-id="9fed6-103">Criar uma classe de trabalho</span><span class="sxs-lookup"><span data-stu-id="9fed6-103">Create a work class</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9fed6-104">Este procedimento mostra como configurar uma classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9fed6-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="9fed6-105">Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de trabalho que um funcionário do depósito pode processar em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9fed6-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="9fed6-106">As linhas que um funcionário pode processar são determinadas pelas classes de trabalho nos itens de menu do dispositivo móvel aos quais o funcionário do depósito tem acesso e pela classe de trabalho que está especificada nas linhas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9fed6-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that's specified on the work lines.</span></span> <span data-ttu-id="9fed6-107">Classes de trabalho também podem ser usadas para validar o local de colocação para uma linha da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9fed6-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="9fed6-108">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="9fed6-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="9fed6-109">Esse procedimento é destinado ao gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="9fed6-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="9fed6-110">Vá para Gerenciamento de depósito > Configuração > Trabalho > Classes de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9fed6-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="9fed6-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9fed6-111">Click New.</span></span>
3. <span data-ttu-id="9fed6-112">No campo ID de classe de trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9fed6-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="9fed6-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9fed6-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9fed6-114">No campo Tipo de ordem de trabalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="9fed6-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="9fed6-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9fed6-115">Click New.</span></span>
7. <span data-ttu-id="9fed6-116">No campo Tipo de localização, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9fed6-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="9fed6-117">Se você selecionar um tipo de localização, isso define uma restrição sobre onde os itens podem ser colocados depois que foram separados.</span><span class="sxs-lookup"><span data-stu-id="9fed6-117">If you select a location type, this sets a restriction on where items can be put after they've been picked.</span></span> <span data-ttu-id="9fed6-118">Essa configuração é usada quando uma diretiva de localização tenta resolver a localização, ou se um funcionário do depósito fornece manualmente a localização do item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9fed6-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="9fed6-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9fed6-119">Close the page.</span></span>

