---
title: Automação de processos
description: Este tópico fornece detalhes sobre como a automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 320e18f7fc61300ed2966afef530907fc9fc5ca5
ms.sourcegitcommit: e2a47d31175bbd60acfd7a23ffea70c669358572
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "3690037"
---
# <a name="process-automation"></a><span data-ttu-id="fa215-103">Automação de processos</span><span class="sxs-lookup"><span data-stu-id="fa215-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fa215-104">A automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote.</span><span class="sxs-lookup"><span data-stu-id="fa215-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="fa215-105">A exibição de calendário atualizada do trabalho agendado permite que os usuários finais exibam e executem ações no trabalho agendado e concluído.</span><span class="sxs-lookup"><span data-stu-id="fa215-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="fa215-106">Administração</span><span class="sxs-lookup"><span data-stu-id="fa215-106">Administration</span></span>

<span data-ttu-id="fa215-107">A página de administração central de todas as automações de processos é encontrada no módulo Administração do Sistema no menu **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa215-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="fa215-108">Essa página listará todos os processos automatizados (série) que estão configurados no sistema.</span><span class="sxs-lookup"><span data-stu-id="fa215-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="fa215-109">Ela também permitirá que você adicione novas automações de processos diretamente nela.</span><span class="sxs-lookup"><span data-stu-id="fa215-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="fa215-110">Depois que uma série é configurada, é possível gerenciá-la nesta lista.</span><span class="sxs-lookup"><span data-stu-id="fa215-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="fa215-111">Você pode optar por editar toda a série, excluí-la, exibir todas as ocorrências em uma exibição de lista ou desabilitar a série se desejar pausar o trabalho agendado por um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="fa215-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

<span data-ttu-id="fa215-112">Qualquer processo desabilitado no gerenciamento de recursos não será exibido quando o recurso for desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fa215-112">Any processes that are disabled in feature management will not show when the feature is disabled.</span></span> <span data-ttu-id="fa215-113">Além disso, o mecanismo de plano de automação do processo não agendará ocorrências ou processos em segundo plano para um recurso desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fa215-113">Additionally, the Process automation scheduling engine will not schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="fa215-114">A reabilitação do recurso levará qualquer ocorrência agendada ou processo em segundo plano no passado a ser executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="fa215-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span>

## <a name="calendar-view"></a><span data-ttu-id="fa215-115">Exibição de calendário</span><span class="sxs-lookup"><span data-stu-id="fa215-115">Calendar view</span></span> 
<span data-ttu-id="fa215-116">Uma das principais vantagens da automação de processos é a capacidade de ver o trabalho agendado em uma exibição de calendário simples.</span><span class="sxs-lookup"><span data-stu-id="fa215-116">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="fa215-117">Essa exibição permite ver o trabalho de uma semana por vez.</span><span class="sxs-lookup"><span data-stu-id="fa215-117">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="fa215-118">Você verá essa exibição no lado direito da página **Automação de processos**.</span><span class="sxs-lookup"><span data-stu-id="fa215-118">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="fa215-119">Ela será preenchida com o trabalho agendado para a série selecionada.</span><span class="sxs-lookup"><span data-stu-id="fa215-119">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="fa215-120">[![Calendário da automação de processos](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="fa215-120">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="fa215-121">Alterações de ocorrência</span><span class="sxs-lookup"><span data-stu-id="fa215-121">Occurrence changes</span></span>
<span data-ttu-id="fa215-122">Cada ocorrência pode ser modificada sem afetar outras ocorrências definidas pela série que as originou.</span><span class="sxs-lookup"><span data-stu-id="fa215-122">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="fa215-123">As ocorrências de trabalho agendado podem ser editadas na exibição de calendário selecionando o botão **Exibir/Editar** e selecionando **Ocorrência**.</span><span class="sxs-lookup"><span data-stu-id="fa215-123">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="fa215-124">Isso permite acessar todas as configurações originalmente exibidas no assistente de configuração da série e oferece a capacidade de fazer uma alteração única na ocorrência selecionada.</span><span class="sxs-lookup"><span data-stu-id="fa215-124">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="fa215-125">Uma ocorrência de trabalho agendado também pode ser desativada selecionando o botão **Desabilitar** na exibição de calendário.</span><span class="sxs-lookup"><span data-stu-id="fa215-125">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="fa215-126">Documentação do Desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="fa215-126">Developer documentation</span></span> 
<span data-ttu-id="fa215-127">No momento, a documentação do desenvolvedor está sendo escrita para permitir que os desenvolvedores estendam a estrutura de automação de processos.</span><span class="sxs-lookup"><span data-stu-id="fa215-127">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="fa215-128">Essa documentação fornecerá informações sobre como criar processos personalizados que precisam ser executados pelo servidor de lote agendado com o assistente de automação de processos e aparecem na exibição de calendário automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fa215-128">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
