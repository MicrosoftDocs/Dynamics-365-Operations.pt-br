---
title: Digitalizar códigos de barras usando uma câmera no aplicativo de depósito
description: Este tópico explica como configurar o aplicativo de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 71ec15b2568eefd8bea99e64c258a65461a7ad95
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965619"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a>Digitalizar códigos de barras usando uma câmera no aplicativo de depósito

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o aplicativo de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel. 

## <a name="prerequisites"></a>Pré-requisitos
Para usar este recurso, você precisa ter instalada a versão 1.2.0.0 do aplicativo de depósito, e o dispositivo deve ter uma câmera. Ao abrir o aplicativo depois da atualização, você será solicitado a permitir que o aplicativo use a câmera. Se o dispositivo não tiver uma câmera, nenhuma solicitação será mostrada, e você não poderá usar uma câmera como scanner. 

## <a name="setup"></a>Instalação
Nas Configurações de exibição do aplicativo de depósito, você pode selecionar se a câmera deve ser usada para digitalização de códigos de barras. Se você habilitar **Usar a câmera como scanner**, você pode usar a câmera em cada campo de entrada que tenha o modo de entrada preferido definido como **Digitalização**. 

Para controlar se um campo de entrada pode ser digitalizado ou não, na página **Nomes de campo no aplicativo de depósito**, defina o **Modo de entrada preferido** como **Digitalização**. Quando esta opção for selecionada, uma câmera poderá ser usada para digitalização no aplicativo de depósito. Para obter informações sobre como configurar nomes de campos do aplicativo no Warehousing, consulte [Configurar nomes de campos no aplicativo de depósito](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Formatos de código de barras compatíveis
Os formatos de código de barras mais comuns são compatíveis, incluindo os códigos 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A e QR. 

## <a name="navigation"></a>Navegação
A página da câmera será iniciada em cada página em que o campo de entrada tiver o modo de entrada preferido definido como Digitalização. Quando você estiver na página Câmera, use as seguintes opções para navegar:
- Clique no botão Voltar para voltar para a página Tarefa e detalhes. 
- Clique no lápis da página Tarefa e detalhes ir para a página em que você pode digitar a entrada manualmente.
- Clique na câmera da página Tarefa e detalhes para voltar para a página Câmera. 

| Página Tarefa e detalhes | Página Câmera | 
| :---------------------: | :--------------------: |
| ![Página de detalhes da tarefa de exemplo de verificação da câmera](./media/camera-scanning-example-task-detail-page50.png)          | ![Exemplo de verificação da câmera - página da câmera reduzida](./media/camera-scanning-example-camera-page50.png)          |

Na página da câmera, ao clicar no botão Câmera, ele terá aparência esmaecida enquanto tenta identificar um código de barras. Se um código de barras não for identificado em 5 segundos, o processo atingirá o tempo limite e o botão Câmera ficará disponível novamente. Você poderá tentar digitalizar um código de barras novamente.

Ao apontar a câmera para um código de barras, mantenha o código de barras alinhado dentro dos colchetes para obter o melhor resultado. Quando um código de barras for digitalizado com êxito, o resultado será processado, e você será levado à próxima etapa. Se a etapa seguinte tiver outro campo de entrada com o modo de entrada preferido definido como Digitalização, a página da câmera será iniciada novamente. Se a etapa seguinte não for um campo de digitalização, a página da câmera não será iniciada.

