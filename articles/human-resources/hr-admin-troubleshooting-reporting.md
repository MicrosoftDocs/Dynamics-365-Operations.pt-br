---
title: Opções de relatório
description: Este artigo explica como resolver o problema em que um cliente deseja personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 830c8c32128a8dfc1b009557afb272e48ae3a1ff
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111456"
---
# <a name="reporting-options"></a><span data-ttu-id="ccf5c-103">Opções de relatório</span><span class="sxs-lookup"><span data-stu-id="ccf5c-103">Reporting options</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="ccf5c-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="ccf5c-104">**Environment details**</span></span>

<span data-ttu-id="ccf5c-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-105">This issue applies to all environments.</span></span>

<span data-ttu-id="ccf5c-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="ccf5c-106">**Symptom**</span></span>

<span data-ttu-id="ccf5c-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="ccf5c-108">**Saída**</span><span class="sxs-lookup"><span data-stu-id="ccf5c-108">**Issue**</span></span>

<span data-ttu-id="ccf5c-109">O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="ccf5c-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="ccf5c-110">**Solution**</span></span>

- <span data-ttu-id="ccf5c-111">Os dados do Human Resources que fluem para o Dataverse podem ser relatados por meio do conector Power Apps Dataverse para o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="ccf5c-112">Observe que o Dataverse contém um subconjunto de dados do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="ccf5c-113">Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="ccf5c-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="ccf5c-114">O relatório eletrônico (ER) está disponível para alguns relatórios no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="ccf5c-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="ccf5c-116">Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Human Resources fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="ccf5c-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="ccf5c-117">**Long-term solution**</span></span>

<span data-ttu-id="ccf5c-118">Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ccf5c-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>
