---
title: Abrir URL no PDV
description: Este artigo fornece uma visão geral de melhorias feitas à funcionalidade de pesquisa de produto e cliente no Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.custom: 141393
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: ad82cf1039515e58d1717453ee3fb4e3dafd84fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276418"
---
# <a name="open-url-in-pos"></a>Abrir URL no PDV

[!include [banner](includes/banner.md)]

Este artigo descreve como você pode configurar um botão no ponto de venda (POS) do Dynamics 365 Commerce para abrir uma URL. Este recurso não requer uma personalização de código, e pode ser configurado por alguém em uma função de não desenvolvedor. 

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

- Para computadores Windows, consulte [Exportar ou importar Associações de aplicação padrão](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) para definir as associações de protocolo padrão se você estiver configurando seu computador usando Deployment Image Servicing and Management (DISM).
- Se estiver usando MDM, como Intune para gerenciar os computadores do Windows, consulte [CSP de política - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults).
- Se você for um desenvolvedor que cria um local personalizado, consulte [Iniciar o aplicativo padrão para uma URI](/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Abrir um aplicativo nativo perfeitamente

Windows, iOS e Android também permitem abrir aplicativos de forma perfeita, com base em uma associação de protocolo de aplicativo. Se seu aplicativo não estiver configurado para lidar com a abertura de um navegador da Web, você pode precisar de um desenvolvedor para configurar essa parte.

- Para Windows, consulte [Habilitar aplicativo para websites usando manipuladores de URI de aplicativo](/windows/uwp/launch-resume/web-to-app-linking).
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
