---
title: Despesas intercompanhia
description: Um trabalhador contratado por uma entidade legal em uma organização pode executar o trabalho para outra entidade legal na mesma organização. Nessa situação, será possível usar o recurso de despesas intercompanhia para atribuir as despesas do trabalhador para a entidade legal à qual o trabalho foi realizado.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390875"
---
# <a name="intercompany-expenses"></a><span data-ttu-id="d0b0a-104">Despesas intercompanhia</span><span class="sxs-lookup"><span data-stu-id="d0b0a-104">Intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0b0a-105">Um trabalhador contratado por uma entidade legal em uma organização pode executar o trabalho para outra entidade legal na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-105">A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization.</span></span> <span data-ttu-id="d0b0a-106">Nessa situação, será possível usar o recurso de despesas intercompanhia para atribuir as despesas do trabalhador para a entidade legal à qual o trabalho foi realizado.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-106">In this situation, you can use the intercompany expense feature to assign the worker’s expenses to the legal entity for which the work was performed.</span></span> <span data-ttu-id="d0b0a-107">A entidade legal que emprega o trabalhador é chamada de entidade legal de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-107">The legal entity that employs the worker is called the loaning legal entity.</span></span> <span data-ttu-id="d0b0a-108">As entidade legal para a qual o trabalhador incorre as despesas é chamada de entidade legal de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-108">The legal entity for which the worker incurs expenses is called the borrowing legal entity.</span></span> 

<span data-ttu-id="d0b0a-109">Antes que um trabalhador possa criar e enviar despesas de trabalho executadas para uma pessoa jurídica diferente, na entidade legal do empréstimo, na página **Parâmetros de gerenciamento de despesas** , selecione a opção **Permitir linhas de despesa intercompanhia** .</span><span class="sxs-lookup"><span data-stu-id="d0b0a-109">Before a worker can create and submit expenses for work that is performed for a different legal entity, in the loaning legal entity, on the **Expense management parameters** page, select the **Allow intercompany expense lines** option.</span></span> 

## <a name="tax-posting-for-intercompany-expenses"></a><span data-ttu-id="d0b0a-110">Lançamento de imposto para despesas intercompanhia</span><span class="sxs-lookup"><span data-stu-id="d0b0a-110">Tax posting for intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0b0a-111">Se você deseja usar grupos de impostos associados à entidade legal de empréstimo (origem) em vez da entidade legal de empréstimo (destino) no seu relatório de despesas, será necessário configurá-lo na configuração do imposto sobre vendas da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-111">If you want to use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you will need to configure this in the General ledger sales tax set up.</span></span> <span data-ttu-id="d0b0a-112">Quando o parâmetro da contabilidade **Entidade legal para lançamento de imposto intercompanhia** é definido como **Origem** e **Aplicar regras de tributação de imposto sobre vendas** está definido como **Não**, a combinação de impostos para a entidade legal de empréstimo será usada.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-112">When the General ledger parameter, **Legal entity for intercompany tax posting** is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity will be used.</span></span> <span data-ttu-id="d0b0a-113">Quando o mesmo parâmetro é definido como **Destino**, a combinação de impostos para a entidade legal de empréstimo será usada.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-113">When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used.</span></span> <span data-ttu-id="d0b0a-114">Para entidades legais nos Estados Unidos, quando o parâmetro é definido como **origem**, o campo **Imposto sobre vendas a receber** também deve ser configurado na página **Novos grupos de lançamento contábil**.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-114">For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page.</span></span> <span data-ttu-id="d0b0a-115">O mecanismo de contabilidade usará as informações deste campo para entrada contábil relacionada ao imposto.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-115">The accounting engine will use the information from this field for tax related accounting entry.</span></span>   
<span data-ttu-id="d0b0a-116">O comportamento é consistente para linhas de despesas lançadas com ou sem um projeto.</span><span class="sxs-lookup"><span data-stu-id="d0b0a-116">The behavior is consistent for expense lines posted with or without a project.</span></span>  
