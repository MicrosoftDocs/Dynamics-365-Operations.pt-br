---
title: Gerenciar licença
description: Este procedimento mostra a criação de registros de licença de funcionário.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmEmploymentLeave
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 61729d384b1a403f14ce1bcf227074aa28ab369a
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693007"
---
# <a name="manage-leave-of-absence"></a><span data-ttu-id="5d3b5-103">Gerenciar licença</span><span class="sxs-lookup"><span data-stu-id="5d3b5-103">Manage leave of absence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d3b5-104">Este procedimento mostra a criação de registros de licença de funcionário.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="5d3b5-105">Você pode rastrear tempo de licença para os motivos pelos quais incluem atividades, médicas de formação educacional, ou parentais.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="5d3b5-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="5d3b5-107">Vá para Recursos humanos > Trabalhadores > Funcionários.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="5d3b5-108">Na lista, selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="5d3b5-109">Exiba informações detalhadas sobre o funcionário selecionando o nome do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="5d3b5-110">Clique na guia Emprego.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="5d3b5-111">Clique na licença.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-111">Click Leave.</span></span>
6. <span data-ttu-id="5d3b5-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-112">Click New.</span></span>
7. <span data-ttu-id="5d3b5-113">No campo Tipo de licença, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5d3b5-114">Você pode associar um tipo de licença para um código de salário no formulário Tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="5d3b5-115">Se um tipo de licença está associado a um código de trabalho, uma linha de salário será gerada com o código associado de trabalho durante o período de licença inseridos.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="5d3b5-116">Na lista, selecione um tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="5d3b5-117">Por exemplo: Adoção</span><span class="sxs-lookup"><span data-stu-id="5d3b5-117">For example: Adoption</span></span>  
9. <span data-ttu-id="5d3b5-118">Insira a data em que a licença será iniciada.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="5d3b5-119">Exemplo '2015-10-26'</span><span class="sxs-lookup"><span data-stu-id="5d3b5-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="5d3b5-120">Por exemplo: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="5d3b5-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="5d3b5-121">Insira a data em que a licença será iniciada.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="5d3b5-122">Por exemplo: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="5d3b5-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="5d3b5-123">No campo Nota, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="5d3b5-124">Por exemplo: Deixar para adoção</span><span class="sxs-lookup"><span data-stu-id="5d3b5-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="5d3b5-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-125">Click Save.</span></span>

