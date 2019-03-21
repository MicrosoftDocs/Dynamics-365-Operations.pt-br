---
title: Notificações de alerta do cliente por email
description: Este tópico fornece informações sobre como configurar regras que enviam notificações por email se ocorrerem eventos predefinidos.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9545731af20a96c322b4e92c17f3a46b7077295b
ms.sourcegitcommit: a13f44549ab402cfd04b600f6097ba179915f233
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "775055"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="e67e1-103">Notificações de alerta do cliente por email</span><span class="sxs-lookup"><span data-stu-id="e67e1-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="e67e1-104">No Microsoft Dynamics 365 for Finance and Operations, você pode definir regras de alerta personalizados que monitoram exibições filtradas de dados e enviam notificações por email automaticamente quando ocorrerem eventos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="e67e1-104">In Microsoft Dynamics 365 for Finance and Operations, you can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="e67e1-105">A opção para enviar notificações por email está disponível para todos os tipos de alerta com suporte e também pode ser ativada para regras de alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="e67e1-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="e67e1-106">Você pode usar controles internos para criar regras de alerta que monitoram as exibições filtradas de trabalhos em lotes do sistema.</span><span class="sxs-lookup"><span data-stu-id="e67e1-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="e67e1-107">Monitorando o valor do campo **Status**, você também pode configurar regras de alerta que enviam email quando há falha em um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="e67e1-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="e67e1-108">Depois que essas regras de alerta forem criadas, você não precisará verificar os relatórios de alterações nos dados comerciais.</span><span class="sxs-lookup"><span data-stu-id="e67e1-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="e67e1-109">Em vez disso, deixe que o serviço de detecção inteligente de alterações do Finance and Operations faça o monitoramento por você.</span><span class="sxs-lookup"><span data-stu-id="e67e1-109">Instead, you can let the Finance and Operations intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="e67e1-110">Os alertas de cliente dependem do subsistema de email fornecido por meio da integração com o Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="e67e1-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="e67e1-111">É recomendável usar o provedor de protocolo SMTP (Simple Mail Transfer Protocol), para que a distribuição de email que não tenha que depender de um cliente de email local.</span><span class="sxs-lookup"><span data-stu-id="e67e1-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="e67e1-112">Para enviar notificações por email, os clientes devem configurar serviços de email integrado.</span><span class="sxs-lookup"><span data-stu-id="e67e1-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="e67e1-113">As notificações por email são enviadas aos destinatários em nome dos proprietários dos alertas.</span><span class="sxs-lookup"><span data-stu-id="e67e1-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="e67e1-114">Para obter mais informações sobre como configurar no Finance and Operations, consulte [Configurar e enviar email](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="e67e1-114">For more information about how to configure email in Finance and Operations, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="e67e1-115">A imagem a seguir mostra a caixa de diálogo **Criar regra de alerta**, que agora inclui uma opção **Enviar email**.</span><span class="sxs-lookup"><span data-stu-id="e67e1-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="e67e1-116">[![Criar a caixa de diálogo da regra de alerta em que a opção Enviar email esteja definida como Sim](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="e67e1-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e67e1-117">Quando a opção **Enviar email** estiver definida como **Sim**, as notificações de alerta continuarão a ser enviadas da Central de Ações.</span><span class="sxs-lookup"><span data-stu-id="e67e1-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="e67e1-118">Modelos de email de notificação de alerta</span><span class="sxs-lookup"><span data-stu-id="e67e1-118">Alert notification email templates</span></span>

<span data-ttu-id="e67e1-119">O serviço envia notificações por email usando modelos predefinidos de email que fornecem os detalhes básicos da notificação de alerta.</span><span class="sxs-lookup"><span data-stu-id="e67e1-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="e67e1-120">A imagem a seguir mostra a estrutura das notificações de alerta quando elas são recebidas por email.</span><span class="sxs-lookup"><span data-stu-id="e67e1-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="e67e1-121">[![Notificações de alerta baseadas em modelo para a criação de registros, alterações de campo e exclusão de modelos](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="e67e1-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
