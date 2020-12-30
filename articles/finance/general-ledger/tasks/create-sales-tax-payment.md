---
title: Criar um pagamento de imposto
description: O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.
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
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7aec00c2fb657f0b4074063ef7acad5f4372ebca
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646326"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="39be7-103">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="39be7-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39be7-104">O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.</span><span class="sxs-lookup"><span data-stu-id="39be7-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="39be7-105">Vá para **Imposto > Declarações > Imposto > Liquidar e lançar imposto**.</span><span class="sxs-lookup"><span data-stu-id="39be7-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="39be7-106">No campo **Período de liquidação**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39be7-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="39be7-107">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="39be7-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="39be7-108">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="39be7-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="39be7-109">Se você não selecionar **Incluir correções** na página **Parâmetros da contabilidade**, a liquidação pode ser processada para várias versões.</span><span class="sxs-lookup"><span data-stu-id="39be7-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="39be7-110">O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="39be7-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="39be7-111">As últimas correções estabelecerão as transações de imposto que foram lançadas depois que a versão original foi criada.</span><span class="sxs-lookup"><span data-stu-id="39be7-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="39be7-112">No campo **Data de transação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="39be7-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="39be7-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39be7-113">Click **OK**.</span></span>

