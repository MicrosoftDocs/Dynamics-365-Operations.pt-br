---
title: Reduzir os dias em taxas de subscrição
description: Para reduzir o número de dias de uma taxa de subscrição existente, você pode criar uma nova transação e remover o período que não deverá mais fazer parte do intervalo da taxa de subscrição.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd76e30b14d0fd21617e0ab7d892ba5ea3e89f2f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217301"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="43a45-103">Reduzir os dias em taxas de subscrição</span><span class="sxs-lookup"><span data-stu-id="43a45-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="43a45-104">Para reduzir o número de dias de uma taxa de subscrição existente, você pode criar uma nova transação e remover o período que não deverá mais fazer parte do intervalo da taxa de subscrição.</span><span class="sxs-lookup"><span data-stu-id="43a45-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="43a45-105">Reduzir os dias de uma taxa de subscrição</span><span class="sxs-lookup"><span data-stu-id="43a45-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="43a45-106">Clique em **Gerenciamento de serviço** \> **Comum** \> **Subscrições de serviço** \> **Todas as subscrições de serviço**.</span><span class="sxs-lookup"><span data-stu-id="43a45-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="43a45-107">Selecione a subscrição no serviço e, no Painel de Ação, clique em **Taxas de subscrição**.</span><span class="sxs-lookup"><span data-stu-id="43a45-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="43a45-108">No campo **Tipo de subscrição**, selecione **Dias de redução**.</span><span class="sxs-lookup"><span data-stu-id="43a45-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="43a45-109">Use os campos **Data inicial** e **Data final** para definir o intervalo de datas da taxa de subscrição que você deseja remover do período dessa taxa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="43a45-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="43a45-110">Para exibir a transação criada, no formulário **Inscrição**, clique em **Transações de taxa**.</span><span class="sxs-lookup"><span data-stu-id="43a45-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="43a45-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="43a45-111">Example</span></span>

<span data-ttu-id="43a45-112">Se o período de uma transação de subscrição for de 1 a 31 de janeiro, e você desejar reduzi-lo em 10 dias, crie uma nova transação na qual o período de redução seja de 1 a 10 de janeiro.</span><span class="sxs-lookup"><span data-stu-id="43a45-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="43a45-113">(Esse período também poderia ser de 5 a 15 de janeiro, ou qualquer outro período de dez dias).</span><span class="sxs-lookup"><span data-stu-id="43a45-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="43a45-114">Além disso, se o campo **Data inicial** do período de redução for igual a 21 de janeiro (31 menos 10), você poderá definir o campo **Data final** como qualquer data após 31 de janeiro, e 10 dias ainda serão removidos do período da transação a taxa.</span><span class="sxs-lookup"><span data-stu-id="43a45-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="43a45-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="43a45-115">See also</span></span>

[<span data-ttu-id="43a45-116">Exemplo de dias de redução</span><span class="sxs-lookup"><span data-stu-id="43a45-116">Reduction days example</span></span>](reduction-days-example.md)

  


