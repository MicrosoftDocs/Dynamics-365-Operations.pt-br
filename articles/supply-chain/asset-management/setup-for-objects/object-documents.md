---
title: Documentos do ativo
description: Este tópico explica documentos de ativo no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f994e519e354a766a2437f182d2ade39155749b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216542"
---
# <a name="asset-documents"></a><span data-ttu-id="e7782-103">Documentos do ativo</span><span class="sxs-lookup"><span data-stu-id="e7782-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e7782-104">Este tópico explica documentos de ativo no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="e7782-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="e7782-105">No Asset Management, você pode configurar documentos para que eles sejam automaticamente relacionados a tipos de trabalho, fabricantes de ativo, tipos de ativo ou ativos, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="e7782-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="e7782-106">Essa funcionalidade será útil quando versões atualizadas de documento forem liberadas.</span><span class="sxs-lookup"><span data-stu-id="e7782-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="e7782-107">Nesse caso, você só precisará colocar o documento atualizado no local padrão utilizado para seus documentos do Supply Chain Management e anexá-lo ao registro de documentos do ativo criado.</span><span class="sxs-lookup"><span data-stu-id="e7782-107">In that case, you just have to put the updated document in the standard location that you use for your Supply Chain Management documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="e7782-108">O documento atualizado pode ser acessado dos itens de menu **Todos os ativos**, **Ativos ativos**, **Meus ativos ativos**, **Todas as ordens de trabalho** e **Trabalhos de ordem de serviço ativos**.</span><span class="sxs-lookup"><span data-stu-id="e7782-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="e7782-109">O processo de anexação de documentos a um registro de documentos de ativo usa o sistema padrão de manuseio de documentos.</span><span class="sxs-lookup"><span data-stu-id="e7782-109">The process for attaching documents to an asset document record uses the standard document handling system.</span></span>

<span data-ttu-id="e7782-110">**Exemplo 1:** um documento relacionado a um tipo de trabalho deve descrever um procedimento desse tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e7782-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="e7782-111">**Exemplo 2:** um documento relacionado a uma combinação de um tipo de ativo, fabricante e modelo pode ser o manual padrão para o modelo de fabricante do ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="e7782-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="e7782-112">Criar relação de documento de ativo</span><span class="sxs-lookup"><span data-stu-id="e7782-112">Create asset document relation</span></span>

1. <span data-ttu-id="e7782-113">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Documentos de ativo**.</span><span class="sxs-lookup"><span data-stu-id="e7782-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="e7782-114">Selecione **Novo** para criar um registro de documento de ativo.</span><span class="sxs-lookup"><span data-stu-id="e7782-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="e7782-115">Dependendo do grau de especificidade desejado para a relação do documento, faça seleções relevantes em um ou mais dos seguintes campos: **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Categoria do tipo de trabalho**, **Tipo de trabalho**, **Variação do tipo de trabalho** e **Necessidade de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e7782-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="e7782-116">As opções disponíveis nos campos **Variação do tipo de trabalho** e **Necessidade de trabalho** dependem da seleção no campo **Tipo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e7782-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7782-117">Quando o sistema pesquisar documentos que tenham de estar relacionados a um ativo ou uma ordem de serviço, o Asset Management examinará todos os registros de documento de ativo para verificar se há uma possível correspondência.</span><span class="sxs-lookup"><span data-stu-id="e7782-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="e7782-118">Ele sempre verifica a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7782-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="e7782-119">Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Necessidade de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e7782-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="e7782-120">Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e7782-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="e7782-121">Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Tipo de trabalho** e assim em diante.</span><span class="sxs-lookup"><span data-stu-id="e7782-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="e7782-122">Como você pode perceber no layout da página **Documentos de ativo**, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="e7782-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="e7782-123">Vários documentos podem estar relacionados a um ativo ou uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e7782-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="e7782-124">Você pode editar o nível de serviço em uma solicitação de manutenção ou ordem de serviço como necessário.</span><span class="sxs-lookup"><span data-stu-id="e7782-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="e7782-125">Selecione **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="e7782-125">Select **Attachments**.</span></span> <span data-ttu-id="e7782-126">A página **Manuseio de documentos** padrão será exibida.</span><span class="sxs-lookup"><span data-stu-id="e7782-126">The standard **Document handling** page appears.</span></span>
5. <span data-ttu-id="e7782-127">Configure os documentos ou as anotações que devem ser anexados ao registro do documento de ativo.</span><span class="sxs-lookup"><span data-stu-id="e7782-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="e7782-128">Depois que você anexar documentos, o campo **Anexos** mostrará o número de documentos relacionados ao registro.</span><span class="sxs-lookup"><span data-stu-id="e7782-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
