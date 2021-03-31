---
title: Categorias de custo usadas no Controle de produção e na Contabilidade e gerenciamento do projeto
description: Alguns tipos de trabalho de produção podem ser aplicados a estimativas de tempo de projeto e a relatórios. Este artigo oferece informações sobre as categorias de custo que você deve definir para esses tipos de trabalho de produção para fins de produção e de relatório.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 540d020820222b024f838f8156aaef823605e950
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228698"
---
# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="a60ce-104">Categorias de custo usadas no Controle de produção e na Contabilidade e gerenciamento do projeto</span><span class="sxs-lookup"><span data-stu-id="a60ce-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a60ce-105">Alguns tipos de trabalho de produção podem ser aplicados a estimativas de tempo de projeto e a relatórios.</span><span class="sxs-lookup"><span data-stu-id="a60ce-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="a60ce-106">Este artigo oferece informações sobre as categorias de custo que você deve definir para esses tipos de trabalho de produção para fins de produção e de relatório.</span><span class="sxs-lookup"><span data-stu-id="a60ce-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="a60ce-107">Alguns tipos de trabalho de produção podem ser aplicados a estimativas de tempo de projeto e a relatórios.</span><span class="sxs-lookup"><span data-stu-id="a60ce-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="a60ce-108">Nesse caso, uma categoria de custo é necessária para fins de produção e de projeto.</span><span class="sxs-lookup"><span data-stu-id="a60ce-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="a60ce-109">Quando uma categoria de custo é usada na produção e em projetos, as informações adicionais relacionadas ao projeto devem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="a60ce-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="a60ce-110">Por exemplo, os custos horários associados a projetos podem ser diferentes dos custos horários associados à produção.</span><span class="sxs-lookup"><span data-stu-id="a60ce-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="a60ce-111">Você pode usar a página **Categorias de custo** para definir uma categoria de custo usada no Controle de produção e na Contabilidade e gerenciamento do projeto.</span><span class="sxs-lookup"><span data-stu-id="a60ce-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="a60ce-112">**Observação:** A contabilização de custos tem uma página **Categorias de projeto**, mas esta página não está relacionada à funcionalidade descrita neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a60ce-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="a60ce-113">Quando você usa uma categoria de custo nos projetos, a página **Categorias de custo** tem guias adicionais que mostram informações adicionais relacionadas ao projeto.</span><span class="sxs-lookup"><span data-stu-id="a60ce-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="a60ce-114">Essas informações incluem o grupo de categorias, a propriedade de linha e as contas contábeis atribuídas à categoria de custo.</span><span class="sxs-lookup"><span data-stu-id="a60ce-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="a60ce-115">A categoria de custo deve ser atribuída a um grupo de categorias que suporte o tipo de transação **Horas**.</span><span class="sxs-lookup"><span data-stu-id="a60ce-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="a60ce-116">A propriedade de linha indica as informações padrão sobre como o tempo informado poderá ser cobrado para um projeto.</span><span class="sxs-lookup"><span data-stu-id="a60ce-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="a60ce-117">Normalmente, as contas contábeis relacionadas aos custos e vendas são definidas para o grupo de categorias atribuído à categoria de custo.</span><span class="sxs-lookup"><span data-stu-id="a60ce-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="a60ce-118">No entanto, é possível definir contas específicas para uma categoria de custo individual.</span><span class="sxs-lookup"><span data-stu-id="a60ce-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="a60ce-119">Os botões adicionais da página **Categorias de custo** dão acesso a informações relacionadas ao projeto sobre uma categoria de custo selecionada.</span><span class="sxs-lookup"><span data-stu-id="a60ce-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="a60ce-120">Por exemplo, você pode ver transações relacionadas ao projeto, definir funcionários ou projetos, definir custos de hora e preços de venda, e ver relatórios.</span><span class="sxs-lookup"><span data-stu-id="a60ce-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]