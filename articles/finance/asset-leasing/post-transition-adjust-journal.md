---
title: Lançar entradas de diário de ajuste de transição em Arrendamento de ativo
description: Este tópico descreve a funcionalidade que permite a transição de um portfólio de arrendamento para os novos padrões contábeis de arrendamento, os padrões contábeis Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51ae41e22507d77f32b8b0f4685cce797fd19cff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969544"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="e6ea4-103">Lançar entradas de diário de ajuste de transição em Arrendamento de ativo</span><span class="sxs-lookup"><span data-stu-id="e6ea4-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6ea4-104">Este tópico descreve a funcionalidade que permite a transição de um portfólio de arrendamento para os novos padrões de contabilização de arrendamento: Tópico 842 da Codificação de Padrões Contábeis (ASC 842), que é o padrão nos Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP), e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="e6ea4-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="e6ea4-105">Para obter informações sobre como configurar um registro para a transição para os novos padrões, consulte [Configurar registros de arrendamento](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="e6ea4-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="e6ea4-106">Quando você cria uma entrada de diário de ajuste de transição, uma entrada de diário é gerada.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="e6ea4-107">Essa entrada reflete o impacto da folha de equilíbrio do registro do arrendamento sob os novos padrões nessa data.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="e6ea4-108">A conta de ativo apropriada é debitada no valor de transporte dessa data e a conta de passivo é creditada.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="e6ea4-109">A diferença é debitada ou creditada nos ganhos retidos.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="e6ea4-110">Para lançar um ajuste de transição em conformidade com os novos padrões contábeis, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="e6ea4-111">Na página **Resumo do arrendamento**, selecione o arrendamento e selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="e6ea4-112">No registro, selecione **Agenda de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="e6ea4-113">Na caixa de diálogo **Agenda de pagamento**, selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="e6ea4-114">Em seguida, feche a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="e6ea4-115">Selecione **Ajuste de transição**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6ea4-116">Um ajuste de transição pode ser criado somente para os catálogos de arrendamento atribuídos a um registro no qual o campo **Registro de transições** está disponível.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="e6ea4-117">Se o valor no campo **Início do arrendamento** for posterior à data de transição, o valor no campo **Ajuste de transição** não será atualizado.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="e6ea4-118">Para exibir a entrada de diário, selecione **Diários de arrendamento de ativo**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="e6ea4-119">Selecione o novo diário e depois **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="e6ea4-119">Select the new journal, and then select **Post**.</span></span>
