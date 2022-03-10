---
title: Transferir razão auxiliar para a contabilidade
description: Este tópico descreve recursos que estão relacionados ao processo de transferência do razão auxiliar na contabilidade.
author: rcarlson
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 213bbc2541c614aa26b0c830431818fb99c7682d
ms.sourcegitcommit: f5885999e008a49fe072d95f15e239905c24918a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900713"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transferir razão auxiliar para a contabilidade

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que estão relacionados às regras de transferência em lotes das entradas no diário-razão auxiliar.

Na versão 8.1, as alterações foram feitas para permitir a transferência de regras, o que substituiu a opção **Síncrona**. Para obter mais informações, consulte [Recursos removidos ou substituídos do Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

As opções a seguir estão disponíveis para transferir lotes do razão auxiliar:

- **Assíncrona** – a transferência das entradas de contabilidade do razão auxiliar para a contabilidade é agendada imediatamente. O comprovante da contabilidade será registrado assim que os recursos estiverem disponíveis para processar a solicitação no servidor.
- **Lote agendado** – as entradas contábeis do razão auxiliar que devem ser transferidas são adicionadas à fila de processamento na Contabilidade. As entradas na fila serão processadas na ordem em que foram recebidas. Cada comprovante da contabilidade atualizará as contas no horário agendado se os recursos estiverem disponíveis para processar o trabalho em lotes no servidor.

Na versão 10.0.8, foram feitas melhorias para aprimorar o desempenho da opção **Assíncrona**. Este recurso está habilitado com o nome **Transferência do razão auxiliar para a otimização do desempenho da Contabilidade**.

A funcionalidade para a transferência assíncrona de lotes do razão auxiliar ajuda a melhorar a transferência de dados do razão auxiliar para a contabilidade. Ao agrupar conjuntos de transações menores e transferir as transações em grupos, a funcionalidade processa as transações com mais eficiência. Quando as transações são agrupadas, os recursos do servidor de lote são usados com mais eficiência.

A transferência assíncrona de lotes do razão auxiliar requer que o servidor de lote seja configurado, esteja online e em funcionamento porque as tarefas em lotes são criadas para execução imediata no servidor de lote. Quando o recurso **Transferência do razão auxiliar para a otimização do desempenho da Contabilidade** estiver habilitado, o trabalho em lotes do sistema de **Automação de processos** chamado **Trabalho de sistema de sondagem de automação do processo** também deverá estar habilitado. Para obter mais informações, consulte [Automação de processos](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

A alteração de eficiência no nível do lote usa um único trabalho em lotes recorrente para todas as entidades legais no sistema. No tempo de execução, um novo trabalho em lotes é criado para processar os registros necessários que ainda não foram transferidos. Mais configurações podem ser controladas na página **Automação de processo**, na administração do sistema. Nessa página, é possível modificar o processo em segundo plano, alterar a frequência e definir um período de suspensão.

Para obter mais informações sobre a configuração do processo de automação, consulte [Processo de automação](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
