---
title: "Importar dados de modelos de entidade de dados do Excel com várias planilhas"
description: "Este tópico descreve como importar dados usando modelos de entidade de dados do Excel no Microsoft Dynamics 365 for Finance and Operations."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cfaf17a8279026bf9bc8b581afd07e4fdbd3f03a
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="excel-templates-with-multiple-worksheets"></a><span data-ttu-id="95ea7-103">Modelos do Excel com várias planilhas</span><span class="sxs-lookup"><span data-stu-id="95ea7-103">Excel templates with multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95ea7-104">O gerenciamento de dados no Microsoft Dynamics 365 for Finance and Operations oferece suporte a modelos baseados no Microsoft Excel para entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="95ea7-104">Data management in Microsoft Dynamics 365 for Finance and Operations supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="95ea7-105">Esses modelos podem conter uma ou mais planilhas.</span><span class="sxs-lookup"><span data-stu-id="95ea7-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="95ea7-106">Os modelos com várias planilhas frequentemente são usados quando é conveniente gerenciar dados em um único arquivo e os importar para várias entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="95ea7-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="95ea7-107">Um exemplo seria locais e depósitos.</span><span class="sxs-lookup"><span data-stu-id="95ea7-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="95ea7-108">Carregar um arquivo e depois mapeá-lo para todas as entidades</span><span class="sxs-lookup"><span data-stu-id="95ea7-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="95ea7-109">Vamos ver um exemplo no qual há um arquivo do Excel com planilhas chamadas **Locais** e **Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="95ea7-109">Let’s take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="95ea7-110">Para configurar o projeto de importação de dados, você adicionaria a primeira entidade de dados, **Locais** e depois carregaria o arquivo.</span><span class="sxs-lookup"><span data-stu-id="95ea7-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="95ea7-111">Você pode selecionar **Locais** como a planilha a ser usada para esta entidade.</span><span class="sxs-lookup"><span data-stu-id="95ea7-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="95ea7-112">Se adicionar a segunda entidade **Depósitos** sem deixar o formulário **Adicionar arquivo**, a pesquisa de planilha permitirá que você selecione a planilha **Depósitos** sem ter que carregar novamente o arquivo.</span><span class="sxs-lookup"><span data-stu-id="95ea7-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="95ea7-113">O único motivo para carregar um novo arquivo seria se os dados dos **Depósitos** estivessem em um arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="95ea7-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Várias planilhas](./media/AddFileMultipleWorkSheets.png) 

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="95ea7-115">Planilha de correção para o mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="95ea7-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="95ea7-116">O mapeamento da planilha para uma entidade de dados no job de importação pode ser corrigido na grade.</span><span class="sxs-lookup"><span data-stu-id="95ea7-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="95ea7-117">A coluna **Planilha** na grade mostra as planilhas do arquivo que foi mapeado.</span><span class="sxs-lookup"><span data-stu-id="95ea7-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="95ea7-118">Você pode escolher uma planilha diferente do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="95ea7-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="95ea7-119">Se a planilha escolhida já estiver mapeada para uma entidade no projeto de dados, o sistema solicitará que você confirme a alteração.</span><span class="sxs-lookup"><span data-stu-id="95ea7-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="95ea7-120">Recomendamos que você corrija os mapeamentos na grade.</span><span class="sxs-lookup"><span data-stu-id="95ea7-120">We recommend that you fix all mappings in the grid.</span></span>

![Atualizar mapeamento da planilha](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="95ea7-122">Remapear para um novo arquivo</span><span class="sxs-lookup"><span data-stu-id="95ea7-122">Re-map to a new file</span></span>

<span data-ttu-id="95ea7-123">Nos casos em que uma nova versão do mesmo arquivo ou um arquivo completamente novo tiver que ser carregado para entidades existentes em um projeto de dados, você deverá usar a experiência **Adicionar arquivo** e adicionar as entidades novamente, como se elas fossem adicionadas pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="95ea7-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="95ea7-124">O sistema confirmará que se você deseja substituir as entidades existentes no projeto de dados antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="95ea7-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="95ea7-125">As entidades que não são adicionadas novamente (ou substituídas) continuarão mantendo os mapeamentos anteriores do arquivo anterior.</span><span class="sxs-lookup"><span data-stu-id="95ea7-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="95ea7-126">Carregar um arquivo usando Executar projeto</span><span class="sxs-lookup"><span data-stu-id="95ea7-126">Upload a file using Run project</span></span>

<span data-ttu-id="95ea7-127">Você pode carregar um arquivo do Excel ao usar a opção **Executar projeto** para executar um projeto de importação.</span><span class="sxs-lookup"><span data-stu-id="95ea7-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="95ea7-128">Tenha cautela ao carregar somente arquivos que têm as mesmas planilhas que os mapeamentos existentes nas entidades de dados no projeto de dados.</span><span class="sxs-lookup"><span data-stu-id="95ea7-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="95ea7-129">Se a planilha não for encontrada no arquivo recém-carregado, o sistema exibirá um erro e interromperá a importação.</span><span class="sxs-lookup"><span data-stu-id="95ea7-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="95ea7-130">Se o mapeamento para a planilha tiver que ser alterado para uma entidade, então os mapeamentos no projeto de dados devem ser atualizados primeiro dentro do projeto de dados, antes de usar o arquivo na experiência **Executar projeto**.</span><span class="sxs-lookup"><span data-stu-id="95ea7-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>


