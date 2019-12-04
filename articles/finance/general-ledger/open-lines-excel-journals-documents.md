---
title: Publicar linhas de diário e documentos do Excel
description: Este tópico explica como inserir e publicar linhas de diários gerais do Microsoft Excel. Inclui informações sobre os vários modelos que podem ser usados, dependendo do tipo de transação que você está inserindo.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5619460a36d23a25c793c660a54e98593820c46
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176364"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a><span data-ttu-id="4114f-104">Publicar linhas de diário e documentos do Excel</span><span class="sxs-lookup"><span data-stu-id="4114f-104">Publish journal lines and documents from Excel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4114f-105">Este tópico explica como inserir e publicar linhas de diários gerais do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4114f-105">This topic explains how to enter and publish lines for general journals from Microsoft Excel.</span></span> <span data-ttu-id="4114f-106">Inclui informações sobre os vários modelos que podem ser usados, dependendo do tipo de transação que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="4114f-106">It includes information about the various templates that you can use, depending on the type of transactions that you're entering.</span></span>

<span data-ttu-id="4114f-107">Os usuários podem inserir e publicar linhas para diários financeiros do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4114f-107">Users can enter and publish lines for financial journals from Microsoft Excel.</span></span> <span data-ttu-id="4114f-108">Depois que um usuário cria um diário, o botão **Abrir linhas no Excel** exibe modelos que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4114f-108">After a user creates a journal, the **Open lines in Excel** button displays the templates that are available.</span></span> <span data-ttu-id="4114f-109">Os modelos são criados para oferecer suporte a cenários específicos, porém nem todas combinações de tipo de conta são suportadas no diário.</span><span class="sxs-lookup"><span data-stu-id="4114f-109">Templates are designed to support specific scenarios, however not every combination of account type is supported in the journal.</span></span> <span data-ttu-id="4114f-110">A tabela a seguir mostra os modelos disponíveis e os tipos de conta às quais oferecem suporte.</span><span class="sxs-lookup"><span data-stu-id="4114f-110">The following table shows the templates that are available and the account types which they support.</span></span>

