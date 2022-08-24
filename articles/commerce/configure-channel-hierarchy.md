---
title: Configurar um canal para usar uma hierarquia de navegação de canal
description: Este artigo descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b15e6eee86880f0315f42b34056385f718cc6bf1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280384"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Configurar um canal para usar uma hierarquia de navegação de canal


[!include [banner](includes/banner.md)]

Este artigo descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

As hierarquias de navegação de canal organizam os produtos em categorias para que os produtos possam ser procurados em um site de comércio eletrônico ou em pontos de venda (PDV). Os canais de varejo e online devem ser configurados com hierarquias de navegação de canal.

## <a name="configure-the-channel"></a>Configurar o canal

Para configurar um canal para usar uma hierarquia de navegação de canal, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal a configurar.
1. No painel de ação, selecione **Definir metadados de atributo**.
1. Na lista suspensa **Hierarquia de categoria**, selecione a hierarquia de navegação de canal apropriada.
1. No painel de ação, selecione **Salvar**.
1. Em **Grupo de atributos**, adicione os grupos de atributos que serão atributos globais de todos os nós.

A imagem a seguir mostra como configurar um canal para usar uma hierarquia de navegação de canal.

![Exemplo de configuração de canal.](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Definir metadados de atributo

Definir os metadados de atributo permitirá a configuração de atributos em cada nó.

Para definir metadados de atributo, siga estas etapas.

1. No painel de ação, selecione **Definir metadados de atributo**.
1. Para cada nó, selecione **Atributos de produto do canal**.
1. Defina **Mostrar atributo no canal** como **Sim** e **Pode ser refinado** como **Sim** para habilitar refinadores nesse canal.
1. Depois de configurar cada nó conforme desejado, no **Painel de ação**, selecione o botão **Salvar** para salvar.
1. Selecione o **X** no canto superior direito para sair desta tela e voltar à página **Categorias do canal e atributos de produto**.

A imagem a seguir mostra um exemplo de conjunto de atributos de produto de canal configurados em um nó de categoria de canal.

![Atributos de canal em um nó de categoria de canal.](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publicar alterações

Para que as alterações entrem em vigor, você precisará publicá-las.

Para publicar alterações, siga estas etapas.

1. No painel de ação, selecione **Publicar atualizações de canal**.
1. No painel **Publicar atualizações de canal**, selecione **OK**.

A imagem a seguir mostra como publicar atualizações de canal.

![Publicar atualizações de canal.](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Recursos adicionais

[Criar uma hierarquia de navegação de canal](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
