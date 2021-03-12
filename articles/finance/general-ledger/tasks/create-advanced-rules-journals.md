---
title: Criar regras avançadas para diários
description: Este procedimento aborda a criação de regras avançadas para diários.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c06855c7a7648c5829b90bc548a7d2e400967698
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988593"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="d0394-103">Criar regras avançadas para diários</span><span class="sxs-lookup"><span data-stu-id="d0394-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0394-104">Este procedimento aborda a criação de regras avançadas para diários.</span><span class="sxs-lookup"><span data-stu-id="d0394-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="d0394-105">Inclui a configuração de controle de diário e restrições de lançamento de usuário.</span><span class="sxs-lookup"><span data-stu-id="d0394-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="d0394-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="d0394-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="d0394-107">Configurar controle do diário</span><span class="sxs-lookup"><span data-stu-id="d0394-107">Set up journal control</span></span>
1. <span data-ttu-id="d0394-108">No **Painel de Navegação**, vá para **Módulos > Contabilidade > Configuração do diário > Nomes de diário**.</span><span class="sxs-lookup"><span data-stu-id="d0394-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="d0394-109">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d0394-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d0394-110">No **Painel de Ações**, clique em **Controle de diário**.</span><span class="sxs-lookup"><span data-stu-id="d0394-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="d0394-111">Na Guia Rápida **Que tipos de conta podem ser lançados?**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d0394-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="d0394-112">No campo **Contas da empresa**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d0394-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d0394-113">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d0394-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d0394-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0394-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d0394-115">Na Guia Rápida **Que valores de segmento são válidos para este diário?**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d0394-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="d0394-116">No campo **Estrutura de conta**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d0394-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d0394-117">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d0394-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="d0394-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0394-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d0394-119">No campo **Segmento**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d0394-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="d0394-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0394-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d0394-121">No campo **Valor inicial**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d0394-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d0394-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d0394-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d0394-123">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0394-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d0394-124">No campo **Valor final**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d0394-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="d0394-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d0394-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="d0394-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0394-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="d0394-127">Configurar restrições de lançamento</span><span class="sxs-lookup"><span data-stu-id="d0394-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="d0394-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d0394-128">Close the page.</span></span>
2. <span data-ttu-id="d0394-129">Clique em **Restrições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="d0394-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="d0394-130">No campo **Como deseja configurar as restrições de lançamento**, selecione "Por grupo de usuários".</span><span class="sxs-lookup"><span data-stu-id="d0394-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="d0394-131">Na árvore, verifique 'o grupo do qual deseja permitir o lançamento para o nome desse diário'.</span><span class="sxs-lookup"><span data-stu-id="d0394-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="d0394-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0394-132">Click **OK**.</span></span>

