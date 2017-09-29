---
title: "Gerenciador de fontes contábeis"
description: "Este artigo fornece informações sobre o explorador de origem da contabilidade, que pode ser usado para análise detalhada das informações de origem, além das entradas contábeis da contabilidade."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 3f5ed28400f333776ce4a5de47ce52aed49094e3
ms.contentlocale: pt-br
ms.lasthandoff: 06/29/2017


---

# <a name="accounting-source-explorer"></a><span data-ttu-id="dc285-103">Gerenciador de fontes contábeis</span><span class="sxs-lookup"><span data-stu-id="dc285-103">Accounting source explorer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dc285-104">Este artigo fornece informações sobre o explorador de origem da contabilidade, que pode ser usado para análise detalhada das informações de origem, além das entradas contábeis da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="dc285-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="dc285-105">O explorador de origem contábil é uma nova página que mostra informações de origem.</span><span class="sxs-lookup"><span data-stu-id="dc285-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="dc285-106">Você pode usar o explorador de origem contábil como uma ferramenta independente ou analisar os detalhes das entradas de contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="dc285-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="dc285-107">Por exemplo, você pode usar o explorador de origem contábil para obter as informações mais detalhadas da origem para um saldo no rastreamento de saldos ou para uma transação do voucher.</span><span class="sxs-lookup"><span data-stu-id="dc285-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="dc285-108">Você pode usar o recurso Exportar para Ms Excel para dividir as informações no Microsoft Excel (por exemplo, em uma Tabela Dinâmica ou em um relatório de Tabela Dinâmica).</span><span class="sxs-lookup"><span data-stu-id="dc285-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="dc285-109">O explorador de origem contábil sempre exibe o valor total por conta contábil como é exibido pela contabilidade (por exemplo, no balancete).</span><span class="sxs-lookup"><span data-stu-id="dc285-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="dc285-110">Como no Balancete, é possível exibir segmentos nas colunas separadas.</span><span class="sxs-lookup"><span data-stu-id="dc285-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="dc285-111">Selecione o conjunto de dimensões financeiras apropriado.</span><span class="sxs-lookup"><span data-stu-id="dc285-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="dc285-112">É possível usar os parâmetros para definir um intervalo de datas para análise.</span><span class="sxs-lookup"><span data-stu-id="dc285-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="dc285-113">Esta funcionalidade também se assemelha à funcionalidade no Balancete.</span><span class="sxs-lookup"><span data-stu-id="dc285-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="dc285-114">Para todos os documentos que usam estrutura do documento de origem, o explorador da origem contábil exibe informações adicionais, com base nas distribuições contábeis e, se aplicável, em distribuições contábeis do projeto</span><span class="sxs-lookup"><span data-stu-id="dc285-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="dc285-115">Essas informações incluem o tipo de valor monetário, projeto, atividade, categoria e a linha de propriedade.</span><span class="sxs-lookup"><span data-stu-id="dc285-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="dc285-116">Veja alguns exemplos da análise que você pode fazer:</span><span class="sxs-lookup"><span data-stu-id="dc285-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="dc285-117">Variações entre ordens de compra e faturas de fornecedor, pois cada variação é representada por um tipo de valor monetário, como a variação de encargo</span><span class="sxs-lookup"><span data-stu-id="dc285-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="dc285-118">Horas faturáveis versus horas não faturáveis e despesas por projeto, unidade de negócios e conta principal</span><span class="sxs-lookup"><span data-stu-id="dc285-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="dc285-119">Para documentos de origem que usam o conceito das identidades de referência do documento de origem, o explorador de origem contábil exibe ainda mais detalhes, como o cliente, o fornecedor, o trabalhador, o produto, a quantidade, o texto de unidade e as descrições.</span><span class="sxs-lookup"><span data-stu-id="dc285-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="dc285-120">Veja alguns exemplos da análise que você pode fazer:</span><span class="sxs-lookup"><span data-stu-id="dc285-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="dc285-121">Despesas com hotéis por unidade de negócios e nome do hotel para um período fiscal, com base nos relatórios de despesas</span><span class="sxs-lookup"><span data-stu-id="dc285-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="dc285-122">Descontos por fornecedor, produtos, departamento</span><span class="sxs-lookup"><span data-stu-id="dc285-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="dc285-123">Para esses documentos, também é possível navegar no documento de origem real do explorador de origem contábil.</span><span class="sxs-lookup"><span data-stu-id="dc285-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>




