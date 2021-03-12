---
title: Configurar modelos de depreciação
description: Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92c965775980d15e367b8cd5742d3bc61c3f698c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994781"
---
# <a name="set-up-value-models"></a><span data-ttu-id="3b1c0-103">Configurar modelos de depreciação</span><span class="sxs-lookup"><span data-stu-id="3b1c0-103">Set up value models</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b1c0-104">Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="3b1c0-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="3b1c0-106">Criar um registro</span><span class="sxs-lookup"><span data-stu-id="3b1c0-106">Create a book</span></span>
1. <span data-ttu-id="3b1c0-107">Vá para Ativos fixos > Configuração > Registros.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="3b1c0-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-108">Click New.</span></span>
3. <span data-ttu-id="3b1c0-109">No campo Registro, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="3b1c0-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3b1c0-111">Se a opção Calcular a depreciação for selecionada, o registro de ativos associado será incluído nas propostas de depreciação.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="3b1c0-112">Se não estiver selecionado, o registro de ativos não será depreciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="3b1c0-113">Selecione Sim no campo Calcular depreciação.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="3b1c0-114">No campo Perfil de depreciação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="3b1c0-115">Um perfil de depreciação alternativo também é conhecido como um método alternativo de depreciação.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="3b1c0-116">A proposta de depreciação alternará para esse perfil quando o perfil alternativo calcular um valor de depreciação que seja igual ou maior do que o perfil de depreciação padrão.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="3b1c0-117">O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="3b1c0-118">Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="3b1c0-119">Se criar ajustes de depreciação com os ajustes de base for selecionado, os ajustes de depreciação serão criados automaticamente quando o valor do ativo fixo for atualizado.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="3b1c0-120">Se não estiver selecionado, o valor dos ativos atualizados afetará apenas os cálculos de depreciação seguintes.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="3b1c0-121">Selecione Sim no campo Criar ajustes de depreciação com ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="3b1c0-122">Por padrão, as transações do registro de ativos serão lançadas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="3b1c0-123">Você pode desabilitar o lançamento na contabilidade para o registro definindo o campo Lançar na contabilidade como Não.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="3b1c0-124">Os registros que não são lançados na contabilidade geralmente são usados para relatórios de imposto.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="3b1c0-125">Isso fornece flexibilidade adicional para excluir transações históricas do registro de ativos porque elas não foram confirmadas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="3b1c0-126">O nível de lançamento usará como padrão a camada atual se o registro fizer lançamentos na contabilidade e Nenhuma se não fizer.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="3b1c0-127">Atualize o nível de lançamento se você necessitar que as transações desse registro sejam lançadas em uma camada diferente.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="3b1c0-128">No campo Calendário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="3b1c0-129">Os registros derivados lançarão transações em registros diferentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="3b1c0-130">Você cria as transações com o registro principal e, durante um lançamento, uma cópia exata da transação será lançada no registro derivado.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="3b1c0-131">Não há recálculo com transações derivadas do registro, portanto ele não deve ser usado para transações de depreciação.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="3b1c0-132">Associar o registro a um grupo de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="3b1c0-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="3b1c0-133">Clique em Grupos de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="3b1c0-134">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="3b1c0-135">No campo Vida útil, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="3b1c0-136">Observe que os períodos de depreciação são calculados depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="3b1c0-137">Você pode definir a convenção de depreciação conforme necessário para fins tributários.</span><span class="sxs-lookup"><span data-stu-id="3b1c0-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  

