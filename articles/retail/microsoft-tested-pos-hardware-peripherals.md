---
title: "Periféricos de hardware do PDV"
description: "O ponto de venda moderno manager (POS) e o retail do nuvem podem utilizar uma grande variedade de periféricos de hardware do pos, com várias opções de interfaces e implantação obter vários cenários comerciais de um fornecedor."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 250ab6570e152ad57b4a590203e9321d89e7b5d1
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="a8ad0-103">Periféricos de hardware do PDV</span><span class="sxs-lookup"><span data-stu-id="a8ad0-103">POS hardware peripherals</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a8ad0-104">O ponto de venda moderno manager (POS) e o retail do nuvem podem utilizar uma grande variedade de periféricos de hardware do pos, com várias opções de interfaces e implantação obter vários cenários comerciais de um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="a8ad0-105">Para dar suporte a maior seleção de dispositivos entre fabricantes e modelos, PDV utiliza interfaces padrão como OLE para Retail POS (OPOS), Unidades de dispositivo Windows e ponto Windows de interfaces de programa aplicativo de serviço (APIs).</span><span class="sxs-lookup"><span data-stu-id="a8ad0-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="a8ad0-106">Geralmente, o PDV funcionará nesses dispositivos fornecidos onde a unidade apropriada e fornecida.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="a8ad0-107">No entanto, como cada fabricante e implementação de desenvolvedor de software desses padrões pode variar, há diferenças frequentes nas funcionalidades suportadas ou comportamentos.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="a8ad0-108">A lista a seguir contém os modelos de dispositivo, em cada classe, que foram testados internamente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="a8ad0-109">**Dispositivos OPOS**</span><span class="sxs-lookup"><span data-stu-id="a8ad0-109">**OPOS devices**</span></span>

-   <span data-ttu-id="a8ad0-110">Código de barras – Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="a8ad0-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="a8ad0-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span><span class="sxs-lookup"><span data-stu-id="a8ad0-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="a8ad0-112">LineDisplay – Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="a8ad0-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="a8ad0-113">Pinpad – Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="a8ad0-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="a8ad0-114">Dispositivo de assinaturas – Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="a8ad0-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="a8ad0-115">Impressora – EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="a8ad0-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="a8ad0-116">Caixas registradoras – Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="a8ad0-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="a8ad0-117">Escala – Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="a8ad0-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="a8ad0-118">**LTM leitor de cartão de crédito do teclado**</span><span class="sxs-lookup"><span data-stu-id="a8ad0-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="a8ad0-119">USB de Magtek</span><span class="sxs-lookup"><span data-stu-id="a8ad0-119">Magtek USB</span></span>

<span data-ttu-id="a8ad0-120">**Terminal de pagamento**</span><span class="sxs-lookup"><span data-stu-id="a8ad0-120">**Payment terminal**</span></span>

-   <span data-ttu-id="a8ad0-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="a8ad0-121">Equinox L3500</span></span>
-   <span data-ttu-id="a8ad0-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="a8ad0-122">Verifone MX925</span></span>

<span data-ttu-id="a8ad0-123">**Dispositivos de rede**</span><span class="sxs-lookup"><span data-stu-id="a8ad0-123">**Network devices**</span></span>

-   <span data-ttu-id="a8ad0-124">Impressora – Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="a8ad0-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="a8ad0-125">Caixas registradoras – APG Atwood</span><span class="sxs-lookup"><span data-stu-id="a8ad0-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="a8ad0-126">Terminal de pagamento – MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="a8ad0-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="a8ad0-127">**MPOS direcionam CPI somente**</span><span class="sxs-lookup"><span data-stu-id="a8ad0-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="a8ad0-128">Código de barras – Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="a8ad0-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="a8ad0-129">MSR – Magtek PN - 21073075</span><span class="sxs-lookup"><span data-stu-id="a8ad0-129">MSR – Magtek PN - 21073075</span></span>





