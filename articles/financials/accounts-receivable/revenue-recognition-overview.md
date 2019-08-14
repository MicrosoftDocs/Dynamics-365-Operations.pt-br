---
title: Visão geral do reconhecimento de receita
description: Este tópico fornece informações sobre o recurso Reconhecimento de receita. Este recurso fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita para ordens de vários elementos.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863554"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="de72b-104">Visão geral do reconhecimento de receita</span><span class="sxs-lookup"><span data-stu-id="de72b-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="de72b-105">O recurso Reconhecimento de receita ainda não pode ser ativado por meio do Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="de72b-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="de72b-106">No momento, você deve usar as chaves de configuração para ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="de72b-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="de72b-107">As empresas em setores que vendem vários elementos, como produtos, serviços, assinaturas, etc, devem ter a capacidade de dividir ordens de vários elementos de modo que a receita possa ser reconhecida com base em um conjunto de diretrizes específicas da empresa e específicas do setor.</span><span class="sxs-lookup"><span data-stu-id="de72b-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="de72b-108">Em geral, o processo de reconhecimento de receita pode ser usado para realizar estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="de72b-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="de72b-109">Alocar a receita, para ajudar a garantir que o preço adequado da receita seja reconhecido com base no valor dos componentes em ordens de vários elementos.</span><span class="sxs-lookup"><span data-stu-id="de72b-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized based on the value of the components on the multi-element orders.</span></span>
* <span data-ttu-id="de72b-110">Adiar receita, com base em uma agenda de receita que representa o período e as porcentagens contratuais para reconhecer receitas ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="de72b-110">Defer revenue, based on a revenue schedule that represents the contractual timeframe and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="de72b-111">O recurso Reconhecimento de receita fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="de72b-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="de72b-112">Os produtos lançados são usados para dar suporte ao reconhecimento de receita em documentos de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de72b-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="de72b-113">Os produtos lançados contêm a configuração necessária para determinar o preço de receita e a agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="de72b-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="de72b-114">A ordem de venda pode ser originária de um projeto de Tempo e material.</span><span class="sxs-lookup"><span data-stu-id="de72b-114">The sales order can originate from a Time and material project.</span></span>

<span data-ttu-id="de72b-115">As empresas podem usar a funcionalidade de agenda de receita sem usar a funcionalidade de preço de receita.</span><span class="sxs-lookup"><span data-stu-id="de72b-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="de72b-116">Portanto, o preço nas linhas de ordem de venda será usado como receita ou receita adiada.</span><span class="sxs-lookup"><span data-stu-id="de72b-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="de72b-117">Se houver uma agenda de receita na linha de ordem de venda, preço na linha de ordem de venda será adiado.</span><span class="sxs-lookup"><span data-stu-id="de72b-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="de72b-118">Se não houver uma agenda de receita na linha de ordem de venda, o preço na linha de ordem de venda será lançado em uma conta de receita quando for faturada.</span><span class="sxs-lookup"><span data-stu-id="de72b-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="de72b-119">O preço de receita será calculado alguém quando a ordem de venda for confirmada ou a fatura for lançada.</span><span class="sxs-lookup"><span data-stu-id="de72b-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="de72b-120">Para visualizar o preço de receita antes que a fatura seja lançada, você deverá confirmar a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de72b-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="de72b-121">Quando a ordem de venda for confirmada, uma agenda de receita prevista também será criada se qualquer linha de ordem de venda contiver uma agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="de72b-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line contains a revenue schedule.</span></span> <span data-ttu-id="de72b-122">Quando a ordem de venda for faturada, a agenda de receita prevista será excluída e será substituída pela agenda real de reconhecimento de receita.</span><span class="sxs-lookup"><span data-stu-id="de72b-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="de72b-123">Os detalhes da agenda de reconhecimento de receita são mantidos para cada linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de72b-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="de72b-124">Portanto, o gerente de reconhecimento de receita poderá exibir os detalhes e pode liberar linhas para a receita quando a obrigação contratual for concluída.</span><span class="sxs-lookup"><span data-stu-id="de72b-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="de72b-125">No final de cada período, o gerente de reconhecimento de receita poderá criar um diário de receita para liberar linhas da agenda que estão vencidas ou antes de uma data que ele definir.</span><span class="sxs-lookup"><span data-stu-id="de72b-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="de72b-126">Esse diário de receita não é lançado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="de72b-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="de72b-127">Portanto, o gerente de reconhecimento de receita poderá verificar se os valores corretos estão sendo liberados da receita adiada para a receita real.</span><span class="sxs-lookup"><span data-stu-id="de72b-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="de72b-128">Se uma alteração contratual fizer com que uma nova linha de ordem de venda seja adicionada à ordem de venda existente a uma nova ordem de venda, um processo a realocação pode ser executado para corrigir o preço de receita em todas as linhas das ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="de72b-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines the sales orders.</span></span>
