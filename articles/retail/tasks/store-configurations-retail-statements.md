--- 
title: "Definir configurações de loja que afetam os demonstrativos de varejo"
description: "Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: fdfb233a3e6c3ab17577afb67aa0fdd0d4588020
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="configure-store-settings-that-affect-retail-statements"></a><span data-ttu-id="e975d-103">Definir configurações de loja que afetam os demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="e975d-103">Configure store settings that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e975d-104">Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="e975d-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="e975d-105">As dimensões financeiras em lojas de Varejo são cobertas em outro procedimento.</span><span class="sxs-lookup"><span data-stu-id="e975d-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="e975d-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="e975d-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="e975d-107">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="e975d-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="e975d-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="e975d-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e975d-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e975d-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e975d-110">As configurações na seção Demonstrativo/fechamento afetam a criação, a validação e lançamento da seção para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e975d-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="e975d-111">Abra a seção Demonstrativo/fechamento.</span><span class="sxs-lookup"><span data-stu-id="e975d-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="e975d-112">Selecione o método que deseja usar para agrupar as linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="e975d-112">Select the method you want to use to group the statement lines by.</span></span>  
    * <span data-ttu-id="e975d-113">Selecione “Sim”, se tiver que haver apenas uma instrução criada por dia ao criar demonstrativos do trabalho em lotes de criação do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="e975d-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="e975d-114">O campo Cálculo da declaração de meios de pagamento define se as declarações de proposta devem ser adicionadas juntas ou se a última deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="e975d-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="e975d-115">Selecione a conta contábil para lançar nas diferenças de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="e975d-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="e975d-116">No campo Diferença máxima de arredondamento, você pode inserir a diferença máxima de arredondamento permitida.</span><span class="sxs-lookup"><span data-stu-id="e975d-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="e975d-117">No campo Lançamentos, você pode inserir a diferença máxima total de lançamentos permitida para um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="e975d-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="e975d-118">No campo Turno, você pode inserir a diferença máxima total dentro de um turno em um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="e975d-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="e975d-119">No campo da transação, você pode inserir a diferença total máxima em uma linha do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="e975d-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="e975d-120">No campo Método de fechamento, você pode definir se as transações que serão incluídas em um demonstrativo devem ser parte de um turno fechado ou se podem ser quaisquer transações no intervalo de data/hora definido.</span><span class="sxs-lookup"><span data-stu-id="e975d-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="e975d-121">No campo Fim do dia útil, você pode inserir um horário, se as transações que ocorrem depois da meia-noite tiverem que ser lançadas com o dia anterior.</span><span class="sxs-lookup"><span data-stu-id="e975d-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="e975d-122">Selecione “Sim”, se as transações que ocorrerem depois da meia-noite tiverem que ser lançadas como parte do dia anterior.</span><span class="sxs-lookup"><span data-stu-id="e975d-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="e975d-123">Selecione "Sim" para obter instruções criadas para cada método do demonstrativo definido.</span><span class="sxs-lookup"><span data-stu-id="e975d-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="e975d-124">Isso pode ser útil se o desempenho de lançamentos precisar ser aprimorado para armazenamentos com volumes altos de transação, já que criará vários demonstrativos menores que podem ser processadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="e975d-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="e975d-125">No campo Cliente padrão, você pode selecionar a conta de cliente a ser usada para vendas para clientes sem marcação.</span><span class="sxs-lookup"><span data-stu-id="e975d-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  


