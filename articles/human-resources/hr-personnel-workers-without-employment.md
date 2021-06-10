---
title: Trabalhadores sem emprego
description: Os trabalhadores sem emprego futuro, ativo ou histórico com a sua organização aparecem no formulário Trabalhadores sem emprego.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6fbada6feb55b8627b1aa1ddfe367177edb7a0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051704"
---
# <a name="workers-without-employment"></a><span data-ttu-id="3253a-103">Trabalhadores sem emprego</span><span class="sxs-lookup"><span data-stu-id="3253a-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3253a-104">Os trabalhadores sem emprego futuro, ativo ou histórico com a sua organização aparecem no formulário **Trabalhadores sem emprego**.</span><span class="sxs-lookup"><span data-stu-id="3253a-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="3253a-105">Os trabalhadores com esse status podem aparecer quando você importa trabalhadores sem um registro de emprego ou quando exclui um emprego de trabalhador por meio de **Trabalhadores > Histórico de emprego**.</span><span class="sxs-lookup"><span data-stu-id="3253a-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="3253a-106">Por padrão, o formulário **Trabalhadores sem emprego** está disponível para as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="3253a-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="3253a-107">Assistente de Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="3253a-107">Human Resources Assistant</span></span>
- <span data-ttu-id="3253a-108">Gerente de Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="3253a-108">Human Resources Manager</span></span>
- <span data-ttu-id="3253a-109">Recrutador</span><span class="sxs-lookup"><span data-stu-id="3253a-109">Recruiter</span></span>
- <span data-ttu-id="3253a-110">Gerente de remuneração e benefícios</span><span class="sxs-lookup"><span data-stu-id="3253a-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="3253a-111">Administrador de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="3253a-111">Payroll Administrator</span></span>
- <span data-ttu-id="3253a-112">Gerente de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="3253a-112">Payroll Manager</span></span>
- <span data-ttu-id="3253a-113">Gerente de treinamento</span><span class="sxs-lookup"><span data-stu-id="3253a-113">Training Manager</span></span>

<span data-ttu-id="3253a-114">Na lista **Trabalhadores sem emprego**, você pode excluir as pessoas listadas.</span><span class="sxs-lookup"><span data-stu-id="3253a-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="3253a-115">Por padrão, esse privilégio é dado à função assistente de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="3253a-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="3253a-116">Você pode conceder esse privilégio a outras funções com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3253a-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="3253a-117">Selecione **Administração do sistema** e, depois, **Configuração de segurança**.</span><span class="sxs-lookup"><span data-stu-id="3253a-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="3253a-118">Na guia **Privilégios**, filtre a lista **Privilégios** para **Manter trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="3253a-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="3253a-119">[![Lista Filtrar Privilégios](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="3253a-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="3253a-120">Na coluna **Referências**, selecione **Exibir itens do menu**.</span><span class="sxs-lookup"><span data-stu-id="3253a-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="3253a-121">Em **Exibir itens do menu**, selecione **HcmWorkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="3253a-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="3253a-122">[![Selecionar formulário](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="3253a-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="3253a-123">Defina a permissão **Excluir** para **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="3253a-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="3253a-124">Selecione a guia **Objetos não publicados**.</span><span class="sxs-lookup"><span data-stu-id="3253a-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="3253a-125">Selecione **Publicar tudo**.</span><span class="sxs-lookup"><span data-stu-id="3253a-125">Select **Publish all**.</span></span>

   <span data-ttu-id="3253a-126">[![Publicar alterações](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="3253a-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]