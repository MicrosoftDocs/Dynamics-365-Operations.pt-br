---
title: "Opções de relatório em Talent"
description: "Este tópico explica como resolver o problema onde um cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a><span data-ttu-id="e1318-103">Opções de relatório em Talent</span><span class="sxs-lookup"><span data-stu-id="e1318-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e1318-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="e1318-104">**Environment details**</span></span>

<span data-ttu-id="e1318-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="e1318-105">This issue applies to all environments.</span></span>

<span data-ttu-id="e1318-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="e1318-106">**Symptom**</span></span>

<span data-ttu-id="e1318-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="e1318-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="e1318-108">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e1318-108">**Issue**</span></span>

<span data-ttu-id="e1318-109">O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.</span><span class="sxs-lookup"><span data-stu-id="e1318-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="e1318-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="e1318-110">**Solution**</span></span>

- <span data-ttu-id="e1318-111">Os dados de Core HR que fluem para Common Data Service de aplicativos podem ser relatados por meio do conector PowerApps CDS para Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="e1318-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="e1318-112">Observe que Common Data Service para aplicativos contém um subconjunto de dados Core HR.</span><span class="sxs-lookup"><span data-stu-id="e1318-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="e1318-113">Para obter mais informações sobre Power BI e painéis, consulte [Criar relatórios do Power BI e painéis com Common Data Service do PowerApps](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="e1318-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="e1318-114">Relatório eletrônico (ER) está disponível para alguns relatórios no Talent.</span><span class="sxs-lookup"><span data-stu-id="e1318-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="e1318-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="e1318-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="e1318-116">Os dados podem ser exportados para Microsoft Excel ou Microsoft Word usando as diversas entidades de dados que Talent fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="e1318-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="e1318-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="e1318-117">**Long-term solution**</span></span>

<span data-ttu-id="e1318-118">As opções adicionais do Power BI estarão disponíveis, e mais dados e entidades serão parte de Common Data Service para aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e1318-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>

