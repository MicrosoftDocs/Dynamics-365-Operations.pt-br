--- 
title: Criar um pagamento de imposto
description: "Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9b6e60ff6465ef0bddda2e93b07f41e47f2e1ddd
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="42854-103">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="42854-103">Create a sales tax payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42854-104">Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.</span><span class="sxs-lookup"><span data-stu-id="42854-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="42854-105">Vá para Imposto > Declarações > Imposto > Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="42854-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="42854-106">No campo Período de liquidação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="42854-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="42854-107">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="42854-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="42854-108">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="42854-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="42854-109">Se a opção Incluir correções não estiver marcada na página Parâmetros da contabilidade, o pagamento pode ser processado para várias versões.</span><span class="sxs-lookup"><span data-stu-id="42854-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="42854-110">O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="42854-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="42854-111">As últimas correções estabelecerão as transações de imposto sobre vendas que foram lançadas depois que a versão original foi criada.</span><span class="sxs-lookup"><span data-stu-id="42854-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="42854-112">No campo Transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="42854-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="42854-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="42854-113">Click OK.</span></span>


