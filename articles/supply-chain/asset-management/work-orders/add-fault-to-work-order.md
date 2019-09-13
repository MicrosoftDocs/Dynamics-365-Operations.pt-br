---
title: Adicionar falha à ordem de serviço
description: Este tópico descreve como adicionar registros de falha a ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875509"
---
# <a name="add-fault-to-work-order"></a>Adicionar falha à ordem de serviço

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


É possível adicionar falhas configuradas no designer de falhas a uma ordem de serviço. O ativo selecionado na ordem de serviço deve conter tipos de ativos que possuem um ou mais registros de falhas conectados a ele. Leia mais sobre a instalação na seção [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Na lista, selecione a ordem de serviço na qual deseja registrar uma falha e clique em **Falha de ativo**.

3. Na Guia Rápida **Sintomas**, clique em **Adicionar linha**. Um número de falha sequencial é inserido automaticamente no campo **Falha**.

4. Selecione o sintoma relevante no campo **Sintoma de falha**.

5. Selecione **Área com falha** e **Tipo de falha**.

6. No campo **Data da falha**, a data atual é inserida automaticamente. Você pode selecionar outra data, se necessário.

7. Na Guia Rápida **Causas do sintoma selecionado**, adicione uma linha descrevendo a causa do problema.

8. Na Guia Rápida **Recursos do sintoma selecionado**, adicione uma linha descrevendo uma possível solução para o problema.

9. Clique em **Salvar**.

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Exibir falhas de ativos

Na lista **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos.

Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo** para abrir a lista.


## <a name="print-asset-fault-report"></a>Imprimir relatório de falha de ativo

Na página da lista **Todos os ativos**, você pode imprimir um relatório de falhas de ativos exibindo todos os registros de falhas, bem como uma visão geral gráfica das estatísticas de falhas.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.

2. Na lista **Ativos**, selecione o ativo para o qual você deseja imprimir um relatório de falhas.

3. Na guia **Geral** > **seção Relatórios**, clique em **Falha de ativo**.

4. Insira um período específico ou selecione um tipo de falha.

5. Clique em **OK** para imprimir o relatório.

>[!NOTE]
>Você também pode imprimir um relatório de falhas para vários ativos ou tipos de ativos clicando em **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Falha de ativo**.

