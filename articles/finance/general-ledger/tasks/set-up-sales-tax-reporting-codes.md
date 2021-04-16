---
title: Configurar códigos de relatório de imposto
description: Os Códigos de relatório de imposto fazem referência a um número listado um relatório de imposto.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e040bac6ef9e950e8d7f97e3c136636acf1fe43
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813522"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="11cd0-103">Configurar códigos de relatório de imposto</span><span class="sxs-lookup"><span data-stu-id="11cd0-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="11cd0-104">Os Códigos de relatório de imposto fazem referência a um número listado um relatório de imposto.</span><span class="sxs-lookup"><span data-stu-id="11cd0-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="11cd0-105">Eles são usados em layouts de relatório específicos de um país/região.</span><span class="sxs-lookup"><span data-stu-id="11cd0-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="11cd0-106">Eles também são usados no relatório Pagamento de imposto por código.</span><span class="sxs-lookup"><span data-stu-id="11cd0-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="11cd0-107">Esse relatório mostra os valores de imposto para um período de liquidação resumido para cada código de relatório.</span><span class="sxs-lookup"><span data-stu-id="11cd0-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="11cd0-108">Depois que você criar os Códigos de relatórios de imposto, poderá fazer referência a eles nas Guias Rápidas Configuração de relatório, que podem ser acessadas na página **Código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="11cd0-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="11cd0-109">Este registro usa a empresa de dados de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="11cd0-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="11cd0-110">No **Painel de navegação**, acesse **Imposto > Configuração > Imposto > Códigos de relatório de imposto**.</span><span class="sxs-lookup"><span data-stu-id="11cd0-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="11cd0-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="11cd0-111">Click **New**.</span></span>
3. <span data-ttu-id="11cd0-112">Selecione o layout de relatório ao qual o código se refere.</span><span class="sxs-lookup"><span data-stu-id="11cd0-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="11cd0-113">Esse layout é usado para filtrar os códigos de relatórios disponíveis para um código de imposto.</span><span class="sxs-lookup"><span data-stu-id="11cd0-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="11cd0-114">Cada código de imposto pertence a um período de liquidação que pertence a uma Autoridade de imposto que usa um layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="11cd0-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="11cd0-115">No campo **Código do relatório**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="11cd0-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="11cd0-116">No campo **Texto do relatório**, insira uma descrição para a exibição nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="11cd0-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="11cd0-117">No campo **Descrição breve**, digite uma descrição para fins internos.</span><span class="sxs-lookup"><span data-stu-id="11cd0-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="11cd0-118">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="11cd0-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]