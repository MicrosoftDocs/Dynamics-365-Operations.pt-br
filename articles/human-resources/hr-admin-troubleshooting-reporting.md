---
title: Opções de relatório
description: Este artigo explica como resolver o problema em que um cliente deseja personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a03724d81745373d028d76a8cc64aab66efdbb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053290"
---
# <a name="reporting-options"></a><span data-ttu-id="3c824-103">Opções de relatório</span><span class="sxs-lookup"><span data-stu-id="3c824-103">Reporting options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3c824-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="3c824-104">**Environment details**</span></span>

<span data-ttu-id="3c824-105">Esse problema aplica-se a todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="3c824-105">This issue applies to all environments.</span></span>

<span data-ttu-id="3c824-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="3c824-106">**Symptom**</span></span>

<span data-ttu-id="3c824-107">O cliente quer personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.</span><span class="sxs-lookup"><span data-stu-id="3c824-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="3c824-108">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3c824-108">**Issue**</span></span>

<span data-ttu-id="3c824-109">O usuário não pode personalizar os relatórios do Microsoft Power BI inseridos.</span><span class="sxs-lookup"><span data-stu-id="3c824-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="3c824-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="3c824-110">**Solution**</span></span>

- <span data-ttu-id="3c824-111">Os dados do Human Resources que fluem para o Dataverse podem ser relatados por meio do conector Power Apps Dataverse para o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="3c824-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="3c824-112">Observe que o Dataverse contém um subconjunto de dados do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3c824-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="3c824-113">Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="3c824-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="3c824-114">O relatório eletrônico (ER) está disponível para alguns relatórios no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3c824-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="3c824-115">Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.</span><span class="sxs-lookup"><span data-stu-id="3c824-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="3c824-116">Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Human Resources fornece por meio da integração do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="3c824-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="3c824-117">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="3c824-117">**Long-term solution**</span></span>

<span data-ttu-id="3c824-118">Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3c824-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]