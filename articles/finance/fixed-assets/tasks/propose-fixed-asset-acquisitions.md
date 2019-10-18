---
title: Propor aquisições de ativo fixo
description: Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b35b13dc266fd5bccde437526400832d394b9aa
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176387"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="5eec8-103">Propor aquisições de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="5eec8-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5eec8-104">Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="5eec8-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="5eec8-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="5eec8-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="5eec8-106">No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="5eec8-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-107">Select **New**.</span></span>
3. <span data-ttu-id="5eec8-108">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5eec8-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="5eec8-109">No painel de ações, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="5eec8-110">Selecione **Propostas**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="5eec8-111">Selecione **Proposta de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="5eec8-112">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-112">Select **Filter**.</span></span> <span data-ttu-id="5eec8-113">Selecione **Redefinir** para limpar valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="5eec8-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="5eec8-114">Selecione a linha de **Número de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="5eec8-115">No campo **Critérios**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5eec8-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="5eec8-116">Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.</span><span class="sxs-lookup"><span data-stu-id="5eec8-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="5eec8-117">Selecione **OK** duas vezes a sair do painel.</span><span class="sxs-lookup"><span data-stu-id="5eec8-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="5eec8-118">Verifique as linhas de transação criadas.</span><span class="sxs-lookup"><span data-stu-id="5eec8-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="5eec8-119">Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="5eec8-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="5eec8-120">Na página, selecione a guia **Registros**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="5eec8-121">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="5eec8-121">Select **Post**.</span></span>

