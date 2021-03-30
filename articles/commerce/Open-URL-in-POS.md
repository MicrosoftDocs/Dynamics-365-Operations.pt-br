---
title: Abrir URL no POS
description: Este tópico fornece uma visão geral das melhorias realizadas na funcionalidade de pesquisa de produtos e clientes no Dynamics 365 Commerce.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 91d10ac383ed860a69d2d62f4a246c5ca8690b3c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206790"
---
# <a name="open-url-in-pos"></a>Abrir URL no POS

[!include [banner](includes/banner.md)]

Este tópico descreve como você pode configurar um botão no ponto de venda de Retail (POS) para abrir uma URL. Este recurso não requer uma personalização de código, e pode ser configurado por alguém em uma função de não desenvolvedor. 

Esse recurso permite a configuração de um botão no POS, usando o criador de grade de botões para abrir uma URL. Atualmente, isso é suportado nas seguintes configurações:

- Abrir em nova janela.
- Abra dentro do POS.
- Abrir um aplicativo nativo.

## <a name="open-in-new-window"></a>Abrir em nova janela

Essa configuração define se abre a URL em uma nova janela ou dentro do aplicativo. Quando configurado para abrir uma URL dentro do aplicativo, o painel de navegação lateral e barra superior de POS estão disponíveis e visíveis para interação de usuário. Quando configurado para abrir em uma nova janela, a URL será aberta em uma nova janela no Modern POS para Windows, e em uma guia de um novo navegador em todos outros clientes de POS. Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** selecionada.

## <a name="open-within-pos"></a>Abra dentro do POS

Abrir uma URL da Web dentro do POS atualmente só é suportado para Modern POS no Windows. Em outros clientes, esse recurso está em desenvolvimento e planejado para liberação em atualizações futuras. Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** não selecionada.

## <a name="open-a-native-app"></a>Abrir um aplicativo nativo

Este recurso também permite que você especifique URLs da Web para abrir um descritivo nativo. Por exemplo, você pode especificar os protocolos de URL como MailTo, SIP, IM ou MSTEAMS, que podem ser lidados por aplicativos respectivos nativos no dispositivo host. Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** selecionada.

- Para computadores Windows, consulte [Exportar ou importar Associações de aplicação padrão](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) para definir as associações de protocolo padrão se você estiver configurando seu computador usando Deployment Image Servicing and Management (DISM).
- Se estiver usando MDM, como Intune para gerenciar os computadores do Windows, consulte [CSP de política - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).
- Se você for um desenvolvedor que cria um local personalizado, consulte [Iniciar o aplicativo padrão para uma URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Abrir um aplicativo nativo perfeitamente

Windows, iOS e Android também permitem abrir aplicativos de forma perfeita, com base em uma associação de protocolo de aplicativo. Se seu aplicativo não estiver configurado para lidar com a abertura de um navegador da Web, você pode precisar de um desenvolvedor para configurar essa parte.

- Para Windows, consulte [Habilitar aplicativo para websites usando manipuladores de URI de aplicativo](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).
- Para iOS, consulte [Links universais para desenvolvedores](https://developer.apple.com/ios/universal-links/).
- Para Android, consulte [Como Manusear Links do Aplicativo Android](https://developer.android.com/training/app-links/).

| Cliente                | Abrir em nova janela | Abrir aplicativo nativo | Abra dentro do POS | Detalhes                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS no Windows | ✓\*                | ✓               | ✓              | \* Abre em uma nova janela Modern POS |
| PDV em Nuvem             | ✓\*                | ✓               | X              | \* Abre em uma nova guia do navegador        |
| Modern POS no iOS     | ✓\*                | ✓               | X              | \* Abre em uma nova guia do navegador        |
| Modern POS no Android | ✓\*                | ✓               | X              | \* Abre em uma nova guia do navegador        |

## <a name="before-you-begin"></a>Antes de começar

Antes de começar, verifique como configurar [Layouts de tela para ponto de venda (POS)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Abrir URL no POS

Para configurar uma URL a ser aberta no POS, execute estas etapas.

1. Na matriz, acesse **Retail e Commerce \> Configuração do Canal \> Configuração do PDV \> PDV \> Layouts da Tela**.
2. Selecione **Grades de Botões \> Designer**.
3. Crie um novo botão.
4. Selecione o botão **Propriedades**.
5. Selecione **Abrir URL** como a ação.
6. Insira a URL que deseja usar.
7. Configure se deseja abrir a URL em uma nova janela.


[!INCLUDE[footer-include](../includes/footer-banner.md)]