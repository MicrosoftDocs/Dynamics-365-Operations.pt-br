---
title: Adicionar um canal a uma hierarquia organizacional
description: Este artigo descreve como adicionar um canal a uma hierarquia organizacional no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8de9242b9d272158dff9c486006a1684f073935e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876577"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Adicionar um canal a uma hierarquia organizacional


[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar um canal a uma hierarquia organizacional no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Os canais precisam ser associados a uma ou mais hierarquias organizacionais. Antes de criar canais, você precisa confirmar que suas hierarquias organizacionais foram configuradas.  

Consulte [Hierarquias organizacionais](channels-org-hierarchies.md) para obter mais detalhes sobre como criar hierarquias organizacionais.

## <a name="select-a-hierarchy"></a>Selecionar uma hierarquia

Para selecionar uma hierarquia, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de Canal \> Hierarquias da organização**.
1. Na lista, selecione a hierarquia da organização à qual você adicionará o canal.
1. No painel de ação, selecione **Exibir** para ver detalhes de hierarquia.

A imagem a seguir mostra os detalhes da hierarquia organizacional selecionada.

![Detalhes da hierarquia organizacional selecionada.](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Adicionar um canal a um nó de hierarquia

Para adicionar um canal a um nó da hierarquia, siga estas etapas.

1. No painel de ação, selecione **Editar**.
1. Selecione o nó da hierarquia ao qual você deseja adicionar o canal e, na lista suspensa **Inserir**, selecione **Canal de Varejo**. 
1. Selecione o canal a ser adicionado e clique no botão **OK**.
1. No painel de ação, selecione **Salvar**.
1. No painel de ação, selecione **Publicar** e especifique uma **Data de efetivação** no passado para que esta ação entre em vigor imediatamente.

A imagem a seguir mostra como selecionar um canal a ser adicionado a um nó de hierarquia.

![Selecionar um canal para adicionar a um nó de hierarquia.](media/channel-add-to-org-hierarchy-2.png)

A imagem a seguir mostra uma hierarquia com vários canais adicionados.

![Uma hierarquia com vários canais adicionados.](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planejar sua hierarquia da organização](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hierarquias da organização](channels-org-hierarchies.md)

[Configurar um canal de varejo](channel-setup-retail.md)
    
[Configurar um canal online](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]