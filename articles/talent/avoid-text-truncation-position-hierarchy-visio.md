---
title: Evite texto truncado na hierarquia de posição e exporte para Visio
description: Este tópico explica como resolver um problema em que os nomes de pessoas e cargos estão truncados quando os clientes exibem a hierarquia de cargos no Microsoft Dynamics 365 for Talent. Texto truncado pode tornar difícil realizar um screenshot ou imprimir a hierarquia.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b688a396e3b384aedb06c470b1634150ae7aa038
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303230"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="01214-104">Evite texto truncado na hierarquia de posição e exporte para Visio</span><span class="sxs-lookup"><span data-stu-id="01214-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01214-105">**Saída**</span><span class="sxs-lookup"><span data-stu-id="01214-105">**Issue**</span></span>

<span data-ttu-id="01214-106">Quando um cliente exibe a hierarquia de cargos no Microsoft Dynamics 365 for Talent, os nomes de pessoas e cargos estão truncados.</span><span class="sxs-lookup"><span data-stu-id="01214-106">When a customer views the position hierarchy in Microsoft Dynamics 365 for Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="01214-107">Portanto, pode ser difícil realizar uma captura de tela, ou imprimir e distribuir a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="01214-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Hierarquia de posições](media/position-h.png)

<span data-ttu-id="01214-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="01214-109">**Cause**</span></span>

<span data-ttu-id="01214-110">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="01214-110">This behavior is by design.</span></span>

<span data-ttu-id="01214-111">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="01214-111">**Resolution**</span></span>

<span data-ttu-id="01214-112">Infelizmente, os usuários não podem alterar facilmente o tamanho do texto.</span><span class="sxs-lookup"><span data-stu-id="01214-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="01214-113">Entretanto, você pode exportar uma hierarquia de posição de fora do Talent e depois importá-lo no Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="01214-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="01214-114">Embora o artigo a seguir tenha sido escrito para o Microsoft Dynamics AX 2012, o processo ainda se aplica ao Talent: [Exportar uma hierarquia de cargos para o Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="01214-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="01214-115">Rastrear essas etapas para exportar para Visio.</span><span class="sxs-lookup"><span data-stu-id="01214-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="01214-116">No Talent, abra a página de lista **Posições**.</span><span class="sxs-lookup"><span data-stu-id="01214-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="01214-117">Para incluir mais informações no diagrama de estrutura organizacional, adicione os campos à lista **Posições**, de forma que esteja disponível quando você usar o assistente posteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="01214-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="01214-118">No Painel de Ação, selecione o botão **Abrir no Microsoft Office** e, em **Exportar para o Excel**, selecione **Cargos**.</span><span class="sxs-lookup"><span data-stu-id="01214-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="01214-119">Alternativamente, pressione Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="01214-119">Alternatively, press Ctrl+T.</span></span>

    ![Exporte a página de lista de Posições para Excel](media/org-admin.png)

3. <span data-ttu-id="01214-121">Salve o arquivo Excel que é exportado.</span><span class="sxs-lookup"><span data-stu-id="01214-121">Save the Excel file that is exported.</span></span>

    ![Exportar para a caixa de diálogo do Excel](media/export-excel.png)

4. <span data-ttu-id="01214-123">Em Visio, selecione **Visio - Criar novo**, e selecione a categoria de modelo **Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="01214-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Diagrama novo](media/new.png)

5. <span data-ttu-id="01214-125">Selecione **Assistente de gráfico organizacional**, e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="01214-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Caixa de diálogo do assistente do diagrama organizacional](media/orgchart-wizard.png)

6. <span data-ttu-id="01214-127">Selecione **Informações que já estão armazenadas em um arquivo ou banco de dados**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="01214-129">Escolha **A text, Org Plus (\*.txt), ou arquivo Excel**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="01214-131">Navegue para selecionar o arquivo Excel exportado que contém a hierarquia de posição, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="01214-133">Defina o campo **Nome** como **Posição**, defina o campo **Relatar a** como **Relatar a posição**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="01214-135">Selecione os campos que precisam ser mostrados em cada nó, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="01214-137">Adicione a coluna **Posição** para a lista **Campos de dados de forma**, e depois selecione, **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="01214-139">As imagens não estão disponíveis atualmente.</span><span class="sxs-lookup"><span data-stu-id="01214-139">Pictures aren't currently available.</span></span> <span data-ttu-id="01214-140">Portanto, na página seguinte, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01214-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="01214-141">Selecione **Desejo que o assistente interrompa automaticamente meu gráfico de organização entre páginas**.</span><span class="sxs-lookup"><span data-stu-id="01214-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Assistente de cronograma organizacional 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="01214-143">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="01214-143">Select **Finish**.</span></span>

    <span data-ttu-id="01214-144">Se houver qualquer posição que não seja a estrutura, você será solicitado a incluí-la no diagrama.</span><span class="sxs-lookup"><span data-stu-id="01214-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="01214-145">O diagrama gerado em Visio mostra cada gerente em uma planilha separada.</span><span class="sxs-lookup"><span data-stu-id="01214-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="01214-146">Com base nos campos que você selecionou para incluir no diagrama, cada nó mostra as informações apropriadas quando o arquivo Visio é gerado.</span><span class="sxs-lookup"><span data-stu-id="01214-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagrama de hierarquia](media/hierarchy.png)

<span data-ttu-id="01214-148">**Opção adicional**</span><span class="sxs-lookup"><span data-stu-id="01214-148">**Additional option**</span></span>

<span data-ttu-id="01214-149">Em Talent, você também pode usar o espaço de trabalho **Pessoas** para exibir algumas informações relacionadas de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="01214-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>