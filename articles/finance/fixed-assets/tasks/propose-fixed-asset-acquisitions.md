---
title: Propor aquisições de ativo fixo
description: Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817147"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="d5310-103">Propor aquisições de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="d5310-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5310-104">Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d5310-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="d5310-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="d5310-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="d5310-106">Para adquirir um ativo fixo por meio de um diário de propostas de ativos fixos, é necessário criar o registro de ativo fixo e definir o preço de aquisição no registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="d5310-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="d5310-107">Crie uma proposta de aquisição de ativo</span><span class="sxs-lookup"><span data-stu-id="d5310-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="d5310-108">Conclua estas etapas para criar uma proposta de aquisição de ativo.</span><span class="sxs-lookup"><span data-stu-id="d5310-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="d5310-109">No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="d5310-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="d5310-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d5310-110">Select **New**.</span></span>
3. <span data-ttu-id="d5310-111">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5310-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="d5310-112">No Painel de Ações, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d5310-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="d5310-113">Selecione **Propostas**.</span><span class="sxs-lookup"><span data-stu-id="d5310-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="d5310-114">Selecione **Proposta de aquisição**.</span><span class="sxs-lookup"><span data-stu-id="d5310-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="d5310-115">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="d5310-115">Select **Filter**.</span></span> <span data-ttu-id="d5310-116">Selecione **Redefinir** para limpar valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5310-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="d5310-117">Selecione a linha de **Número de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="d5310-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="d5310-118">No campo **Critérios**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5310-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="d5310-119">Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.</span><span class="sxs-lookup"><span data-stu-id="d5310-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="d5310-120">Selecione **OK** duas vezes a sair do painel.</span><span class="sxs-lookup"><span data-stu-id="d5310-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="d5310-121">Verifique se as linhas de transação foram criadas.</span><span class="sxs-lookup"><span data-stu-id="d5310-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="d5310-122">Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="d5310-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="d5310-123">Na página, selecione a guia **Registros**.</span><span class="sxs-lookup"><span data-stu-id="d5310-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="d5310-124">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="d5310-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="d5310-125">Inclua dimensões financeiras padrão em uma proposta de aquisição</span><span class="sxs-lookup"><span data-stu-id="d5310-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="d5310-126">A transação de aquisição pode ser criada usando suplementos do Excel, acessando **Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="d5310-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="d5310-127">Crie um novo diário e mova-o para a seção **Linhas** da página e selecione o ícone do Excel. Depois, selecione uma linha de Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d5310-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="d5310-128">O sistema criará e abrirá um modelo do Excel representando linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="d5310-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="d5310-129">Você pode adicionar dados nas linhas do diário que está adicionando no modelo e publicar essas informações de volta no sistema.</span><span class="sxs-lookup"><span data-stu-id="d5310-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="d5310-130">Se as dimensões padrão foram configuradas para o registro de ativos selecionado e os ativos fixos correspondentes inseridos no modelo do Excel, as dimensões financeiras padrão serão retiradas a partir dos dados mestres de registros de ativos quando o diário for lançado do Excel para o sistema.</span><span class="sxs-lookup"><span data-stu-id="d5310-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="d5310-131">Para incluir dimensões financeiras em um registro de ativos automaticamente ao mesmo tempo em que lança o diário de ativos fixos a partir do suplemento do Excel, as dimensões padrão devem ser configuradas com antecedência.</span><span class="sxs-lookup"><span data-stu-id="d5310-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
