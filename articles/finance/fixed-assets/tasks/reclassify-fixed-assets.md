---
title: Reclassificar ativos fixos
description: Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944701"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="1ef69-103">Reclassificar ativos fixos</span><span class="sxs-lookup"><span data-stu-id="1ef69-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ef69-104">Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="1ef69-105">Quando um ativo fixo é reclassificado:</span><span class="sxs-lookup"><span data-stu-id="1ef69-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="1ef69-106">Todos os livros do ativo fixo existente são criados para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="1ef69-107">Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="1ef69-108">O status dos livros para o ativo fixo original é Fechado.</span><span class="sxs-lookup"><span data-stu-id="1ef69-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="1ef69-109">Os novos registros do novo ativo fixo contêm a data da reclassificação no campo **Data de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="1ef69-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="1ef69-110">A data indicada no campo **Data de execução da depreciação** é copiada das informações originais de ativo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="1ef69-111">Caso a depreciação já tenha sido iniciada, o campo **Data da última depreciação exibirá** a data da reclassificação.</span><span class="sxs-lookup"><span data-stu-id="1ef69-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="1ef69-112">As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="1ef69-113">Quando um ativo que tem uma transação de transferência for reclassificado, o sistema exibirá uma mensagem na **Central de ações** para indicar que uma transação de transferência não foi concluída durante o processo de reclassificação.</span><span class="sxs-lookup"><span data-stu-id="1ef69-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="1ef69-114">É necessário concluir uma transação de transferência para mover as transações de reclassificação existentes para as dimensões financeiras apropriadas.</span><span class="sxs-lookup"><span data-stu-id="1ef69-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="1ef69-115">Durante o processo de reclassificação, o sistema executa as ações a seguir para reclassificar o saldo do ativo original para o novo ativo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="1ef69-116">O processo de reclassificação copia os dados do registro de ativos fixos original para o novo registro de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="1ef69-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="1ef69-117">A transação de reclassificação usa informações da aquisição original lançada que inclui as informações de dimensão financeira incluídas na transação de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1ef69-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="1ef69-118">Ao mesmo tempo, o processo de reclassificação reverte a transação original de aquisição e transferência de ativos.</span><span class="sxs-lookup"><span data-stu-id="1ef69-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="1ef69-119">O diagrama e o procedimento a seguir fornecem um exemplo do processo de reclassificação.</span><span class="sxs-lookup"><span data-stu-id="1ef69-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="1ef69-120">[![Diagrama mostrando o processo de reclassificação](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="1ef69-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="1ef69-121">Siga essa etapas para reclassificar um ativo fixo:</span><span class="sxs-lookup"><span data-stu-id="1ef69-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="1ef69-122">Vá para **Ativos fixos > Tarefas periódicas > Reclassificação**.</span><span class="sxs-lookup"><span data-stu-id="1ef69-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="1ef69-123">No campo **Grupo de ativos fixos**, selecione o grupo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="1ef69-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="1ef69-124">No campo **Número do ativo fixo**, selecione o ativo fixo a ser reclassificado.</span><span class="sxs-lookup"><span data-stu-id="1ef69-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="1ef69-125">No campo **Novo grupo de ativos fixos**, selecione um grupo para o qual deseja transferir o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1ef69-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="1ef69-126">Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo **Número do novo ativo fixo** será atualizado com o número da nova sequência numérica do grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="1ef69-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="1ef69-127">Caso contrário, o campo **Número do novo ativo fixo** será atualizado com o número da sequência numérica que está configurada na página **Parâmetros do ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="1ef69-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="1ef69-128">Se uma sequência numérica não estiver configurada na página **Parâmetros do ativo fixo**, insira um número no campo **Número do novo ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="1ef69-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="1ef69-129">No campo **Data de reclassificação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1ef69-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="1ef69-130">No campo **Série de comprovante**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1ef69-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="1ef69-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef69-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
