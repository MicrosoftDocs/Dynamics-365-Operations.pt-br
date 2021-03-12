---
title: Escolher o lote mais antigo em um dispositivo móvel
description: Este tópico descreve como configurar e aplicar as opções para escolher o lote mais antigo de um dispositivo móvel.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdf6335bd333569e278ccd9cf3972c0ec57d4e6c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989659"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="f509f-103">Escolher o lote mais antigo em um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f509f-103">Pick oldest batch on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f509f-104">Você pode acessar a configuração **Escolher lote mais antigo** em um menu de dispositivo móvel, o que permite a você forçar os trabalhadores do depósito ou orientá-los a escolher o lote mais antigo do local atual.</span><span class="sxs-lookup"><span data-stu-id="f509f-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="f509f-105">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="f509f-105">Where it applies</span></span>
<span data-ttu-id="f509f-106">Escolher lote mais antigo é configurado em itens de menu de dispositivo móvel e afeta a separação de lote dos itens abaixo.</span><span class="sxs-lookup"><span data-stu-id="f509f-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="f509f-107">Como definir a configuração para Escolher lote mais antigo</span><span class="sxs-lookup"><span data-stu-id="f509f-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="f509f-108">Para itens definidos de modo a usar o trabalho existente, **Escolher lote mais antigo** pode ser definido como **Nenhum**, **Avisar**, ou **Forçar** do menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f509f-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="f509f-109">**Nenhum**: Os trabalhadores não receberão nenhuma mensagem e poderão escolher qualquer lote no local.</span><span class="sxs-lookup"><span data-stu-id="f509f-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="f509f-110">**Avisar** e **Forçar**: Uma lista de lote(s) com a data de vencimento mais antiga será exibida acima do controle de lote quando o trabalhador selecionar um lote.</span><span class="sxs-lookup"><span data-stu-id="f509f-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="f509f-111">Se a localização for controlada por placa de licença, uma lista de placas de licença com o lote mais antigo será exibida acima do controle de placa de licença.</span><span class="sxs-lookup"><span data-stu-id="f509f-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="f509f-112">**Avisar**: Se um trabalhador escolher uma placa de licença ou um lote que não esteja na lista exibida, o controle será cancelado e um aviso de que há um lote mais antigo a selecionar será exibido.</span><span class="sxs-lookup"><span data-stu-id="f509f-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="f509f-113">Para poder continuar o trabalho, o trabalhador pode selecionar novamente a mesma placa de licença ou lote.</span><span class="sxs-lookup"><span data-stu-id="f509f-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="f509f-114">**Forçar**: os trabalhadores continuarão a receber a mensagem informando que há um lote mais antigo a escolher.</span><span class="sxs-lookup"><span data-stu-id="f509f-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>
