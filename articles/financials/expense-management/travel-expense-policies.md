---
title: "Definir políticas de despesas"
description: "Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: b0f9a5ca275944aeb27798a2f3377356319589c7
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="expense-policies"></a><span data-ttu-id="7ee42-103">Diretivas de despesas</span><span class="sxs-lookup"><span data-stu-id="7ee42-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7ee42-104">Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem.</span><span class="sxs-lookup"><span data-stu-id="7ee42-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="7ee42-105">A implementação de diretivas de despesas pode ajudá-lo a gerenciar as despesas de forma eficiente.</span><span class="sxs-lookup"><span data-stu-id="7ee42-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="7ee42-106">Por exemplo, você pode definir uma política para despesas de hotel em Nova Iorque, que determina que as despesas com hotéis por noite não poderão exceder USD 250.</span><span class="sxs-lookup"><span data-stu-id="7ee42-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="7ee42-107">Se um trabalhador enviar um relatório de despesas ou uma requisição de viagem na qual a taxa do quarto excede esse valor, o sistema notificará o trabalhador de que o valor da política da despesa foi excedido.</span><span class="sxs-lookup"><span data-stu-id="7ee42-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="7ee42-108">É possível configurar a mensagem que o trabalhador receberá quando você definir a política.</span><span class="sxs-lookup"><span data-stu-id="7ee42-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="7ee42-109">Você pode definir três tipos de política:</span><span class="sxs-lookup"><span data-stu-id="7ee42-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="7ee42-110">Aviso – permite que o trabalhador envie um relatório de despesas ou uma requisição de viagem, mas a despesa será marcada para todos os aprovadores e</span><span class="sxs-lookup"><span data-stu-id="7ee42-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="7ee42-111">para o relatório mais recente.</span><span class="sxs-lookup"><span data-stu-id="7ee42-111">for later reporting.</span></span> 
 - <span data-ttu-id="7ee42-112">Erro – exige que o trabalhador revise a despesa para cumprimento da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="7ee42-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="7ee42-113">Justificativa – exige que o trabalhador ou um gerente insira uma justificativa para o excedente do valor da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="7ee42-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="7ee42-114">Você também pode configurar um intervalo de datas no qual as políticas de despesas estão em vigor.</span><span class="sxs-lookup"><span data-stu-id="7ee42-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="7ee42-115">Por exemplo, as tarifas aéreas para voos entre a Dinamarca e Nova Iorque podem ser caras durante a estação de pico de viagens de férias.</span><span class="sxs-lookup"><span data-stu-id="7ee42-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="7ee42-116">Você pode definir uma regra de despesas com voos que restrinja o custo dos voos para Nova Iorque a um limite de DKK 5000 e pode especificar que essa regra estará em vigor entre 15 de março e 15 de setembro.</span><span class="sxs-lookup"><span data-stu-id="7ee42-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

