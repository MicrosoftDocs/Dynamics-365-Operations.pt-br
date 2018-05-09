---
title: "Lançar transações de ativo fixo em níveis de lançamento"
description: "Este artigo oferece uma visão geral da funcionalidade de nível de lançamento para transações de ativo fixo."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a1d12f5910e38f683ee161f6fab9422db715745b
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="52a4c-103">Lançar transações de ativo fixo em níveis de lançamento</span><span class="sxs-lookup"><span data-stu-id="52a4c-103">Post fixed asset transactions to posting layers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52a4c-104">Este artigo oferece uma visão geral da funcionalidade de nível de lançamento para transações de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="52a4c-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="52a4c-105">Um ativo fixo geralmente é depreciado de diferentes maneiras para diferentes finalidades.</span><span class="sxs-lookup"><span data-stu-id="52a4c-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="52a4c-106">A depreciação para fins fiscais é calculada de acordo com as normas fiscais atuais para obter a mais alta depreciação possível antes dos impostos, mas a depreciação para fins de relatórios é calculada de acordo com as leis e padrões contábeis.</span><span class="sxs-lookup"><span data-stu-id="52a4c-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="52a4c-107">Os vários tipos de depreciação são calculados e registrados separadamente nos níveis de lançamento.</span><span class="sxs-lookup"><span data-stu-id="52a4c-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="52a4c-108">Cada registro anexado a um ativo fixo é configurado para um nível específico de lançamento que tem um objetivo de depreciação geral.</span><span class="sxs-lookup"><span data-stu-id="52a4c-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="52a4c-109">Há dez níveis de lançamento: Atual, operações, impostos, sete e níveis personalizados.</span><span class="sxs-lookup"><span data-stu-id="52a4c-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="52a4c-110">Também é possível desabilitar o lançamento na contabilidade para o registro definindo o campo Lançar na contabilidade como Não.</span><span class="sxs-lookup"><span data-stu-id="52a4c-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="52a4c-111">O campo Nível de lançamento é definido automaticamente como Nenhum.</span><span class="sxs-lookup"><span data-stu-id="52a4c-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="52a4c-112">Geralmente, os registros que não são lançados na contabilidade são usados para relatórios de imposto.</span><span class="sxs-lookup"><span data-stu-id="52a4c-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="52a4c-113">Esta abordagem fornece flexibilidade adicional para excluir transações históricas do registro de ativos, porque não foram confirmados a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="52a4c-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="52a4c-114">Fixo diários de ativos são definidos usando a página Nomes de diários em Contabilidade > Configuração de diário > Nomes de diários.</span><span class="sxs-lookup"><span data-stu-id="52a4c-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="52a4c-115">Cada diário onde você pode lançar depreciações será definido por seu nome de diário somente para um nível de lançamento.</span><span class="sxs-lookup"><span data-stu-id="52a4c-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="52a4c-116">O nível de lançamento no diário não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="52a4c-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="52a4c-117">Essa limitação ajuda a garantia que as transações de cada nível de lançamento serão mantidas separadas.</span><span class="sxs-lookup"><span data-stu-id="52a4c-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="52a4c-118">Pelo menos, um nome de diário será criado para cada nível de lançamento.</span><span class="sxs-lookup"><span data-stu-id="52a4c-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="52a4c-119">Se estiver usando registros que não são lançados na contabilidade, também precisará criar um diário no qual o nível de lançamento é definido como Nenhum.</span><span class="sxs-lookup"><span data-stu-id="52a4c-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="52a4c-120">É possível designar contas contábeis para transações de ativo fixo na página Perfis de lançamentos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="52a4c-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="52a4c-121">Para cada perfil de postagem, selecione o tipo de transação e o registro relevantes, e designar as contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="52a4c-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="52a4c-122">Configurar uma registradora de postagem de perfil para cada registro que será lançada na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="52a4c-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="52a4c-123">O uso de registros derivados permite que você lance, ao mesmo tempo, as transações em diferentes níveis de lançamento.</span><span class="sxs-lookup"><span data-stu-id="52a4c-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="52a4c-124">Você cria as transações do registro primário em um diário com o nível de lançamento correspondente ao nível de lançamento do registro.</span><span class="sxs-lookup"><span data-stu-id="52a4c-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="52a4c-125">Durante o lançamento, as transações do registro derivado serão lançadas em seus respectivos níveis de lançamento.</span><span class="sxs-lookup"><span data-stu-id="52a4c-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="52a4c-126">Para obter mais informações, consulte [Registros derivados](derived-books.md) e [Lançar com registros de depreciações derivados](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="52a4c-126">For more information see, [Derived books](derived-books.md) and [Posting with derived books](post-derived-value-models.md).</span></span>




