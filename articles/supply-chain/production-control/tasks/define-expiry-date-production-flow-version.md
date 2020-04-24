---
title: Definir uma data de vencimento de uma versão de fluxo de produção
description: Para encerrar a validade e o processamento de uma versão de fluxo de produção em uma data planejada ou para planejar a substituição de uma versão ativa por uma nova, é necessário definir uma data de vencimento na versão.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d942f54b2739f2ca3dcc3e8b8a497166a8edb42
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212080"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="7014f-103">Definir uma data de vencimento de uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="7014f-103">Define an expiry date for a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7014f-104">Para encerrar a validade e o processamento de uma versão de fluxo de produção em uma data planejada ou para planejar a substituição de uma versão ativa por uma nova, é necessário definir uma data de vencimento na versão.</span><span class="sxs-lookup"><span data-stu-id="7014f-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="7014f-105">Não é necessário desativar a versão.</span><span class="sxs-lookup"><span data-stu-id="7014f-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="7014f-106">Definir uma data de vencimento para encerrar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="7014f-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="7014f-107">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="7014f-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="7014f-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7014f-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7014f-109">Selecione qualquer fluxo de produção que tenha uma versão já definida.</span><span class="sxs-lookup"><span data-stu-id="7014f-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="7014f-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7014f-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7014f-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="7014f-111">Click Edit.</span></span>
5. <span data-ttu-id="7014f-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7014f-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="7014f-113">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="7014f-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="7014f-114">Para a data de vencimento, uma nova versão não iniciará nem será ativada.</span><span class="sxs-lookup"><span data-stu-id="7014f-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="7014f-115">Também não será possível criar ou iniciar trabalhos para esse fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="7014f-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="7014f-116">Ainda será possível concluir trabalhos iniciados após a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="7014f-116">You can still complete started jobs after the expiration date.</span></span>  

