---
title: Confirmar remessas de saída de trabalhos em lote
description: Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d47b88fcc5e25fc85377b52fa9832916a4bb2217
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572376"
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

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]