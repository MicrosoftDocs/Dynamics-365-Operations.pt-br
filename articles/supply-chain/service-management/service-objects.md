---
title: Objetos de serviço
description: Objetos de serviço são os ativos e os produtos de um cliente para o qual você pode executar um serviço.
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5641077de84b6702d2c5621edef74783f2f104fd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353393"
---
# <a name="service-objects"></a><span data-ttu-id="619ed-103">Objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="619ed-103">Service objects</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="619ed-104">Objetos de serviço são os ativos e os produtos de um cliente para o qual você pode executar um serviço.</span><span class="sxs-lookup"><span data-stu-id="619ed-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="619ed-105">Dependendo do tipo de serviço fornecido, os objetos podem ser tangíveis ou intangíveis:</span><span class="sxs-lookup"><span data-stu-id="619ed-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="619ed-106">Exemplos de objetos tangíveis são uma máquina ou um edifício, nos quais é possível executar uma tarefa de serviço física.</span><span class="sxs-lookup"><span data-stu-id="619ed-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="619ed-107">Um objeto de serviço concreto também pode ser um item de estoque que você cria no formulário Detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="619ed-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="619ed-108">Dependendo do grupo de dimensões de estoque associado ao item, é possível criar um objeto de serviço com detalhes que incluem o número de série do item.</span><span class="sxs-lookup"><span data-stu-id="619ed-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="619ed-109">Isso é útil quando você deve acompanhar o item exato representado pelo objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="619ed-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="619ed-110">Um objeto de serviço concreto também pode ser um item que não esteja diretamente relacionado à produção direta ou à cadeia de fornecedores de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="619ed-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="619ed-111">Por exemplo, um kit de ferramentas que é usado para reparos em uma ordem de serviço pode ser um objeto de serviço que ainda não foi incluído no estoque.</span><span class="sxs-lookup"><span data-stu-id="619ed-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="619ed-112">Nesse caso, você não o registra como um item de estoque.</span><span class="sxs-lookup"><span data-stu-id="619ed-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="619ed-113">Objetos intangíveis são itens abstratos, como um conjunto de contas ou um documento legal, nos quais você pode executar uma tarefa de serviço.</span><span class="sxs-lookup"><span data-stu-id="619ed-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="619ed-114">Exemplo de um objeto de serviço intangível</span><span class="sxs-lookup"><span data-stu-id="619ed-114">Example of an intangible service object</span></span>

<span data-ttu-id="619ed-115">A empresa A mantém os registros financeiros de várias pequenas empresas.</span><span class="sxs-lookup"><span data-stu-id="619ed-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="619ed-116">Um dos clientes da Empresa A é a equipe de futebol local, para a qual a Empresa A faz a escrituração contábil semanal e a auditoria anual das contas do clube.</span><span class="sxs-lookup"><span data-stu-id="619ed-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="619ed-117">Essas contas são configuradas no formulário Objetos de serviço e são especificadas como objeto no contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="619ed-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="619ed-118">Há duas linhas de contrato de serviço para o objeto.</span><span class="sxs-lookup"><span data-stu-id="619ed-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="619ed-119">A linha 1 é a escrituração contábil semanal com um intervalo semanal atribuído à linha, e a linha 2 é a auditoria anual com um intervalo anual atribuído a ela.</span><span class="sxs-lookup"><span data-stu-id="619ed-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="619ed-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="619ed-120">Related topics</span></span>

[<span data-ttu-id="619ed-121">Criar objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="619ed-121">Create service objects</span></span>](create-service-objects.md)

