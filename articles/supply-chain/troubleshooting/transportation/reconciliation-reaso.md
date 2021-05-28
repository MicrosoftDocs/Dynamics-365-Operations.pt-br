---
title: Você só pode adicionar a conta principal como a conta de crédito para fins de reconciliação
description: Quando você configura um motivo de reconciliação no Gerenciamento de transporte, você só pode adicionar a conta principal como conta de crédito.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026255"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="36d97-103">Você só pode adicionar a conta principal como a conta de crédito para fins de reconciliação</span><span class="sxs-lookup"><span data-stu-id="36d97-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="36d97-104">Número da base de dados de conhecimento: 4603538</span><span class="sxs-lookup"><span data-stu-id="36d97-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="36d97-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="36d97-105">Symptoms</span></span>

<span data-ttu-id="36d97-106">Quando você configura um motivo de reconciliação no Gerenciamento de transporte, você só pode adicionar a conta principal como conta de crédito.</span><span class="sxs-lookup"><span data-stu-id="36d97-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="36d97-107">Não é possível adicionar um centro de custo ou qualquer outra dimensão como conta de crédito.</span><span class="sxs-lookup"><span data-stu-id="36d97-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="36d97-108">No entanto, a conta de débito permite que você selecione outras dimensões.</span><span class="sxs-lookup"><span data-stu-id="36d97-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="36d97-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="36d97-109">Resolution</span></span>

<span data-ttu-id="36d97-110">Se a reconciliação não for feita para pagar o fornecedor, e sim para creditar uma conta principal específica, o sistema não permitirá que você selecione uma dimensão financeira para a conta de crédito quando você configurar o motivo da reconciliação.</span><span class="sxs-lookup"><span data-stu-id="36d97-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="36d97-111">Se a estrutura de conta exigir um valor de dimensão financeira específico para a conta de crédito principal, o diário do fornecedor resultante não poderá ser postado automaticamente, pois o valor de dimensão financeira está ausente.</span><span class="sxs-lookup"><span data-stu-id="36d97-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="36d97-112">Portanto, você deve primeiro especificar a conta de crédito usando a página **Diário de fatura**.</span><span class="sxs-lookup"><span data-stu-id="36d97-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="36d97-113">Como um valor de dimensão é obrigatório para a conta de crédito, o diário de fatura do fornecedor não pode ser postado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="36d97-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="36d97-114">Você deve postá-lo manualmente após adicionar manualmente o valor de dimensão à conta principal para a linha de crédito.</span><span class="sxs-lookup"><span data-stu-id="36d97-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
