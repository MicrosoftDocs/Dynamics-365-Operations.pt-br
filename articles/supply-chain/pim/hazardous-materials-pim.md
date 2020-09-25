---
title: Materiais perigosos
description: Este tópico fornece informações sobre documentos e informações de materiais perigosos armazenados no seu ambiente.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 54e5dca38b31c9310d44bdda5f5af14ca1515541
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802692"
---
# <a name="hazardous-materials"></a><span data-ttu-id="b5262-103">Materiais perigosos</span><span class="sxs-lookup"><span data-stu-id="b5262-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b5262-104">As informações sobre materiais perigosos são configuradas no Gerenciamento de informações sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="b5262-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="b5262-105">Este módulo também fornece documentos que podem ser impressos por meio do gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="b5262-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="b5262-106">Quando você envia materiais que são classificados como mercadorias perigosas, a papelada adicional deve ser incluída nas remessas.</span><span class="sxs-lookup"><span data-stu-id="b5262-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="b5262-107">A funcionalidade de materiais perigosos permite que os clientes armazenem informações de classificação e as relacionem para liberar itens.</span><span class="sxs-lookup"><span data-stu-id="b5262-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="b5262-108">Essas informações podem ser usadas para ajudar a preparar a documentação de remessa.</span><span class="sxs-lookup"><span data-stu-id="b5262-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5262-109">Os recursos de materiais perigosos no Microsoft Dynamics 365 Supply Chain Management fornecem uma coleção de campos úteis de informações de produtos e funcionalidades relacionadas que podem ajudar você a registrar e consultar informações relacionadas aos produtos perigosos.</span><span class="sxs-lookup"><span data-stu-id="b5262-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="b5262-110">Esses recursos também podem ajudá-lo a criar e imprimir documentos de remessa que incluam algumas das mesmas informações sobre materiais perigosos que você está enviando.</span><span class="sxs-lookup"><span data-stu-id="b5262-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="b5262-111">No entanto, o sistema não o tornará automaticamente compatível com todos os regulamentos aplicáveis em seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="b5262-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="b5262-112">Embora essas ferramentas tenham a finalidade de ajudá-lo a cumprir as regulamentações comuns, elas não são suficientes, nem garantidas.</span><span class="sxs-lookup"><span data-stu-id="b5262-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="b5262-113">Sua organização é responsável por conhecer todas as regulamentações aplicáveis e por executar todas as etapas necessárias para cumpri-las.</span><span class="sxs-lookup"><span data-stu-id="b5262-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="b5262-114">Para poder usar essa funcionalidade, é necessária a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="b5262-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="b5262-115">**Gerenciamento de informações sobre produtos**: configure códigos que possam ser aplicados a produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b5262-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="b5262-116">**Gerenciamento de depósito**: use documentos de remessa adicionais para imprimir informações de remessa.</span><span class="sxs-lookup"><span data-stu-id="b5262-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="b5262-117">Gerenciamento de informações sobre produtos</span><span class="sxs-lookup"><span data-stu-id="b5262-117">Product information management</span></span>

<span data-ttu-id="b5262-118">No Gerenciamento de informações sobre produtos, há uma gama de tabelas de configuração em que você pode adicionar as informações de referência fornecidas nas listas de mercadorias perigosas para frete rodoviário, aéreo e marítimo.</span><span class="sxs-lookup"><span data-stu-id="b5262-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="b5262-119">Veja a seguir algumas das normas que costumam ser mencionadas:</span><span class="sxs-lookup"><span data-stu-id="b5262-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="b5262-120">**ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias</span><span class="sxs-lookup"><span data-stu-id="b5262-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="b5262-121">**CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas</span><span class="sxs-lookup"><span data-stu-id="b5262-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="b5262-122">**IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)</span><span class="sxs-lookup"><span data-stu-id="b5262-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="b5262-123">**IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)</span><span class="sxs-lookup"><span data-stu-id="b5262-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="b5262-124">Cada uma dessas regulamentações tem uma lista de mercadorias perigosas que inclui códigos de referência.</span><span class="sxs-lookup"><span data-stu-id="b5262-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="b5262-125">As listas para cada tipo de transporte são combinadas em classificações internacionais compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="b5262-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="b5262-126">O Supply Chain Management fornece uma tabela de referência para os códigos compartilhados nessas listas.</span><span class="sxs-lookup"><span data-stu-id="b5262-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="b5262-127">Cada lista também tem alguns códigos exclusivos que podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="b5262-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="b5262-128">Para começar a configurar essas informações, crie uma regulamentação que possa ser usada para configurar os parâmetros iniciais.</span><span class="sxs-lookup"><span data-stu-id="b5262-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="b5262-129">Gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="b5262-129">Warehouse management</span></span>

<span data-ttu-id="b5262-130">Quando uma remessa é preparada, vários relatórios novos podem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="b5262-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="b5262-131">Esses relatórios usam as informações configuradas no Gerenciamento de informações sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="b5262-131">These reports use the information that you set up in Product information management.</span></span>
