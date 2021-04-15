---
title: Configurações de loja para obter demonstrativos de varejo
description: Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Commerce foram criadas e lançadas.
author: jashanno
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: da862af25df241ad42b7e1ade3fdca19f6280278
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804104"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="c46c8-103">Configurações de loja para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="c46c8-103">Store configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c46c8-104">Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Commerce foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="c46c8-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="c46c8-105">As dimensões financeiras em lojas são cobertas em outro procedimento.</span><span class="sxs-lookup"><span data-stu-id="c46c8-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="c46c8-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="c46c8-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="c46c8-107">No **Painel de navegação**, acesse **Módulos > Varejo e Comércio > Canais > Lojas > Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="c46c8-107">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="c46c8-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c46c8-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c46c8-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c46c8-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c46c8-110">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c46c8-110">Click **Edit**.</span></span>
5. <span data-ttu-id="c46c8-111">As configurações na Guia Rápida **Demonstrativo/fechamento** afetam a criação, a validação e o lançamento da seção para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c46c8-111">The settings in the **Statement/closing** FastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="c46c8-112">Expanda a Guia Rápida **Demonstrativo/fechamento**.</span><span class="sxs-lookup"><span data-stu-id="c46c8-112">Expand the **Statement/closing** FastTab.</span></span>  
6. <span data-ttu-id="c46c8-113">No campo **Método de demonstrativo**, selecione o método que deseja usar para agrupar as linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-113">In the **Statement method** field, select the method you want to use to group the statement lines by.</span></span>  
7. <span data-ttu-id="c46c8-114">Selecione “Sim” em **Um demonstrativo por dia**, se tiver que haver apenas uma instrução criada por dia ao criar demonstrativos do trabalho em lotes de criação do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="c46c8-115">O campo **Cálculo da declaração de meios de pagamento** define se as declarações de proposta devem ser adicionadas juntas ou se a última deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="c46c8-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="c46c8-116">No campo **Arredondamento**, selecione a conta contábil para lançar nas diferenças de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="c46c8-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="c46c8-117">No campo **Diferença máxima de arredondamento**, insira a diferença máxima de arredondamento permitida.</span><span class="sxs-lookup"><span data-stu-id="c46c8-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="c46c8-118">No campo **Lançamentos**, insira a diferença máxima total de lançamentos permitida para um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="c46c8-119">No campo **Turno**, você pode inserir a diferença máxima total dentro de um turno em um demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="c46c8-120">No campo **Transação**, insira a diferença total máxima em uma linha do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="c46c8-121">No campo **Método de fechamento**, defina se as transações que serão incluídas em um demonstrativo devem ser parte de um turno fechado ou se podem ser quaisquer transações no intervalo de data/hora definido.</span><span class="sxs-lookup"><span data-stu-id="c46c8-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="c46c8-122">No campo **Fim do dia útil**, insira um horário, se as transações que ocorrem depois da meia-noite tiverem que ser lançadas com o dia anterior.</span><span class="sxs-lookup"><span data-stu-id="c46c8-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="c46c8-123">Selecione “Sim” em **Lançar como dia útil**, se as transações que ocorrerem depois da meia-noite tiverem que ser lançadas como parte do dia anterior.</span><span class="sxs-lookup"><span data-stu-id="c46c8-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="c46c8-124">Selecione "Sim" em **Método Dividir por Demonstrativo** para obter instruções criadas para cada método do demonstrativo definido.</span><span class="sxs-lookup"><span data-stu-id="c46c8-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="c46c8-125">Essa ação poderá ser útil se o desempenho de lançamentos precisar ser aprimorado para armazenamentos com volumes altos de transação, já que criará vários demonstrativos menores que poderão ser processados em paralelo.</span><span class="sxs-lookup"><span data-stu-id="c46c8-125">This action can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="c46c8-126">Na Guia Rápida **Geral**, no campo **Cliente padrão**, você pode selecionar a conta de cliente a ser usada para vendas para clientes sem hora marcada.</span><span class="sxs-lookup"><span data-stu-id="c46c8-126">In the **General** FastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]