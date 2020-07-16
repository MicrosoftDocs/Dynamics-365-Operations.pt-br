---
title: Automação de processos
description: Este tópico fornece detalhes sobre como a automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
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
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508176"
---
# <a name="process-automation"></a><span data-ttu-id="40ab0-103">Automação de processos</span><span class="sxs-lookup"><span data-stu-id="40ab0-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="40ab0-104">A automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote.</span><span class="sxs-lookup"><span data-stu-id="40ab0-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="40ab0-105">A exibição de calendário atualizada do trabalho agendado permite que os usuários finais exibam e executem ações no trabalho agendado e concluído.</span><span class="sxs-lookup"><span data-stu-id="40ab0-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="40ab0-106">Administração</span><span class="sxs-lookup"><span data-stu-id="40ab0-106">Administration</span></span>

<span data-ttu-id="40ab0-107">A página de administração central de todas as automações de processos é encontrada no módulo Administração do Sistema no menu **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="40ab0-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="40ab0-108">Essa página listará todos os processos automatizados (série) que estão configurados no sistema.</span><span class="sxs-lookup"><span data-stu-id="40ab0-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="40ab0-109">Ela também permitirá que você adicione novas automações de processos diretamente nela.</span><span class="sxs-lookup"><span data-stu-id="40ab0-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="40ab0-110">Depois que uma série é configurada, é possível gerenciá-la nesta lista.</span><span class="sxs-lookup"><span data-stu-id="40ab0-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="40ab0-111">Você pode optar por editar toda a série, excluí-la, exibir todas as ocorrências em uma exibição de lista ou desabilitar a série se desejar pausar o trabalho agendado por um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="40ab0-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="40ab0-112">Exibição de calendário</span><span class="sxs-lookup"><span data-stu-id="40ab0-112">Calendar view</span></span> 
<span data-ttu-id="40ab0-113">Uma das principais vantagens da automação de processos é a capacidade de ver o trabalho agendado em uma exibição de calendário simples.</span><span class="sxs-lookup"><span data-stu-id="40ab0-113">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="40ab0-114">Essa exibição permite ver o trabalho de uma semana por vez.</span><span class="sxs-lookup"><span data-stu-id="40ab0-114">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="40ab0-115">Você verá essa exibição no lado direito da página **Automação de processos**.</span><span class="sxs-lookup"><span data-stu-id="40ab0-115">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="40ab0-116">Ela será preenchida com o trabalho agendado para a série selecionada.</span><span class="sxs-lookup"><span data-stu-id="40ab0-116">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="40ab0-117">[![Calendário da automação de processos](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="40ab0-117">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="40ab0-118">Alterações de ocorrência</span><span class="sxs-lookup"><span data-stu-id="40ab0-118">Occurrence changes</span></span>
<span data-ttu-id="40ab0-119">Cada ocorrência pode ser modificada sem afetar outras ocorrências definidas pela série que as originou.</span><span class="sxs-lookup"><span data-stu-id="40ab0-119">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="40ab0-120">As ocorrências de trabalho agendado podem ser editadas na exibição de calendário selecionando o botão **Exibir/Editar** e selecionando **Ocorrência**.</span><span class="sxs-lookup"><span data-stu-id="40ab0-120">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="40ab0-121">Isso permite acessar todas as configurações originalmente exibidas no assistente de configuração da série e oferece a capacidade de fazer uma alteração única na ocorrência selecionada.</span><span class="sxs-lookup"><span data-stu-id="40ab0-121">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="40ab0-122">Uma ocorrência de trabalho agendado também pode ser desativada selecionando o botão **Desabilitar** na exibição de calendário.</span><span class="sxs-lookup"><span data-stu-id="40ab0-122">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="40ab0-123">Documentação do Desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="40ab0-123">Developer documentation</span></span> 
<span data-ttu-id="40ab0-124">No momento, a documentação do desenvolvedor está sendo escrita para permitir que os desenvolvedores estendam a estrutura de automação de processos.</span><span class="sxs-lookup"><span data-stu-id="40ab0-124">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="40ab0-125">Essa documentação fornecerá informações sobre como criar processos personalizados que precisam ser executados pelo servidor de lote agendado com o assistente de automação de processos e aparecem na exibição de calendário automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40ab0-125">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
