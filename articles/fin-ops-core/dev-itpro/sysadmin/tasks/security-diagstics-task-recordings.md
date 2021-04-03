---
title: Diagnóstico de segurança de gravações de tarefas
description: Este tópico fornece informações sobre como analisar e gerenciar requisitos de permissão de segurança com base em uma gravação de tarefas.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 99f9da527e818892eb3f46aceca3cc4588b99e81
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570972"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="1ebef-103">Diagnóstico de segurança de gravações de tarefas</span><span class="sxs-lookup"><span data-stu-id="1ebef-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="1ebef-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1ebef-104">Before you begin</span></span>

<span data-ttu-id="1ebef-105">Este tópico fornece informações sobre como analisar e gerenciar requisitos de permissão de segurança com base em uma gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="1ebef-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="1ebef-106">Antes de concluir as etapas deste tópico, você deve ter uma gravação de tarefa do processo comercial que deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="1ebef-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="1ebef-107">Para registrar um processo comercial, consulte [Recursos do gravador de tarefas](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="1ebef-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="1ebef-108">Gerenciar a segurança de um registro de tarefa</span><span class="sxs-lookup"><span data-stu-id="1ebef-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="1ebef-109">Vá para **Administração do sistema** > **Segurança** > **Diagnóstico de segurança para registro de tarefa**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="1ebef-110">Abra o registro de tarefa a partir da localização.</span><span class="sxs-lookup"><span data-stu-id="1ebef-110">Open the task recording from its location.</span></span> <span data-ttu-id="1ebef-111">Selecione **Abrir neste PC** ou **Abrir a partir do Lifecycle Services** e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="1ebef-112">Isso abrirá a página **Detalhes do item de menu segurança** que lista os objetos de segurança necessários para o processo.</span><span class="sxs-lookup"><span data-stu-id="1ebef-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="1ebef-113">Os itens de menu **Ação** e **Saída** não estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="1ebef-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="1ebef-114">No campo **ID de usuário**, selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="1ebef-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="1ebef-115">Se o usuário não tiver permissões para alguns itens de menu, o campo **Permissões ausentes** será atualizado para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Página de detalhes do item de menu de segurança](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="1ebef-117">Selecione **Adicionar referência** para ver uma lista dos objetos de segurança, incluindo as funções, as obrigações e os privilégios que concedem a permissão ausente.</span><span class="sxs-lookup"><span data-stu-id="1ebef-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="1ebef-118">Selecione um objeto de segurança na lista:</span><span class="sxs-lookup"><span data-stu-id="1ebef-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="1ebef-119">Se a **função** for selecionada, selecione **Adicionar função ao usuário**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="1ebef-120">Isso abrirá a página **Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="1ebef-121">Para obter mais informações, consulte a página [Atribuir usuários a funções de segurança](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1ebef-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="1ebef-122">Se **Obrigação** estiver selecionado, selecione **Adicionar obrigação à função**, selecione as funções às quais o imposto deve ser adicionado e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="1ebef-123">Se **Privilégio** estiver selecionado, selecione **Adicionar privilégio a obrigações**, selecione as funções às quais o imposto deve ser adicionado e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ebef-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]