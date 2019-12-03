---
title: Criação de ordens baseadas em um fluxo constante para transações de loja de varejo
description: Este tópico descreve a criação de ordens baseadas em um fluxo constante para transações de loja de varejo no Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: deb8399aa401af16b6fe123a433eb21864e178c6
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693080"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a><span data-ttu-id="6abd4-103">Criação de ordens baseadas em um fluxo constante para transações de loja de varejo (Visualização pública)</span><span class="sxs-lookup"><span data-stu-id="6abd4-103">Trickle feed-based order creation for retail store transactions (Public preview)</span></span>

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6abd4-104">No Dynamics 365 Retail versões 10.0.4 e anteriores, o lançamento de demonstrativo de varejo é uma operação de fechamento do dia e todas as transações são lançadas nos registros no final do dia.</span><span class="sxs-lookup"><span data-stu-id="6abd4-104">In Dynamics 365 Retail versions 10.0.4 and earlier, retail statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="6abd4-105">As grandes transações devem ser processadas em uma janela de tempo limitado, ocasionalmente resultando em falhas no lançamento de demonstrativo e bloqueios de carga.</span><span class="sxs-lookup"><span data-stu-id="6abd4-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="6abd4-106">Os varejistas também podem não reconhecer receitas e pagamentos em seu registros durante o dia.</span><span class="sxs-lookup"><span data-stu-id="6abd4-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="6abd4-107">Com a visualização pública criação de ordens baseadas em um fluxo constante apresentada no Retail versão 10.0.5, as transações são processadas durante o dia e somente a reconciliação financeira dos meios de pagamento e outras transações de gerenciamento de caixa são processadas no final do dia.</span><span class="sxs-lookup"><span data-stu-id="6abd4-107">With the public preview of trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="6abd4-108">Essa funcionalidade divide a carga de criação de ordens de venda, faturas e pagamentos durante o dia, proporcionando melhor desempenho percebido e a possibilidade de reconhecer receitas e pagamentos nos registros quase que em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6abd4-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="6abd4-109">Como usar o lançamento baseado em um fluxo constante</span><span class="sxs-lookup"><span data-stu-id="6abd4-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="6abd4-110">Para habilitar o lançamento baseado em um fluxo constante de transações de varejo, acesse **Administração do sistema > Configurar > Configuração da licença** e desabilite a chave **Demonstrativos de varejo**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-110">To enable trickle feed-based posting of retail transactions, go to **System administration > Set up > License configuration** and disable the the **Retail statements** key.</span></span>

2. <span data-ttu-id="6abd4-111">Na mesma página, habilite a chave de licença **Demonstrativos de varejo (fluxo constante) — Visualização**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-111">On the same page, enable the **Retail statements (trickle feed) – Preview** license key.</span></span> <span data-ttu-id="6abd4-112">Ao habilitar essa chave, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado.</span><span class="sxs-lookup"><span data-stu-id="6abd4-112">When you enable this key, make sure there are no pending statements waiting to be posted.</span></span> 

> [!Important]
> <span data-ttu-id="6abd4-113">Antes de habilitar a chave de licença **Demonstrativos de varejo (fluxo constante) — Visualização**, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado.</span><span class="sxs-lookup"><span data-stu-id="6abd4-113">Before you enable the **Retail statements (trickle feed) – Preview** license key, make sure that no pending statements are waiting to be posted.</span></span>

3. <span data-ttu-id="6abd4-114">O documento do demonstrativo atual será dividido em dois tipos diferentes: demonstrativo transacional e demonstrativo financeiro.</span><span class="sxs-lookup"><span data-stu-id="6abd4-114">The current statement document will be split into two different types; transactional statement and financial statement.</span></span>

      - <span data-ttu-id="6abd4-115">O demonstrativo transacional pegará todas as transações de varejo não lançadas validadas e criará ordens de venda, faturas de vendas, diários de pagamentos e de desconto e transações de receita/despesa na cadência que você configurar.</span><span class="sxs-lookup"><span data-stu-id="6abd4-115">The transactional statement will pick up all unposted and validated retail transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="6abd4-116">Configure esse processo para ser executado com alta frequência para que os documentos sejam criados quando as transações de varejo forem carregadas no Retail Headquarters pelo trabalho P.</span><span class="sxs-lookup"><span data-stu-id="6abd4-116">You should configure this process to run at a high frequency so that documents are created when the retail transactions are uploaded into Retail Headquarters through the P-job.</span></span> <span data-ttu-id="6abd4-117">Com o demonstrativo transacional que já cria ordens de venda e faturas de vendas, não há necessidade real de configurar o trabalho em lotes **Lançar estoque**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-117">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="6abd4-118">No entanto, você ainda poderá usá-lo para atender a necessidades comerciais específicas que possa ter.</span><span class="sxs-lookup"><span data-stu-id="6abd4-118">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="6abd4-119">O demonstrativo financeiro foi projetado para ser criado no final do dia e oferece suporte somente ao método de fechamento **Turno**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-119">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="6abd4-120">Esse demonstrativo estará limitado à reconciliação financeira e criará somente os diários para os valores de diferenças entre o valor contado e o valor da transação dos diferentes meios de pagamento, juntamente com os diários para outras transações de gerenciamento de caixa.</span><span class="sxs-lookup"><span data-stu-id="6abd4-120">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

4. <span data-ttu-id="6abd4-121">Para calcular o demonstrativo transacional, clique em **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos transacionais em lote**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-121">To calculate the transactional statement, click **Retail > Retail IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="6abd4-122">Para lançar os demonstrativos do demonstrativo transacional em lote, clique em **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-122">To post the transactional statement statements in batch, click **Retail > Retail IT > POS Posting > Post transactional statements in batch**.</span></span>

5. <span data-ttu-id="6abd4-123">Para calcular o demonstrativo financeiro, clique em **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-123">To calculate the financial statement, click **Retail > Retail IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="6abd4-124">Para lançar os demonstrativos financeiros em lote, clique em **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-124">To post the financial statements in batch, click **Retail > Retail IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="6abd4-125">Os itens de menu **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos em lote** e **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos em lote** foram removidos com este novo recurso.</span><span class="sxs-lookup"><span data-stu-id="6abd4-125">The menu items **Retail > Retail IT > POS Posting > Calculate statements in batch** and **Retail > Retail IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="6abd4-126">Como alternativa, os tipos de demonstrativo transacional e financeiro podem ser criados manualmente.</span><span class="sxs-lookup"><span data-stu-id="6abd4-126">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="6abd4-127">Acesse **Varejo > Canais > Lojas de varejo** e clique em **Demonstrativos de varejo**.</span><span class="sxs-lookup"><span data-stu-id="6abd4-127">Go to **Retail > Channels > Retail stores** and click **Retail statements**.</span></span> <span data-ttu-id="6abd4-128">Clique em **Novo** e escolha o tipo de demonstrativo que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="6abd4-128">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="6abd4-129">Os campos na página **Demonstrativos de varejo** e as ações no **Grupo de demonstrativos** da página mostrarão os dados relevantes e as ações baseadas no tipo de demonstrativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="6abd4-129">Fields on the **Retail statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
