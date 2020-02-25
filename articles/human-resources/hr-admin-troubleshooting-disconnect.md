---
title: O cliente desconecta
description: Este artigo explica o que fazer se o cliente estiver desconectado de seu ambiente e não sabe o porquê.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.article: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73f0c31d5153a82651ed77aa37bc10966ce7c9b1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008062"
---
# <a name="client-disconnects"></a><span data-ttu-id="58465-103">O cliente desconecta</span><span class="sxs-lookup"><span data-stu-id="58465-103">Client disconnects</span></span>

<span data-ttu-id="58465-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="58465-104">**Environment details**</span></span> 

<span data-ttu-id="58465-105">Esse problema pode ocorrer em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="58465-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="58465-106">**Sintoma**</span><span class="sxs-lookup"><span data-stu-id="58465-106">**Symptom**</span></span> 

<span data-ttu-id="58465-107">O cliente estiver desconectado de seu ambiente e não sabe o porquê.</span><span class="sxs-lookup"><span data-stu-id="58465-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="58465-108">O cliente recebe uma das mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="58465-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="58465-109">Perdemos sua conexão.</span><span class="sxs-lookup"><span data-stu-id="58465-109">We've lost your connection.</span></span> <span data-ttu-id="58465-110">Clique em Fechar para continuar trabalhando.</span><span class="sxs-lookup"><span data-stu-id="58465-110">Click Close to continue working.</span></span>
- <span data-ttu-id="58465-111">Parece que você perdeu a conectividade de rede. Clique em Repetir para tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="58465-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="58465-112">**Sinalizador vermelho**</span><span class="sxs-lookup"><span data-stu-id="58465-112">**Red flag**</span></span>

<span data-ttu-id="58465-113">Esse problema ocorre com frequência quando usuários estão no estágio de implementação, são informações de comparação entre produção e ambientes de teste, e esquecem que estão movendo entre sessões.</span><span class="sxs-lookup"><span data-stu-id="58465-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="58465-114">Se os usuários estiverem neste estágio, eles provavelmente passarão por esse problema.</span><span class="sxs-lookup"><span data-stu-id="58465-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="58465-115">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="58465-115">**Issue**</span></span> 

<span data-ttu-id="58465-116">**Tipos de navegador:** Google Chrome, Internet Explorer e Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="58465-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="58465-117">O Microsoft Dynamics 365 Human Resources desconecta os usuários quando duas sessões diferentes são abertas ao mesmo tempo para o mesmo usuário e o mesmo tipo de navegador.</span><span class="sxs-lookup"><span data-stu-id="58465-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="58465-118">(Por exemplo, usuário A está exibindo tanto o ambiente 1 quanto o 2 no Chrome.) Não importa se os usuários abram janelas de navegador diferentes ou guias diferentes.</span><span class="sxs-lookup"><span data-stu-id="58465-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="58465-119">Se as mesmas credenciais de usuário são usadas para entrar tanto no ambiente 1 quanto no ambiente 2 ao mesmo tempo e no mesmo tipo de navegador, Human Resources desconecta uma das sessões.</span><span class="sxs-lookup"><span data-stu-id="58465-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="58465-120">**Solução**</span><span class="sxs-lookup"><span data-stu-id="58465-120">**Solution**</span></span>

<span data-ttu-id="58465-121">Verifique se somente um ambiente está aberto em vez de um navegador de tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="58465-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="58465-122">Os usuários podem abrir mais sessões no mesmo ambiente (ou seja, várias guias no navegador.)</span><span class="sxs-lookup"><span data-stu-id="58465-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="58465-123">Os usuários que desejam pular entre dois ambientes ao mesmo tempo devem abrir cada ambiente em um tipo de navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="58465-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="58465-124">(Por exemplo, o usuário A pode exibir o ambiente 1 no Chrome e o ambiente 2 no Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="58465-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>
