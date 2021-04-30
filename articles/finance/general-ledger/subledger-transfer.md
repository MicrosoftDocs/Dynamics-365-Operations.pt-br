---
title: Transferir razão auxiliar para a Contabilidade
description: Este tópico descreve recursos no Microsoft Dynamics 365 Finance relacionados ao processo de transferência do razão auxiliar na contabilidade.
author: roschlom
ms.date: 09/09/2019
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
ms.openlocfilehash: 1efdf095e379b73d553ca3525abbeee8ca35bcbb
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897495"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transferir razão auxiliar para a Contabilidade

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos no Microsoft Dynamics 365 Finance que estão relacionados às regras de transferência em lotes das entradas no diário-razão auxiliar.

Na versão 8.1, as alterações foram feitas para permitir a transferência de regras, o que substituiu a opção **Síncrona**. Para obter mais informações, consulte [Recursos removidos ou substituídos do Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

As opções a seguir estão disponíveis para transferir lotes do razão auxiliar. 

 - Assíncrona – Esta opção imediatamente agendará a transferência das entradas de contabilidade do razão auxiliar para a contabilidade. O comprovante da contabilidade será registrado assim que os recursos estiverem livres para processar esta solicitação no servidor. 

- Lote agendado – Esta opção permitirá adicionar as entradas de contabilidade do razão auxiliar que estão sendo transferidas para a fila de processamento na contabilidade, na qual as entradas serão processadas na ordem em que forem recebidas. O comprovante da contabilidade será registrado no horário agendado se os recursos estiverem livres para processar o trabalho em lotes no servidor. 
 
Na versão 10.0.8, foram feitas melhorias para aprimorar o desempenho da opção Assíncrona. Este recurso está habilitado com o nome **Transferência do razão auxiliar para a otimização do desempenho da Contabilidade**. 
 
Esta funcionalidade aprimora a transferência de dados do razão auxiliar para a contabilidade. Ela permite que o processo seja mais eficiente e agrupa conjuntos de transações menores para a transferência. Isto permite um uso mais eficiente do servidor de lote. Esta funcionalidade requer que o servidor de lote esteja configurado, conectado e funcionando para que a opção de transferência Assíncrona seja executada corretamente. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]