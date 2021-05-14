---
title: Variáveis de teste de gerenciamento de qualidade
description: Este tópico descreve como criar variáveis de teste que possam ser usadas para testes qualitativos em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e94972b41baf3f59a633fa7bbc7434abfb90460
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956549"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="b81dc-103">Variáveis de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="b81dc-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b81dc-104">Este tópico descreve como criar variáveis de teste que possam ser usadas para testes qualitativos em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b81dc-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b81dc-105">Para cada teste qualitativo definido na página **Testes**, você deve definir uma variável de teste e seus possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="b81dc-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="b81dc-106">(Para testes qualitativos, o campo **Tipo** na página **Testes** é definido como *Opção*.)</span><span class="sxs-lookup"><span data-stu-id="b81dc-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="b81dc-107">Use a página **Variáveis de teste** para configurar, editar e exibir os possíveis resultados de uma variável de teste associada a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="b81dc-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="b81dc-108">Para cada resultado, você atribui um status de resultado *Aprovado* ou *Reprovado* para indicar se o teste é aprovado ou reprovado quando esse resultado é selecionado como resultado do teste.</span><span class="sxs-lookup"><span data-stu-id="b81dc-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="b81dc-109">Use a página **Grupos de teste** para atribuir uma variável de teste e um resultado padrão a um teste qualitativo individual.</span><span class="sxs-lookup"><span data-stu-id="b81dc-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="b81dc-110">Para cada variável de teste, recomendamos que você defina pelo menos dois resultados: um que tenha o status de resultado *Aprovado* e um que tenha o status de resultado *Reprovado*.</span><span class="sxs-lookup"><span data-stu-id="b81dc-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="b81dc-111">Não há limite para o número total de variáveis ou resultados que podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="b81dc-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="b81dc-112">Além disso, vários testes podem usar as mesmas variáveis de teste para registrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="b81dc-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="b81dc-113">Exemplos de variáveis de teste</span><span class="sxs-lookup"><span data-stu-id="b81dc-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="b81dc-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b81dc-114">Example 1</span></span>

<span data-ttu-id="b81dc-115">Uma empresa de fabricação realiza dois testes em materiais fabricados.</span><span class="sxs-lookup"><span data-stu-id="b81dc-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="b81dc-116">Em um teste, o nível de pH é associado a uma faixa colorida.</span><span class="sxs-lookup"><span data-stu-id="b81dc-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="b81dc-117">Os níveis de pH aceitáveis aparecem em cores mais claras, e os níveis de pH inaceitáveis aparecem em cores mais escuras.</span><span class="sxs-lookup"><span data-stu-id="b81dc-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="b81dc-118">Em outro teste, várias inspeções visuais são realizadas, e os trabalhadores de qualidade usam seu julgamento para determinar se o item é aprovado ou reprovado na inspeção visual.</span><span class="sxs-lookup"><span data-stu-id="b81dc-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="b81dc-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b81dc-119">Example 2</span></span>

<span data-ttu-id="b81dc-120">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="b81dc-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="b81dc-121">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="b81dc-121">This inspection test has several variables.</span></span> <span data-ttu-id="b81dc-122">Uma variável é sabor, e os possíveis resultados para ela são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="b81dc-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="b81dc-123">Uma segunda variável é cor, e os possíveis resultados são: muito escura, muito clara e correta.</span><span class="sxs-lookup"><span data-stu-id="b81dc-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="b81dc-124">Criar uma variável de teste</span><span class="sxs-lookup"><span data-stu-id="b81dc-124">Create a test variable</span></span>

<span data-ttu-id="b81dc-125">Siga estas etapas para criar uma variável de teste.</span><span class="sxs-lookup"><span data-stu-id="b81dc-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="b81dc-126">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Variáveis de teste**.</span><span class="sxs-lookup"><span data-stu-id="b81dc-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="b81dc-127">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b81dc-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b81dc-128">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="b81dc-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b81dc-129">**Variável** – Insira um nome ou uma ID exclusiva para a variável.</span><span class="sxs-lookup"><span data-stu-id="b81dc-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="b81dc-130">**Descrição** – Insira uma descrição detalhada da variável.</span><span class="sxs-lookup"><span data-stu-id="b81dc-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="b81dc-131">Enquanto a nova linha ainda estiver selecionada, selecione **Resultados** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="b81dc-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="b81dc-132">Na página **Resultados da variável de teste**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b81dc-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b81dc-133">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="b81dc-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b81dc-134">**Resultado** – Insira um nome ou uma ID exclusiva para o resultado.</span><span class="sxs-lookup"><span data-stu-id="b81dc-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="b81dc-135">**Descrição** – Insira uma descrição detalhada do resultado.</span><span class="sxs-lookup"><span data-stu-id="b81dc-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="b81dc-136">**Status de resultado** – Selecione *Aprovado* ou *Reprovado* para indicar se o teste é aprovado ou reprovado quando o resultado é selecionado como resultado do teste.</span><span class="sxs-lookup"><span data-stu-id="b81dc-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="b81dc-137">Repita a etapa anterior para cada resultado adicional.</span><span class="sxs-lookup"><span data-stu-id="b81dc-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="b81dc-138">Verifique se, pelo menos, um resultado tem o status de resultado *Aprovado* e se, pelo menos, um resultado tem o status *Reprovado*.</span><span class="sxs-lookup"><span data-stu-id="b81dc-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="b81dc-139">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="b81dc-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b81dc-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b81dc-140">Additional resources</span></span>

- [<span data-ttu-id="b81dc-141">Instrumentos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="b81dc-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="b81dc-142">Testes de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="b81dc-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="b81dc-143">Grupos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="b81dc-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
