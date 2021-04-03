---
title: Monitorar e gerenciar a inteligência IoT
description: Este tópico explica como monitorar e gerenciar a Inteligência de IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8a037cb31e297926b1bcb66bff91bdd7eb5c40b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264839"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="e65e3-103">Monitorar e gerenciar a inteligência IoT</span><span class="sxs-lookup"><span data-stu-id="e65e3-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e65e3-104">Este tópico explica como monitorar e gerenciar a Inteligência de IoT.</span><span class="sxs-lookup"><span data-stu-id="e65e3-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="e65e3-105">Monitorar cenários no Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e65e3-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="e65e3-106">Você pode monitorar o processamento de Inteligência de IoT a partir de vários locais:</span><span class="sxs-lookup"><span data-stu-id="e65e3-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="e65e3-107">**Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Notificações** – Exibir a lista de notificações não resolvidas.</span><span class="sxs-lookup"><span data-stu-id="e65e3-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="e65e3-108">**Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Notificações fechadas** – Exibir a lista de notificações que foram solucionadas ou descartadas.</span><span class="sxs-lookup"><span data-stu-id="e65e3-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="e65e3-109">**Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Chaves de métrica** – Exibir as chaves de métrica para os gráficos de série **Status de recurso**.</span><span class="sxs-lookup"><span data-stu-id="e65e3-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="e65e3-110">**Módulos \> Controle de produção \> Execução de fabricação \> Status de recurso** – Rastrear métricas específicas usando a caixa de diálogo **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e65e3-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="e65e3-111">Se um cenário detecta uma exceção, uma notificação mostra os detalhes da exceção.</span><span class="sxs-lookup"><span data-stu-id="e65e3-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="e65e3-112">**Espaços de trabalho \> Gerenciamento do chão de fábrica \> Notificações** – Exibir a lista de notificações não resolvidas.</span><span class="sxs-lookup"><span data-stu-id="e65e3-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="e65e3-113">Modificar um cenário de Inteligência IoT em execução</span><span class="sxs-lookup"><span data-stu-id="e65e3-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="e65e3-114">Quando um cenário está em execução, você pode fazer as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="e65e3-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="e65e3-115">Adicionar novas definições de esquema de sensor.</span><span class="sxs-lookup"><span data-stu-id="e65e3-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="e65e3-116">Selecione novos valores de dados de sinal.</span><span class="sxs-lookup"><span data-stu-id="e65e3-116">Select new signal data values.</span></span>
+ <span data-ttu-id="e65e3-117">Cancela a seleção de valores de dados de sinal existentes.</span><span class="sxs-lookup"><span data-stu-id="e65e3-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="e65e3-118">Adicione e mapeie novos valores de dados de sinal.</span><span class="sxs-lookup"><span data-stu-id="e65e3-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="e65e3-119">Atualize os valores de limite.</span><span class="sxs-lookup"><span data-stu-id="e65e3-119">Update threshold values.</span></span>

<span data-ttu-id="e65e3-120">Quando um cenário está em execução, essas alterações são proibidas:</span><span class="sxs-lookup"><span data-stu-id="e65e3-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="e65e3-121">Exclua ou modifique qualquer definição de esquema consumida no momento por um cenário habilitado.</span><span class="sxs-lookup"><span data-stu-id="e65e3-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="e65e3-122">Altera os caminhos de esquema selecionados do cenário habilitado.</span><span class="sxs-lookup"><span data-stu-id="e65e3-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="e65e3-123">Opções de simulação</span><span class="sxs-lookup"><span data-stu-id="e65e3-123">Simulation options</span></span>

<span data-ttu-id="e65e3-124">Você pode simular os sinais da máquina de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e65e3-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="e65e3-125">Para obter mais informações, consulte esses tópicos:</span><span class="sxs-lookup"><span data-stu-id="e65e3-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="e65e3-126">Conectar IoT DevKit AZ3166 ao Hub IoT do Azure</span><span class="sxs-lookup"><span data-stu-id="e65e3-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="e65e3-127">Conectar simulador online Raspberry Pi ao Hub IoT do Azure (Node.js)</span><span class="sxs-lookup"><span data-stu-id="e65e3-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="e65e3-128">Visão geral do acelerador de soluções de simulação de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e65e3-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]