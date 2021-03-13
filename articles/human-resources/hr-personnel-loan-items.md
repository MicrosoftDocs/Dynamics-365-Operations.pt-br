---
title: Gerenciar itens emprestados aos trabalhadores
description: Os itens de empréstimo são registros que ajudam os gerentes a rastrear os itens físicos que sua empresa empresta aos trabalhadores.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: d34551e4a3cc08ce3fe47e8f8fd2c3cc68c0daf7
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130124"
---
# <a name="manage-items-that-are-lent-to-workers"></a><span data-ttu-id="fcda0-103">Gerenciar itens emprestados aos trabalhadores</span><span class="sxs-lookup"><span data-stu-id="fcda0-103">Manage items that are lent to workers</span></span>

<span data-ttu-id="fcda0-104">Os itens de empréstimo são registros que ajudam os gerentes a rastrear os itens físicos que sua empresa empresta aos trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="fcda0-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="fcda0-105">Os pontos a seguir são exemplos de itens que uma empresa pode emprestar aos trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="fcda0-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="fcda0-106">Telefones celulares</span><span class="sxs-lookup"><span data-stu-id="fcda0-106">Mobile telephones</span></span>
-   <span data-ttu-id="fcda0-107">Automóveis</span><span class="sxs-lookup"><span data-stu-id="fcda0-107">Automobiles</span></span>
-   <span data-ttu-id="fcda0-108">Equipamentos de informática</span><span class="sxs-lookup"><span data-stu-id="fcda0-108">Computer equipment</span></span>

<span data-ttu-id="fcda0-109">Cada item físico deve ter um item de empréstimo correspondente.</span><span class="sxs-lookup"><span data-stu-id="fcda0-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="fcda0-110">Cada registro de item de empréstimo deve descrever o que está sendo emprestado, quem é a pessoa responsável pelo empréstimo e o número de dias que o item poderá ficar emprestado a um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="fcda0-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="fcda0-111">Você pode criar vários itens de empréstimo, para itens como chaves, cartões de acesso ou uniformes, ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="fcda0-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="fcda0-112">Ao emprestar um item, insira a data que ele foi emprestado e a data de devolução planejada.</span><span class="sxs-lookup"><span data-stu-id="fcda0-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="fcda0-113">Quando o item for devolvido, insira a data real da devolução.</span><span class="sxs-lookup"><span data-stu-id="fcda0-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="fcda0-114">Os funcionários podem exibir os registros dos itens que foram emprestados a eles usando o espaço de trabalho de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="fcda0-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="fcda0-115">Eles também podem editar os registros existentes ou inserir novos itens de empréstimo, se receberem itens físicos adicionais.</span><span class="sxs-lookup"><span data-stu-id="fcda0-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="fcda0-116">O fluxo de trabalho poderá ser configurado para rotear as alterações a itens de empréstimo novos ou existentes por meio de um processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="fcda0-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="fcda0-117">Os gerentes podem exibir itens emprestados para seus subordinados diretos.</span><span class="sxs-lookup"><span data-stu-id="fcda0-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="fcda0-118">Eles também podem ter permissão para adicionar novos itens de empréstimo em nome dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="fcda0-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="fcda0-119">Conta para itens de empréstimo perdidos ou extraviados</span><span class="sxs-lookup"><span data-stu-id="fcda0-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="fcda0-120">Se um item for danificado ou extraviado, insira um registro de devolução fictícia.</span><span class="sxs-lookup"><span data-stu-id="fcda0-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="fcda0-121">Em seguida, exclua o item ou mantenha-o na visão geral e altere a descrição para indicar que ele não está disponível.</span><span class="sxs-lookup"><span data-stu-id="fcda0-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="additional-resources"></a><span data-ttu-id="fcda0-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="fcda0-122">Additional resources</span></span>
--------

[<span data-ttu-id="fcda0-123">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="fcda0-123">Human resources</span></span>](index.md)



