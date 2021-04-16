---
title: Digitalizar códigos de barras usando uma câmera no aplicativo móvel de gerenciamento de depósito
description: Este tópico explica como configurar o aplicativo móvel de gerenciamento de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831209"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="e77e7-103">Digitalizar códigos de barras usando uma câmera no aplicativo móvel de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="e77e7-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e77e7-104">Este tópico explica como configurar o aplicativo móvel de gerenciamento de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="e77e7-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="e77e7-105">Configurar</span><span class="sxs-lookup"><span data-stu-id="e77e7-105">Setup</span></span>

<span data-ttu-id="e77e7-106">Nas configurações de exibição do aplicativo móvel de gerenciamento de depósito, você pode selecionar se a câmera deve ser usada para digitalização de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="e77e7-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="e77e7-107">Se você habilitar **Usar a câmera como scanner**, você pode usar a câmera em cada campo de entrada que tenha o modo de entrada preferido definido como **Digitalização**.</span><span class="sxs-lookup"><span data-stu-id="e77e7-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="e77e7-108">Para controlar se um campo de entrada pode ser digitalizado ou não, na página **Nomes de campo no aplicativo de depósito**, defina o **Modo de entrada preferido** como **Digitalização**.</span><span class="sxs-lookup"><span data-stu-id="e77e7-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="e77e7-109">Quando esta opção for selecionada, uma câmera poderá ser usada para digitalização no aplicativo móvel de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="e77e7-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="e77e7-110">Para obter mais informações, consulte [Configurar campos para o aplicativo móvel de gerenciamento de depósito](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="e77e7-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="e77e7-111">Formatos de código de barras compatíveis</span><span class="sxs-lookup"><span data-stu-id="e77e7-111">Supported bar code formats</span></span>

<span data-ttu-id="e77e7-112">Os formatos de código de barras mais comuns são compatíveis, incluindo os códigos 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A e QR.</span><span class="sxs-lookup"><span data-stu-id="e77e7-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="e77e7-113">Navegação</span><span class="sxs-lookup"><span data-stu-id="e77e7-113">Navigation</span></span>

<span data-ttu-id="e77e7-114">A página da câmera será iniciada em cada página em que o campo de entrada tiver o **Modo de entrada preferencial** definido como *Digitalização*. Quando você estiver na página da câmera, use as seguintes opções para navegar:</span><span class="sxs-lookup"><span data-stu-id="e77e7-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="e77e7-115">Selecione o botão Voltar para voltar para a página **Tarefa e detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e77e7-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="e77e7-116">Selecione o lápis na página **Tarefa e detalhes** para acessar a página em que você pode digitar a entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="e77e7-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="e77e7-117">Selecione a câmera da página **Tarefa e detalhes** para voltar à página da câmera.</span><span class="sxs-lookup"><span data-stu-id="e77e7-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="e77e7-118">Na página da câmera, ao selecionar o botão da câmera, ele aparecerá esmaecido quando você tentar identificar um código de barras.</span><span class="sxs-lookup"><span data-stu-id="e77e7-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="e77e7-119">Se um código de barras não for identificado em 5 segundos, o processo atingirá o tempo limite e o botão da câmera ficará disponível novamente.</span><span class="sxs-lookup"><span data-stu-id="e77e7-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="e77e7-120">Você poderá tentar digitalizar um código de barras novamente.</span><span class="sxs-lookup"><span data-stu-id="e77e7-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="e77e7-121">Ao apontar a câmera para um código de barras, mantenha o código de barras alinhado dentro dos colchetes para obter o melhor resultado.</span><span class="sxs-lookup"><span data-stu-id="e77e7-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="e77e7-122">Quando um código de barras for digitalizado com êxito, o resultado será processado, e você será levado à próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="e77e7-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="e77e7-123">Se a etapa seguinte tiver outro campo de entrada com o modo de entrada preferido definido como Digitalização, a página da câmera será iniciada novamente.</span><span class="sxs-lookup"><span data-stu-id="e77e7-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="e77e7-124">Se a etapa seguinte não for um campo de digitalização, a página da câmera não será iniciada.</span><span class="sxs-lookup"><span data-stu-id="e77e7-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]