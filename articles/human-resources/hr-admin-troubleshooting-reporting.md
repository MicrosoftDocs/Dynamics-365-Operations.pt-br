---
title: Opções de relatório
description: Este artigo explica como resolver o problema em que um cliente deseja personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5d47524033bf39a1db6b22b28ee3fcc65348829c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431006"
---
# <a name="reporting-options"></a><span data-ttu-id="243db-103">Opções de relatório</span><span class="sxs-lookup"><span data-stu-id="243db-103">Reporting options</span></span>

<span data-ttu-id="243db-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="243db-104">**Environment details**</span></span>

<span data-ttu-id="243db-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="243db-105">This issue applies to all environments.</span></span>

<span data-ttu-id="243db-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="243db-106">**Symptom**</span></span>

<span data-ttu-id="243db-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="243db-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="243db-108">**Saída**</span><span class="sxs-lookup"><span data-stu-id="243db-108">**Issue**</span></span>

<span data-ttu-id="243db-109">O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.</span><span class="sxs-lookup"><span data-stu-id="243db-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="243db-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="243db-110">**Solution**</span></span>

- <span data-ttu-id="243db-111">Os dados do Human Resources que fluem para o Common Data Service podem ser relatados por meio do conector Power Apps Common Data Service para o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="243db-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="243db-112">Observe que o Common Data Service contém um subconjunto de dados do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="243db-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="243db-113">Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="243db-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="243db-114">O relatório eletrônico (ER) está disponível para alguns relatórios no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="243db-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="243db-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="243db-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="243db-116">Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Human Resources fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="243db-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="243db-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="243db-117">**Long-term solution**</span></span>

<span data-ttu-id="243db-118">Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="243db-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
