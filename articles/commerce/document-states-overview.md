---
title: Estados de documento e de ciclo de vida
description: Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4a00f1c363e5ecb0e3e64637a8f487c48df2df72
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261504"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="ff8f9-103">Estados de documento e de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="ff8f9-103">Document states and lifecycle</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ff8f9-104">Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="ff8f9-105">Descrições de estado do documento</span><span class="sxs-lookup"><span data-stu-id="ff8f9-105">Document state descriptions</span></span>

<span data-ttu-id="ff8f9-106">O tópico [Elementos da página](page-elements-overview.md) lista vários tipos de documentos no sistema de gerenciamento do conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="ff8f9-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="ff8f9-107">Esses tipos de documentos podem ter vários estados na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="ff8f9-108">Os estados de documento ajudam a evitar conflitos de dados e a aplicar o controle de versão.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="ff8f9-109">Eles determinam quem pode alterar os documentos, quando documentos podem ser alterados e, quando as alterações podem ser exibidas por outros contatos.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="ff8f9-110">A tabela a seguir mostra os estados possíveis de documento de elementos de página em Comércio.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="ff8f9-111">Estado do documento</span><span class="sxs-lookup"><span data-stu-id="ff8f9-111">Document state</span></span>      | <span data-ttu-id="ff8f9-112">Ação para criação de site</span><span class="sxs-lookup"><span data-stu-id="ff8f9-112">Site builder action</span></span>        | <span data-ttu-id="ff8f9-113">descrição</span><span class="sxs-lookup"><span data-stu-id="ff8f9-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ff8f9-114">Check-out efetuado</span><span class="sxs-lookup"><span data-stu-id="ff8f9-114">Checked out</span></span>         | <span data-ttu-id="ff8f9-115">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-115">Select **Edit**.</span></span>           | <span data-ttu-id="ff8f9-116">O documento aplicável foi enviado para você.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="ff8f9-117">Enquanto um documento está nesse estado, ele não pode ser alterado por outros usuários do sistema autenticados e todas as alterações feitas no documento são visíveis somente para você.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="ff8f9-118">Salvo</span><span class="sxs-lookup"><span data-stu-id="ff8f9-118">Saved</span></span>               | <span data-ttu-id="ff8f9-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-119">Select **Save**.</span></span>           | <span data-ttu-id="ff8f9-120">As alterações feitas em um documento com check-out são salvas no banco de dados, mas o documento ainda não foi verificado ou publicado.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="ff8f9-121">As alterações salvas não são visíveis para outros usuários autenticados do sistema até o autor selecionar **Terminar edição**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="ff8f9-122">Eles não estão visíveis para os usuários externos até que o item seja publicado.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="ff8f9-123">Descartar check-out</span><span class="sxs-lookup"><span data-stu-id="ff8f9-123">Discarded check out</span></span> | <span data-ttu-id="ff8f9-124">Selecione **Descartar edições**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="ff8f9-125">Todas as alterações no documento com check-out são descartadas, e o item é revertido para a última versão com check-in.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="ff8f9-126">Check-in efetuado</span><span class="sxs-lookup"><span data-stu-id="ff8f9-126">Checked in</span></span>          | <span data-ttu-id="ff8f9-127">Selecione **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-127">Select **Finish editing**.</span></span> | <span data-ttu-id="ff8f9-128">O check-in do documento editado será feito.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-128">The edited document is checked in.</span></span> <span data-ttu-id="ff8f9-129">Todas as alterações são visíveis para outros usuários do sistema autenticados, e esses usuários podem editar o documento.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="ff8f9-130">Cada check-in cria uma registro de versão do documento no histórico do item.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="ff8f9-131">Publicado</span><span class="sxs-lookup"><span data-stu-id="ff8f9-131">Published</span></span>           | <span data-ttu-id="ff8f9-132">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-132">Select **Publish**.</span></span>        | <span data-ttu-id="ff8f9-133">O documento é publicado, e as alterações são enviadas para seu local dinâmico e tornam-se detectáveis por usuários externos.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="ff8f9-134">Os itens podem ser publicados somente se tiverem sido feitos check-in primeiro, selecionando **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="ff8f9-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ff8f9-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ff8f9-135">Additional resources</span></span>

[<span data-ttu-id="ff8f9-136">Maneiras de adicionar conteúdo</span><span class="sxs-lookup"><span data-stu-id="ff8f9-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="ff8f9-137">Glossário do modelo de página</span><span class="sxs-lookup"><span data-stu-id="ff8f9-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="ff8f9-138">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="ff8f9-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="ff8f9-139">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="ff8f9-139">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="ff8f9-140">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="ff8f9-140">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="ff8f9-141">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="ff8f9-141">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="ff8f9-142">Personalizar a navegação do site</span><span class="sxs-lookup"><span data-stu-id="ff8f9-142">Customize site navigation</span></span>](customize-site-navigation.md)
