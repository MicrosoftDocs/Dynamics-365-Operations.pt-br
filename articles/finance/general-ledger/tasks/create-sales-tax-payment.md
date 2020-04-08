---
title: Criar um pagamento de imposto
description: Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139912"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="977c8-103">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="977c8-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="977c8-104">Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.</span><span class="sxs-lookup"><span data-stu-id="977c8-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="977c8-105">Vá para Imposto > Declarações > Imposto > Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="977c8-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="977c8-106">No campo Período de liquidação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="977c8-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="977c8-107">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="977c8-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="977c8-108">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="977c8-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="977c8-109">Se a opção Incluir correções não estiver marcada na página Parâmetros da contabilidade, o pagamento pode ser processado para várias versões.</span><span class="sxs-lookup"><span data-stu-id="977c8-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="977c8-110">O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="977c8-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="977c8-111">As últimas correções estabelecerão as transações de imposto sobre vendas que foram lançadas depois que a versão original foi criada.</span><span class="sxs-lookup"><span data-stu-id="977c8-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="977c8-112">No campo Transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="977c8-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="977c8-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="977c8-113">Click OK.</span></span>

