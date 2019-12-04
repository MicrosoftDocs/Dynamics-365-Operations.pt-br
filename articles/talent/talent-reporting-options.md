---
title: Opções de relatório em Talent
description: Este tópico explica como resolver o problema onde um cliente quer personalizar relatórios do Microsoft Dynamics 365 Talent ou criar novos relatórios.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ecbeb03b535f19131ddc6649d005702876bab65c
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772956"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="8d45f-103">Opções de relatório no Talent</span><span class="sxs-lookup"><span data-stu-id="8d45f-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8d45f-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="8d45f-104">**Environment details**</span></span>

<span data-ttu-id="8d45f-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="8d45f-105">This issue applies to all environments.</span></span>

<span data-ttu-id="8d45f-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="8d45f-106">**Symptom**</span></span>

<span data-ttu-id="8d45f-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 Talent ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="8d45f-107">The customer wants to customize Microsoft Dynamics 365 Talent reports or create new reports.</span></span>

<span data-ttu-id="8d45f-108">**Saída**</span><span class="sxs-lookup"><span data-stu-id="8d45f-108">**Issue**</span></span>

<span data-ttu-id="8d45f-109">O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.</span><span class="sxs-lookup"><span data-stu-id="8d45f-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="8d45f-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="8d45f-110">**Solution**</span></span>

- <span data-ttu-id="8d45f-111">Os dados do Core HR que fluem para o Common Data Service podem ser relatados por meio do conector Power Apps Common Data Service para o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="8d45f-111">The Core HR data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="8d45f-112">Observe que o Common Data Service contém um subconjunto de dados do Core HR.</span><span class="sxs-lookup"><span data-stu-id="8d45f-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="8d45f-113">Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="8d45f-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="8d45f-114">Relatório eletrônico (ER) está disponível para alguns relatórios no Talent.</span><span class="sxs-lookup"><span data-stu-id="8d45f-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="8d45f-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="8d45f-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="8d45f-116">Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Talent fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="8d45f-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="8d45f-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="8d45f-117">**Long-term solution**</span></span>

<span data-ttu-id="8d45f-118">Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8d45f-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
