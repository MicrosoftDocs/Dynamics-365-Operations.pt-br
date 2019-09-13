---
title: Atualização automática de contadores de ativos
description: Este tópico descreve a atualização automática de contadores de ativos no Gerenciamento de Ativos.
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875511"
---
# <a name="automatic-update-of-asset-counters"></a>Atualização automática de contadores de ativos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

O registro manual dos contadores de ativos é descrito na seção anterior. A configuração dos contadores de ativos é descrita em [Contadores](../setup-for-objects/counters.md).

Os valores dos contadores também podem ser atualizados automaticamente usando registros de produção, com base nas horas de produção ou na quantidade de produção. Isso é feito em **Atualizar contadores de ativos**. É possível atualizar um ou vários ativos inserindo um parâmetro **Data inicial**. Esse parâmetro especifica a data de início dos registros de produção (horas ou quantidade de produção), ou seja, a data de início a partir da qual os valores dos contadores devem ser atualizados.

Todos os ativos que estão relacionados a um recurso *e* possuem contadores de ativos, configurados para serem atualizados com base nas horas ou quantidade de produção, serão incluídos em uma atualização automática e novos valores de contador serão criados.

No caso dos contadores com base na quantidade de produção, quantidade sem erros e quantidade de erros registradas estão incluídas na contagem. Se a unidade usada para registrar a quantidade produzida for diferente da unidade usada no contador, a quantidade será convertida para corresponder à unidade do contador.

Como mencionado acima, os contadores automáticos podem ser atualizados por meio de registros de produção. Sendo assim, o ativo para o qual você deseja atualizar automaticamente os contadores deve estar relacionado a um recurso (máquina). As descrições a seguir fornecem uma visão geral da configuração e do processamento das ordens de produção (no módulo **Controle de produção**), que é usado como base para a atualização automática de contadores em um ativo no módulo **Gerenciamento de ativos**.

Quando quantidades ou horas de produção tiverem sido registradas no recurso, será possível atualizar os contadores de ativos relacionados.

1. Clique em **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Atualizar contadores de ativos**.

2. Selecione a data de início da atualização automática no campo **Data inicial**.

>[!NOTE]
>A data nesse campo é a data do "trabalho em andamento" em **Transações de roteiro** ( campo **Controle de produção** > **Consultas e relatórios** > **Produção** > **Transações de roteiro** > **Data física**).

3. Se quiser selecionar ativos, tipos de ativos ou recursos específicos para a atualização automática, clique em **Filtrar** na Guia Rápida **Registros a serem incluídos** e faça as seleções relevantes.

4. Se necessário, você pode configurar a atualização automática como trabalho em lotes na Guia Rápida **Executar em segundo plano**.

![Figura 1](media/12-work-orders.png)

5. Clique em **OK**. Quando a atualização automática do contador de ativos é concluída, é possível ver os registros do contador relacionados ao ativo em **Contadores de ativos** (**Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos** > selecione o ativo > botão **Contadores**).

Em **Totais do contador de ativos**, você pode obter uma visão geral do registro mais recente feito em todos os tipos de contadores em todos os ativos. Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Valor agregado do ativo**. A exibição é muito semelhante a **Contadores de ativos**, mas não é possível adicionar ou editar registros no **Valor agregado do ativo**. É apenas para visão geral.

![Figura 2](media/13-work-orders.png)


- Ainda é possível criar registros manuais de valores de contador para tipos de contador que são atualizados automaticamente. Consulte a seção "Atualização manual de contadores de ativo" para obter mais informações.
- Você pode configurar contadores relacionados a outro contador, ou seja, quando um contador é atualizado, os contadores relacionados são atualizados automaticamente ao mesmo tempo. Consulte [Contadores](../setup-for-objects/counters.md) para saber mais sobre a configuração de contadores relacionados.
