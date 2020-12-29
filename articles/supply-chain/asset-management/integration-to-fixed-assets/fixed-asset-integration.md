---
title: Integrar gerenciamento de ativos com ativos fixos
description: Este tópico explica como integrar os módulos de gerenciamento de ativos e ativos fixos, de forma que você possa vincular ativos fixos com ativos de manutenção.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: cdda44d361011706fe0ba170309908533aa0c2f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422074"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Integrar gerenciamento de ativos com ativos fixos

[!include [banner](../../includes/banner.md)]

Ao integrar os módulos de **gerenciamento de ativos** e **ativos fixos**, você pode vincular ativos fixos com ativos de manutenção. Usuários de ativos fixos podem criar um ativo de manutenção a partir de um ativo fixo novo ou existente, e os usuários de gerenciamento de ativos podem associar um ativo de manutenção a um ativo fixo existente. Esse recurso também torna mais fácil para os usuários de ativos fixos exibirem os custos lançados a partir de ordens de trabalho para ativos de manutenção relacionados.

> [!NOTE]
> Neste tópico, *ativos de manutenção* refere-se a ativos do módulo **Gerenciamento de ativos** e *ativos fixos* refere-se aos ativos do módulo **Ativos fixos**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Definir um local padrão para novos ativos de manutenção que são criados a partir de ativos fixos (opcional)

Essa configuração opcional permite que você defina um local funcional padrão para nossos ativos de manutenção que são criados de ativos fixos. Normalmente, você completa essa configuração apenas uma vez, se você concluí-la.

Para concluir a configuração, siga as etapas abaixo.

1. Vá para **Gerenciamento de ativo \> Configuração \> Parâmetros de gerenciamento de ativo**.
1. Na guia **Ativos fixos**, no campo **Local funcionar**, selecione o local padrão.
1. No Painel de ações, selecione **Salvar**.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Trabalhar com ativos fixos e de manutenção integrados

Esta seção fornece um conjunto de procedimentos que mostram várias maneiras que você pode trabalhar com os recursos de gerenciamento de ativos integrados e ativos fixos.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Associar um ativo de manutenção existente a um ativo fixo

Para associar um ativo de manutenção existente a um ativo fixo, siga estas etapas.

1. Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).
1. Selecionar um ativo.
1. Na Guia Rápida **Ativo fixo**, no campo **Número do ativo fixo**, selecione um ativo fixo existente.
1. No Painel de ações, selecione **Salvar**.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Exibir o ativo fixo associado a um ativo de manutenção selecionado

Para exibir o ativo fixo associado a um ativo de manutenção selecionado, siga estas etapas.

1. Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).
1. Selecionar um ativo.
1. Na Guia Rápida **Ativo fixo**, no campo **Número do ativo fixo**, selecione o link.

    A página **Ativos fixos** do ativo selecionado é aberta. (Normalmente, essa página é localizada em **Ativos fixos \> Ativos fixos \> Ativos fixos**.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Exibir o ativo de manutenção associado a um ativo fixo selecionado

Para exibir o ativo de manutenção associado a um ativo fixo selecionado, siga estas etapas.

1. Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.
1. Selecionar um ativo.
1. No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Exibir**, selecione **Ativo de manutenção**.

    A página **Ativo de manutenção** do ativo associado ao ativo fixo selecionado é aberta. (Normalmente, essa página é encontrada em **Gerenciamento de ativo \> Ativos \> Todos os ativos**.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Exibir os custos de manutenção associados a um ativo fixo

As ordens de trabalho de gerenciamento de ativos podem ser lançadas para ativos de manutenção, e cada uma dessas ordens de trabalho normalmente tem um custo. Quando um ativo fixo é associado a um ativo de manutenção, você pode ir diretamente do ativo fixo para exibir os custos relacionados.

Para exibir os custos de manutenção que são associados com um ativo fixo, siga estas etapas.

1. Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.
1. Selecionar um ativo.
1. No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Exibir**, selecione **Custo de manutenção**.

    A página **Custo de manutenção** é aberta e mostra os custos relacionados.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Criar um novo ativo de manutenção para um ativo fixo existente

Para criar um novo ativo de manutenção para um ativo fixo existente, siga estas etapas.

1. Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.
1. Selecionar um ativo.
1. No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Novo**, selecione **Criar ativo de manutenção**. (Se esta opção não estiver disponível, um ativo de manutenção talvez já esteja associado ao ativo fixo selecionado.)
1. Conclua a criação do ativo, conforme descrito em [Criar um ativo](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Criar um novo ativo fixo e adicionar um novo ativo de manutenção para ele

Para criar um novo ativo fixo e adicionar um novo ativo de manutenção para ele, siga estas etapas.

1. Vá para **Ativos fixos \> Ativos fixos \> Ativos fixos**.
1. No Painel de Ações, selecione **Novo**.
1. Conclua a criação do ativo fixo, conforme descrito em [Criar um ativo fixo](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. No Painel de Ações, na guia **Gerenciamento de ativos**, no grupo **Novo**, selecione **Criar ativo de manutenção**.
1. Conclua a criação do ativo, conforme descrito em [Criar um ativo](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Remover a associação entre dois ativos

Em alguns casos, talvez seja necessário desassociar um ativo de manutenção do ativo fixo. Por exemplo, se desejar [Criar um novo ativo de manutenção](#new-maintenance-from-fixed) a partir de um ativo fixo, você deverá primeiro remover qualquer associação existente.

Para remover uma associação existente entre um ativo de manutenção e um ativo fixo, siga estas etapas.

1. Vá para **Gerenciamento de ativos \> Ativos \> Todos os ativos** (ou **Ativos ativos**).
1. Localize e abra o ativo fixo.
1. Na Guia Rápida **Ativos fixos**, limpe o valor do campo **Local funcional**.
1. No Painel de ações, selecione **Salvar**.
