---
title: Quando redefinir um data mart
description: Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart e as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093203"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="a0ecb-103">Quando redefinir um data mart</span><span class="sxs-lookup"><span data-stu-id="a0ecb-103">When to reset a data mart</span></span>

<span data-ttu-id="a0ecb-104">A redefinição de um data mart pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="a0ecb-105">Dependendo das circunstâncias, essa ação pode não ser a solução necessária.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="a0ecb-106">Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart, bem como as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="a0ecb-107">Quando é necessário fazer uma redefinição de data mart?</span><span class="sxs-lookup"><span data-stu-id="a0ecb-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="a0ecb-108">Considere as afirmações a seguir antes de redefinir um data mart.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="a0ecb-109">Se uma ou mais afirmações forem aplicáveis, é possível que sua organização se beneficie da redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="a0ecb-110">O banco de dados do aplicativo foi restaurado, mas o banco de dados do data mart não foi.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="a0ecb-111">Você vê dados incorretos para um período contábil, que não são o resultado de um problema com o design de relatórios.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="a0ecb-112">Você vê dados incorretos para um período contábil e os registros são listados em Tentativas de integração na página **Status de integração** no Designer de Relatórios (inicie o Designer de Relatórios e selecione **Ferramentas > Status de integração**).</span><span class="sxs-lookup"><span data-stu-id="a0ecb-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="a0ecb-113">Você abriu um incidente de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="a0ecb-114">Quando não é adequado redefinir um data mart?</span><span class="sxs-lookup"><span data-stu-id="a0ecb-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="a0ecb-115">Há algumas circunstâncias em que não é recomendável redefinir um data mart.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="a0ecb-116">Veja a seguir.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-116">These include the following.</span></span> 

- <span data-ttu-id="a0ecb-117">Sempre que o motivo não estiver listado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="a0ecb-118">Se você estiver enfrentando problemas de desempenho associados a uma sincronização de dados. Neste caso, a redefinição do data mart provavelmente não ajudará.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="a0ecb-119">Se você tiver um padrão de redefinição recorrente devido a qualquer um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="a0ecb-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="a0ecb-120">**Dados ausentes** – Primeiro, elimine problemas de design de relatórios e problemas de tempo de sincronização de dados, por exemplo, ao observar que o mapa de fatos não é executado desde que os dados ausentes foram lançados.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="a0ecb-121">**Estado de integração travado** – Se a integração estiver lenta ou parecer travada, a redefinição do data mart provavelmente não resolverá o problema.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="a0ecb-122">**Tentativas de redefinição malsucedidas** – Se um número de tentativas de concluir uma redefinição tiver sido feito e não tiver tido êxito devido a dados ausentes, é recomendável abrir um incidente de suporte e trabalhar com um engenheiro de suporte para analisar sua situação antes de tentar redefinir o data mart novamente.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="a0ecb-123">**Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente a redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="a0ecb-124">Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhoria.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="a0ecb-125">O que uma redefinição de data mart não faz</span><span class="sxs-lookup"><span data-stu-id="a0ecb-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="a0ecb-126">Uma redefinição só será iniciada quando as tarefas existentes forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="a0ecb-127">Isso garante que dados antigos não sejam inseridos.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="a0ecb-128">Nesse momento, talvez você veja uma mensagem como: "Não foi possível processar a redefinição do data mart por causa de uma tarefa ativa.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="a0ecb-129">Tente novamente mais tarde.”</span><span class="sxs-lookup"><span data-stu-id="a0ecb-129">Please try again later.”</span></span>
- <span data-ttu-id="a0ecb-130">A redefinição desabilitará as tarefas de integração e excluirá todos os dados do data mart.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="a0ecb-131">A integração é habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="a0ecb-132">Os pontos a seguir especificam duas coisas que a redefinição de um data mart *não* fará.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="a0ecb-133">As redefinições não limpam designs de relatórios.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="a0ecb-134">As redefinições não limpam dados da empresa ou dados do usuário a menos que sejam selecionados.</span><span class="sxs-lookup"><span data-stu-id="a0ecb-134">Resets do not clear company data or user data unless selected.</span></span>
