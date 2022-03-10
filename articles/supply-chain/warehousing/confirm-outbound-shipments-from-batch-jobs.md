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
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103906"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmar remessas de saída de trabalhos em lote

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa. O trabalho em lotes aqui descrito só se aplica a remessas de ordens de transferência e não a ordens de venda.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Ativar ou desativar o recurso Confirmar remessas de saída de trabalhos em lote

Para usar a funcionalidade descrita neste tópico, o recurso *Confirmar remessas de saída de trabalhos em lote* deve estar ativado no sistema. A partir da versão 10.0.21 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Confirmar remessas de saída de trabalhos em lote* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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