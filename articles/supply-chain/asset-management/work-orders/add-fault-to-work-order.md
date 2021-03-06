---
title: Adicionar falha à ordem de serviço
description: Este tópico descreve como adicionar registros de falha a ordens de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0a79986e3b477865bc1816a1d28c1b7094ae3974
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809797"
---
# <a name="add-fault-to-work-order"></a>Adicionar falha à ordem de serviço

[!include [banner](../../includes/banner.md)]



É possível adicionar falhas que foram configuradas no designer de falhas a uma ordem de serviço. Um ou mais registros de falha devem estar conectados aos tipos de ativo usados para o ativo selecionado na ordem de serviço. Para obter mais informações sobre a configuração, consulte [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço para a qual será criado um registro de falha e, em seguida, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Ativo**, selecione **Falha de ativo**.

3. Na Guia Rápida **Sintomas**, selecione **Adicionar linha**. Um número de falha sequencial é inserido automaticamente no campo **Falha**.

4. No campo **Sintoma de falha**, selecione o sintoma relevante.

5. Nos campos **Área de falha** e **Tipo de falha**, selecione os valores apropriados.

6. No campo **Data da falha**, a data atual é inserida automaticamente. Você pode selecionar uma data diferente conforme o necessário.

7. Na Guia Rápida **Causas do sintoma selecionado**, adicione uma linha para descrever a causa do problema.

8. Na Guia Rápida **Recursos para o sintoma selecionado**, adicione uma linha para descrever uma possível solução para o problema.

9. Selecione **Salvar**.

A ilustração a seguir mostra um exemplo de um registro de falha.

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Exibir falhas de ativos

Na lista **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos.

Na página de listagem **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos. Para abrir a página, selecione **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo**.


## <a name="print-asset-fault-report"></a>Imprimir relatório de falha de ativo

Na página de listagem **Todos os ativos**, você pode imprimir um relatório de falhas de ativos que mostre todos os registros de falha e uma visão geral gráfica das estatísticas de falhas.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.

2. Selecione o ativo para o qual será impresso um relatório de falha.

3. No Painel de Ação, na guia **Geral**, no grupo **Relatórios**, selecione **Falha de ativo**.

4. Insira um período específico ou selecione um tipo de falha.

5. Selecione **OK** para imprimir o relatório.

>[!NOTE]
>Para imprimir um relatório de falhas para vários ativos ou tipos de ativos, selecione **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Falha de ativo**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]