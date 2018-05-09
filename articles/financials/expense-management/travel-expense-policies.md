---
title: "Definir políticas de despesas"
description: "Você pode definir políticas de despesas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem no Microsoft Dynamics 365 for Finance and Operations."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 062d6f01bb07324ad5b8dc6b9fd7617756502c17
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="expense-policies"></a><span data-ttu-id="521fb-103">Diretivas de despesas</span><span class="sxs-lookup"><span data-stu-id="521fb-103">Expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="521fb-104">Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem.</span><span class="sxs-lookup"><span data-stu-id="521fb-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="521fb-105">A implementação de diretivas de despesas pode ajudá-lo a gerenciar as despesas de forma eficiente.</span><span class="sxs-lookup"><span data-stu-id="521fb-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="521fb-106">Por exemplo, você pode definir uma política para despesas de hotel em Nova Iorque, que determina que as despesas com hotéis por noite não poderão exceder USD 250.</span><span class="sxs-lookup"><span data-stu-id="521fb-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="521fb-107">Se um trabalhador enviar um relatório de despesas ou uma requisição de viagem em que a taxa de hospedagem exceda esse valor, o sistema notificará o</span><span class="sxs-lookup"><span data-stu-id="521fb-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="521fb-108">trabalhador que o valor da política para a despesa foi excedido.</span><span class="sxs-lookup"><span data-stu-id="521fb-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="521fb-109">É possível configurar a mensagem que o trabalhador receberá quando você</span><span class="sxs-lookup"><span data-stu-id="521fb-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="521fb-110">definir a política.</span><span class="sxs-lookup"><span data-stu-id="521fb-110">define the policy.</span></span>      
        
<span data-ttu-id="521fb-111">Você pode definir três tipos de política:</span><span class="sxs-lookup"><span data-stu-id="521fb-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="521fb-112">Aviso – permite que o trabalhador envie um relatório de despesas ou uma requisição de viagem, mas a despesa será marcada para todos os aprovadores e</span><span class="sxs-lookup"><span data-stu-id="521fb-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="521fb-113">para o relatório mais recente.</span><span class="sxs-lookup"><span data-stu-id="521fb-113">for later reporting.</span></span>        

- <span data-ttu-id="521fb-114">Erro – exige que o trabalhador revise a despesa para cumprimento da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="521fb-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
  - <span data-ttu-id="521fb-115">Justificativa – exige que o trabalhador ou um gerente insira uma justificativa para o excedente do valor da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="521fb-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
  <span data-ttu-id="521fb-116">Você também pode configurar um intervalo de datas no qual as políticas de despesas estão em vigor.</span><span class="sxs-lookup"><span data-stu-id="521fb-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="521fb-117">Por exemplo, tarifas aéreas para voos entre a Dinamarca</span><span class="sxs-lookup"><span data-stu-id="521fb-117">For example, airline fares for flights between Denmark</span></span>      
  <span data-ttu-id="521fb-118">e a cidade de Nova Iorque podem ser dispendiosas durante a estação de pico de viagens de férias.</span><span class="sxs-lookup"><span data-stu-id="521fb-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="521fb-119">É possível definir uma regra de despesas com voos que restrinja o</span><span class="sxs-lookup"><span data-stu-id="521fb-119">You can define a flight expense rule that restricts the</span></span>      
  <span data-ttu-id="521fb-120">custo dos voos para a cidade de Nova Iorque a um limite de DKK 5000, e você pode especificar que essa regra esteja em vigor entre 15 de março e</span><span class="sxs-lookup"><span data-stu-id="521fb-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
  <span data-ttu-id="521fb-121">15 de setembro.</span><span class="sxs-lookup"><span data-stu-id="521fb-121">September 15.</span></span>

