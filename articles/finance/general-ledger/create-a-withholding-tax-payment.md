---
title: Criar um pagamento de imposto retido na fonte
description: O procedimento de trabalho de pagamento de imposto retido na fonte liquida os saldos de imposto retido na fonte de Contas a pagar em contas de imposto retido na fonte e os desloca para a conta de liquidação de imposto retido na fonte por determinado período. Este tópico lista as etapas para a configuração de um pagamento de imposto retido na fonte.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: e522711340b663bd849825b3d4dd2b7e78e4737c
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060702"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="4879f-104">Criar um pagamento de imposto retido na fonte</span><span class="sxs-lookup"><span data-stu-id="4879f-104">Create a withholding tax payment</span></span>

<span data-ttu-id="4879f-105">O procedimento de trabalho de pagamento de imposto retido na fonte liquida os saldos de imposto retido na fonte de Contas a pagar em contas de imposto retido na fonte e os desloca para a conta de liquidação de imposto retido na fonte por determinado período.</span><span class="sxs-lookup"><span data-stu-id="4879f-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="4879f-106">Este tópico lista as etapas para a configuração de um pagamento de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="4879f-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="4879f-107">A contrapartida de imposto retido na fonte (de contas a receber) não é levada em conta quando é calculado um pagamento de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="4879f-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="4879f-108">Acesse **Painel de navegação > Módulos > Imposto > Declarações > Imposto retido na fonte > Pagamento de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="4879f-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="4879f-109">No campo **Período de liquidação**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4879f-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4879f-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4879f-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4879f-111">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4879f-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="4879f-112">No campo **Data de transação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4879f-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="4879f-113">Selecione **Atualizar** para lançar o comprovante de pagamento de imposto retido na fonte na conta de liquidação de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="4879f-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="4879f-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4879f-114">Click **OK**.</span></span>

![Parâmetros para o pagamento de imposto retido na fonte](media/withholding-tax-payment.png)
