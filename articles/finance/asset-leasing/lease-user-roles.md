---
title: Atribuir funções de usuário de arrendamento
description: Este tópico descreve as funções de segurança usadas no Arrendamento de ativos. Também explica como atribuir usuários a essas funções.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: df23e219f5bd859b0072785dfd5f7a0ec63f540e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995384"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="5ed5d-104">Atribuir funções de usuário de arrendamento</span><span class="sxs-lookup"><span data-stu-id="5ed5d-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ed5d-105">Este tópico descreve as funções de segurança usadas no Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="5ed5d-106">Também explica como atribuir usuários a essas funções.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="5ed5d-107">Três funções de usuário diferenciam o acesso no Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="5ed5d-108">Uma função é apropriada para manter arrendamentos, uma é apropriada para exibir arrendamentos e uma é apropriada para realizar as obrigações de um auxiliar de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="5ed5d-109">Cada função tem permissões específicas para todas as páginas de arrendamento e permite que os usuários exibam, criem, editem ou excluam arrendamentos de acordo com suas tarefas.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="5ed5d-110">Função</span><span class="sxs-lookup"><span data-stu-id="5ed5d-110">Role</span></span>           | <span data-ttu-id="5ed5d-111">descrição</span><span class="sxs-lookup"><span data-stu-id="5ed5d-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="5ed5d-112">Manter Arrendamento</span><span class="sxs-lookup"><span data-stu-id="5ed5d-112">Maintain Lease</span></span> | <span data-ttu-id="5ed5d-113">Os usuários nessa função podem adicionar, editar, excluir e exibir arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="5ed5d-114">Essa função foi criada para usuários diários cujas tarefas incluem a criação e o lançamento de entradas de diário mensal e a adição de novos arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="5ed5d-115">Essa função dá acesso a toda a funcionalidade de Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="5ed5d-116">Exibir Arrendamento</span><span class="sxs-lookup"><span data-stu-id="5ed5d-116">View Lease</span></span>     | <span data-ttu-id="5ed5d-117">Os usuários nessa função só podem exibir registros de arrendamento, agendas e executar relatórios.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="5ed5d-118">Eles não podem criar novos arrendamentos, editar arrendamentos existentes ou criar entradas de diário em arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="5ed5d-119">A função foi criada para usuários que só precisam exibir arrendamentos, agendas de arrendamento e transações que ocorrem nesses arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="5ed5d-120">Auxiliar de Arrendamento</span><span class="sxs-lookup"><span data-stu-id="5ed5d-120">Lease Clerk</span></span>    | <span data-ttu-id="5ed5d-121">Os usuários nessa função só podem criar novos arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="5ed5d-122">Eles não podem editar ou excluir arrendamentos existentes, exibir agendas de arrendamento ou lançar entradas de diário de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="5ed5d-123">Essa função foi criada para usuários que trabalham em uma capacidade de entrada de dados.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="5ed5d-124">Siga estas etapas para atribuir aos usuários as funções usadas em Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="5ed5d-125">Vá para **Administração do sistema \> Segurança \> Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="5ed5d-126">Selecione a função **Manter arrendamento**, **Auxiliar de arrendamento** ou **Exibir arrendamento** e depois selecione **Atribuir/excluir usuários manualmente**.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="5ed5d-127">Selecione o usuário a ser atribuído à função e selecione **Atribuir à função**.</span><span class="sxs-lookup"><span data-stu-id="5ed5d-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>