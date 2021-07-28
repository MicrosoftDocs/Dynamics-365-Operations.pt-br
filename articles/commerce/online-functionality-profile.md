---
title: Criar um perfil de funcionalidade online
description: Este tópico descreve como criar um perfil de funcionalidade online no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 45df6566a24cd519ccaad67c5d47abd9b7af7aee
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353027"
---
# <a name="create-an-online-functionality-profile"></a>Criar um perfil de funcionalidade online

[!include [banner](includes/banner.md)]

Este tópico apresenta uma visão geral da configuração de um perfil de funcionalidade online para o Microsoft Dynamics 365 Commerce.

O perfil de funcionalidade online fornece várias configurações usadas em canais online. Cada canal online deve especificar um perfil de funcionalidade online.

## <a name="create-an-online-functionality-profile"></a>Criar um perfil de funcionalidade online

O procedimento a seguir explica como criar um perfil de funcionalidade online no aplicativo da sede do Commerce.

1. No painel de navegação, vá para **Módulos \> Configuração de canal \> Configuração de loja online \> Perfis de funcionalidade**.
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
