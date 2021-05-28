---
title: Quando redefinir um data mart
description: Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart e as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988983"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="92edd-103">Quando redefinir um data mart</span><span class="sxs-lookup"><span data-stu-id="92edd-103">When to reset a data mart</span></span>

<span data-ttu-id="92edd-104">A redefinição de um data mart pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="92edd-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="92edd-105">Dependendo das circunstâncias, essa ação pode não ser a solução necessária.</span><span class="sxs-lookup"><span data-stu-id="92edd-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="92edd-106">Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart, bem como as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.</span><span class="sxs-lookup"><span data-stu-id="92edd-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="92edd-107">Quando preciso fazer uma redefinição de data mart?</span><span class="sxs-lookup"><span data-stu-id="92edd-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="92edd-108">Considere as afirmações a seguir antes de redefinir um data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="92edd-109">Se uma ou mais afirmações forem aplicáveis, é possível que sua organização se beneficie da redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="92edd-110">O banco de dados do aplicativo foi restaurado?</span><span class="sxs-lookup"><span data-stu-id="92edd-110">Was the application database restored?</span></span>
- <span data-ttu-id="92edd-111">Você reportou incidente de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas?</span><span class="sxs-lookup"><span data-stu-id="92edd-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="92edd-112">Quando não é adequado redefinir um data mart?</span><span class="sxs-lookup"><span data-stu-id="92edd-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="92edd-113">Há algumas circunstâncias em que não é recomendável redefinir um data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="92edd-114">Veja a seguir.</span><span class="sxs-lookup"><span data-stu-id="92edd-114">These include the following.</span></span> 

- <span data-ttu-id="92edd-115">Você está enfrentando problemas de desempenho associados a uma sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="92edd-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="92edd-116">Se você tiver um padrão de redefinição recorrente devido a qualquer um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="92edd-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="92edd-117">**Dados ausentes**</span><span class="sxs-lookup"><span data-stu-id="92edd-117">**Missing data**</span></span> 
  - <span data-ttu-id="92edd-118">**Estado de integração travado**</span><span class="sxs-lookup"><span data-stu-id="92edd-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="92edd-119">**Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente a redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="92edd-120">Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhoria.</span><span class="sxs-lookup"><span data-stu-id="92edd-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="92edd-121">O que é uma redefinição de data mart?</span><span class="sxs-lookup"><span data-stu-id="92edd-121">What is a data mart reset?</span></span>
- <span data-ttu-id="92edd-122">Uma redefinição só será iniciada quando as tarefas existentes forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="92edd-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="92edd-123">Isso garante que dados antigos não sejam inseridos.</span><span class="sxs-lookup"><span data-stu-id="92edd-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="92edd-124">Nesse momento, talvez você veja uma mensagem como: "Não foi possível processar a redefinição do data mart por causa de uma tarefa ativa.</span><span class="sxs-lookup"><span data-stu-id="92edd-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="92edd-125">Tente novamente mais tarde.”</span><span class="sxs-lookup"><span data-stu-id="92edd-125">Please try again later.”</span></span>
- <span data-ttu-id="92edd-126">A redefinição desabilitará as tarefas de integração e excluirá todos os dados do data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="92edd-127">A integração é habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="92edd-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="92edd-128">Se redefinir o data mart, perderei os relatórios já criados?</span><span class="sxs-lookup"><span data-stu-id="92edd-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="92edd-129">Não, os relatórios são armazenados em tabelas de SQL que não são afetadas por uma redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="92edd-130">Se você estiver preocupado em perder os relatórios que criou, poderá fazer backup daqueles que não deseja perder.</span><span class="sxs-lookup"><span data-stu-id="92edd-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="92edd-131">Para fazer backups, abra o Report Designer e acesse **Empresa > Empresas > Blocos de construção > Exportar**.</span><span class="sxs-lookup"><span data-stu-id="92edd-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="92edd-132">É necessário que todos os usuários saiam do sistema para redefinir o data mart?</span><span class="sxs-lookup"><span data-stu-id="92edd-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="92edd-133">Não, os usuários podem continuar trabalhando no sistema durante a redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="92edd-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="92edd-134">No entanto, eles não poderão acessar os relatórios criados com o Financial Reporter até que a redefinição seja concluída.</span><span class="sxs-lookup"><span data-stu-id="92edd-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
