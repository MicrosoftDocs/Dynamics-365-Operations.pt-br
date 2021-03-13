---
title: Visão geral de materiais perigosos
description: Este tópico fornece uma visão geral dos recursos relacionados ao manuseio e à documentação de materiais perigosos durante o gerenciamento de informações do produto e o gerenciamento de depósito.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: ff285e7e8bcdd2a3197f0ccae569ac880b796028
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007582"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="3a24a-103">Visão geral de materiais perigosos</span><span class="sxs-lookup"><span data-stu-id="3a24a-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="3a24a-104">Para permanecer em conformidade com as regulamentações de remessa e transporte, as organizações que enviam materiais que são classificados como mercadorias perigosas devem incluir documentos adicionais com suas remessas.</span><span class="sxs-lookup"><span data-stu-id="3a24a-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="3a24a-105">O recurso materiais perigosos permite que os clientes armazenem informações relacionadas aos itens liberados.</span><span class="sxs-lookup"><span data-stu-id="3a24a-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="3a24a-106">Essas informações podem ser usadas para ajudar a preparar a documentação de remessa.</span><span class="sxs-lookup"><span data-stu-id="3a24a-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="3a24a-107">Uma organização que envia mercadorias perigosas deve ter seus próprios processos e procedimentos para o gerenciamento do processo de remessa.</span><span class="sxs-lookup"><span data-stu-id="3a24a-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="3a24a-108">O Microsoft Dynamics 365 Supply Chain Management é a ferramenta que pode ajudar a gerar os documentos necessários.</span><span class="sxs-lookup"><span data-stu-id="3a24a-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="3a24a-109">O diagrama a seguir ilustra as etapas necessárias para configurar e usar o recurso materiais perigosos.</span><span class="sxs-lookup"><span data-stu-id="3a24a-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="3a24a-110">![Configurar e usar o recurso materiais perigosos](media/hazmat-overview.png "Configurar e usar o recurso materiais perigosos")</span><span class="sxs-lookup"><span data-stu-id="3a24a-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="3a24a-111">O recurso materiais perigosos é configurado no Gerenciamento de informações do produto e fornece documentos que podem ser impressos por meio do Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="3a24a-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="3a24a-112">Portanto, em geral, essas áreas são as duas principais áreas nas quais você vai revisar, configurar e usar a funcionalidade desse recurso:</span><span class="sxs-lookup"><span data-stu-id="3a24a-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="3a24a-113">**Gerenciamento de informações do produto** — configure os códigos que serão aplicados a um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="3a24a-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="3a24a-114">**Gerenciamento de depósito** — trabalhe com documentos de remessa adicionais que serão impressos para remessas.</span><span class="sxs-lookup"><span data-stu-id="3a24a-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a24a-115">Os recursos materiais perigosos no Supply Chain Management fornecem uma coleção de campos úteis de informações de produtos e funcionalidades relacionadas que podem ajudar você a registrar e consultar informações relacionadas aos produtos perigosos.</span><span class="sxs-lookup"><span data-stu-id="3a24a-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="3a24a-116">Esses recursos também podem ajudá-lo a criar e imprimir documentos de remessa que incluam algumas das mesmas informações sobre materiais perigosos que você está enviando.</span><span class="sxs-lookup"><span data-stu-id="3a24a-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="3a24a-117">No entanto, o sistema não o tornará automaticamente compatível com todos os regulamentos aplicáveis em seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="3a24a-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="3a24a-118">Embora essas ferramentas tenham a finalidade de ajudá-lo a cumprir as regulamentações comuns, elas não são suficientes, nem garantidas.</span><span class="sxs-lookup"><span data-stu-id="3a24a-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="3a24a-119">Sua organização é responsável por conhecer todas as regulamentações aplicáveis e por executar todas as etapas necessárias para cumpri-las.</span><span class="sxs-lookup"><span data-stu-id="3a24a-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="3a24a-120">Gerenciamento de informações do produto</span><span class="sxs-lookup"><span data-stu-id="3a24a-120">Product information management</span></span>

<span data-ttu-id="3a24a-121">O Gerenciamento de informações do produto fornece uma variedade de tabelas de configuração em que você pode inserir as informações de referência de várias listas de mercadorias perigosas para frete rodoviário, aéreo e marítimo.</span><span class="sxs-lookup"><span data-stu-id="3a24a-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="3a24a-122">As seguintes regulamentações comuns foram usadas como referência quando essa funcionalidade foi desenvolvida:</span><span class="sxs-lookup"><span data-stu-id="3a24a-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="3a24a-123">**ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias</span><span class="sxs-lookup"><span data-stu-id="3a24a-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="3a24a-124">**CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas</span><span class="sxs-lookup"><span data-stu-id="3a24a-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="3a24a-125">**IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)</span><span class="sxs-lookup"><span data-stu-id="3a24a-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="3a24a-126">**IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)</span><span class="sxs-lookup"><span data-stu-id="3a24a-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="3a24a-127">Cada conjunto de regulamentos fornece listas padronizadas de mercadorias perigosas e códigos de referência.</span><span class="sxs-lookup"><span data-stu-id="3a24a-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="3a24a-128">Portanto, o Supply Chain Management fornece uma tabela de referência para os códigos comuns nessas listas.</span><span class="sxs-lookup"><span data-stu-id="3a24a-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="3a24a-129">Cada lista tem também alguns códigos exclusivos que você pode definir.</span><span class="sxs-lookup"><span data-stu-id="3a24a-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="3a24a-130">Para obter mais informações sobre como configurar regulamentos e valores para materiais perigosos e como atribuir os valores aos produtos relevantes, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3a24a-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="3a24a-131">Configurar materiais perigosos</span><span class="sxs-lookup"><span data-stu-id="3a24a-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="3a24a-132">Materiais perigosos em produtos, ordens, remessas e cargas</span><span class="sxs-lookup"><span data-stu-id="3a24a-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="3a24a-133">Gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="3a24a-133">Warehouse management</span></span>

<span data-ttu-id="3a24a-134">Ao preparar uma remessa no Gerenciamento de depósito, você poderá imprimir vários relatórios novos que usam as informações configuradas no Gerenciamento de informações do produto.</span><span class="sxs-lookup"><span data-stu-id="3a24a-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="3a24a-135">Para obter mais informações sobre os relatórios disponíveis e sobre como usá-los, consulte [Consultas e relatórios de materiais perigosos](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="3a24a-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>
