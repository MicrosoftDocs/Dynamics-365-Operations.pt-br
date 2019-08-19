---
title: Lançar com registros de depreciações derivados
description: Este artigo descreve como usar registros de registros derivadas.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b58b2da949211f7eef804af98c866bf5074d47f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840280"
---
# <a name="post-with-derived-books"></a><span data-ttu-id="7e86c-103">Lançar com registros de depreciações derivados</span><span class="sxs-lookup"><span data-stu-id="7e86c-103">Post with derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e86c-104">Este artigo descreve como usar registros de registros derivadas.</span><span class="sxs-lookup"><span data-stu-id="7e86c-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="7e86c-105">Quando você lança transações para um registro que contém registros derivados, as transações do registro de depreciações derivadas são lançadas automaticamente a partir dos diários, das ordens de compra ou do faturamento de texto livre.</span><span class="sxs-lookup"><span data-stu-id="7e86c-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="7e86c-106">Entretanto, se as transações primárias do registro forem preparadas no diário de Ativos fixos, você poderá exibir e modificar os valores das transações derivadas antes de lançá-las.</span><span class="sxs-lookup"><span data-stu-id="7e86c-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="7e86c-107">Certas contas, como as contas de impostos sobre vendas, de cliente ou de fornecedor, são atualizadas apenas uma vez pelos lançamentos do método de depreciação primário.</span><span class="sxs-lookup"><span data-stu-id="7e86c-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="7e86c-108">As transações de registro derivado são lançadas nas contas definidas para o registro derivado na página Perfis de lançamento de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="7e86c-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="7e86c-109">A aquisição geralmente é usada como o tipo de transação para o registro derivado.</span><span class="sxs-lookup"><span data-stu-id="7e86c-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="7e86c-110">Use essa opção quando o registro e o registro de depreciações derivadas devem ser aplicados ao ativo fixo a partir do momento da aquisição desse ativo.</span><span class="sxs-lookup"><span data-stu-id="7e86c-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="7e86c-111">Outros valores do tipo de transação também podem ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="7e86c-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="7e86c-112">Por exemplo, se o registro principal e os registros de depreciações derivadas tiverem os mesmos intervalos relativos à venda ou à alienação, todos os tipos de transação de ativo fixo estarão disponíveis para a configuração de um registro derivado.</span><span class="sxs-lookup"><span data-stu-id="7e86c-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="7e86c-113">A depreciação lançada no registro de depreciações derivadas terá o mesmo valor que foi lançado para o registro principal.</span><span class="sxs-lookup"><span data-stu-id="7e86c-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="7e86c-114">Se os métodos de depreciação forem diferentes, as transações de registros não devem ser geradas usando o processo derivado.</span><span class="sxs-lookup"><span data-stu-id="7e86c-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="7e86c-115">exemplo</span><span class="sxs-lookup"><span data-stu-id="7e86c-115">Example</span></span> 
<span data-ttu-id="7e86c-116">As informações a seguir descrevem como configurar transações de aquisição com a funcionalidade do registro derivado.</span><span class="sxs-lookup"><span data-stu-id="7e86c-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="7e86c-117">Crie os registros na página de registros.</span><span class="sxs-lookup"><span data-stu-id="7e86c-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="7e86c-118">O registro para contabilidade: VM 1, Nível de lançamento atual</span><span class="sxs-lookup"><span data-stu-id="7e86c-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="7e86c-119">O registro para fins de tributação: VM 2, Nível de lançamento de imposto</span><span class="sxs-lookup"><span data-stu-id="7e86c-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="7e86c-120">Em VM 1, clique na guia Registros derivados. Selecione VM 2 no campo Registro e Aquisição no campo Tipo de transação.</span><span class="sxs-lookup"><span data-stu-id="7e86c-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="7e86c-121">Em seguida, os registros poderão ser anexados a ativos fixos específicos.</span><span class="sxs-lookup"><span data-stu-id="7e86c-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="7e86c-122">Quando uma aquisição for lançada para um ativo fixo com o livro VM 1, a aquisição não será lançada somente em VM 1, mas também no registro do livro derivado VM 2.</span><span class="sxs-lookup"><span data-stu-id="7e86c-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="7e86c-123">O status dos livros de ativo fixo é atualizado para Aberto.</span><span class="sxs-lookup"><span data-stu-id="7e86c-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="7e86c-124">Se você não usar registros derivados, será necessário lançar a aquisição do ativo fixo tanto para o método VM 1 como para o registro VM 2.</span><span class="sxs-lookup"><span data-stu-id="7e86c-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="7e86c-125">Para obter mais informações, consulte [Registros derivados](derived-books.md).</span><span class="sxs-lookup"><span data-stu-id="7e86c-125">For more information, see [Derived books](derived-books.md)</span></span>



