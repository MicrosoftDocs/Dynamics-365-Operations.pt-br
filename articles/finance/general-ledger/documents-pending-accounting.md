---
title: Documentos com contabilidade pendente
description: Este artigo descreve como usar a funcionalidade na página Documentos com contabilidade pendente.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: e915c248abd1c842f8f01490a49db9b824644a29
ms.sourcegitcommit: 07ed6f04dcf92a2154777333651fefe3206a817a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424356"
---
# <a name="documents-pending-accounting"></a>Documentos com contabilidade pendente

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este artigo descreve como usar a funcionalidade na página **Documentos com contabilidade pendente**.

No Microsoft Dynamics 365 Finance 10.0.30, o recurso **Desempenho aprimorado para estrutura contábil do documento de origem** está disponível. Este recurso aprimora os processos de lançamento de documentos habilitados para o documento de origem, começando com o processo de lançamento para faturas de texto livre.

Quando este recurso é habilitado, o lançamento do documento razão auxiliar é feito separadamente do processo de geração contábil ou *lançamento em diário* que cria os detalhes contábeis completos que são transferidos para a contabilidade. Por exemplo, no processo de lançamento de fatura de texto livre, a fatura do cliente no módulo **Contas a receber** é registrada antes que a contabilidade completa seja gerada. Este recurso de desempenho aprimorado permite que as faturas de clientes sejam registradas com mais rapidez enquanto a geração contábil está atrasada.

Os botões a seguir estão disponíveis na página **Documentos com contabilidade pendente**.

- **Gerar contabilidade** – envie um documento que tenha a geração de conta e o lançamento em diário pendente no momento.
- **Exibir distribuições** – exiba as distribuições contábeis de um documento selecionado na lista.
- **Exibir log de erros** – Exiba os detalhes da mensagem de erro de um documento em que o estado contábil indique erros. Você pode exibir os mesmos detalhes da mensagem de erro selecionando o link **Log de erros** na linha do documento.

A geração contábil é feita por um processo em segundo plano de automação chamado **Processador da estrutura contábil**. Para obter mais informações sobre a instalação e a configuração de todas as automações de processo, consulte [Automação de processo](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
