---
title: Propor aquisições de ativo fixo
description: Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 426a5e42c1fc26958ab37eddd915334f8b0e19cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205019"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="65a8e-103">Propor aquisições de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="65a8e-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="65a8e-104">Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="65a8e-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="65a8e-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="65a8e-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="65a8e-106">Para adquirir um ativo fixo por meio de um diário de propostas de ativos fixos, é necessário criar o registro de ativo fixo e definir o preço de aquisição no registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="65a8e-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="65a8e-107">No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="65a8e-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-108">Select **New**.</span></span>
3. <span data-ttu-id="65a8e-109">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="65a8e-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="65a8e-110">No painel de ações, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="65a8e-111">Selecione **Propostas**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="65a8e-112">Selecione **Proposta de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="65a8e-113">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-113">Select **Filter**.</span></span> <span data-ttu-id="65a8e-114">Selecione **Redefinir** para limpar valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="65a8e-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="65a8e-115">Selecione a linha de **Número de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="65a8e-116">No campo **Critérios**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="65a8e-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="65a8e-117">Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.</span><span class="sxs-lookup"><span data-stu-id="65a8e-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="65a8e-118">Selecione **OK** duas vezes a sair do painel.</span><span class="sxs-lookup"><span data-stu-id="65a8e-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="65a8e-119">Verifique as linhas de transação criadas.</span><span class="sxs-lookup"><span data-stu-id="65a8e-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="65a8e-120">Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="65a8e-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="65a8e-121">Na página, selecione a guia **Registros**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="65a8e-122">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="65a8e-122">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]