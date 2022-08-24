---
title: Criar um perfil de funcionalidade online
description: Este artigo descreve como criar um perfil de funcionalidade online no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5ce81900cd0648132748167d03906afc64e97f25
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276792"
---
# <a name="create-an-online-functionality-profile"></a>Criar um perfil de funcionalidade online

[!include [banner](includes/banner.md)]

Este artigo apresenta uma visão geral da configuração de um perfil de funcionalidade online para o Microsoft Dynamics 365 Commerce.

O perfil de funcionalidade online fornece várias configurações usadas em canais online. Cada canal online deve especificar um perfil de funcionalidade online.

## <a name="create-an-online-functionality-profile"></a>Criar um perfil de funcionalidade online

O procedimento a seguir explica como criar um perfil de funcionalidade online no aplicativo do Commerce headquarters.

1. No painel de navegação, Acesse **Módulos \> Configuração de canal \> Configuração de loja online \> Perfis de funcionalidade**.
1. No painel de ação, selecione **Novo**.
1. No campo **Perfil**, insira uma ID para o perfil.
1. No campo **Descrição**, insira um valor ("perfil da Adventure Works" no exemplo da imagem abaixo).
1. Na seção **Funções**, modifique as configurações de **CARRINHO**, **CLIENTES DE VAREJO** ou **FINALIZAR COMPRA**, conforme necessário.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de perfil de funcionalidade online.
  
![Exemplo de perfil de funcionalidade online.](media/online-functionality-profile.png)

## <a name="functions"></a>Funções

- **Produtos agregados**: quando habilitados, esta função permite que o carrinho atualize a quantidade quando o mesmo item é adicionado várias vezes.
- **Permitir finalizar a compra sem pagamentos**: quando habilitada, esta função trata o cenário quando os itens adicionados ao carrinho têm um preço de US$0,00.
- **Criar cliente no modo assíncrono**: esta é uma configuração herdada aplicável a canais de comércio eletrônico de terceiros e não se aplica ao site de comércio eletrônico do Dynamics 365.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Configurar um canal online](channel-setup-online.md)

[Configurar um canal de varejo](channel-setup-retail.md)

[Configurar um canal de call center](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
