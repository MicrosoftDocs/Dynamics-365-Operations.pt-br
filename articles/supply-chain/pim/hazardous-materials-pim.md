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
ms.openlocfilehash: 5006f06d90ddcc314a51878e9e21337de7d493e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208447"
---
# <a name="hazardous-materials"></a><span data-ttu-id="3ee0f-103">Materiais perigosos</span><span class="sxs-lookup"><span data-stu-id="3ee0f-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ee0f-104">As informações sobre materiais perigosos são configuradas no Gerenciamento de informações sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="3ee0f-105">Este módulo também fornece documentos que podem ser impressos por meio do gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="3ee0f-106">Quando você envia materiais que são classificados como mercadorias perigosas, a papelada adicional deve ser incluída nas remessas.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="3ee0f-107">A funcionalidade de materiais perigosos permite que os clientes armazenem informações de classificação e as relacionem para liberar itens.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="3ee0f-108">Essas informações podem ser usadas para ajudar a preparar a documentação de remessa.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ee0f-109">Para ajudar a gerenciar remessas de mercadorias perigosas, o Microsoft Dynamics 365 Supply Chain Management permite configurar informações de referência adicionais relacionadas aos produtos.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="3ee0f-110">Você também pode configurar documentos de remessa adicionais.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="3ee0f-111">No entanto, o sistema não é compatível automaticamente com as regulamentações de seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="3ee0f-112">Em vez disso, é uma ferramenta que pode ajudar eu programa geral.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="3ee0f-113">Para poder usar essa funcionalidade, é necessária a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="3ee0f-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="3ee0f-114">**Gerenciamento de informações sobre produtos**: configure códigos que possam ser aplicados a produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="3ee0f-115">**Gerenciamento de depósito**: use documentos de remessa adicionais para imprimir informações de remessa.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="3ee0f-116">Gerenciamento de informações sobre produtos</span><span class="sxs-lookup"><span data-stu-id="3ee0f-116">Product information management</span></span>

<span data-ttu-id="3ee0f-117">No Gerenciamento de informações sobre produtos, há uma gama de tabelas de configuração em que você pode adicionar as informações de referência fornecidas nas listas de mercadorias perigosas para frete rodoviário, aéreo e marítimo.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="3ee0f-118">Veja a seguir algumas das normas que costumam ser mencionadas:</span><span class="sxs-lookup"><span data-stu-id="3ee0f-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="3ee0f-119">**ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias</span><span class="sxs-lookup"><span data-stu-id="3ee0f-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="3ee0f-120">**CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas</span><span class="sxs-lookup"><span data-stu-id="3ee0f-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="3ee0f-121">**IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)</span><span class="sxs-lookup"><span data-stu-id="3ee0f-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="3ee0f-122">**IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)</span><span class="sxs-lookup"><span data-stu-id="3ee0f-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="3ee0f-123">Cada uma dessas regulamentações tem uma lista de mercadorias perigosas que inclui códigos de referência.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="3ee0f-124">As listas para cada tipo de transporte são combinadas em classificações internacionais compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="3ee0f-125">O Supply Chain Management fornece uma tabela de referência para os códigos compartilhados nessas listas.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="3ee0f-126">Cada lista também tem alguns códigos exclusivos que podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="3ee0f-127">Para começar a configurar essas informações, crie uma regulamentação que possa ser usada para configurar os parâmetros iniciais.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="3ee0f-128">Gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="3ee0f-128">Warehouse management</span></span>

<span data-ttu-id="3ee0f-129">Quando uma remessa é preparada, vários relatórios novos podem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="3ee0f-130">Esses relatórios usam as informações configuradas no Gerenciamento de informações sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-130">These reports use the information that you set up in Product information management.</span></span>
