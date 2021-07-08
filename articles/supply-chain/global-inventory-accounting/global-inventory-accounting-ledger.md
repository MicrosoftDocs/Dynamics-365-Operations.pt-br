---
title: Razão do Contabilidade de estoque global
description: Este tópico descreve os razões da Contabilidade de estoque global, que são definidos por uma combinação de uma moeda, um calendário, uma convenção e uma associação com uma entidade legal.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273112"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="89df9-103">Razão do Contabilidade de estoque global</span><span class="sxs-lookup"><span data-stu-id="89df9-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="89df9-104">A Contabilidade de estoque global tem seu próprio conjunto de razões.</span><span class="sxs-lookup"><span data-stu-id="89df9-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="89df9-105">Toda vez que uma transação relacionada ao inventário é processada para uma entidade legal relevante, o sistema pode considerar essa transação em qualquer número de razões da Contabilidade de estoque global, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="89df9-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="89df9-106">Um razão é um registro de medidas de débito e crédito.</span><span class="sxs-lookup"><span data-stu-id="89df9-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="89df9-107">Essas medidas são classificadas usando elementos de custo e contas de sub-razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="89df9-108">Um razão da Contabilidade de estoque global é definido por sua combinação de uma moeda, um calendário, uma convenção e uma associação com uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="89df9-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="89df9-109">Para configurar os razões contábeis de estoque global, vá para **Contabilidade de estoque global \> configuração \> Razões do Contabilidade de estoque global**.</span><span class="sxs-lookup"><span data-stu-id="89df9-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="89df9-110">Em cada razão, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="89df9-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="89df9-111">**Nome** – Digite o nome do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="89df9-112">**Descrição** – Digite uma descrição do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="89df9-113">**Calendário fiscal** – Especifique o calendário fiscal do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="89df9-114">**Moeda e tipo de taxa de câmbio** – Use os campos nesta FastTab para selecionar a moeda contábil usada pelo razão e o tipo de taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="89df9-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="89df9-115">A moeda selecionada pode ser diferente da moeda usada pela entidade legal.</span><span class="sxs-lookup"><span data-stu-id="89df9-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="89df9-116">Na Contabilidade de estoque global, os usuários podem definir quantos razões de custo forem necessários.</span><span class="sxs-lookup"><span data-stu-id="89df9-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="89df9-117">A Contabilidade de estoque global oferece suporte a estatísticas de estoque em várias moedas e em várias avaliações.</span><span class="sxs-lookup"><span data-stu-id="89df9-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="89df9-118">Defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="89df9-118">Set the following fields:</span></span>

    - <span data-ttu-id="89df9-119">**Moeda** – Selecione a moeda de custo na qual os valores relacionados ao estoque são mantidos.</span><span class="sxs-lookup"><span data-stu-id="89df9-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="89df9-120">Esses valores incluem o valor de estoque, o custo dos produtos vendidos, o estoque em trânsito e todos os tipos de variação.</span><span class="sxs-lookup"><span data-stu-id="89df9-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="89df9-121">**Tipo de taxa de câmbio** – Selecione a taxa de câmbio que o sistema deve usar para converter o valor da transação na moeda da transação e o custo padrão dos itens na moeda de custo.</span><span class="sxs-lookup"><span data-stu-id="89df9-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="89df9-122">**Nome da convenção** – Especifique uma convenção.</span><span class="sxs-lookup"><span data-stu-id="89df9-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="89df9-123">Uma convenção é um conjunto de diretivas que estabelecem como os custos serão contabilizados neste razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="89df9-124">**Entidade legal** – O razão considerará os documentos lançados na entidade legal selecionada.</span><span class="sxs-lookup"><span data-stu-id="89df9-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="89df9-125">**Preparação** – Escolha se as transações de estoque criadas antes da criação do razão devem ser processadas de acordo com a moeda e a convenção do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="89df9-126">Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="89df9-126">Select one of the following values:</span></span>

    - <span data-ttu-id="89df9-127">**Ativado** – O razão deve processar transações criadas antes da criação do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="89df9-128">**Ativado** – O razão deve processar somente transações que foram criadas depois do razão.</span><span class="sxs-lookup"><span data-stu-id="89df9-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="89df9-129">Você **não** poderá voltar e definir este campo depois de inserir novos documentos.</span><span class="sxs-lookup"><span data-stu-id="89df9-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="89df9-130">**Status** – O sistema define automaticamente o status de os razões recém-criados para *Preparar*.</span><span class="sxs-lookup"><span data-stu-id="89df9-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
