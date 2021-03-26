---
title: Visão geral do reconhecimento de receita
description: Este tópico fornece informações sobre o recurso Reconhecimento de receita. Este recurso fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita para ordens de vários elementos.
author: kweekley
manager: aolson
ms.date: 11/11/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b21cf04674d01df31dc3304886e7cda035bdcce2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238247"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="ca299-104">Visão geral do reconhecimento de receita</span><span class="sxs-lookup"><span data-stu-id="ca299-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca299-105">As empresas em setores que vendem vários elementos, como produtos, serviços, assinaturas etc., devem ter a capacidade de dividir ordens de vários elementos de modo que a receita possa ser reconhecida com base em um conjunto de diretrizes específicas da empresa e do setor.</span><span class="sxs-lookup"><span data-stu-id="ca299-105">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

> [!NOTE]
> <span data-ttu-id="ca299-106">O recurso Reconhecimento de receita não pode ser ativado por meio do Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="ca299-106">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="ca299-107">No momento, você deve usar as chaves de configuração para ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="ca299-107">Currently, you must use configuration keys to turn it on.</span></span>

> <span data-ttu-id="ca299-108">O reconhecimento de receita, incluindo a funcionalidade de pacote, não é compatível com o uso em canais do Commerce (comércio eletrônico, PDV, call center).</span><span class="sxs-lookup"><span data-stu-id="ca299-108">Revenue recognition, including bundle functionality, isn't supported for use in Commerce channels (e-commerce, POS, call center).</span></span> <span data-ttu-id="ca299-109">Os itens configurados com reconhecimento de receita não devem ser adicionados a ordens ou transações criadas em canais do Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca299-109">Items configured with revenue recognition should not be added to orders or transactions created in Commerce channels.</span></span>

<span data-ttu-id="ca299-110">Em geral, o processo de reconhecimento de receita pode ser usado para realizar estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="ca299-110">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="ca299-111">Alocar a receita, para ajudar a garantir que o preço adequado da receita seja reconhecido com base no valor dos componentes em ordens de vários elementos.</span><span class="sxs-lookup"><span data-stu-id="ca299-111">Allocate revenue, to help ensure that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="ca299-112">Adiar receita, com base em uma agenda de receita que representa o período e as porcentagens contratuais para reconhecer receitas ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="ca299-112">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="ca299-113">O vídeo [Como usar o reconhecimento de receita no Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (mostrado acima) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.</span><span class="sxs-lookup"><span data-stu-id="ca299-113">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="ca299-114">O recurso Reconhecimento de receita fornece uma estrutura flexível que permite definir regras específicas da empresa para reconhecer o preço de receita e a agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="ca299-114">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="ca299-115">Os produtos lançados são usados para dar suporte ao reconhecimento de receita em documentos de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="ca299-115">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="ca299-116">Os produtos lançados contêm a configuração necessária para determinar o preço de receita e a agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="ca299-116">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="ca299-117">A ordem de venda pode ser originária de um projeto de Tempo e materiais.</span><span class="sxs-lookup"><span data-stu-id="ca299-117">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="ca299-118">As empresas podem usar a funcionalidade de agenda de receita sem usar a funcionalidade de preço de receita.</span><span class="sxs-lookup"><span data-stu-id="ca299-118">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="ca299-119">Portanto, o preço nas linhas de ordem de venda será usado como receita ou receita adiada.</span><span class="sxs-lookup"><span data-stu-id="ca299-119">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="ca299-120">Se houver uma agenda de receita na linha de ordem de venda, preço na linha de ordem de venda será adiado.</span><span class="sxs-lookup"><span data-stu-id="ca299-120">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="ca299-121">Se não houver uma agenda de receita na linha de ordem de venda, o preço na linha de ordem de venda será lançado em uma conta de receita quando for faturada.</span><span class="sxs-lookup"><span data-stu-id="ca299-121">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="ca299-122">O preço de receita será calculado alguém quando a ordem de venda for confirmada ou a fatura for lançada.</span><span class="sxs-lookup"><span data-stu-id="ca299-122">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="ca299-123">Para visualizar o preço de receita antes que a fatura seja lançada, você deverá confirmar a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="ca299-123">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="ca299-124">Quando a ordem de venda for confirmada, uma agenda de receita prevista também será criada se qualquer linha de ordem de venda tiver uma agenda de receita.</span><span class="sxs-lookup"><span data-stu-id="ca299-124">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="ca299-125">Quando a ordem de venda for faturada, a agenda de receita prevista será excluída e substituída pela agenda real de reconhecimento de receita.</span><span class="sxs-lookup"><span data-stu-id="ca299-125">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="ca299-126">Os detalhes da agenda de reconhecimento de receita são mantidos para cada linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="ca299-126">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="ca299-127">Portanto, o gerente de reconhecimento de receita poderá exibir os detalhes e pode liberar linhas para a receita quando a obrigação contratual for concluída.</span><span class="sxs-lookup"><span data-stu-id="ca299-127">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="ca299-128">No final de cada período, o gerente de reconhecimento de receita poderá criar um diário de receita para liberar linhas da agenda que estão vencidas ou antes de uma data que definirem.</span><span class="sxs-lookup"><span data-stu-id="ca299-128">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date they define.</span></span> <span data-ttu-id="ca299-129">Esse diário de receita não é lançado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ca299-129">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="ca299-130">Portanto, o gerente de reconhecimento de receita poderá verificar se os valores corretos estão sendo liberados da receita adiada para a receita real.</span><span class="sxs-lookup"><span data-stu-id="ca299-130">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="ca299-131">Se uma alteração contratual fizer com que uma nova linha de ordem de venda seja adicionada à ordem de venda existente ou a uma nova ordem de venda, um processo de realocação pode ser executado para corrigir o preço de receita em todas as linhas das ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="ca299-131">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]