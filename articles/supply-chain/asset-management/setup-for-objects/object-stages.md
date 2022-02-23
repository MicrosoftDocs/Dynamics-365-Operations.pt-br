---
title: Estados de ciclo de vida de ativo
description: Este tópico explica os estados de ciclo de vida de ativo e os modelos do ciclo de vida no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dffedfafd9d75320accf0e27f072bab6fd51f135
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016543"
---
# <a name="asset-lifecycle-states"></a>Estados de ciclo de vida de ativo

[!include [banner](../../includes/banner.md)]

 

Este tópico explica os estados de ciclo de vida de ativo e os modelos do ciclo de vida no Asset Management. Os estados de ciclo de vida de ativo são usados para definir se um ativo está ativo ou inativo. Por exemplo, você pode configurar os estados de ciclo de vida de ativo como **Criado**, **Ativo** e **Concluído**.

> [!NOTE]
> - Os estados de ciclo de vida da solicitação estão vinculados aos estados de ciclo de vida de ativo. Portanto, quando uma solicitação é alterada para um novo estado de ciclo de vida da solicitação, o ativo associado à solicitação é alterado para um novo estado de ciclo de vida de ativo. Por exemplo, se o estado de ciclo de vida de uma solicitação for alterado para **Entrada**, o estado de ciclo de vida de ativo associado será alterado para o estado de ciclo de vida selecionado no campo **Estado do ciclo de vida de entrada** na Guia Rápida **Estado de ciclo de vida de ativo** da página **Modelos de estado de ciclo de vida de ativo**. 


Os estados de ciclo de vida de ativo podem ser configurados nos modelos de ciclo de vida de ativo, onde você pode definir os estados necessários do ciclo de vida para vários tipos de ativos. Primeiro, você configura os estados de ciclo de vida. Então, v-Você cria um modelo no ciclo de vida e seleciona os estados de ciclo de vida para ele.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Estados de ciclo de vida**.
2. Selecione **Novo** para criar um novo estado de ciclo de vida de ativo.
3. No campo **Estado de ciclo de vida**, insira a ID do estado de ciclo de vida.
4. No campo **Nome**, insira uma descrição.

    O campo **Modelos de ciclo de vida** mostra o número de modelos de ciclo de vida de ativo que usam o estado de ciclo de vida de ativo.

5. Defina a opção **Ativo** como **Sim** se esse estado de ciclo de vida tiver de ser um estado de ciclo de vida ativo (ou seja, se as ordens de serviço podem ser criadas para ativos que estejam nesse estado de ciclo de vida).
6. Defina a opção **Excluir linhas do calendário em aberto** como **Sim** se as linhas do calendário de ativos em aberto com um estado de ciclo de vida **Criado** do ativo tiverem de ser excluídas quando estiverem nesse estado de ciclo de vida. Essa configuração será útil se você quiser limpar qualquer agendamento de manutenção em aberto que não seja mais relevante para o ativo (por exemplo, se o ativo não estiver mais ativo).

> [!NOTE]
> Os estados de ciclo de vida de ativo, os modelos de ciclo de vida de ativo e o ativo estão relacionados. Eles são usados da mesma forma como os estados de ciclo de vida da ordem serviço, os modelos de ciclo de vida da ordem de serviço e os tipos de ordem de serviço. 


Após a criação dos estados de ciclo de vida do ativo necessários, você poderá configurá-los nos modelos de ciclo de vida de ativo.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **ativos** \> **modelos de ciclo de vida**.
2. Selecione **Novo** para criar um novo modelo de ciclo de vida de ativo.
3. No campo **Modelo de ciclo de vida**, insira a ID do modelo de ciclo de vida.
4. No campo **Nome**, insira uma descrição.

    O campo **Estados de ciclo de vida** mostra o número de estados de ciclo de vida de ativo selecionados no modelo de ciclo de vida de ativo. O campo **Tipos de ativo** mostra o número de tipos de ativo que usam o modelo de ciclo de vida.

5. Na Guia Rápida **Estados de ciclo de vida**, selecione os estados de ciclo de vida de ativo que devem ser incluídos no modelo de ciclo de vida de ativo:

    - Para usar um estado de ciclo de vida para o modelo, selecione-o na seção **Estados de ciclo de vida restantes** e selecione o botão de seta para a direita ![Seta para a direita](media/15-setup-for-objects.png) para movê-lo até a seção **Estados de ciclo de vida selecionados**.
    - Para usar todos os estados de ciclo de vida disponíveis para o modelo, selecione o botão **Todos os estados de ciclo de vida disponíveis** ![Todos os estados de ciclo de vida disponíveis](media/20-setup-for-objects.png). Todos os estados de ciclo de vida são transferidos para a seção **Estados de ciclo de vida selecionados**.
    - Para remover um estado de ciclo de vida do modelo, selecione-o na seção **estados de ciclo de vida selecionados** e selecione o botão de seta para a esquerda ![Seta para a esquerda](media/16-setup-for-objects.png) para movê-lo até a seção **Estados de ciclo de vida restantes**.

6. Selecione **Atualizações do estado de ciclo de vida** para definir os estados de ciclo de vida de ativo que possam acompanhar um estado de ciclo de vida selecionado.
7. Use a Guia Rápida **Estado de ativo** se você lidar com ativos recebidos para reparo. Na seção **Entrada/saída**, é possível selecionar estados de ciclo de vida de ativo para indicar o fluxo de trabalho de um ativo recebido para reparo. Se oferecer ativos de empréstimo a clientes ou departamentos, na seção **Empréstimo** , você poderá selecionar estados de ciclo de vida para ativos de empréstimo.
