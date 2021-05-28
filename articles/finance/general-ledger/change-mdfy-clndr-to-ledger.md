---
title: Alterar ou reatribuir um calendário do razão
description: Este tópico explica como alterar o calendário que está atribuído no momento a um razão e como atribuir um novo calendário ao razão.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 052b8944c0a015187d1d7c4ba3db878c52faeeea
ms.sourcegitcommit: 905a8c7a0c1bc06ada2acfba913dfe5f7b44ea16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6039941"
---
# <a name="change-or-reassign-a-ledger-calendar"></a><span data-ttu-id="7be7f-103">Alterar ou reatribuir um calendário do razão</span><span class="sxs-lookup"><span data-stu-id="7be7f-103">Change or reassign a ledger calendar</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7be7f-104">Este tópico explica como alterar o calendário que está atribuído no momento a um razão e como atribuir um novo calendário ao razão.</span><span class="sxs-lookup"><span data-stu-id="7be7f-104">This topic explains how to change the calendar that is currently assigned to a ledger, and how to assign a new calendar to the ledger.</span></span>

## <a name="issue"></a><span data-ttu-id="7be7f-105">Problema</span><span class="sxs-lookup"><span data-stu-id="7be7f-105">Issue</span></span>

<span data-ttu-id="7be7f-106">Às vezes, as empresas devem alterar o calendário existente atribuído a um razão ou atribuir um novo calendário.</span><span class="sxs-lookup"><span data-stu-id="7be7f-106">Sometime, companies must either change the existing calendar that is assigned to a ledger or assign a new calendar.</span></span>

## <a name="resolution"></a><span data-ttu-id="7be7f-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="7be7f-107">Resolution</span></span>

<span data-ttu-id="7be7f-108">Há dois cenários para alterar ou reatribuir um calendário do razão.</span><span class="sxs-lookup"><span data-stu-id="7be7f-108">There are two scenarios for changing or reassigning a ledger calendar.</span></span> <span data-ttu-id="7be7f-109">O primeiro cenário envolve a alteração de um calendário existente que já está atribuído ao razão.</span><span class="sxs-lookup"><span data-stu-id="7be7f-109">The first scenario involves changing an existing calendar that is already assigned to the ledger.</span></span> <span data-ttu-id="7be7f-110">O segundo cenário envolve a criação de um calendário e sua atribuição ao razão.</span><span class="sxs-lookup"><span data-stu-id="7be7f-110">The second scenario involves creating a new calendar and assigning it to the ledger.</span></span> <span data-ttu-id="7be7f-111">Ambas as alterações podem ser feitas a qualquer momento, mesmo depois que as transações tiverem sido lançadas no razão.</span><span class="sxs-lookup"><span data-stu-id="7be7f-111">Both changes can be done at any time, even after transactions have been posted to the ledger.</span></span>

### <a name="change-an-existing-fiscal-calendar"></a><span data-ttu-id="7be7f-112">Alterar um calendário fiscal existente</span><span class="sxs-lookup"><span data-stu-id="7be7f-112">Change an existing fiscal calendar</span></span>

<span data-ttu-id="7be7f-113">Para alterar um calendário existente atribuído ao seu razão, acesse **Contabilidade \> Configuração do razão \> Razão** e selecione o link para o calendário fiscal para abrir a página **Calendários do razão**.</span><span class="sxs-lookup"><span data-stu-id="7be7f-113">To change an existing calendar that is assigned to your ledger, go to **General ledger \> Ledger setup \> Ledger**, and select the link for the fiscal calendar to open the **Ledger calendars** page.</span></span>

<span data-ttu-id="7be7f-114">Existem limites para as alterações que podem ser feitas em um calendário.</span><span class="sxs-lookup"><span data-stu-id="7be7f-114">There are limits to the changes that can be made to a calendar.</span></span> <span data-ttu-id="7be7f-115">Por exemplo, você pode alterar as datas de início e término dos *períodos* em um ano, mas não pode alterar as datas de início e término de um *ano* no calendário.</span><span class="sxs-lookup"><span data-stu-id="7be7f-115">For example, you can change the start and end dates of the *periods* in a year, but you can't change the start and end dates of a *year* in the calendar.</span></span>

<span data-ttu-id="7be7f-116">Para alterar os períodos em um ano, selecione o calendário e o ano apropriados.</span><span class="sxs-lookup"><span data-stu-id="7be7f-116">To change the periods in a year, select the appropriate calendar and year.</span></span> <span data-ttu-id="7be7f-117">Primeiro, use o botão **Excluir período** para excluir alguns ou todos os períodos operacionais existentes.</span><span class="sxs-lookup"><span data-stu-id="7be7f-117">First, use the use the **Delete period** button to delete some or all of the existing operating periods.</span></span> <span data-ttu-id="7be7f-118">É possível excluir todos os períodos operacionais, exceto o primeiro.</span><span class="sxs-lookup"><span data-stu-id="7be7f-118">All operating periods except the first can be deleted.</span></span> <span data-ttu-id="7be7f-119">Em seguida, use o botão **Dividir período** para dividir o período ou os períodos restantes em novos períodos inserindo uma data de início apropriada para o próximo período.</span><span class="sxs-lookup"><span data-stu-id="7be7f-119">Then use the **Divide period** button to divide the remaining period or periods into new periods by entering an appropriate start date for the next period.</span></span>

