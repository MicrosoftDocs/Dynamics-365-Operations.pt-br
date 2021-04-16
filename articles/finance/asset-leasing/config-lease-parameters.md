---
title: Configurar parâmetros de arrendamento (Versão Preliminar)
description: Este tópico descreve as definições de configuração para Arrendamento de ativos, como informações de segurança e configurações de contabilidade.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c681f7d356752a2194a86bc7eaef6ceac1e0af6b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816091"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="25745-103">Configurar parâmetros de arrendamento</span><span class="sxs-lookup"><span data-stu-id="25745-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25745-104">Várias definições de configuração afetam o comportamento do arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="25745-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="25745-105">Essas configurações incluem nomes de diário, parâmetros gerais e configurações de perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="25745-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="25745-106">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="25745-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="25745-107">Na guia **Arrendamentos**, selecione a FastTab **Geral**.</span><span class="sxs-lookup"><span data-stu-id="25745-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="25745-108">O parâmetro **Permitir substituição de classificação manual** determina se a classificação de arrendamento pode ser substituída antes da confirmação do plano de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25745-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="25745-109">O parâmetro **Lote entre entidades** determina se é possível lançar em outras entidades legais a partir da entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="25745-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="25745-110">Se esse parâmetro estiver ativado, é possível criar entradas de diário para entidades legais às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="25745-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="25745-111">Defina a opção **Permitir a exclusão de arrendamentos confirmados** como **Sim** para permitir a exclusão de arrendamentos com planos de pagamento confirmados.</span><span class="sxs-lookup"><span data-stu-id="25745-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="25745-112">Os arrendamentos não podem ser excluídos se transações lançadas ou não lançadas estiverem associadas, independentemente da configuração dessa opção.</span><span class="sxs-lookup"><span data-stu-id="25745-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="25745-113">Não é possível restaurar um registro de arrendamento após ele ser excluído.</span><span class="sxs-lookup"><span data-stu-id="25745-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="25745-114">Se você carregar registros de um arrendamento excluído, manualmente ou por meio de entidades de dados, as informações carregadas serão tratadas como novas e não como uma atualização de um arrendamento existente.</span><span class="sxs-lookup"><span data-stu-id="25745-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="25745-115">Se você definir essa opção como **Sim** e o tipo de transição do registro for **Opção de catchup cumulativo A ou B**, o sistema definirá o campo **Taxa incremental de empréstimo** como o valor do campo **Taxa incremental de empréstimo na transição** na página **Configuração do registro**.</span><span class="sxs-lookup"><span data-stu-id="25745-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="25745-116">Se essa opção for definida como **Não**, a taxa no arrendamento principal é definida como o valor do campo **Taxa incremental de empréstimo** na página **Detalhes do registro**, independentemente do tipo de transição do registro:</span><span class="sxs-lookup"><span data-stu-id="25745-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="25745-117">Defina a opção **Permitir reversões de depreciação na versão do livro fechado** como **Sim** para permitir a reversão das transações de despesas de depreciação.</span><span class="sxs-lookup"><span data-stu-id="25745-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="25745-118">As transações de despesas podem ser revertidas mesmo quando a versão do livro é fechada.</span><span class="sxs-lookup"><span data-stu-id="25745-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25745-119">Recomendamos manter essa opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="25745-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="25745-120">A configuração dessa opção é usada como validação e controle para impedir que uma versão de livro fechada seja depreciada por engano.</span><span class="sxs-lookup"><span data-stu-id="25745-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="25745-121">Ao manter a opção definida como **Não**, você ajuda a manter a precisão do valor líquido contábil e os cálculos de depreciação futuros.</span><span class="sxs-lookup"><span data-stu-id="25745-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]