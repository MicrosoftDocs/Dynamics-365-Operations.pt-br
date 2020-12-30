---
title: Criar um grupo de arrendamento
description: Este tópico explica como configurar grupos de arrendamento. Os grupos de arrendamento são necessários para criar novos arrendamentos.
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
ms.openlocfilehash: f8512a59d0e9935090f97a0f0237bfefc8473955
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440550"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="a196c-104">Criar um grupo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a196c-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a196c-105">Este tópico explica como configurar grupos de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="a196c-106">Os grupos de arrendamento são necessários para criar novos arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="a196c-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="a196c-107">Os registros de arrendamento estão associados a cada grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="a196c-108">Os registros de arrendamento determinam os registros padrão que devem ser criados para cada arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="a196c-109">Você pode atribuir contas específicas a um grupo de arrendamento na página **Parâmetros de lançamento de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="a196c-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="a196c-110">Criar um registro de arrendamento e adicionar um grupo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a196c-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="a196c-111">Acesse **Arrendamento de ativo \> Configuração \> Grupos de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="a196c-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="a196c-112">No Painel de ações, selecione **Novo** para adicionar um grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="a196c-113">Uma linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="a196c-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="a196c-114">Na nova linha, no campo **Grupo de arrendamento**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="a196c-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="a196c-115">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="a196c-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="a196c-116">As informações inseridas são adicionadas ao campo **Grupo de arrendamento** na página **Adicionar arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="a196c-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="a196c-117">Associar um registro a um grupo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a196c-117">Associate a book with a lease group</span></span>

<span data-ttu-id="a196c-118">Depois de criar grupos de arrendamento, você pode atribuir registros a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="a196c-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="a196c-119">Ao criar um arrendamento e atribuí-lo a um grupo de arrendamento, o sistema cria um conjunto de agendas para cada registro associado a esse grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="a196c-120">Os registros devem ser configurados antes que possam ser atribuídos a um grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="a196c-121">Acesse **Arrendamento de ativo \> Configuração \> Grupo de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="a196c-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="a196c-122">Selecione um grupo de arrendamento e, em seguida, selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="a196c-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="a196c-123">Selecione **Novo** e, no campo **Tipo de registro**, selecione o registro a ser atribuído ao grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="a196c-124">Caso seja necessário considerar um arrendamento de maneiras diferentes, você pode atribuir vários registros a um grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a196c-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>
