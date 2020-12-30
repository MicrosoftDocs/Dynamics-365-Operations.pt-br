---
title: Associar ativos fixos a arrendamentos
description: O tópico explica como associar um ativo fixo existente a um novo arrendamento.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d627633e43c2e6f5cad90dfe4100ff95a71541f7
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440556"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="9f184-103">Associar ativos fixos a arrendamentos</span><span class="sxs-lookup"><span data-stu-id="9f184-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f184-104">O tópico explica como associar um ativo fixo existente a um novo arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9f184-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="9f184-105">Quando você associa um ativo fixo a um arrendamento, o valor de ativo de ROU (direito de uso) no reconhecimento inicial será o custo de aquisição do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="9f184-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="9f184-106">Para poder associar um ativo fixo a um arrendamento, você deve criar um registro para o ativo fixo em Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="9f184-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="9f184-107">Em seguida, na página **Resumo da arrendamento**, você deve criar um arrendamento e vincular o ativo a esse arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9f184-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="9f184-108">Adicione um arrendamento seguindo as etapas em [Adicionar ou copiar arrendamentos](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="9f184-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="9f184-109">Na página **Adicionar leasing**, no campo **Número de ativo fixo**, selecione o ativo que ainda não foi adquirido.</span><span class="sxs-lookup"><span data-stu-id="9f184-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="9f184-110">Selecione **Livros** e confirme a agenda de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9f184-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="9f184-111">Selecione **Reconhecimento inicial**.</span><span class="sxs-lookup"><span data-stu-id="9f184-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="9f184-112">Selecione **Diário de arrendamento de ativo**.</span><span class="sxs-lookup"><span data-stu-id="9f184-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="9f184-113">A entrada de diário de reconhecimento inicial para os débitos de leasing do ativo fixo para o valor que geralmente é debitado na conta de ativo ROU.</span><span class="sxs-lookup"><span data-stu-id="9f184-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="9f184-114">Agora você pode exibir o tipo de transação e o registro para o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="9f184-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="9f184-115">Selecione **Detalhes do diário**.</span><span class="sxs-lookup"><span data-stu-id="9f184-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="9f184-116">Selecione **Linhas** para exibir as linhas individuais da entrada de diário.</span><span class="sxs-lookup"><span data-stu-id="9f184-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="9f184-117">Selecione a linha do diário que contém o ativo e, em seguida, selecione a guia **Ativos Fixos**.</span><span class="sxs-lookup"><span data-stu-id="9f184-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="9f184-118">A guia **Ativos fixos** mostra o tipo de transação e o registro.</span><span class="sxs-lookup"><span data-stu-id="9f184-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="9f184-119">Por padrão, o campo **Tipo de transação** é definido como **Aquisição**, e o campo **Livro** é definido como o livro atual do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="9f184-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="9f184-120">Depois de lançar a entrada inicial do diário de reconhecimento, a transação aparece como uma transação de aquisição para o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="9f184-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="9f184-121">Para exibir a tabela de transações, vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**, selecione o ativo apropriado e depois **Avaliações**.</span><span class="sxs-lookup"><span data-stu-id="9f184-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="9f184-122">Você verá que a entrada inicial do diário de reconhecimento criou uma transação de aquisição para o ativo fixo especificado.</span><span class="sxs-lookup"><span data-stu-id="9f184-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="9f184-123">O ativo fixo agora pode ser depreciado usando a funcionalidade de depreciação padrão em Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="9f184-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="9f184-124">Para obter mais informações depreciação, consulte [Métodos e convenções de depreciação](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="9f184-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9f184-125">Se você associar um ativo fixo a um arrendamento, os botões **Depreciação de ativo** e **Redução ao valor recuperável de arrendamento** serão desabilitados no arrendamento do Ativo.</span><span class="sxs-lookup"><span data-stu-id="9f184-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="9f184-126">Você pode exibir as transações de depreciação de ativo e de deficiência de arrendamento de Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="9f184-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="9f184-127">O botão **Transações de ativos** que abre um formulário de consulta também é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="9f184-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="9f184-128">Você também pode abrir o formulário de **Transações do ativo** nos Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="9f184-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  
