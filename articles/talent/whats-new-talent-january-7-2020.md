---
title: Novidades ou alterações no Dynamics 365 Talent (7 de janeiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 615ed3e4260192ba36826e128f1afa1588e94845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2020
ms.locfileid: "2974421"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="454b0-103">Novidades ou alterações no Dynamics 365 Talent (7 de janeiro de 2020)</span><span class="sxs-lookup"><span data-stu-id="454b0-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="454b0-104">Este artigo descreve os recursos novos ou alterados no Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="454b0-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="454b0-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="454b0-105">Changes in Attract</span></span>

<span data-ttu-id="454b0-106">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="454b0-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="454b0-107">Alterações de Integração</span><span class="sxs-lookup"><span data-stu-id="454b0-107">Changes in Onboard</span></span>

<span data-ttu-id="454b0-108">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="454b0-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="454b0-109">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="454b0-109">Changes in Core HR</span></span>

<span data-ttu-id="454b0-110">As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="454b0-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="454b0-111">Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="454b0-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="454b0-112">Não é possível excluir trabalhadores que não têm registros de emprego - (386157)</span><span class="sxs-lookup"><span data-stu-id="454b0-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="454b0-113">Esta alteração adiciona uma opção de exclusão no formulário **Trabalhadores sem emprego**.</span><span class="sxs-lookup"><span data-stu-id="454b0-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="454b0-114">Os trabalhadores aparecerão neste formulário quando não houver empregos futuros, ativos ou históricos para o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="454b0-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="454b0-115">Nesta versão, a exclusão só é habilitada para Administradores do sistema.</span><span class="sxs-lookup"><span data-stu-id="454b0-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="454b0-116">No entanto, no lançamento da próxima semana, a segurança será atualizada para permitir que todos os usuários com a função de Assistente de RH possam remover funcionários sem emprego.</span><span class="sxs-lookup"><span data-stu-id="454b0-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="454b0-117">Também é possível fazer essas alterações manualmente seguindo as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="454b0-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="454b0-118">Vá para **Configuração de segurança**.</span><span class="sxs-lookup"><span data-stu-id="454b0-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="454b0-119">Na guia **Privilégios**, filtre a lista **Privilégios** para **Manter trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="454b0-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="454b0-120">Na coluna **Referências**, selecione **Exibir itens do menu**.</span><span class="sxs-lookup"><span data-stu-id="454b0-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="454b0-121">Em **Exibir itens do menu**, selecione **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="454b0-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="454b0-122">Defina a permissão **Excluir** para Conceder.</span><span class="sxs-lookup"><span data-stu-id="454b0-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="454b0-123">Selecione a guia **Objetos não publicados**.</span><span class="sxs-lookup"><span data-stu-id="454b0-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="454b0-124">Selecione **Publicar tudo**.</span><span class="sxs-lookup"><span data-stu-id="454b0-124">Select **Publish all**.</span></span>
