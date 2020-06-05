---
title: Definir políticas de despesas
description: Você pode definir políticas de despesas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem no Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389706"
---
# <a name="define-expense-policies"></a><span data-ttu-id="63863-103">Definir políticas de despesas</span><span class="sxs-lookup"><span data-stu-id="63863-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63863-104">Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem.</span><span class="sxs-lookup"><span data-stu-id="63863-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="63863-105">A implementação de diretivas de despesas pode ajudá-lo a gerenciar as despesas de forma eficiente.</span><span class="sxs-lookup"><span data-stu-id="63863-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="63863-106">Por exemplo, você pode definir uma política para despesas de hotel em Nova Iorque, que determina que as despesas com hotéis por noite não poderão exceder USD 250.</span><span class="sxs-lookup"><span data-stu-id="63863-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="63863-107">Se um trabalhador enviar um relatório de despesas ou uma requisição de viagem em que a taxa de hospedagem exceda esse valor, o sistema notificará o</span><span class="sxs-lookup"><span data-stu-id="63863-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="63863-108">trabalhador que o valor da política para a despesa foi excedido.</span><span class="sxs-lookup"><span data-stu-id="63863-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="63863-109">É possível configurar a mensagem que o trabalhador receberá quando você</span><span class="sxs-lookup"><span data-stu-id="63863-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="63863-110">definir a política.</span><span class="sxs-lookup"><span data-stu-id="63863-110">define the policy.</span></span>      
        
<span data-ttu-id="63863-111">Você pode definir três tipos de política:</span><span class="sxs-lookup"><span data-stu-id="63863-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="63863-112">Aviso – permite que o trabalhador envie um relatório de despesas ou uma requisição de viagem, mas a despesa será marcada para todos os aprovadores e</span><span class="sxs-lookup"><span data-stu-id="63863-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="63863-113">para o relatório mais recente.</span><span class="sxs-lookup"><span data-stu-id="63863-113">for later reporting.</span></span>        

- <span data-ttu-id="63863-114">Erro – exige que o trabalhador revise a despesa para cumprimento da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="63863-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="63863-115">Justificativa – exige que o trabalhador ou um gerente insira uma justificativa para o excedente do valor da política antes do envio do relatório de despesas ou da requisição de viagem.</span><span class="sxs-lookup"><span data-stu-id="63863-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="63863-116">Dicas de política</span><span class="sxs-lookup"><span data-stu-id="63863-116">Policy tips</span></span>
<span data-ttu-id="63863-117">Aqui estão algumas sugestões que podem ajudá-lo ao criar novas políticas para gerenciamento de despesas.</span><span class="sxs-lookup"><span data-stu-id="63863-117">Here are a few suggestions that can assist you when creating new policies for expense management.</span></span> 
* <span data-ttu-id="63863-118">As políticas têm data de efetivação e não começarão a valer se a política for cria com uma data após a data que a despesa ocorreu.</span><span class="sxs-lookup"><span data-stu-id="63863-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="63863-119">Por exemplo, se você estiver criando uma nova política hoje para reforçar uma despesa de refeição máxima de $50, então qualquer despesas existentes inseridas a partir de ontem não serão verificadas contra esta política.</span><span class="sxs-lookup"><span data-stu-id="63863-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="63863-120">Ao criar uma política para uma categoria de despesa que pode ser especificada, considere adicionar uma condição para tipo de linha de despesa.</span><span class="sxs-lookup"><span data-stu-id="63863-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="63863-121">Algumas políticas, como a necessidade de um recibo pode não fazer sentido para linhas especificadas e deve ser aplicado apenas a linha do cabeçalho ou a uma linha não especificada.</span><span class="sxs-lookup"><span data-stu-id="63863-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 
* <span data-ttu-id="63863-122">Por padrão, as diretivas de gerenciamento de despesas são avaliadas com base na entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="63863-122">Expense management policies are evaluated against the source entity by default.</span></span> <span data-ttu-id="63863-123">Para cenários intercompanhia, você pode definir a diretiva a ser avaliada em relação à entidade de destino (entidade emprestada).</span><span class="sxs-lookup"><span data-stu-id="63863-123">For intercompany scenarios, you can set the policy to be evaluated against the destination entity (borrowing entity) instead.</span></span> <span data-ttu-id="63863-124">Para executar as diretivas em relação à entidade de destino, ative o recurso "Avaliar a diretiva de despesas em relação à entidade legal de empréstimo" no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="63863-124">To run the policies against the destination entity, turn on the "Evaluate Expense policy against borrowing legal entity" feature in the **Feature Management** workspace.</span></span>

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="63863-125">Quando avaliar políticas</span><span class="sxs-lookup"><span data-stu-id="63863-125">When to evaluate policies</span></span>

<span data-ttu-id="63863-126">Nos parâmetros de gerenciamento de despesas, há uma opção para avaliar as políticas de gerenciamento de despesas quando uma linha é salva ou quando um relatório de despesa é enviado.</span><span class="sxs-lookup"><span data-stu-id="63863-126">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="63863-127">Se você optar por avaliar quando uma linha é salva, isso garante que os usuários tenham uma visibilidade antecipada sobre o que precisam fazer para concluir seu relatório de despesas de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="63863-127">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="63863-128">Caso contrário, você pode atrasar a avaliação de política e economizar tempo se a validação ocorrer no final, durante envio ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="63863-128">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
