---
title: Perguntas frequentes sobre redefinições do data mart
description: Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart.
author: jinniew
ms.date: 06/09/2021
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
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266600"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="f60da-103">Perguntas frequentes sobre redefinições do data mart</span><span class="sxs-lookup"><span data-stu-id="f60da-103">Data mart resets FAQ</span></span>

<span data-ttu-id="f60da-104">Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart.</span><span class="sxs-lookup"><span data-stu-id="f60da-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="f60da-105">Uma redefinição do data mart pode ser um processo demorado e, dependendo das circunstâncias, pode não ser a solução necessária.</span><span class="sxs-lookup"><span data-stu-id="f60da-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="f60da-106">Portanto, este tópico inclui informações sobre as circunstâncias em que uma redefinição do data mart pode ajudar e também quando é improvável que isso ajude.</span><span class="sxs-lookup"><span data-stu-id="f60da-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="f60da-107">O que é uma redefinição de data mart?</span><span class="sxs-lookup"><span data-stu-id="f60da-107">What is a data mart reset?</span></span>

<span data-ttu-id="f60da-108">Uma redefinição do data mart desativará as tarefas de integração, excluirá todos os dados do data mart e, em seguida, reativará a integração.</span><span class="sxs-lookup"><span data-stu-id="f60da-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="f60da-109">Para garantir que os dados antigos não sejam inseridos, uma redefinição do data mart só pode ser iniciada após a conclusão das tarefas existentes.</span><span class="sxs-lookup"><span data-stu-id="f60da-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="f60da-110">Se você tentar redefinir o data mart antes que todas as tarefas sejam concluídas, você pode receber uma mensagem como: "A redefinição do data mart não pôde ser processada por causa de uma tarefa ativa.</span><span class="sxs-lookup"><span data-stu-id="f60da-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="f60da-111">Tente novamente mais tarde."</span><span class="sxs-lookup"><span data-stu-id="f60da-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="f60da-112">Quando preciso fazer uma redefinição de data mart?</span><span class="sxs-lookup"><span data-stu-id="f60da-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="f60da-113">Se uma ou mais das seguintes declarações se aplicarem à sua situação, sua organização poderá se beneficiar de uma redefinição do data mart:</span><span class="sxs-lookup"><span data-stu-id="f60da-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="f60da-114">O banco de dados do aplicativo foi restaurado.</span><span class="sxs-lookup"><span data-stu-id="f60da-114">The application database was restored.</span></span>
- <span data-ttu-id="f60da-115">Você abriu um tíquete de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="f60da-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="f60da-116">Quando uma redefinição de um data mart é inadequada?</span><span class="sxs-lookup"><span data-stu-id="f60da-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="f60da-117">Veja algumas circunstâncias em que não é recomendável redefinir o data mart:</span><span class="sxs-lookup"><span data-stu-id="f60da-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="f60da-118">Você está enfrentando problemas de desempenho associados a uma sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="f60da-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="f60da-119">Você vê um padrão de redefinição recorrente por qualquer um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="f60da-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="f60da-120">**Dados ausentes** – Se você notar que há dados faltando, abra um tíquete de suporte com a Microsoft para analisar o formato do seu relatório e possíveis problemas de sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="f60da-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="f60da-121">**Estado de integração travado**</span><span class="sxs-lookup"><span data-stu-id="f60da-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="f60da-122">**Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente uma redefinição de data mart.</span><span class="sxs-lookup"><span data-stu-id="f60da-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="f60da-123">Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhorias.</span><span class="sxs-lookup"><span data-stu-id="f60da-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="f60da-124">Se redefinir o data mart, perderei os relatórios já criados?</span><span class="sxs-lookup"><span data-stu-id="f60da-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="f60da-125">Não.</span><span class="sxs-lookup"><span data-stu-id="f60da-125">No.</span></span> <span data-ttu-id="f60da-126">Seus relatórios são armazenados em tabelas de SQL que não são afetadas por uma redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="f60da-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="f60da-127">Se estiver preocupado em perder os relatórios que criou, você poderá fazer backup daqueles que não deseja perder.</span><span class="sxs-lookup"><span data-stu-id="f60da-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="f60da-128">Para fazer backups de projetos, abra o Report Designer e acesse **Empresa \> Empresas \> Blocos de construção \> Exportar**.</span><span class="sxs-lookup"><span data-stu-id="f60da-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="f60da-129">Todos os usuários têm que sair do sistema antes que eu possa redefinir o data mart?</span><span class="sxs-lookup"><span data-stu-id="f60da-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="f60da-130">Não.</span><span class="sxs-lookup"><span data-stu-id="f60da-130">No.</span></span> <span data-ttu-id="f60da-131">Os usuários podem continuar trabalhando no sistema durante a redefinição do data mart.</span><span class="sxs-lookup"><span data-stu-id="f60da-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="f60da-132">Porém, eles não poderão acessar os relatórios criados com o Financial Reporter até que a redefinição seja concluída.</span><span class="sxs-lookup"><span data-stu-id="f60da-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
