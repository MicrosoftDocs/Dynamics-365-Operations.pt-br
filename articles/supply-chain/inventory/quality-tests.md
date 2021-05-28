---
title: Testes de gerenciamento de qualidade
description: Este tópico descreve como criar testes que possam ser usados para ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 95f759d051a520b577cb1cf3d595ce64e0dc4668
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021675"
---
# <a name="quality-management-tests"></a><span data-ttu-id="157fc-103">Testes de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="157fc-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="157fc-104">Este tópico descreve como criar testes que possam ser usados para ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="157fc-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="157fc-105">Use a página **Testes** para definir e exibir os testes individuais que determinam se os seus produtos atendem às especificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="157fc-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="157fc-106">Você pode atribuir um ou mais testes individuais a um grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="157fc-107">Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="157fc-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="157fc-108">Os valores de medição são usados para testes quantitativos.</span><span class="sxs-lookup"><span data-stu-id="157fc-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="157fc-109">Para testes qualitativos, são usadas variáveis de teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="157fc-110">Para testes quantitativos, o campo **Tipo** é definido como *Inteiro* ou *Fração*.</span><span class="sxs-lookup"><span data-stu-id="157fc-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="157fc-111">Uma unidade de medida também é especificada.</span><span class="sxs-lookup"><span data-stu-id="157fc-111">A unit of measure is also specified.</span></span> <span data-ttu-id="157fc-112">As especificações de qualidade e os resultados de teste são expressos em números.</span><span class="sxs-lookup"><span data-stu-id="157fc-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="157fc-113">Para testes qualitativos, o campo **Tipo** é definido como *Opção*.</span><span class="sxs-lookup"><span data-stu-id="157fc-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="157fc-114">Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas.</span><span class="sxs-lookup"><span data-stu-id="157fc-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="157fc-115">As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.</span><span class="sxs-lookup"><span data-stu-id="157fc-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="157fc-116">Opcionalmente, você pode atribuir um instrumento de teste a um teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="157fc-117">No entanto, os instrumentos de teste não são necessários para criar e usar testes com ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="157fc-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="157fc-118">Para obter mais informações, consulte [Instrumentos de teste de gerenciamento de qualidade](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="157fc-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="157fc-119">Você também pode especificar uma unidade para um teste, a fim de indicar a unidade de medida na qual os resultados do teste são registrados.</span><span class="sxs-lookup"><span data-stu-id="157fc-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="157fc-120">Por exemplo, um teste de temperatura pode incluir uma unidade de graus Fahrenheit ou graus Celsius.</span><span class="sxs-lookup"><span data-stu-id="157fc-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="157fc-121">Exemplo de um teste</span><span class="sxs-lookup"><span data-stu-id="157fc-121">Example of a test</span></span>

<span data-ttu-id="157fc-122">Uma empresa de fabricação realiza dois testes em material adquirido: um teste quantitativo para verificar a qualidade do material e um teste qualitativo para verificar se há danos na embalagem.</span><span class="sxs-lookup"><span data-stu-id="157fc-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="157fc-123">A empresa especifica informações adicionais sobre o teste qualitativo para definir a variável de teste (por exemplo, embalagem danificada) e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="157fc-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="157fc-124">A empresa usa a página **Grupos de teste** para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="157fc-125">O grupo de teste é atribuído a uma ordem de qualidade, de modo que a empresa possa informar os resultados dos dois testes.</span><span class="sxs-lookup"><span data-stu-id="157fc-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="157fc-126">Criar um teste</span><span class="sxs-lookup"><span data-stu-id="157fc-126">Create a test</span></span>

<span data-ttu-id="157fc-127">Siga estas etapas para criar um teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="157fc-128">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Testes**.</span><span class="sxs-lookup"><span data-stu-id="157fc-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="157fc-129">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="157fc-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="157fc-130">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="157fc-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="157fc-131">**Teste** – Insira um nome ou uma ID exclusiva para o teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="157fc-132">**Descrição** – Insira uma descrição detalhada do teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="157fc-133">**Tipo** – Selecione o tipo de resultados que o teste produz.</span><span class="sxs-lookup"><span data-stu-id="157fc-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="157fc-134">Para testes quantitativos, selecione *Fração* ou *Inteiro*.</span><span class="sxs-lookup"><span data-stu-id="157fc-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="157fc-135">Para testes qualitativos, selecione *Opção*.</span><span class="sxs-lookup"><span data-stu-id="157fc-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="157fc-136">**Instrumento de teste** – Selecione um [instrumento de teste](quality-test-instruments.md) que deve ser usado para o teste.</span><span class="sxs-lookup"><span data-stu-id="157fc-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="157fc-137">**Unidade** – Se você selecionou *Fração* ou *Inteiro* no campo **Tipo** (ou seja, se o teste for um teste quantitativo), selecione a unidade de medida na qual os resultados do teste devem ser registrados.</span><span class="sxs-lookup"><span data-stu-id="157fc-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="157fc-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="157fc-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="157fc-139">Depois de salvar um teste, não será mais possível editar o campo **Tipo** na grade.</span><span class="sxs-lookup"><span data-stu-id="157fc-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="157fc-140">Se você precisar alterar o tipo de resultados de teste que serão registrados para um teste, selecione **Alterar tipo de teste de qualidade** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="157fc-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="157fc-141">Na caixa de diálogo **Alterar tipo de teste de qualidade**, defina o campo **Novo tipo** como o tipo desejado e, em seguida, selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="157fc-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="157fc-142">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="157fc-142">Additional resources</span></span>

- [<span data-ttu-id="157fc-143">Instrumentos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="157fc-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="157fc-144">Grupos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="157fc-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="157fc-145">Variáveis de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="157fc-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="157fc-146">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="157fc-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
