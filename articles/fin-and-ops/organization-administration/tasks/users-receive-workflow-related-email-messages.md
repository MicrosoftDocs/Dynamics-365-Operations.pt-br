---
title: Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho
description: Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916383"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="803a8-103">Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="803a8-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="803a8-104">Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="803a8-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="803a8-105">Por exemplo, as mensagens de email poderão ser enviadas aos usuários quando documentos forem atribuídos a eles para aprovação.</span><span class="sxs-lookup"><span data-stu-id="803a8-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="803a8-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="803a8-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="803a8-107">Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários**.</span><span class="sxs-lookup"><span data-stu-id="803a8-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="803a8-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="803a8-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="803a8-109">No **Painel de ação**, clique em **Opções de usuário**.</span><span class="sxs-lookup"><span data-stu-id="803a8-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="803a8-110">Clique na guia **Fluxo de trabalho**. Verifique se a seção **Notificações** está expandida.</span><span class="sxs-lookup"><span data-stu-id="803a8-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="803a8-111">Na seção **Notificações**, você pode especificar como deseja que o usuário seja notificado sobre eventos relacionados a fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="803a8-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="803a8-112">No campo **Tipo de notificação de fluxo de trabalho de item de linha**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="803a8-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="803a8-113">Agrupado – As notificações para itens de linha são agrupadas em uma única mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="803a8-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="803a8-114">Individual – Uma mensagem de email é enviada para cada item de linha.</span><span class="sxs-lookup"><span data-stu-id="803a8-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="803a8-115">Se quiser que o usuário receba notificações no cliente, marque a caixa de seleção **Enviar notificações no email**.</span><span class="sxs-lookup"><span data-stu-id="803a8-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="803a8-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="803a8-116">Click **Save**.</span></span>
7. <span data-ttu-id="803a8-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="803a8-117">Close the page.</span></span>

