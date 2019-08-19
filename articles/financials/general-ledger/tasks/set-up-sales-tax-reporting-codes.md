---
title: Configurar códigos de relatório de imposto
description: Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 830a3465944b32cc17feee60e3cbc5ad0a4dc9d7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834764"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="7bfa5-103">Configurar códigos de relatório de imposto</span><span class="sxs-lookup"><span data-stu-id="7bfa5-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7bfa5-104">Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="7bfa5-105">São usados em layouts de relatório específicos do país e o Pagamento de imposto sobre vendas por código de relatório para imprimir valores de imposto sobre vendas para um período de liquidação resumidos por código de relatório.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="7bfa5-106">Depois que você criar os Códigos de relatórios de imposto sobre vendas, poderá fazer referência a eles na guia rápida de configuração Relatório na página Código de imposto.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="7bfa5-107">Este registro usa a empresa de dados de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-107">This recording uses the DEMF demo company.</span></span>



1. <span data-ttu-id="7bfa5-108">Vá para Imposto > Configurações > Impostos > Códigos de relatório de impostos.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-108">Go to Tax > Setup > Sales tax > Sales tax reporting codes.</span></span>
2. <span data-ttu-id="7bfa5-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-109">Click New.</span></span>
3. <span data-ttu-id="7bfa5-110">Selecione o layout de relatório ao qual o código se refere.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-110">Select the report layout that the reporting code belongs to.</span></span>
    * <span data-ttu-id="7bfa5-111">Esse layout é usado para filtrar os códigos de relatórios disponíveis para um código de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="7bfa5-112">Cada código de imposto sobre vendas pertence a um período de liquidação que pertence a uma autoridade de imposto sobre vendas que usa um layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="7bfa5-113">Insira um número que seja referenciado em um relatório de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-113">Enter a number that refers to a field on a sales tax report.</span></span>
5. <span data-ttu-id="7bfa5-114">No campo de texto Relatório, insira uma descrição para a exibição nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-114">In the Report text field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="7bfa5-115">No campo Descrição breve, digite uma descrição para fins internos.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-115">In the Brief description field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="7bfa5-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7bfa5-116">Click Save.</span></span>

