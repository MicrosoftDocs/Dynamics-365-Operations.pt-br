---
title: Estados de documento e de ciclo de vida
description: Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914878"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="b3f53-103">Estados de documento e de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="b3f53-103">Document states and lifecycle</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b3f53-104">Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3f53-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="b3f53-105">Descrições de estado do documento</span><span class="sxs-lookup"><span data-stu-id="b3f53-105">Document state descriptions</span></span>

<span data-ttu-id="b3f53-106">O tópico [Elementos da página](page-elements-overview.md) lista vários tipos de documentos no sistema de gerenciamento do conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="b3f53-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="b3f53-107">Esses tipos de documentos podem ter vários estados na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="b3f53-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="b3f53-108">Os estados de documento ajudam a evitar conflitos de dados e a aplicar o controle de versão.</span><span class="sxs-lookup"><span data-stu-id="b3f53-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="b3f53-109">Eles determinam quem pode alterar os documentos, quando documentos podem ser alterados e, quando as alterações podem ser exibidas por outros contatos.</span><span class="sxs-lookup"><span data-stu-id="b3f53-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="b3f53-110">A tabela a seguir mostra os estados possíveis de documento de elementos de página em Comércio.</span><span class="sxs-lookup"><span data-stu-id="b3f53-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="b3f53-111">Estado do documento</span><span class="sxs-lookup"><span data-stu-id="b3f53-111">Document state</span></span> | <span data-ttu-id="b3f53-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3f53-112">Description</span></span> |
|---|---|
| <span data-ttu-id="b3f53-113">Com Check-out</span><span class="sxs-lookup"><span data-stu-id="b3f53-113">Checked out</span></span> | <span data-ttu-id="b3f53-114">Quando um item de CMS está com check-out para você, ele não pode ser editado por outros usuários autenticados do sistema.</span><span class="sxs-lookup"><span data-stu-id="b3f53-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="b3f53-115">Quaisquer alterações feitas ao item são visíveis apenas por você.</span><span class="sxs-lookup"><span data-stu-id="b3f53-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="b3f53-116">Com Check-in</span><span class="sxs-lookup"><span data-stu-id="b3f53-116">Checked in</span></span> | <span data-ttu-id="b3f53-117">Quando um item de CMS realiza check-in, as alterações são visíveis para outros usuários autenticados do sistema e esses usuários poderão efetuar check-out do item e editá-lo.</span><span class="sxs-lookup"><span data-stu-id="b3f53-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="b3f53-118">Cada check-in cria uma registro de versão do documento no histórico do item.</span><span class="sxs-lookup"><span data-stu-id="b3f53-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="b3f53-119">Publicado</span><span class="sxs-lookup"><span data-stu-id="b3f53-119">Published</span></span> | <span data-ttu-id="b3f53-120">Quando um item de CMS é publicado, ele é enviado em seu site e torna-se perceptível na Internet por usuários externos não autenticados.</span><span class="sxs-lookup"><span data-stu-id="b3f53-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="b3f53-121">Os itens podem ser publicados somente se o check-in tiver sido efetuado.</span><span class="sxs-lookup"><span data-stu-id="b3f53-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="b3f53-122">Salvo</span><span class="sxs-lookup"><span data-stu-id="b3f53-122">Saved</span></span> | <span data-ttu-id="b3f53-123">Mudanças que foram realizadas a um item de CMS com check-out podem ser salvos ao CMS antes do item ser verificado ou publicado.</span><span class="sxs-lookup"><span data-stu-id="b3f53-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="b3f53-124">Essas alterações salvas não são visíveis para outros usuários autenticados do sistema até o item ter o check-in realizado.</span><span class="sxs-lookup"><span data-stu-id="b3f53-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="b3f53-125">Eles não estão visíveis para os usuários externos até que o item seja publicado.</span><span class="sxs-lookup"><span data-stu-id="b3f53-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="b3f53-126">Descartar check-out</span><span class="sxs-lookup"><span data-stu-id="b3f53-126">Discarded check out</span></span> | <span data-ttu-id="b3f53-127">Quando um item feito o check-out de CMS for rejeitado, alterações salvas serão excluídas e o item volta para versão na qual o check-in foi realizado recentemente.</span><span class="sxs-lookup"><span data-stu-id="b3f53-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="b3f53-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b3f53-128">Additional resources</span></span>

[<span data-ttu-id="b3f53-129">Maneiras de adicionar conteúdo</span><span class="sxs-lookup"><span data-stu-id="b3f53-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="b3f53-130">Glossário do modelo de página</span><span class="sxs-lookup"><span data-stu-id="b3f53-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="b3f53-131">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="b3f53-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="b3f53-132">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="b3f53-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="b3f53-133">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="b3f53-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="b3f53-134">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="b3f53-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="b3f53-135">Personalizar a navegação do site</span><span class="sxs-lookup"><span data-stu-id="b3f53-135">Customize site navigation</span></span>](customize-site-navigation.md)