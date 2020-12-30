---
title: Filtragem avançada no RCS/Repositório global
description: Este tópico descreve os recursos aprimorados de filtragem para o repositório global RCS, que foram aprimorados para incluir os filtros adicionais.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440226"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="dc20f-103">Opções de filtragem avançada no RCS para encontrar configurações no RCS/Repositório global</span><span class="sxs-lookup"><span data-stu-id="dc20f-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc20f-104">Este tópico descreve os recursos de filtragem avançada para o repositório global do Regulatory Configuration Services (RCS), que foram aprimorados para incluir a possibilidade de filtrar com os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="dc20f-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="dc20f-105">**País/região** — com base nos códigos de país ISO</span><span class="sxs-lookup"><span data-stu-id="dc20f-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="dc20f-106">Tipos de **marcas** para:</span><span class="sxs-lookup"><span data-stu-id="dc20f-106">**Tags** types for:</span></span>
  - <span data-ttu-id="dc20f-107">Área funcional</span><span class="sxs-lookup"><span data-stu-id="dc20f-107">Functional area</span></span>
  - <span data-ttu-id="dc20f-108">Área de recursos</span><span class="sxs-lookup"><span data-stu-id="dc20f-108">Feature area</span></span>
  - <span data-ttu-id="dc20f-109">Indústria</span><span class="sxs-lookup"><span data-stu-id="dc20f-109">Industry</span></span> 
  - <span data-ttu-id="dc20f-110">Documento comercial</span><span class="sxs-lookup"><span data-stu-id="dc20f-110">Business document</span></span> 

<span data-ttu-id="dc20f-111">Para facilitar a descoberta de configurações específicas ou relacionadas às quais você pode aplicar filtros, individualmente ou em grupo.</span><span class="sxs-lookup"><span data-stu-id="dc20f-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="dc20f-112">Por exemplo, para encontrar um único tipo de documento comercial configurável que esteja relacionado a notas fiscais de fornecedor, você pode aplicar um filtro de **Tipo de documento comercial** para procurar esse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="dc20f-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="dc20f-113">[![Filtrar seção do repositório global](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="dc20f-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="dc20f-114">É possível refinar ainda mais a pesquisa selecionando o tipo de documento, por exemplo "fatura de fornecedor" clicando em **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="dc20f-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="dc20f-115">O exemplo a seguir mostra os resultados ao filtrar em **Tipo de documento comercial** co o tipo de documento adicionado.</span><span class="sxs-lookup"><span data-stu-id="dc20f-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="dc20f-116">[![Filtro e importação aplicados para tipo de documento comercial](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="dc20f-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="dc20f-117">Os resultados filtrados podem ser importados em um repositório do RCS ou em um ambiente do Dynamics 365 Finance dos usuários, individualmente ou como um conjunto.</span><span class="sxs-lookup"><span data-stu-id="dc20f-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="dc20f-118">Para fazer isso, selecione o grupo de configurações e clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="dc20f-118">To do this, select the group of configurations, and click **Import**.</span></span>
