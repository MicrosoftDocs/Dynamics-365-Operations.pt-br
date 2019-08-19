---
title: Digitalizar códigos de barras usando uma câmera no Dynamics 365 for Finance and Operations – Warehousing
description: Este tópico explica como configurar o Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barras usando uma câmera de um dispositivo móvel.
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
ms.openlocfilehash: 5ec9197c2e8b7970fcbf5ea42612c60f940bcae0
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742912"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-for-finance-and-operations--warehousing"></a>Digitalizar códigos de barras usando uma câmera no Dynamics 365 for Finance and Operations – Warehousing

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barras usando uma câmera de um dispositivo móvel. 

## <a name="prerequisites"></a>Pré-requisitos
Para usar esse recurso, você precisa ter a versão 1.2.0.0 do Warehousing instalada, e o dispositivo deve ter uma câmera. Ao abrir o aplicativo depois da atualização, você será solicitado a permitir que o aplicativo Dynamics 365 for Finance and Operations – Warehousing use a câmera. Se o dispositivo não tiver uma câmera, nenhuma solicitação será mostrada, e você não poderá usar uma câmera como scanner. 

## <a name="setup"></a>Configurar
Nas Configurações de exibição do aplicativo de depósito, você pode selecionar se a câmera deve ser usada para digitalização de códigos de barras. Se você habilitar **Usar a câmera como scanner**, você pode usar a câmera em cada campo de entrada que tenha o modo de entrada preferido definido como **Digitalização**. 

Para controlar se um campo de entrada pode ser digitalizado ou não, na página **Nomes de campo no aplicativo de depósito** do Dynamics 365 for Finance and Operations, defina o **Modo de entrada preferido** como **Digitalização**. Quando esta opção for selecionada, uma câmera poderá ser usada para digitalização no aplicativo de depósito. Para obter informações sobre como configurar nomes de campos no aplicativo de depósito, consulte [Configurar nomes de campo no aplicativo de depósito](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Formatos de código de barras compatíveis
Os formatos de código de barras mais comuns são compatíveis, incluindo os códigos 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A e QR. 

## <a name="navigation"></a>Navegação
A página da câmera será iniciada em cada página em que o campo de entrada tiver o modo de entrada preferido definido como Digitalização. Quando você estiver na página Câmera, use as seguintes opções para navegar:
- Clique no botão Voltar para voltar para a página Tarefa e detalhes. 
- Clique no lápis da página Tarefa e detalhes ir para a página em que você pode digitar a entrada manualmente.
- Clique na câmera da página Tarefa e detalhes para voltar para a página Câmera. 

| Página Tarefa e detalhes | Página Câmera | 
| :---------------------: | :--------------------: |
| ![camera-scanning-example-task-detail-page](./media/camera-scanning-example-task-detail-page50.png)          | ![camera-scanning-example-camera-page-smaller](./media/camera-scanning-example-camera-page50.png)          |

Na página da câmera, ao clicar no botão Câmera, ele terá aparência esmaecida enquanto tenta identificar um código de barras. Se um código de barras não for identificado em 5 segundos, o processo atingirá o tempo limite e o botão Câmera ficará disponível novamente. Você poderá tentar digitalizar um código de barras novamente.

Ao apontar a câmera para um código de barras, mantenha o código de barras alinhado dentro dos colchetes para obter o melhor resultado. Quando um código de barras for digitalizado com êxito, o resultado será processado, e você será levado à próxima etapa. Se a etapa seguinte tiver outro campo de entrada com o modo de entrada preferido definido como Digitalização, a página da câmera será iniciada novamente. Se a etapa seguinte não for um campo de digitalização, a página da câmera não será iniciada.

