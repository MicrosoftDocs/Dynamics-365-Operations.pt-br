---
title: "Modelos de Serviço"
description: "Você pode definir um contrato de serviço como um modelo e copiar posteriormente as linhas do modelo para outro contrato ou ordem de serviço."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
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
ms.sourcegitcommit: 09f2da382cd7f3e0e3d4bfa389e9cdf74f00b501
ms.openlocfilehash: ade518095b77141fb31b597a955dd23aaae119d7
ms.contentlocale: pt-br
ms.lasthandoff: 02/27/2018

---

# <a name="service-templates"></a><span data-ttu-id="9ee81-103">Modelos de Serviço</span><span class="sxs-lookup"><span data-stu-id="9ee81-103">Service templates</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9ee81-104">Você pode definir um contrato de serviço como um modelo e copiar posteriormente as linhas do modelo para outro contrato ou ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9ee81-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="9ee81-105">exemplo</span><span class="sxs-lookup"><span data-stu-id="9ee81-105">Example</span></span>

<span data-ttu-id="9ee81-106">Um cliente ao qual você presta serviços possui elevadores idênticos em cinco locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="9ee81-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="9ee81-107">Você deseja configurar cinco contratos de serviço para o cliente, um para cada local.</span><span class="sxs-lookup"><span data-stu-id="9ee81-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="9ee81-108">Para limitar o trabalho de configuração repetitivo e garantir que as informações de configuração dos contratos sejam idênticas, você cria um contrato de serviço e especifica-o como modelo para o trabalho relacionado aos elevadores.</span><span class="sxs-lookup"><span data-stu-id="9ee81-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="9ee81-109">Agora, você poderá copiar as linhas do modelo para os cinco novos contratos de serviço de modo que cada contrato seja preenchido com essas linhas.</span><span class="sxs-lookup"><span data-stu-id="9ee81-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="9ee81-110">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="9ee81-110">Create a template</span></span>

<span data-ttu-id="9ee81-111">Ao criar um modelo de serviço, você cria um contrato de serviço com as linhas necessárias e, depois, associa o contrato a um grupo de modelos de serviço.</span><span class="sxs-lookup"><span data-stu-id="9ee81-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="9ee81-112">É possível definir um contrato de serviço como um modelo somente quando não há ordens de serviço associadas a ele.</span><span class="sxs-lookup"><span data-stu-id="9ee81-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="9ee81-113">Além disso, nenhuma ordem de serviço pode ser gerada a partir de um contrato definido como modelo.</span><span class="sxs-lookup"><span data-stu-id="9ee81-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="9ee81-114">Copiar Linhas do Modelo</span><span class="sxs-lookup"><span data-stu-id="9ee81-114">Copy template lines</span></span>

<span data-ttu-id="9ee81-115">Você pode copiar linhas de um modelo de serviço para outro contrato de serviço ou para uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9ee81-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="9ee81-116">Quando você copia linhas de um modelo para ordens ou contratos de serviço, os grupos de modelos são exibidos em um modo de exibição de árvore em que cada grupo pode ser expandido.</span><span class="sxs-lookup"><span data-stu-id="9ee81-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="9ee81-117">Essa exibição permite que você visualize cada modelo e cada linha do modelo.</span><span class="sxs-lookup"><span data-stu-id="9ee81-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="9ee81-118">É mais fácil determinar as linhas do modelo de serviço que você deseja copiar agrupando os modelos com nomes que indiquem o seu uso.</span><span class="sxs-lookup"><span data-stu-id="9ee81-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ee81-119">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ee81-119">Related topics</span></span>

[<span data-ttu-id="9ee81-120">Copiar linhas de modelos de serviço</span><span class="sxs-lookup"><span data-stu-id="9ee81-120">Copy service templates lines</span></span>](copy-service-template-lines.md)
