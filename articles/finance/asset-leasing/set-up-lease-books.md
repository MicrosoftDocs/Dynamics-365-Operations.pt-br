---
title: Configurar registros de arrendamento
description: Este tópico descreve as informações que são mantidas em registros de arrendamento. Os registros de arrendamento contêm as políticas contábeis que determinam como um arrendamento é contabilizado no sistema.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440549"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="b315e-104">Configurar registros de arrendamento</span><span class="sxs-lookup"><span data-stu-id="b315e-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b315e-105">Os registros de arrendamento contêm as políticas contábeis que determinam como um arrendamento é contabilizado no sistema.</span><span class="sxs-lookup"><span data-stu-id="b315e-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="b315e-106">Além da contabilidade base do caixa, o Arrendamento de ativo oferece suporte aos seguintes padrões:</span><span class="sxs-lookup"><span data-stu-id="b315e-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="b315e-107">Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP)</span><span class="sxs-lookup"><span data-stu-id="b315e-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="b315e-108">Tópico 842 da Codificação de Padrões Contábeis (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="b315e-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="b315e-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="b315e-109">ASC 840</span></span>
- <span data-ttu-id="b315e-110">Padrão Internacional de Relatórios Financeiros 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="b315e-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="b315e-111">Padrão Internacional Contábil 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="b315e-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="b315e-112">Para criar um registro de arrendamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b315e-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="b315e-113">Acesse **Arrendamento de ativo \> Configuração \> Registros de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="b315e-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="b315e-114">Selecione **Novo** para adicionar um registro.</span><span class="sxs-lookup"><span data-stu-id="b315e-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="b315e-115">Defina os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b315e-115">Set the following fields.</span></span>

    | <span data-ttu-id="b315e-116">Organização</span><span class="sxs-lookup"><span data-stu-id="b315e-116">Name</span></span>                                     | <span data-ttu-id="b315e-117">descrição</span><span class="sxs-lookup"><span data-stu-id="b315e-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="b315e-118">Nível de lançamento</span><span class="sxs-lookup"><span data-stu-id="b315e-118">Posting layer</span></span>                            | <span data-ttu-id="b315e-119">Selecione o nível de lançamento a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b315e-119">Select the posting layer to use.</span></span> <span data-ttu-id="b315e-120">Cada registro anexado a um arrendamento é configurado para um nível de lançamento específico.</span><span class="sxs-lookup"><span data-stu-id="b315e-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="b315e-121">Cada nível de lançamento tem finalidades de lançamento diferentes.</span><span class="sxs-lookup"><span data-stu-id="b315e-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="b315e-122">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="b315e-122">Lease type</span></span>                               | <span data-ttu-id="b315e-123">Selecione se o arrendamento deve ser classificado automaticamente ou se deve ser predefinido como um Arrendamento mercantil ou operacional.</span><span class="sxs-lookup"><span data-stu-id="b315e-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="b315e-124">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="b315e-124">Accounting framework</span></span>                     | <span data-ttu-id="b315e-125">Selecione a estrutura associada ao registro.</span><span class="sxs-lookup"><span data-stu-id="b315e-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="b315e-126">Configuração de Prazo do arrendamento/Vida útil</span><span class="sxs-lookup"><span data-stu-id="b315e-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="b315e-127">O sistema classificará o arrendamento como mercantil se o tipo de arrendamento tiver sido definido como **Automático** e se o prazo de arrendamento sobre a vida útil do ativo for maior ou igual ao percentual inserido nesse campo.</span><span class="sxs-lookup"><span data-stu-id="b315e-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="b315e-128">Configuração de Valor presente/Valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="b315e-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="b315e-129">Insira um número inteiro para definir o limite que determinará o tipo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="b315e-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="b315e-130">Se o valor presente de pagamentos de arrendamento mínimos futuros for maior do que o valor definido pelo usuário na configuração do registro e se a classificação de arrendamento do registro estiver definida como automático, o sistema classificará o arrendamento como um arrendamento mercantil.</span><span class="sxs-lookup"><span data-stu-id="b315e-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="b315e-131">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="b315e-131">Short-term threshold</span></span>                     | <span data-ttu-id="b315e-132">Digite o número de meses a ser usado como limite para arrendamentos de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="b315e-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="b315e-133">Se o prazo do arrendamento for menor ou igual ao número de meses inseridos aqui, o sistema classificará a concessão como um arrendamento de curto prazo e o tratamento do arrendamento diferido será aplicado.</span><span class="sxs-lookup"><span data-stu-id="b315e-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="b315e-134">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="b315e-134">Low value threshold</span></span>                      | <span data-ttu-id="b315e-135">Insira um valor a ser usado como limite para arrendamentos de baixo valor.</span><span class="sxs-lookup"><span data-stu-id="b315e-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="b315e-136">Se o valor justo do ativo for menor ou igual ao valor inserido aqui, o sistema classificará o arrendamento como um arrendamento de baixo valor, e o tratamento do arrendamento diferido será aplicado.</span><span class="sxs-lookup"><span data-stu-id="b315e-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="b315e-137">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="b315e-137">Pay to vendor</span></span>                            | <span data-ttu-id="b315e-138">Defina essa opção como **Sim** para permitir que os pagamentos de arrendamento sejam lançados, como uma fatura, na conta de fornecedor especificada em cada arrendamento.</span><span class="sxs-lookup"><span data-stu-id="b315e-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="b315e-139">Quando um pagamento de arrendamento for lançado, a conta do fornecedor será creditada.</span><span class="sxs-lookup"><span data-stu-id="b315e-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="b315e-140">Se essa opção for definida como **Não**, a conta especificada para o tipo de lançamento de **Pagamento de arrendamento** na página **Parâmetros de lançamento de arrendamento** será creditada.</span><span class="sxs-lookup"><span data-stu-id="b315e-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |