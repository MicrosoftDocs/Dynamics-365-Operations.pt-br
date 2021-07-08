---
title: Regulatory Configuration Service (RCS) - Excluir um ambiente do RCS
description: Este tópico explica como um administrador do sistema RCS (Regulatory Configuration Service, serviço de configuração regulatória) pode excluir um ambiente do RCS e dados relacionados.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295809"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="2ed4a-103">Regulatory Configuration Service (RCS) - Excluir um ambiente do RCS</span><span class="sxs-lookup"><span data-stu-id="2ed4a-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ed4a-104">Este tópico explica como um administrador do sistema RCS (Regulatory Configuration Service, serviço de configuração regulatória) pode excluir um ambiente do RCS e dados relacionados.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="2ed4a-105">Antes de poder concluir o procedimento neste tópico, é preciso atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="2ed4a-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2ed4a-106">Você deve ter a função de **Administrador do sistema** atribuída a você para o ambiente do RCS.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="2ed4a-107">A função **Administrador do sistema** deve ter a função **RCSDeleteEnvironmentDuty** atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="2ed4a-108">Excluir um ambiente do RCS</span><span class="sxs-lookup"><span data-stu-id="2ed4a-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="2ed4a-109">Abra o RCS e selecione o bloco de espaço de trabalho **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="2ed4a-110">Na seção **Links relacionados**, selecione **Excluir ambiente do RCS**.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Excluir ambiente do RCS na seção Links relacionados](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="2ed4a-112">Na caixa de diálogo que aparece, revise as mensagens sobre o escopo da exclusão do ambiente.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Mensagens na caixa de diálogo Excluir ambiente do RCS](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="2ed4a-114">A exclusão de um ambiente do RCS não pode ser revertida.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="2ed4a-115">A operação exclui o ambiente do RCS selecionado e quaisquer dados relacionados, incluindo recursos e configurações armazenadas no repositório global.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="2ed4a-116">Os recursos e configurações que são compartilhados com outras organizações não serão compartilhados e excluídos se não tiverem dependências.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="2ed4a-117">Os recursos e configurações que possuírem dependências serão marcados como descontinuados.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="2ed4a-118">No campo fornecido, insira o identificador global exclusivo (GUID) do ambiente do RCS para confirmar se deseja excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="2ed4a-119">O GUID do ambiente está incluído na mensagem de exclusão.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="2ed4a-120">Selecione **Excluir ambiente**.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="2ed4a-121">Seu ambiente do RCS e quaisquer dados relacionados são excluídos.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ed4a-122">Depois de excluir um ambiente do RCS, não é possível recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="2ed4a-123">Um novo ambiente do RCS pode ser criado em qualquer região disponível do RCS.</span><span class="sxs-lookup"><span data-stu-id="2ed4a-123">A new RCS environment can be created in any available RCS region.</span></span>
