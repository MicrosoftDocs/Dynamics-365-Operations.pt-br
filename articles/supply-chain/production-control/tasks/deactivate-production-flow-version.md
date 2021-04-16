---
title: Desativar uma versão de fluxo de produção
description: Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e47cb950ce488d8b6170f829e1fedc664b921a1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811549"
---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="9348d-103">Desativar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="9348d-103">Deactivate a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9348d-104">Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada.</span><span class="sxs-lookup"><span data-stu-id="9348d-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="9348d-105">Você deverá usar esta opção somente se todas as regras kanban e todas as atividades terminaram e não serão ativadas novamente.</span><span class="sxs-lookup"><span data-stu-id="9348d-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="9348d-106">Observe que a data de vencimento de todas as regras kanban relacionadas a essa versão de fluxo de produção será atualizada com a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="9348d-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="9348d-107">Para modificar uma versão ativa de fluxo de produção, considere definir uma data de vencimento para a versão ativa e criar uma nova versão.</span><span class="sxs-lookup"><span data-stu-id="9348d-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="9348d-108">Isto permitirá que você continue com suas operações de produção enquanto prepara a nova versão e as regras kanban relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9348d-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="9348d-109">Para expirar uma versão ativa de fluxo de produção, é necessário definir uma data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="9348d-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="9348d-110">Nesse sentido, a desativação funciona mais como uma exceção do que uma regra.</span><span class="sxs-lookup"><span data-stu-id="9348d-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="9348d-111">Para este procedimento, é necessário um fluxo de produção com uma versão que possa ser desativada.</span><span class="sxs-lookup"><span data-stu-id="9348d-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="9348d-112">Não tente isso em um ambiente de produção a menos que você tenha plena certeza de que a versão está completamente obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9348d-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="9348d-113">Desativar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="9348d-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="9348d-114">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="9348d-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="9348d-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9348d-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9348d-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9348d-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9348d-117">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9348d-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="9348d-118">Clique em Desativar.</span><span class="sxs-lookup"><span data-stu-id="9348d-118">Click Deactivate.</span></span>
    * <span data-ttu-id="9348d-119">Não continue se não estiver totalmente certo de que esta versão do fluxo de produção esteja obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9348d-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="9348d-120">Clicar em OK expirará todas as regras kanban ativas e interromperá instantaneamente todas as atividades de produção e de reabastecimento desta versão de fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="9348d-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="9348d-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9348d-121">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]