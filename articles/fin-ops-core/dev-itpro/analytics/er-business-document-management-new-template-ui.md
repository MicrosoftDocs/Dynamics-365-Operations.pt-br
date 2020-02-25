---
title: Nova interface de usuário de documento no Gerenciamento de documentos comerciais
description: Este tópico fornece informações sobre como usar a nova interface de usuário de documento no recurso Gerenciamento de documentos comerciais da estrutura do ER (Relatório eletrônico).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4acde9703c721ab7c20d1603299a10dda91b23c4
ms.sourcegitcommit: b8f8ccab2cd9d848e5ecd71caaf0a63237e2236b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2020
ms.locfileid: "2957054"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="855fb-103">Nova interface de usuário de documento no Gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="855fb-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="855fb-104">O Gerenciamento de documentos comerciais permite que os usuários empresariais editem modelos de documento comercial usando um serviço do Microsoft Office 365 ou o aplicativo da área de trabalho apropriado do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="855fb-104">Business document management lets business users edit business document templates by using a Microsoft Office 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="855fb-105">As edições podem incluir alterações de design ou novas implantações, ou os usuários podem adicionar espaços reservados para incluir dados adicionais sem precisar alterar o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="855fb-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="855fb-106">Para obter mais informações sobre como trabalhar com o Gerenciamento de documentos comerciais, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="855fb-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="855fb-107">A nova interface de usuário de documento está menos poluída e mais confortável de usar.</span><span class="sxs-lookup"><span data-stu-id="855fb-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="855fb-108">A área **Documento comercial** mostra apenas os modelos disponíveis para o provedor atual.</span><span class="sxs-lookup"><span data-stu-id="855fb-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="855fb-109">O botão **Novo documento** permite que os usuários criem e editem um modelo em uma configuração de formato do ER (Relatório eletrônico) que é fornecido por outro provedor.</span><span class="sxs-lookup"><span data-stu-id="855fb-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="855fb-110">No exemplo deste tópico, o provedor é a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="855fb-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="855fb-111">Disponibilizar a nova interface de usuário de documento no Gerenciamento de documentos comerciais</span><span class="sxs-lookup"><span data-stu-id="855fb-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="855fb-112">Para começar a usar a nova interface de usuário de documento no Gerenciamento de documentos comerciais, você deve executar o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais** no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="855fb-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="855fb-113">Siga estas etapas a fim de ativar esse recurso para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="855fb-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="855fb-114">No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione na lista o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="855fb-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="855fb-115">Selecione **Habilitar agora** para ativar o recurso selecionado.</span><span class="sxs-lookup"><span data-stu-id="855fb-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="855fb-116">Atualize a página para acessar o novo recurso.</span><span class="sxs-lookup"><span data-stu-id="855fb-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="855fb-117">Editar modelos que são de propriedade de outros provedores</span><span class="sxs-lookup"><span data-stu-id="855fb-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="855fb-118">No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.</span><span class="sxs-lookup"><span data-stu-id="855fb-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="855fb-120">Na caixa de diálogo, selecione o documento a ser usado como um modelo e selecione **Criar documento**.</span><span class="sxs-lookup"><span data-stu-id="855fb-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Caixa de diálogo Documentos comerciais](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="855fb-122">Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="855fb-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="855fb-123">O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="855fb-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="855fb-124">A versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="855fb-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="855fb-125">O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.</span><span class="sxs-lookup"><span data-stu-id="855fb-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="855fb-126">No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.</span><span class="sxs-lookup"><span data-stu-id="855fb-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="855fb-127">No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.</span><span class="sxs-lookup"><span data-stu-id="855fb-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="855fb-128">Selecione **OK** para confirmar o início do processo de edição.</span><span class="sxs-lookup"><span data-stu-id="855fb-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Caixa de diálogo Criação de documento](./media/BDM_overview_new_template3.png)

<span data-ttu-id="855fb-130">O botão **Novo documento** é usado para criar e editar um modelo em uma configuração de formato do ER que é fornecido por outro provedor.</span><span class="sxs-lookup"><span data-stu-id="855fb-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="855fb-131">Neste exemplo, o provedor é a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="855fb-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="855fb-132">Ao selecionar **Novo documento**, você pode ver todos os modelos que pertencem ao provedor atual e a outros.</span><span class="sxs-lookup"><span data-stu-id="855fb-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="855fb-133">Depois que você seleciona o modelo, ele é aberto para edição.</span><span class="sxs-lookup"><span data-stu-id="855fb-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="855fb-134">O modelo editado será armazenado em uma nova configuração de formato de ER que é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="855fb-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="855fb-135">Para obter mais informações, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="855fb-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>
