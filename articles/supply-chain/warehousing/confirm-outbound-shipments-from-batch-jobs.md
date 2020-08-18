---
title: Confirmar remessas de saída de trabalhos em lote
description: Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652211"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmar remessas de saída de trabalhos em lote

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa. O trabalho em lotes aqui descrito só se aplica a remessas de ordens de transferência e não a ordens de venda.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Habilitar o recurso Confirmar remessas de saída de trabalhos em lote

Antes de poder usar esse recurso, ele deverá estar habilitado no seu sistema. Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. O recurso está listado como:

- **Módulo** - *Gerenciamento de depósito*
- **Nome do recurso** - *Confirmar remessas de saída de trabalhos em lote*

## <a name="process-outbound-shipments"></a>Processar remessas de saída

Para configurar um trabalho em lotes agendado para executar a confirmação de remessa de saída para cargas prontas para remessa:

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
1. A caixa de diálogo **Confirmar remessa** é aberta. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
1. A caixa de diálogo do editor de consultas é aberta. Na guia **Intervalo**, adicione uma linha com os seguintes valores:
    - **Tabela** - *Cargas*
    - **Tabela derivada** - *Cargas*
    - **Campo** - *Status de carga*
    - **Critérios** - *Carregados*
1. Selecione **OK** para retornar à caixa de diálogo **Confirmar remessa**.
1. Na guia rápida **Executar em segundo plano**, defina **Processamento em lotes** como **Sim**.
1. Na guia rápida **Executar em segundo plano**, selecione **Recorrência**.
1. A caixa de diálogo **Definir recorrência** será aberta. Defina o plano de execução, conforme necessário para a sua empresa.
1. Selecione **OK** para retornar à caixa de diálogo **Confirmar remessa**.
1. Selecione **OK** na caixa de diálogo **Confirmar remessa** para adicionar o trabalho em lotes à fila de lotes.

Para obter mais informações, consulte [Visão geral do processamento em lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