<span data-ttu-id="7be7f-120">Depois de alterar os períodos em um calendário, você deve executar o processo **Recalcular períodos do razão** em cada entidade legal (empresa) à qual o calendário está atribuído.</span><span class="sxs-lookup"><span data-stu-id="7be7f-120">After you change the periods in a calendar, you must run the **Recalculate ledger periods** process in every legal entity (company) that the calendar is assigned to.</span></span> <span data-ttu-id="7be7f-121">Embora nenhuma mensagem de aviso lembre-o de concluir essa etapa, o processo de recálculo é necessário para atualizar o período atribuído a cada transação lançada na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="7be7f-121">Although no warning message reminds you to complete this step, the recalculation process is required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="7be7f-122">Para executar o processo de recálculo, selecione **Recalcular períodos do razão** na página **Configuração do razão** em cada empresa.</span><span class="sxs-lookup"><span data-stu-id="7be7f-122">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page in each company.</span></span>

<span data-ttu-id="7be7f-123">Se o processo de recálculo não for executado, os saldos da transação em um balancete ou nos demonstrativos financeiros podem ser incluídos incorretamente nos períodos.</span><span class="sxs-lookup"><span data-stu-id="7be7f-123">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="7be7f-124">Nesse caso, você pode corrigir os saldos a qualquer momento executando o processo de recálculo.</span><span class="sxs-lookup"><span data-stu-id="7be7f-124">In this case, you can correct the balances at any time by running the recalculation process.</span></span>

### <a name="assign-a-new-fiscal-calendar"></a><span data-ttu-id="7be7f-125">Atribuir um novo calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="7be7f-125">Assign a new fiscal calendar</span></span>

<span data-ttu-id="7be7f-126">Para atribuir um novo calendário fiscal, acesse **Contabilidade \> Configuração do razão \> Razão** e selecione **Editar** para colocar a página **Razão** no modo de edição.</span><span class="sxs-lookup"><span data-stu-id="7be7f-126">To assign a new fiscal calendar, go to **General ledger \> Ledger setup \> Ledger**, and select **Edit** to put the **Ledger** page into edit mode.</span></span> <span data-ttu-id="7be7f-127">Em seguida, no campo **Calendário fiscal**, selecione um novo calendário fiscal.</span><span class="sxs-lookup"><span data-stu-id="7be7f-127">Then, in the **Fiscal calendar** field, select a new fiscal calendar.</span></span>

<span data-ttu-id="7be7f-128">Depois de alterar o calendário fiscal de um razão, você deve executar a opção **Recalcular períodos do razão**.</span><span class="sxs-lookup"><span data-stu-id="7be7f-128">After you change the fiscal calendar for a ledger, you must run the **Recalculate ledger periods**.</span></span> <span data-ttu-id="7be7f-129">Quando você atribui um novo calendário fiscal a um razão, uma mensagem lembrará você de concluir essa etapa.</span><span class="sxs-lookup"><span data-stu-id="7be7f-129">When you assign a new fiscal calendar to a ledger, a message reminds you to complete this step.</span></span> <span data-ttu-id="7be7f-130">Embora a mensagem pareça indicar que o processo de recálculo é opcional, ele não é.</span><span class="sxs-lookup"><span data-stu-id="7be7f-130">Although the message might seem to indicate that the recalculation process is optional, it isn't.</span></span> <span data-ttu-id="7be7f-131">É necessário atualizar o período que está atribuído a cada transação lançada na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="7be7f-131">It's required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="7be7f-132">Para executar o processo de recálculo, selecione **Recalcular períodos do razão** na página **Configuração do razão**.</span><span class="sxs-lookup"><span data-stu-id="7be7f-132">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page.</span></span>

<span data-ttu-id="7be7f-133">Se o processo de recálculo não for executado, os saldos da transação em um balancete ou nos demonstrativos financeiros podem ser incluídos incorretamente nos períodos.</span><span class="sxs-lookup"><span data-stu-id="7be7f-133">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="7be7f-134">Nesse caso, você pode corrigir os saldos a qualquer momento executando o processo de recálculo.</span><span class="sxs-lookup"><span data-stu-id="7be7f-134">In this case, you can correct the balances at any time by running the recalculation process.</span></span>
