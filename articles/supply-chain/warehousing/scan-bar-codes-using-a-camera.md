---
title: Digitalizar códigos de barra usando uma câmera no aplicativo Dynamics 365 for Finance and Operations – Warehousing
description: Este tópico explica como configurar o aplicativo Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barra usando uma câmera em um dispositivo móvel.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 58cf27a250778d68bdffa1eefa5e939276e467fc
ms.sourcegitcommit: dd960cf07d8be791fd27c7bb72e6baa2d63ccd51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2019
ms.locfileid: "2578140"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-supply-chain-management---warehousing-app"></a><span data-ttu-id="d4183-103">Digitalizar códigos de barra usando uma câmera no aplicativo Dynamics 365 Supply Chain Management – Warehousing</span><span class="sxs-lookup"><span data-stu-id="d4183-103">Scan bar codes using a camera in Dynamics 365 Supply Chain Management - Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4183-104">Este tópico explica como configurar o aplicativo Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barra usando uma câmera em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="d4183-104">This topic explains how to set up Dynamics 365 for Finance and Operations – Warehousing app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d4183-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d4183-105">Prerequisites</span></span>
<span data-ttu-id="d4183-106">Para usar esse recurso, você precisa ter instalada a versão 1.2.0.0 do aplicativo Warehousing, e o dispositivo deve ter uma câmera.</span><span class="sxs-lookup"><span data-stu-id="d4183-106">To use this feature, you need to have version 1.2.0.0 of the Warehousing app installed, and your device must have a camera.</span></span> <span data-ttu-id="d4183-107">Ao abrir o aplicativo depois da atualização, você será solicitado a permitir que o aplicativo use a câmera.</span><span class="sxs-lookup"><span data-stu-id="d4183-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="d4183-108">Se o dispositivo não tiver uma câmera, nenhuma solicitação será mostrada, e você não poderá usar uma câmera como scanner.</span><span class="sxs-lookup"><span data-stu-id="d4183-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="d4183-109">Configurar</span><span class="sxs-lookup"><span data-stu-id="d4183-109">Setup</span></span>
<span data-ttu-id="d4183-110">Nas Configurações de exibição do aplicativo de depósito, você pode selecionar se a câmera deve ser usada para digitalização de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="d4183-110">In the Display settings of the Warehousing application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="d4183-111">Se você habilitar **Usar a câmera como scanner**, você pode usar a câmera em cada campo de entrada que tenha o modo de entrada preferido definido como **Digitalização**.</span><span class="sxs-lookup"><span data-stu-id="d4183-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="d4183-112">Para controlar se um campo de entrada pode ser digitalizado ou não, na página **Nomes de campo no aplicativo de depósito**, defina o **Modo de entrada preferido** como **Digitalização**.</span><span class="sxs-lookup"><span data-stu-id="d4183-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="d4183-113">Quando esta opção for selecionada, uma câmera poderá ser usada para digitalização no aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="d4183-113">When this option is selected, a camera can be used for scanning in the Warehousing app.</span></span> <span data-ttu-id="d4183-114">Para obter informações sobre como configurar nomes de campos no aplicativo de depósito, consulte [Configurar nomes de campo no aplicativo de depósito](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="d4183-114">For information about how to configure app field names in Warehousing, see [Configure app field names in Warehousing app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="d4183-115">Formatos de código de barras compatíveis</span><span class="sxs-lookup"><span data-stu-id="d4183-115">Supported bar code formats</span></span>
<span data-ttu-id="d4183-116">Os formatos de código de barras mais comuns são compatíveis, incluindo os códigos 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A e QR.</span><span class="sxs-lookup"><span data-stu-id="d4183-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="d4183-117">Navegação</span><span class="sxs-lookup"><span data-stu-id="d4183-117">Navigation</span></span>
<span data-ttu-id="d4183-118">A página da câmera será iniciada em cada página em que o campo de entrada tiver o modo de entrada preferido definido como Digitalização. Quando você estiver na página Câmera, use as seguintes opções para navegar:</span><span class="sxs-lookup"><span data-stu-id="d4183-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="d4183-119">Clique no botão Voltar para voltar para a página Tarefa e detalhes.</span><span class="sxs-lookup"><span data-stu-id="d4183-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="d4183-120">Clique no lápis da página Tarefa e detalhes ir para a página em que você pode digitar a entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="d4183-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="d4183-121">Clique na câmera da página Tarefa e detalhes para voltar para a página Câmera.</span><span class="sxs-lookup"><span data-stu-id="d4183-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="d4183-122">Página Tarefa e detalhes</span><span class="sxs-lookup"><span data-stu-id="d4183-122">Task and details page</span></span> | <span data-ttu-id="d4183-123">Página Câmera</span><span class="sxs-lookup"><span data-stu-id="d4183-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Página de detalhes da tarefa de exemplo de verificação da câmera](./media/camera-scanning-example-task-detail-page50.png)          | ![Exemplo de verificação da câmera - página da câmera reduzida](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="d4183-126">Na página da câmera, ao clicar no botão Câmera, ele terá aparência esmaecida enquanto tenta identificar um código de barras.</span><span class="sxs-lookup"><span data-stu-id="d4183-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="d4183-127">Se um código de barras não for identificado em 5 segundos, o processo atingirá o tempo limite e o botão Câmera ficará disponível novamente.</span><span class="sxs-lookup"><span data-stu-id="d4183-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="d4183-128">Você poderá tentar digitalizar um código de barras novamente.</span><span class="sxs-lookup"><span data-stu-id="d4183-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="d4183-129">Ao apontar a câmera para um código de barras, mantenha o código de barras alinhado dentro dos colchetes para obter o melhor resultado.</span><span class="sxs-lookup"><span data-stu-id="d4183-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="d4183-130">Quando um código de barras for digitalizado com êxito, o resultado será processado, e você será levado à próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="d4183-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="d4183-131">Se a etapa seguinte tiver outro campo de entrada com o modo de entrada preferido definido como Digitalização, a página da câmera será iniciada novamente.</span><span class="sxs-lookup"><span data-stu-id="d4183-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="d4183-132">Se a etapa seguinte não for um campo de digitalização, a página da câmera não será iniciada.</span><span class="sxs-lookup"><span data-stu-id="d4183-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>