|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| <span data-ttu-id="4114f-111">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="4114f-111">**Template**</span></span>             | <span data-ttu-id="4114f-112">**Tipos de conta compatíveis**</span><span class="sxs-lookup"><span data-stu-id="4114f-112">**Supported account types**</span></span>                                                                                             | <span data-ttu-id="4114f-113">**Como acessar o modelo**</span><span class="sxs-lookup"><span data-stu-id="4114f-113">**How to access the template**</span></span>                                                          |
| <span data-ttu-id="4114f-114">Linhas do diário-razão</span><span class="sxs-lookup"><span data-stu-id="4114f-114">Ledger journal lines</span></span>     | <span data-ttu-id="4114f-115">Conta: razão, cliente, fornecedor, contrapartida do banco: razão, cliente, fornecedor, intercompanhia de banco é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-115">Account: Ledger, Customer, Vendor, Bank Offset account: Ledger, Customer, Vendor, Bank Intercompany is supported.</span></span>       | <span data-ttu-id="4114f-116">Diário geral</span><span class="sxs-lookup"><span data-stu-id="4114f-116">General journal</span></span>                                                                         |
| <span data-ttu-id="4114f-117">Registro de fatura</span><span class="sxs-lookup"><span data-stu-id="4114f-117">Invoice register</span></span>         | <span data-ttu-id="4114f-118">Contas: Contrapartida de fornecedor: Razão intercompanhia não é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-118">Account: Vendor Offset account: Ledger Intercompany isn't supported.</span></span>                                                    | <span data-ttu-id="4114f-119">Registro de fatura AP</span><span class="sxs-lookup"><span data-stu-id="4114f-119">AP invoice register</span></span>                                                                     |
| <span data-ttu-id="4114f-120">Diário de faturas</span><span class="sxs-lookup"><span data-stu-id="4114f-120">Invoice journal</span></span>          | <span data-ttu-id="4114f-121">Contas: Contrapartida de fornecedor: Razão intercompanhia é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-121">Accounts: Vendor Offset account: Ledger Intercompany is supported.</span></span>                                                      | <span data-ttu-id="4114f-122">Diário de faturas AP</span><span class="sxs-lookup"><span data-stu-id="4114f-122">AP invoice journal</span></span>                                                                      |
| <span data-ttu-id="4114f-123">Fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="4114f-123">Vendor invoice</span></span>           |                                                                                                                         | <span data-ttu-id="4114f-124">Fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="4114f-124">Vendor invoice</span></span>                                                                          |
| <span data-ttu-id="4114f-125">Diário de faturas de clientes</span><span class="sxs-lookup"><span data-stu-id="4114f-125">Customer invoice journal</span></span> | <span data-ttu-id="4114f-126">Conta: Contrapartida de cliente: Razão intercompanhia é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-126">Account: Customer Offset account: Ledger Intercompany is supported.</span></span>                                                     | <span data-ttu-id="4114f-127">Diário geral</span><span class="sxs-lookup"><span data-stu-id="4114f-127">General journal</span></span>                                                                         |
| <span data-ttu-id="4114f-128">Fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="4114f-128">Free text invoice</span></span>        |                                                                                                                         | <span data-ttu-id="4114f-129">Na página **Fatura de texto livre**, clique em **Abrir no Excel** (o ícone do Microsoft Office).</span><span class="sxs-lookup"><span data-stu-id="4114f-129">On the **Free text invoice** page, click **Open in Excel** (the Microsoft Office icon).</span></span> |
| <span data-ttu-id="4114f-130">Diário de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="4114f-130">Fixed assets journal</span></span>     | <span data-ttu-id="4114f-131">Ativo fixo para o razão, banco, cliente ou fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4114f-131">Asset to ledger, bank, customer, or vendor.</span></span> <span data-ttu-id="4114f-132">A intercompanhia não é aceita.</span><span class="sxs-lookup"><span data-stu-id="4114f-132">Intercompany isn't supported.</span></span>                                               | <span data-ttu-id="4114f-133">Diário de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="4114f-133">Fixed asset journal</span></span>                                                                     |
| <span data-ttu-id="4114f-134">Diário de pagamentos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="4114f-134">Vendor payment journal</span></span>   | <span data-ttu-id="4114f-135">Conta: Contrapartida de fornecedor: Intercompanhia de banco é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-135">Account: Vendor Offset account: Ledger, Bank Intercompany is supported.</span></span>                                                 | <span data-ttu-id="4114f-136">Diário de pagamentos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="4114f-136">Vendor payment journal</span></span>                                                                  |
| <span data-ttu-id="4114f-137">Diário de pagamentos do cliente</span><span class="sxs-lookup"><span data-stu-id="4114f-137">Customer payment journal</span></span> | <span data-ttu-id="4114f-138">Conta: Contrapartida de cliente: Razão, banco intercompanhia é suportado.</span><span class="sxs-lookup"><span data-stu-id="4114f-138">Account: Customer Offset account: Ledger, Bank Intercompany is supported.</span></span>                                               | <span data-ttu-id="4114f-139">Diário de pagamentos do cliente</span><span class="sxs-lookup"><span data-stu-id="4114f-139">Customer payment journal</span></span>                                                                |
| <span data-ttu-id="4114f-140">Diário de despesas de projeto</span><span class="sxs-lookup"><span data-stu-id="4114f-140">Project expense journal</span></span>  | <span data-ttu-id="4114f-141">Conta: projeto, razão, cliente, contrapartida de fornecedor: projeto, razão, cliente, intercompanhia de fornecedor é suportada.</span><span class="sxs-lookup"><span data-stu-id="4114f-141">Account: Project, Ledger, Customer, Vendor Offset account: Project, Ledger, Customer, Vendor Intercompany is supported.</span></span> | <span data-ttu-id="4114f-142">Despesas gerais de diários (em gerenciamento de projetos e contabilidade)</span><span class="sxs-lookup"><span data-stu-id="4114f-142">General journal Expense (under Project management and accounting)</span></span>                       |

<span data-ttu-id="4114f-143">Quando as linhas são publicadas, foram validadas para garantir que elas são compatíveis com as regras definidas nos diários financeiros.</span><span class="sxs-lookup"><span data-stu-id="4114f-143">When the lines are published, they are validated to make sure that they comply with the rules that are set up in the financial journals.</span></span> <span data-ttu-id="4114f-144">Depois que as linhas são publicadas, os usuários podem editar ou lançar os comprovantes do Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="4114f-144">After the lines are published, users can edit or post the vouchers from Dynamics 365 Finance.</span></span> 

<span data-ttu-id="4114f-145">Para adicionar dimensões financeiras a um modelo, alterações adicionais são necessárias.</span><span class="sxs-lookup"><span data-stu-id="4114f-145">To add financial dimensions to a template, additional changes are required.</span></span> <span data-ttu-id="4114f-146">Para obter informações adicionais, consulte [Adicionar dimensões ao modelo do Microsoft Excel](../../dev-itpro/financial/add-dimensions-excel-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4114f-146">For additional information, see [Add dimensions to the Microsoft Excel template](../../dev-itpro/financial/add-dimensions-excel-templates.md).</span></span> <span data-ttu-id="4114f-147">Depois que as dimensões são adicionadas à entidade, estarão disponíveis no designer do Excel e poderão ser adicionadas ao modelo.</span><span class="sxs-lookup"><span data-stu-id="4114f-147">After dimensions are added to the entity, they are available in the Excel designer and can be added to the template.</span></span>




