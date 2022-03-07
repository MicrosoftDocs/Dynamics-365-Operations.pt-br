---
title: Digitalizar códigos de barras usando uma câmera no aplicativo móvel de gerenciamento de depósito
description: Este tópico explica como configurar o aplicativo móvel de gerenciamento de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: cc58d88865fea17e0e27463b25e2ba815ee1a5b1
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901963"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Digitalizar códigos de barras usando uma câmera no aplicativo móvel de gerenciamento de depósito

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o aplicativo móvel de gerenciamento de depósito para digitalizar códigos de barras usando uma câmera em um dispositivo móvel.

## <a name="setup"></a>Configurar

Nas configurações de exibição do aplicativo móvel de gerenciamento de depósito, você pode selecionar se a câmera deve ser usada para digitalização de códigos de barras. Se você habilitar **Usar a câmera como scanner**, você pode usar a câmera em cada campo de entrada que tenha o modo de entrada preferido definido como **Digitalização**.

Para controlar se um campo de entrada pode ser digitalizado ou não, na página **Nomes de campo no aplicativo de depósito**, defina o **Modo de entrada preferido** como **Digitalização**. Quando esta opção for selecionada, uma câmera poderá ser usada para digitalização no aplicativo móvel de gerenciamento de depósito. Para obter mais informações, consulte [Configurar campos para o aplicativo móvel de gerenciamento de depósito](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Formatos de código de barras compatíveis

Os formatos de código de barras mais comuns são compatíveis, incluindo os códigos 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A e QR.

## <a name="navigation"></a>Navegação

A página da câmera será iniciada em cada página em que o campo de entrada tiver o **Modo de entrada preferencial** definido como *Digitalização*. Quando você estiver na página da câmera, use as seguintes opções para navegar:

- Selecione o botão Voltar para voltar para a página **Tarefa e detalhes**.
- Selecione o lápis na página **Tarefa e detalhes** para acessar a página em que você pode digitar a entrada manualmente.
- Selecione a câmera da página **Tarefa e detalhes** para voltar à página da câmera.

Na página da câmera, ao selecionar o botão da câmera, ele aparecerá esmaecido quando você tentar identificar um código de barras. Se um código de barras não for identificado em 5 segundos, o processo atingirá o tempo limite e o botão da câmera ficará disponível novamente. Você poderá tentar digitalizar um código de barras novamente.

Ao apontar a câmera para um código de barras, mantenha o código de barras alinhado dentro dos colchetes para obter o melhor resultado. Quando um código de barras for digitalizado com êxito, o resultado será processado, e você será levado à próxima etapa. Se a etapa seguinte tiver outro campo de entrada com o modo de entrada preferido definido como Digitalização, a página da câmera será iniciada novamente. Se a etapa seguinte não for um campo de digitalização, a página da câmera não será iniciada.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]