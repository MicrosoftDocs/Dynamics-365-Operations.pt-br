---
title: Configurações de loja para obter demonstrativos de varejo
description: Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbedcda59f503b103d5448e59038e4ed8ca0b51d
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916521"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="4b416-103">Configurações de loja para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="4b416-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="4b416-104">Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="4b416-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="4b416-105">As dimensões financeiras em lojas de Varejo são cobertas em outro procedimento.</span><span class="sxs-lookup"><span data-stu-id="4b416-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="4b416-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="4b416-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="4b416-107">No **Painel de navegação**, acesse **Módulos > Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo**.</span><span class="sxs-lookup"><span data-stu-id="4b416-107">In the **Navgiation pane**, go to **Modules > Retail and commerce > Channels > Retail stores > All retail stores**.</span></span>
2. <span data-ttu-id="4b416-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4b416-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4b416-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4b416-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4b416-110">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4b416-110">Click **Edit**.</span></span>
5. <span data-ttu-id="4b416-111">As configurações na Guia Rápida **Demonstrativo/fechamento** afetam a criação, a validação e lançamento da seção para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4b416-111">The settings in the **Statement/closing** fastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="4b416-112">Expanda a Guia Rápida **Demonstrativo/fechamento**.</span><span class="sxs-lookup"><span data-stu-id="4b416-112">Expand the **Statement/closing** fastTab.</span></span>  
6. <span data-ttu-id="4b416-113">No campo **Método do demonstrativo**, selecione o método que deseja usar para agrupar as linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="4b416-113">In the **Statement method** field, select the method you want to use to to group the statement lines by.</span></span>  
7. <span data-ttu-id="4b416-114">Selecione “Sim” em **Um demonstrativo por dia**, se tiver que haver apenas uma instrução criada por dia ao criar demonstrativos do trabalho em lotes de criação do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="4b416-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="4b416-115">O campo **Cálculo da declaração de meios de pagamento** define se as declarações de proposta devem ser adicionadas juntas ou se a última deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="4b416-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="4b416-116">No campo **Arredondamento**, selecione a conta contábil para lançar nas diferenças de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="4b416-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="4b416-117">No campo **Diferença máxima de arredondamento**, insira a diferença máxima de arredondamento permitida.</span><span class="sxs-lookup"><span data-stu-id="4b416-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="4b416-118">No campo **Lançamentos**, insira a diferença máxima total de lançamentos permitida para um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="4b416-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="4b416-119">No campo **Turno**, você pode inserir a diferença máxima total dentro de um turno em um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="4b416-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="4b416-120">No campo **Transação**, insira a diferença total máxima em uma linha do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="4b416-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="4b416-121">No campo **Método de fechamento**, defina se as transações que serão incluídas em um demonstrativo devem ser parte de um turno fechado ou se podem ser quaisquer transações no intervalo de data/hora definido.</span><span class="sxs-lookup"><span data-stu-id="4b416-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="4b416-122">No campo **Fim do dia útil**, insira um horário, se as transações que ocorrem depois da meia-noite tiverem que ser lançadas com o dia anterior.</span><span class="sxs-lookup"><span data-stu-id="4b416-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="4b416-123">Selecione “Sim” em **Lançar como dia útil**, se as transações que ocorrerem depois da meia-noite tiverem que ser lançadas como parte do dia anterior.</span><span class="sxs-lookup"><span data-stu-id="4b416-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="4b416-124">Selecione "Sim" em **Método Dividir por Demonstrativo** para obter instruções criadas para cada método do demonstrativo definido.</span><span class="sxs-lookup"><span data-stu-id="4b416-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="4b416-125">Isso pode ser útil se o desempenho de lançamentos precisar ser aprimorado para armazenamentos com volumes altos de transação, já que criará vários demonstrativos menores que podem ser processadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="4b416-125">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="4b416-126">Na Guia Rápida **Gera**, no campo **Cliente padrão**, você pode selecionar a conta de cliente a ser usada para vendas para clientes sem marcação.</span><span class="sxs-lookup"><span data-stu-id="4b416-126">In the **General** fastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

