---
title: Criação de ordens baseadas em um fluxo constante para transações de loja de varejo
description: Este tópico descreve a criação de ordens baseadas em um fluxo constante para transações de loja no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: 79f99b9b401de3e3bcca6ec5a13a3b4f7bad6f8c
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766727"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a><span data-ttu-id="9be88-103">Criação de ordens baseadas em um fluxo constante para transações de loja de varejo</span><span class="sxs-lookup"><span data-stu-id="9be88-103">Trickle feed-based order creation for retail store transactions</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9be88-104">No Dynamics 365 Retail versões 10.0.4 e anteriores, o lançamento de demonstrativo de varejo é uma operação de fechamento do dia e todas as transações são lançadas nos registros no final do dia.</span><span class="sxs-lookup"><span data-stu-id="9be88-104">In Dynamics 365 Retail versions 10.0.4 and earlier, statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="9be88-105">As grandes transações devem ser processadas em uma janela de tempo limitado, ocasionalmente resultando em falhas no lançamento de demonstrativo e bloqueios de carga.</span><span class="sxs-lookup"><span data-stu-id="9be88-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="9be88-106">Os varejistas também podem não reconhecer receitas e pagamentos em seu registros durante o dia.</span><span class="sxs-lookup"><span data-stu-id="9be88-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="9be88-107">Com a criação de ordens baseadas em um fluxo constante apresentada no Retail versão 10.0.5, as transações são processadas durante o dia e somente a reconciliação financeira dos meios de pagamento e outras transações de gerenciamento de caixa são processadas no final do dia.</span><span class="sxs-lookup"><span data-stu-id="9be88-107">With trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="9be88-108">Essa funcionalidade divide a carga de criação de ordens de venda, faturas e pagamentos durante o dia, proporcionando melhor desempenho percebido e a possibilidade de reconhecer receitas e pagamentos nos registros quase que em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9be88-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="9be88-109">Como usar o lançamento baseado em um fluxo constante</span><span class="sxs-lookup"><span data-stu-id="9be88-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="9be88-110">Para habilitar o lançamento de transações de varejo baseado em um fluxo constante, habilite o recurso chamado **Demonstrativos de varejo — Fluxo constante** usando o gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="9be88-110">To enable trickle feed-based posting of retail transactions, enable the feature named **Retail statements - Trickle feed** using Feature management.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9be88-111">Antes de habilitar o recurso, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado.</span><span class="sxs-lookup"><span data-stu-id="9be88-111">Before you enable the feature, make sure that no pending statements are waiting to be posted.</span></span>

2. <span data-ttu-id="9be88-112">O documento do demonstrativo atual será dividido em dois tipos: demonstrativo transacional e demonstrativo financeiro.</span><span class="sxs-lookup"><span data-stu-id="9be88-112">The current statement document will be split into two types: transactional statement and financial statement.</span></span>

      - <span data-ttu-id="9be88-113">O demonstrativo transacional pegará todas as transações de varejo não lançadas e validadas e criará ordens de venda, faturas de vendas, diários de pagamentos e de desconto e transações de receita/despesa na cadência que você configurar.</span><span class="sxs-lookup"><span data-stu-id="9be88-113">The transactional statement will pick up all unposted and validated transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="9be88-114">Configure esse processo para ser executado com alta frequência para que os documentos sejam criados quando as transações forem carregadas no Headquarters pelo trabalho P.</span><span class="sxs-lookup"><span data-stu-id="9be88-114">You should configure this process to run at a high frequency so that documents are created when the transactions are uploaded into Headquarters through the P-job.</span></span> <span data-ttu-id="9be88-115">Com o demonstrativo transacional que já cria ordens de venda e faturas de vendas, não há necessidade real de configurar o trabalho em lotes **Lançar estoque**.</span><span class="sxs-lookup"><span data-stu-id="9be88-115">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="9be88-116">No entanto, você ainda poderá usá-lo para atender a necessidades comerciais específicas que possa ter.</span><span class="sxs-lookup"><span data-stu-id="9be88-116">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="9be88-117">O demonstrativo financeiro foi projetado para ser criado no final do dia e oferece suporte somente ao método de fechamento **Turno**.</span><span class="sxs-lookup"><span data-stu-id="9be88-117">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="9be88-118">Esse demonstrativo estará limitado à reconciliação financeira e criará somente os diários para os valores de diferenças entre o valor contado e o valor da transação dos diferentes meios de pagamento, juntamente com os diários para outras transações de gerenciamento de caixa.</span><span class="sxs-lookup"><span data-stu-id="9be88-118">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

3. <span data-ttu-id="9be88-119">Para calcular o demonstrativo transacional, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos transacionais em lote**.</span><span class="sxs-lookup"><span data-stu-id="9be88-119">To calculate the transactional statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="9be88-120">Para lançar os demonstrativos transacionais em lote, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="9be88-120">To post the transactional statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post transactional statements in batch**.</span></span>

4. <span data-ttu-id="9be88-121">Para calcular o demonstrativo financeiro, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="9be88-121">To calculate the financial statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="9be88-122">Para lançar os demonstrativos financeiros em lote, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.</span><span class="sxs-lookup"><span data-stu-id="9be88-122">To post the financial statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="9be88-123">Os itens de menu **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos em lote** e **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos em lote** foram removidos com este novo recurso.</span><span class="sxs-lookup"><span data-stu-id="9be88-123">The menu items **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate statements in batch** and **Retail and Commerce > Retail and Commerce IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="9be88-124">Como alternativa, os tipos de demonstrativo transacional e financeiro podem ser criados manualmente.</span><span class="sxs-lookup"><span data-stu-id="9be88-124">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="9be88-125">Acesse **Retail e Commerce > Canais > Lojas** e clique em **Demonstrativos**.</span><span class="sxs-lookup"><span data-stu-id="9be88-125">Go to **Retail and Commerce > Channels > Stores** and click **Statements**.</span></span> <span data-ttu-id="9be88-126">Clique em **Novo** e escolha o tipo de demonstrativo que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="9be88-126">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="9be88-127">Os campos na página **Demonstrativos** e as ações no **Grupo de demonstrativos** da página mostrarão os dados relevantes e as ações baseadas no tipo de demonstrativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="9be88-127">Fields on the **Statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
