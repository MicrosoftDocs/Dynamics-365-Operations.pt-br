---
title: Convenções de arrendamento de ativos
description: Este tópico descreve convenções ativos arrendados.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 67c4d2b7162cf6bda2eedfecef43ff0b216e6e6c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881799"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="e8162-103">Convenções de arrendamento de ativos</span><span class="sxs-lookup"><span data-stu-id="e8162-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e8162-104">Este tópico descreve convenções ativos arrendados.</span><span class="sxs-lookup"><span data-stu-id="e8162-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="e8162-105">As convenções de arrendamento são usadas para determinar a data de início de um registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="e8162-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="e8162-106">Se a convenção de arrendamento estiver definida como **Nenhum**, a data de início será a mesma que a data inicial do arrendamento (ou seja, o valor do campo **Data de início do arrendamento**).</span><span class="sxs-lookup"><span data-stu-id="e8162-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="e8162-107">Se a convenção de arrendamento for definida como **Mês completo**, a data de início será o primeiro dia do mês em que a data inicial do arrendamento cairá.</span><span class="sxs-lookup"><span data-stu-id="e8162-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="e8162-108">A data de início determina a data inicial do período para as agendas de amortização de passivos e depreciação de ativos.</span><span class="sxs-lookup"><span data-stu-id="e8162-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="e8162-109">Despesas de juros e despesas de depreciação são lançadas na data de término do período das agendas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e8162-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="e8162-110">A entrada de diário de reconhecimento e ajuste inicial é lançada na data de início.</span><span class="sxs-lookup"><span data-stu-id="e8162-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="e8162-111">O recurso de convenções de arrendamento precisa ser ativado por meio do Gerenciamento de Recursos.</span><span class="sxs-lookup"><span data-stu-id="e8162-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="e8162-112">No espaço de trabalho **Gerenciamento de recursos**, localize e selecione o recurso denominado **Convenção de arrendamento para arrendamento de ativos** e selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="e8162-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="e8162-113">As convenções de arrendamento são atribuídas à configuração de um registro de ativos de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="e8162-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="e8162-114">Para exibir ou atribuir a convenção de arrendamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e8162-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="e8162-115">Acesse **Arrendamento de ativo \> Configuração \> Registros de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="e8162-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="e8162-116">No campo **Convenção de arrendamento**, selecione um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="e8162-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="e8162-117">Convenção de arrendamento</span><span class="sxs-lookup"><span data-stu-id="e8162-117">Leasing convention</span></span> | <span data-ttu-id="e8162-118">descrição</span><span class="sxs-lookup"><span data-stu-id="e8162-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="e8162-119">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="e8162-119">None</span></span>               | <span data-ttu-id="e8162-120">As agendas de amortização de responsabilidade e de depreciação de ativos começam na data de início da concessão porque a data de início equivale à data de início do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="e8162-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="e8162-121">A data final é um mês depois.</span><span class="sxs-lookup"><span data-stu-id="e8162-121">The end date is one month later.</span></span> <span data-ttu-id="e8162-122">Essa convenção de arrendamento não garante que os juros serão lançados no último dia de cada mês.</span><span class="sxs-lookup"><span data-stu-id="e8162-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="e8162-123">Mês inteiro</span><span class="sxs-lookup"><span data-stu-id="e8162-123">Full month</span></span>         | <span data-ttu-id="e8162-124">Para arrendamentos com uma data de início que ocorre a qualquer momento do mês, as agendas de amortização de passivos e depreciação de ativos começam a acumular despesas no primeiro dia do mês.</span><span class="sxs-lookup"><span data-stu-id="e8162-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="e8162-125">Essa convenção de arrendamento garante que os juros sejam acumulados no último dia de cada mês para o mês inteiro.</span><span class="sxs-lookup"><span data-stu-id="e8162-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="e8162-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e8162-126">Select **Save**.</span></span>

<span data-ttu-id="e8162-127">Quando um arrendamento é criado, a data de início de cada registro é inserida automaticamente com base na data inicial inserida para o arrendamento e a convenção de arrendamento especificada para o registro.</span><span class="sxs-lookup"><span data-stu-id="e8162-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
