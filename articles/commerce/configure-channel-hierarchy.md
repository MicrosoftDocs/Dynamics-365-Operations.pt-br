---
title: Configurar um canal para usar uma hierarquia de navegação de canal
description: Este tópico descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7b5041d35d310125c314ab2cb77d3cc40cdb7113
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410093"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Configurar um canal para usar uma hierarquia de navegação de canal


[!include [banner](includes/banner.md)]

Este tópico descreve como configurar um canal para usar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

As hierarquias de navegação de canal organizam os produtos em categorias para que os produtos possam ser procurados em um site de comércio eletrônico ou em pontos de venda (PDV). Os canais de varejo e online devem ser configurados com hierarquias de navegação de canal.

## <a name="configure-the-channel"></a>Configurar o canal

Para configurar um canal para usar uma hierarquia de navegação de canal, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal a configurar.
1. No painel de ação, selecione **Definir metadados de atributo**.
1. Na lista suspensa **Hierarquia de categoria**, selecione a hierarquia de navegação de canal apropriada.
1. No painel de ação, selecione **Salvar**.
1. Em **Grupo de atributos**, adicione os grupos de atributos que serão atributos globais de todos os nós.

A imagem a seguir mostra como configurar um canal para usar uma hierarquia de navegação de canal.

![Exemplo de configuração de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Definir metadados de atributo

Definir os metadados de atributo permitirá a configuração de atributos em cada nó.

Para definir metadados de atributo, siga estas etapas.

1. No painel de ação, selecione **Definir metadados de atributo**.
1. Para cada nó, selecione **Atributos de produto do canal**.
1. Defina **Mostrar atributo no canal** como **Sim** e **Pode ser refinado** como **Sim** para habilitar refinadores nesse canal.
1. Depois de configurar cada nó conforme desejado, no **Painel de ação**, selecione o botão **Salvar** para salvar.
1. Selecione o **X** no canto superior direito para sair desta tela e voltar à página **Categorias do canal e atributos de produto**.

A imagem a seguir mostra um exemplo de conjunto de atributos de produto de canal configurados em um nó de categoria de canal.

![Atributos de canal em um nó de categoria de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publicar alterações

Para que as alterações entrem em vigor, você precisará publicá-las.

Para publicar alterações, siga estas etapas.

1. No painel de ação, selecione **Publicar atualizações de canal**.
1. No painel **Publicar atualizações de canal**, selecione **OK**.

A imagem a seguir mostra como publicar atualizações de canal.

![Publicar atualizações de canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Recursos adicionais

[Criar uma hierarquia de navegação de canal](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]