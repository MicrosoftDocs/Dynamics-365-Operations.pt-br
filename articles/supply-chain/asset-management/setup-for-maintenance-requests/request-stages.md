---
title: Estados de ciclo de vida da solicitação de manutenção
description: Este artigo descreve como configurar estados do ciclo de vida de solicitação de manutenção no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81b30820adf11f0239ea8ff9d1886b5738e38162
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862704"
---
# <a name="maintenance-request-lifecycle-states"></a>Estados do ciclo de vida da solicitação de manutenção

[!include [banner](../../includes/banner.md)]

 


Os estados do ciclo de vida de solicitação de manutenção definem os estágios pelos quais uma solicitação pode passar. Os exemplos incluem **Criada**, **Ativa** e **Concluída**. Quando uma solicitação de manutenção é convertida em uma ordem de serviço, o estado do ciclo de vida de solicitação de manutenção deve ser atualizado para **Concluída** ou **Fechada** para indicar que a solicitação de manutenção não está mais ativa. Na página de listagem **Todas as solicitações de manutenção**, você pode exibir todas as solicitações de manutenção, independentemente do estado de ciclo de vida.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Configurar estados de ciclo de vida de solicitação de manutenção

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Estados de ciclo de vida**.
2. Selecione **Novo** para criar um estado de ciclo de vida de solicitação de manutenção.
3. No campo **Estado de ciclo de vida**, insira uma ID para o estado de ciclo de vida.
4. No campo **Nome**, insira um nome.

    Na Guia Rápida **Detalhes**, o campo **Modelos de ciclo de vida** mostra o número de modelos de ciclo de vida de solicitação de manutenção que usam o estado de ciclo de vida de ativo.

5. Na Guia Rápida **Geral** , defina a opção **Ativa** como **Sim** se uma solicitação de manutenção estiver ativa neste estado de ciclo de vida.
6. Defina a opção **Definir término real** como **Sim** se uma data e hora de término reais são inseridas automaticamente em uma solicitação de manutenção que esteja nesse estado de ciclo de vida.
7. Defina a opção **Criar ordem de serviço** como **Sim** se uma ordem de serviço puder ser criada de uma solicitação de manutenção que esteja nesse estado de ciclo de vida.
8. Defina a opção **Excluir** como **Sim** se uma solicitação de manutenção puder ser excluída quando estiver nesse estado de ciclo de vida.
9. Na Guia Rápida **Atualizar**, as opções **Entrada** e **Saída** na seção **Ativo** são relevantes se você usar o reparo do depósito. Defina a opção adequada como **Sim** se o estado do ciclo de vida do ativo selecionado em uma solicitação de manutenção for atualizado automaticamente para **Entrada** ou **Saída** quando o estado do ciclo de vida da solicitação de manutenção dessa solicitação de manutenção está definida como **Entrada** ou **Saída**.

A ilustração a seguir mostra um exemplo da página **Estados de ciclo de vida de solicitação de manutenção**.

![Página de estados do ciclo de vida da solicitação de manutenção.](media/02-setup-for-requests.png)

> [!NOTE]
> Os estados do ciclo de vida de solicitação de manutenção, os grupos do estado de ciclo de vida e os tipos estão relacionados a, e são usados da mesma forma que, estados de ciclo de vida da ordem de serviço, grupos de estados de ciclo de vida e tipos. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Configurar modelos de ciclo de vida de solicitação de manutenção

Depois de você criar os estados de ciclo de vida que são necessários para as solicitações de manutenção, eles poderão ser divididos em grupos de estados de ciclo de vida, ou modelos de ciclo de vida. Os modelos de ciclo de vida de solicitação de manutenção são usados para criar o fluxo que pode ser usado para diferentes tipos de solicitações de manutenção. Pelo menos um modelo padrão de ciclo de vida de solicitação de manutenção deve ser criado.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Modelos de ciclo de vida**.
2. Selecione **Novo** para criar um modelo de ciclo de vida de solicitação de manutenção.
3. No campo **Modelo de ciclo de vida**, insira a ID do modelo de ciclo de vida.
4. No campo **Nome**, insira um nome.

    Na Guia Rápida **Detalhes**, **Estados de ciclo de vida** mostra o número de estados de ciclo de vida de ativo selecionados no modelo de ciclo de vida de ativo. O campo **Tipos de solicitação de manutenção** mostra o número de tipos de solicitação de manutenção que usam esse modelo de ciclo de vida.

5. Na Guia Rápida **Estados de ciclo de vida**, selecione os estados de ciclo de vida que devem ser incluídos no modelo de ciclo de vida:

    - Para incluir um estado de ciclo de vida no modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida restantes** e selecione o botão de ![seta para a direita.](media/03-setup-for-requests.png) para movê-lo para a seção **Estados do ciclo de vida selecionado**.
    - Para incluir todos os estados de ciclo de vida disponíveis no modelo de ciclo de vida, selecione o botão **Selecionar todos os estados de ciclo de vida disponíveis** ![Selecionar todos os estados de ciclo de vida disponíveis.](media/04-setup-for-requests.png). Todos os estados de ciclo de vida são movidos para a seção **Estados de ciclo de vida selecionados**.
    - Para remover um estado de ciclo de vida do modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida selecionados** e selecione o botão de ![seta para a esquerda.](media/05-setup-for-requests.png) para movê-lo para a seção **Estados do ciclo de vida restantes**.

6. Na Guia Rápida **Geral**, os campos da seção **Atualizações** serão relevantes se você usar o reparo de depósito.

    - No campo **Estado de ciclo de vida para o ativo recebido**, selecione o estado de ciclo de vida de ativo para o qual os ativos selecionados em uma solicitação de manutenção deverão ser automaticamente atualizados quando forem recebidos para reparo de depósito.
    - No campo **Estado de ciclo de vida para o ativo entregue**, selecione o estado de ciclo de vida de ativo para o qual os ativos selecionados em uma solicitação de manutenção deverão ser automaticamente atualizados quando forem devolvidos após o reparo.

A ilustração a seguir mostra um exemplo da página **Modelos de ciclo de vida de solicitação de manutenção**.

![Página dos modelos de ciclo de vida de solicitação de manutenção.](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]