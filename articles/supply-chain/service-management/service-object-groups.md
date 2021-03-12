---
title: Grupos de objetos de serviço
description: Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas.
author: ShylaThompson
manager: tfehr
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a8e050afb44787072f78e2c971394956cb1026f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977579"
---
# <a name="service-object-groups"></a><span data-ttu-id="e08c8-103">Grupos de objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="e08c8-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e08c8-104">Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas.</span><span class="sxs-lookup"><span data-stu-id="e08c8-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="e08c8-105">Por exemplo, você pode agrupar objetos por localização geográfica ou tipo.</span><span class="sxs-lookup"><span data-stu-id="e08c8-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="e08c8-106">Agrupar por localização geográfica</span><span class="sxs-lookup"><span data-stu-id="e08c8-106">Group by geographical location</span></span>

<span data-ttu-id="e08c8-107">Você pode usar este método de agrupamento para mostrar onde estão localizados os vários objetos diferentes para os quais sua empresa presta serviços.</span><span class="sxs-lookup"><span data-stu-id="e08c8-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="e08c8-108">Agrupar objetos por localização geográfica também poderá ser útil se, por exemplo, for necessário identificar os objetos para os quais sua empresa presta serviços em um país/região específico.</span><span class="sxs-lookup"><span data-stu-id="e08c8-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="e08c8-109">exemplo</span><span class="sxs-lookup"><span data-stu-id="e08c8-109">Example</span></span>

<span data-ttu-id="e08c8-110">Um cliente da Bélgica liga para o seu centro de serviço e deseja criar uma contrato de serviço para um objeto, ABC.</span><span class="sxs-lookup"><span data-stu-id="e08c8-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="e08c8-111">Você associou um grupo de objetos para localização geográfica, Bélgica, a todos os objetos atendidos na Bélgica.</span><span class="sxs-lookup"><span data-stu-id="e08c8-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="e08c8-112">Usando esse grupo como um filtro, você pode pesquisar rapidamente e consultar se já existe um registros para ABC no programa ou se é necessário configurar um novo objeto.</span><span class="sxs-lookup"><span data-stu-id="e08c8-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="e08c8-113">Agrupar por tipo</span><span class="sxs-lookup"><span data-stu-id="e08c8-113">Group by type</span></span>

<span data-ttu-id="e08c8-114">Você pode usar este método de agrupamento para mostrar os tipos de objetos que sua empresa presta serviços.</span><span class="sxs-lookup"><span data-stu-id="e08c8-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="e08c8-115">Agrupar objetos por tipo também pode ser útil se, por exemplo, você deseja criar um novo objeto com base em objetos semelhantes que já existam no programa.</span><span class="sxs-lookup"><span data-stu-id="e08c8-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="e08c8-116">exemplo</span><span class="sxs-lookup"><span data-stu-id="e08c8-116">Example</span></span>

<span data-ttu-id="e08c8-117">Um cliente liga e deseja definir um contrato de serviço para uma máquina de ar-condicionado, HIJ.</span><span class="sxs-lookup"><span data-stu-id="e08c8-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="e08c8-118">Você ainda não tem um registro para este computador.</span><span class="sxs-lookup"><span data-stu-id="e08c8-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="e08c8-119">No entanto, você configurou um grupo de objetos intitulado Ar-condicionados e associou esse grupo a todos os objetos de ar-condicionado.</span><span class="sxs-lookup"><span data-stu-id="e08c8-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="e08c8-120">Portanto, é possível pesquisar rapidamente e identificar todas as outras máquinas de ar-condicionado e usar as informações do modelo desses objetos para criar linhas de contrato de serviço para HIJ.</span><span class="sxs-lookup"><span data-stu-id="e08c8-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="e08c8-121">Ao usar grupos de objetos dessa maneira, você pode configurar rapidamente novos objetos e determinar as tarefas de serviço que devem ser realizadas neles.</span><span class="sxs-lookup"><span data-stu-id="e08c8-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="e08c8-122">Criar grupos de objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="e08c8-122">Create service object groups</span></span>

<span data-ttu-id="e08c8-123">Crie grupos aos quais você pode atribuir objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="e08c8-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="e08c8-124">Os objetos de serviço são itens de estoque e outros produtos para os quais os serviços são executados.</span><span class="sxs-lookup"><span data-stu-id="e08c8-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="e08c8-125">Ao agrupar objetos de serviço, você pode criar relatórios de objetos de serviço semelhantes e relacionados.</span><span class="sxs-lookup"><span data-stu-id="e08c8-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="e08c8-126">Por exemplo, um grupo de objetos de serviço pode consistir em dois objetos de serviço: um objeto de serviço é um kit, e o segundo objeto de serviço é o serviço para instalar o kit.</span><span class="sxs-lookup"><span data-stu-id="e08c8-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="e08c8-127">Para criar grupos de objetos de serviço, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e08c8-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="e08c8-128">Clique em **Gerenciamento de serviços > Configuração > Objetos de serviço > Grupos de objetos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e08c8-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="e08c8-129">Clique em **Novo** para criar um novo grupo de objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="e08c8-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="e08c8-130">Insira um nome exclusivo para o grupo de objetos de serviço e, opcionalmente, uma descrição.</span><span class="sxs-lookup"><span data-stu-id="e08c8-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="e08c8-131">Você pode atribuir objetos de serviço ao grupo usando o formulário **Objetos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e08c8-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e08c8-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e08c8-132">See also</span></span>

[<span data-ttu-id="e08c8-133">Criar objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="e08c8-133">Create service objects</span></span>](create-service-objects.md)


