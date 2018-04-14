---
title: "Grupos de objetos de serviço"
description: "Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e539d92753bbbc4ac0ca88cec83c4d15135c388b
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="service-object-groups"></a><span data-ttu-id="dd33d-103">Grupos de objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="dd33d-103">Service object groups</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="dd33d-104">Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas.</span><span class="sxs-lookup"><span data-stu-id="dd33d-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="dd33d-105">Por exemplo, você pode agrupar objetos por localização geográfica ou tipo.</span><span class="sxs-lookup"><span data-stu-id="dd33d-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="dd33d-106">Agrupar por localização geográfica</span><span class="sxs-lookup"><span data-stu-id="dd33d-106">Group by geographical location</span></span>

<span data-ttu-id="dd33d-107">Você pode usar este método de agrupamento para mostrar onde estão localizados os vários objetos diferentes para os quais sua empresa presta serviços.</span><span class="sxs-lookup"><span data-stu-id="dd33d-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="dd33d-108">Agrupar objetos por localização geográfica também poderá ser útil se, por exemplo, for necessário identificar os objetos para os quais sua empresa presta serviços em um país/região específico.</span><span class="sxs-lookup"><span data-stu-id="dd33d-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="dd33d-109">exemplo</span><span class="sxs-lookup"><span data-stu-id="dd33d-109">Example</span></span>

<span data-ttu-id="dd33d-110">Um cliente da Bélgica liga para o seu centro de serviço e deseja criar uma contrato de serviço para um objeto, ABC.</span><span class="sxs-lookup"><span data-stu-id="dd33d-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="dd33d-111">Você associou um grupo de objetos para localização geográfica, Bélgica, a todos os objetos atendidos na Bélgica.</span><span class="sxs-lookup"><span data-stu-id="dd33d-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="dd33d-112">Usando esse grupo como um filtro, você pode pesquisar rapidamente e consultar se já existe um registros para ABC no programa ou se é necessário configurar um novo objeto.</span><span class="sxs-lookup"><span data-stu-id="dd33d-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="dd33d-113">Agrupar por tipo</span><span class="sxs-lookup"><span data-stu-id="dd33d-113">Group by type</span></span>

<span data-ttu-id="dd33d-114">Você pode usar este método de agrupamento para mostrar os tipos de objetos que sua empresa presta serviços.</span><span class="sxs-lookup"><span data-stu-id="dd33d-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="dd33d-115">Agrupar objetos por tipo também pode ser útil se, por exemplo, você deseja criar um novo objeto com base em objetos semelhantes que já existam no programa.</span><span class="sxs-lookup"><span data-stu-id="dd33d-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="dd33d-116">exemplo</span><span class="sxs-lookup"><span data-stu-id="dd33d-116">Example</span></span>

<span data-ttu-id="dd33d-117">Um cliente liga e deseja definir um contrato de serviço para uma máquina de ar-condicionado, HIJ.</span><span class="sxs-lookup"><span data-stu-id="dd33d-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="dd33d-118">Você ainda não tem um registro para este computador.</span><span class="sxs-lookup"><span data-stu-id="dd33d-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="dd33d-119">No entanto, você configurou um grupo de objetos intitulado Ar-condicionados e associou esse grupo a todos os objetos de ar-condicionado.</span><span class="sxs-lookup"><span data-stu-id="dd33d-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="dd33d-120">Portanto, é possível pesquisar rapidamente e identificar todas as outras máquinas de ar-condicionado e usar as informações do modelo desses objetos para criar linhas de contrato de serviço para HIJ.</span><span class="sxs-lookup"><span data-stu-id="dd33d-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="dd33d-121">Ao usar grupos de objetos dessa maneira, você pode configurar rapidamente novos objetos e determinar as tarefas de serviço que devem ser realizadas neles.</span><span class="sxs-lookup"><span data-stu-id="dd33d-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 




