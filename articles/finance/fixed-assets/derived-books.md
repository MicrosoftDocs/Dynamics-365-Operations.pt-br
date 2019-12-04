---
title: Registros derivados
description: Este artigo oferece uma visão geral da funcionalidade de registro derivado.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c31116ba234bd1fce445ac382fe8f8aea263a66
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769468"
---
# <a name="derived-books"></a><span data-ttu-id="dde6e-103">Registros derivados</span><span class="sxs-lookup"><span data-stu-id="dde6e-103">Derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dde6e-104">Este artigo oferece uma visão geral da funcionalidade de registro derivado.</span><span class="sxs-lookup"><span data-stu-id="dde6e-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="dde6e-105">A finalidade dos registros de depreciações derivados é simplificar o lançamento de transações do registro de ativo fixo planejadas para intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="dde6e-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="dde6e-106">Você escolhe um registro como o principal.</span><span class="sxs-lookup"><span data-stu-id="dde6e-106">You choose one book as the primary book.</span></span> <span data-ttu-id="dde6e-107">Esse geralmente é o registro usado para depreciação contábil.</span><span class="sxs-lookup"><span data-stu-id="dde6e-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="dde6e-108">Você o associa a outros registros configurados para lançar transações nos mesmos intervalos do registro principal.</span><span class="sxs-lookup"><span data-stu-id="dde6e-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="dde6e-109">Os registros do imposto costumam ser definidos como sendo registros derivados.</span><span class="sxs-lookup"><span data-stu-id="dde6e-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="dde6e-110">As transações mais comuns a serem definidas para o lançamento nos registros derivados são aquisições, ajustes de aquisição e alienações.</span><span class="sxs-lookup"><span data-stu-id="dde6e-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="dde6e-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dde6e-111">Example</span></span>

<span data-ttu-id="dde6e-112">Registro B e registro C são definidos como registros derivados para registro A para o tipo de transação de aquisição.</span><span class="sxs-lookup"><span data-stu-id="dde6e-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="dde6e-113">No registro A, insira uma transação de aquisição para o ativo 123 de 1.500,00.</span><span class="sxs-lookup"><span data-stu-id="dde6e-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="dde6e-114">Quando a transação é lançada, uma transação de aquisição é gerada e lançada no ativo 123 para o registro B e no ativo 123 para o método de depreciação C em 1.500,00.</span><span class="sxs-lookup"><span data-stu-id="dde6e-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="dde6e-115">Quando você prepara as transações do registro primário para o lançamento no diário de ativo fixo, também é possível exibir e modificar as transações dos registros de depreciações derivados.</span><span class="sxs-lookup"><span data-stu-id="dde6e-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="dde6e-116">Caso você prepare as transações do registro principal em outro diário, as transações do método derivado não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="dde6e-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="dde6e-117">No entanto, são lançadas nas contas e nos níveis de lançamento apropriados quando você lança as transações do registro principal.</span><span class="sxs-lookup"><span data-stu-id="dde6e-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="dde6e-118">Os registros definidos para o lançamento das transações em intervalos que não sejam os do registro principal devem ser anexados ao ativo fixo como registros separados, e não derivados.</span><span class="sxs-lookup"><span data-stu-id="dde6e-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="dde6e-119">Para obter mais informações, consulte [Lançar com registros de derivados](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="dde6e-119">For more information, see [Post with derived books](post-derived-value-models.md).</span></span>


