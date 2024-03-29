---
title: Criar um perfil de funcionalidade de varejo
description: Este artigo descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f006aaf594f1df097f80c77794e34f9b831e9949
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280232"
---
# <a name="create-a-retail-functionality-profile"></a>Criar um perfil de funcionalidade de varejo

[!include [banner](includes/banner.md)]

Este artigo descreve como criar um perfil de funcionalidade no Microsoft Dynamics 365 Commerce.

O perfil de funcionalidade de comércio fornece várias configurações usadas em canais online. Cada canal deve especificar um perfil de funcionalidade.

## <a name="create-a-functionality-profile"></a>Criar um perfil de funcionalidade

Para criar um novo perfil de funcionalidade, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Configuração de canal \> Perfis de PDV \> Perfis de funcionalidade**.
1. No painel de ação, selecione **Novo**.
1. No campo **Perfil**, insira uma ID para o perfil ("FN006" no exemplo da imagem abaixo).
1. No campo **Descrição**, insira um valor ("perfil da Adventure Works" no exemplo da imagem abaixo).
1. Na seção **Geral**, selecione um país/região para a localidade **ISO**.
1. Na seção **Geral**, modifique outras configurações, conforme necessário.
1. Na seção **Geral**, selecione uma **ID do perfil de recibo** para o recebimento de emails.
1. Na seção **Funções**, modifique as configurações, conforme necessário.
1. Na seção **Valor**, modifique as configurações, conforme necessário.
1. Na seção **Códigos Informativos**, modifique as configurações, conforme necessário.
1. Na seção **Numeração de recibo**, modifique as configurações, conforme necessário. 
  
A imagem a seguir mostra um exemplo de perfil de funcionalidade.
  
![Exemplo de perfil de funcionalidade.](media/retail-functionality-profile.png)

## <a name="additional-resources"></a>Recursos adicionais

[Códigos informativos e grupos de códigos informativos](info-codes-retail.md)           

[Criar novo catálogo de endereços](new-address-book.md) 

[Visão geral do layout da tela](pos-screen-layouts.md)       

[Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
