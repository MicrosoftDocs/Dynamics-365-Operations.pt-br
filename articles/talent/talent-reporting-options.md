---
title: Opções de relatório em Talent
description: Este tópico explica como resolver o problema onde um cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303318"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="1df8e-103">Opções de relatório no Talent</span><span class="sxs-lookup"><span data-stu-id="1df8e-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1df8e-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="1df8e-104">**Environment details**</span></span>

<span data-ttu-id="1df8e-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="1df8e-105">This issue applies to all environments.</span></span>

<span data-ttu-id="1df8e-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="1df8e-106">**Symptom**</span></span>

<span data-ttu-id="1df8e-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="1df8e-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="1df8e-108">**Saída**</span><span class="sxs-lookup"><span data-stu-id="1df8e-108">**Issue**</span></span>

<span data-ttu-id="1df8e-109">O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.</span><span class="sxs-lookup"><span data-stu-id="1df8e-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="1df8e-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="1df8e-110">**Solution**</span></span>

- <span data-ttu-id="1df8e-111">Os dados de Core HR que fluem para o Common Data Service para aplicativos podem ser relatados por meio do conector PowerApps CDS para o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="1df8e-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="1df8e-112">Observe que o Common Data Service para aplicativos contém um subconjunto de dados Core HR.</span><span class="sxs-lookup"><span data-stu-id="1df8e-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="1df8e-113">Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="1df8e-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="1df8e-114">Relatório eletrônico (ER) está disponível para alguns relatórios no Talent.</span><span class="sxs-lookup"><span data-stu-id="1df8e-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="1df8e-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="1df8e-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="1df8e-116">Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Talent fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1df8e-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="1df8e-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="1df8e-117">**Long-term solution**</span></span>

<span data-ttu-id="1df8e-118">As opções adicionais do Power BI estarão disponíveis, e mais dados e entidades serão parte do Common Data Service para aplicativos.</span><span class="sxs-lookup"><span data-stu-id="1df8e-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>
