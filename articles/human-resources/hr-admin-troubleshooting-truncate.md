---
title: Evitar o truncamento de texto na hierarquia de posições e exportar para o Visio
description: Este artigo explica como resolver um problema em que os nomes de pessoas e cargos estão truncados quando os clientes exibem a hierarquia de cargos no Microsoft Dynamics 365 Human Resources. Texto truncado pode tornar difícil realizar um screenshot ou imprimir a hierarquia.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0dc91d3165f14c165f75756dc63a3dc8f63149aa
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111474"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="a0e56-104">Evite texto truncado na hierarquia de posição e exporte para Visio</span><span class="sxs-lookup"><span data-stu-id="a0e56-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

<span data-ttu-id="a0e56-105">**Saída**</span><span class="sxs-lookup"><span data-stu-id="a0e56-105">**Issue**</span></span>

<span data-ttu-id="a0e56-106">Quando um cliente exibe a hierarquia de cargos no Microsoft Dynamics 365 Human Resources, os nomes de pessoas e cargos estão truncados.</span><span class="sxs-lookup"><span data-stu-id="a0e56-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Human Resources, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="a0e56-107">Portanto, pode ser difícil realizar uma captura de tela, ou imprimir e distribuir a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="a0e56-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Hierarquia de posições](media/position-h.png)

<span data-ttu-id="a0e56-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a0e56-109">**Cause**</span></span>

<span data-ttu-id="a0e56-110">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="a0e56-110">This behavior is by design.</span></span>

<span data-ttu-id="a0e56-111">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="a0e56-111">**Resolution**</span></span>

<span data-ttu-id="a0e56-112">Infelizmente, os usuários não podem alterar facilmente o tamanho do texto.</span><span class="sxs-lookup"><span data-stu-id="a0e56-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="a0e56-113">Entretanto, você pode exportar uma hierarquia de posição do Human Resources e depois importá-la para o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="a0e56-113">However, you can export the position hierarchy out of Human Resources and then import it into Microsoft Visio.</span></span> <span data-ttu-id="a0e56-114">Embora o seguinte artigo tenha sido escrito para o Microsoft Dynamics AX 2012, o processo ainda se aplica ao Human Resources: [Exportar uma hierarquia de cargos para o Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="a0e56-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Human Resources: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="a0e56-115">Rastrear essas etapas para exportar para Visio.</span><span class="sxs-lookup"><span data-stu-id="a0e56-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="a0e56-116">No Human Resources, abra a página de lista **Posições**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-116">In Human Resources, open the **Positions** list page.</span></span>

    <span data-ttu-id="a0e56-117">Para incluir mais informações no diagrama de estrutura organizacional, adicione os campos à lista **Posições**, de forma que esteja disponível quando você usar o assistente posteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a0e56-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="a0e56-118">No Painel de Ação, selecione o botão **Abrir no Microsoft Office** e, em **Exportar para o Excel**, selecione **Cargos**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="a0e56-119">Alternativamente, pressione Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="a0e56-119">Alternatively, press Ctrl+T.</span></span>

    ![Exporte a página de lista de Posições para Excel](media/org-admin.png)

3. <span data-ttu-id="a0e56-121">Salve o arquivo Excel que é exportado.</span><span class="sxs-lookup"><span data-stu-id="a0e56-121">Save the Excel file that is exported.</span></span>

    ![Exportar para a caixa de diálogo do Excel](media/export-excel.png)

4. <span data-ttu-id="a0e56-123">Em Visio, selecione **Visio - Criar novo**, e selecione a categoria de modelo **Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Diagrama novo](media/new.png)

5. <span data-ttu-id="a0e56-125">Selecione **Assistente de gráfico organizacional**, e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Caixa de diálogo do assistente do diagrama organizacional](media/orgchart-wizard.png)

6. <span data-ttu-id="a0e56-127">Selecione **Informações que já estão armazenadas em um arquivo ou banco de dados**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="a0e56-129">Escolha **A text, Org Plus (\*.txt), ou arquivo Excel**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="a0e56-131">Navegue para selecionar o arquivo Excel exportado que contém a hierarquia de posição, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="a0e56-133">Defina o campo **Nome** como **Posição**, defina o campo **Relatar a** como **Relatar a posição**, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="a0e56-135">Selecione os campos que precisam ser mostrados em cada nó, e depois selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="a0e56-137">Adicione a coluna **Posição** para a lista **Campos de dados de forma**, e depois selecione, **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Assistente de cronograma organizacional 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="a0e56-139">As imagens não estão disponíveis atualmente.</span><span class="sxs-lookup"><span data-stu-id="a0e56-139">Pictures aren't currently available.</span></span> <span data-ttu-id="a0e56-140">Portanto, na página seguinte, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="a0e56-141">Selecione **Desejo que o assistente interrompa automaticamente meu gráfico de organização entre páginas**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Assistente de cronograma organizacional 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="a0e56-143">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a0e56-143">Select **Finish**.</span></span>

    <span data-ttu-id="a0e56-144">Se houver qualquer posição que não seja a estrutura, você será solicitado a incluí-la no diagrama.</span><span class="sxs-lookup"><span data-stu-id="a0e56-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="a0e56-145">O diagrama gerado em Visio mostra cada gerente em uma planilha separada.</span><span class="sxs-lookup"><span data-stu-id="a0e56-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="a0e56-146">Com base nos campos que você selecionou para incluir no diagrama, cada nó mostra as informações apropriadas quando o arquivo Visio é gerado.</span><span class="sxs-lookup"><span data-stu-id="a0e56-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagrama de hierarquia](media/hierarchy.png)

<span data-ttu-id="a0e56-148">**Opção adicional**</span><span class="sxs-lookup"><span data-stu-id="a0e56-148">**Additional option**</span></span>

<span data-ttu-id="a0e56-149">No Human Resources, você também pode usar o espaço de trabalho **Pessoas** para exibir algumas informações relativas à hierarquia.</span><span class="sxs-lookup"><span data-stu-id="a0e56-149">In Human Resources, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
