---
title: Trabalhadores responsáveis por aprovar não conformidades
description: Este tópico descreve como configurar trabalhadores que são responsáveis por aprovar não conformidades.
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
ms.openlocfilehash: 2d3f647de2c188661c2c9c5f31e2642c3f8ca0b5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021771"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="3bb36-103">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="3bb36-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bb36-104">Este tópico descreve como configurar trabalhadores que são responsáveis por aprovar não conformidades.</span><span class="sxs-lookup"><span data-stu-id="3bb36-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="3bb36-105">As não conformidades devem ser aprovadas para que os usuários possam começar a inserir detalhes, como correções ou operações.</span><span class="sxs-lookup"><span data-stu-id="3bb36-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="3bb36-106">Para que os usuários possam aprovar ou rejeitar não conformidades, sua ID de usuário (registro de usuário) deve estar vinculada a um registro de trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3bb36-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="3bb36-107">Opcionalmente, você pode configurar trabalhadores que sejam responsáveis pela qualidade e, em seguida, permitir que um trabalhador aprove o trabalho em nome de outro trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3bb36-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="3bb36-108">Habilitar um usuário para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="3bb36-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="3bb36-109">Para que um usuário possa aprovar ou rejeitar não conformidades, você deve vincular seu registro de usuário a um registro de trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3bb36-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="3bb36-110">Os campos de aprovação podem então ser automaticamente definidos, e o usuário atual pode ser preenchido de forma automática na folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="3bb36-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="3bb36-111">Para que o usuário possa usar as notas do documento, é necessário ativar o manuseio de documentos nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="3bb36-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="3bb36-112">Vá para **Administração do sistema \> Usuários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3bb36-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="3bb36-113">Localize e abra o usuário que deve ser capaz de aprovar ou rejeitar não conformidades.</span><span class="sxs-lookup"><span data-stu-id="3bb36-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="3bb36-114">Defina o campo **Pessoa** como o nome do trabalhador relacionado ao registro de usuário atual.</span><span class="sxs-lookup"><span data-stu-id="3bb36-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="3bb36-115">No Painel de Ações, selecione **Opções do usuário**.</span><span class="sxs-lookup"><span data-stu-id="3bb36-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="3bb36-116">Na página **Opções** do registro de usuário atual, na guia **Preferências**, defina a opção **Habilitar manuseio de documentos** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="3bb36-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="3bb36-117">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="3bb36-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="3bb36-118">Definir trabalhadores responsáveis pela qualidade</span><span class="sxs-lookup"><span data-stu-id="3bb36-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="3bb36-119">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Trabalhadores responsáveis pela qualidade**.</span><span class="sxs-lookup"><span data-stu-id="3bb36-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="3bb36-120">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3bb36-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="3bb36-121">No campo **Trabalhador**, selecione o trabalhador que insere os dados de qualidade.</span><span class="sxs-lookup"><span data-stu-id="3bb36-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="3bb36-122">No campo **Trabalhador responsável**, selecione o trabalhador para o qual o trabalhador selecionado insere trabalhos.</span><span class="sxs-lookup"><span data-stu-id="3bb36-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="3bb36-123">Quando as não conformidades forem criadas e atualizadas, esse trabalhador será inserido por padrão nos campos **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="3bb36-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3bb36-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3bb36-124">Additional resources</span></span>

- [<span data-ttu-id="3bb36-125">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="3bb36-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="3bb36-126">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="3bb36-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="3bb36-127">Encargos de qualidade</span><span class="sxs-lookup"><span data-stu-id="3bb36-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="3bb36-128">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="3bb36-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="3bb36-129">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="3bb36-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="3bb36-130">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="3bb36-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="3bb36-131">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="3bb36-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="3bb36-132">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="3bb36-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
