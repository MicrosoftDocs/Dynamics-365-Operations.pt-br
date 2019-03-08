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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d72c88d6ba851e96ca07b896630549690e9396
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "321745"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="efc24-103">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="efc24-103">Create a sales tax payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efc24-104">Os saldos de impostos sobre vendas dos acordos de trabalho do imposto sobre vendas liquidados e lançamentos nas contas de impostos sobre vendas deslocam-se para a liquidação do imposto sobre vendas de um determinado período.</span><span class="sxs-lookup"><span data-stu-id="efc24-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="efc24-105">Vá para Imposto > Declarações > Imposto > Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="efc24-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="efc24-106">No campo Período de liquidação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efc24-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="efc24-107">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="efc24-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="efc24-108">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="efc24-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="efc24-109">Se a opção Incluir correções não estiver marcada na página Parâmetros da contabilidade, o pagamento pode ser processado para várias versões.</span><span class="sxs-lookup"><span data-stu-id="efc24-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="efc24-110">O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="efc24-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="efc24-111">As últimas correções estabelecerão as transações de imposto sobre vendas que foram lançadas depois que a versão original foi criada.</span><span class="sxs-lookup"><span data-stu-id="efc24-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="efc24-112">No campo Transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="efc24-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="efc24-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="efc24-113">Click OK.</span></span>

