---
title: Reconciliar frete no gerenciamento de transporte
description: "Este artigo descreve o processo de reconciliação de frete."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ab7d21d7a75e2c954831a254bb339d9cf5746d9d
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="reconcile-freight-in-transportation-management"></a>Reconciliar frete no gerenciamento de transporte

[!include[banner](../includes/banner.md)]


Este artigo descreve o processo de reconciliação de frete.

Reconciliação de frete pode ser feita manualmente, ou pode ser configurada para ocorrer automaticamente. Para usar a reconciliação automática de frete, você deve configurar um mestre de auditoria em que você possa definir os critérios que determinam quais listas de frete são comparadas automaticamente.

## <a name="the-freight-reconciliation-process"></a>O processo de reconciliação de frete
Taxas de frete são calculadas pelo mecanismo de taxa que está associado com o carro de entrega relevante. Quando uma carga é confirmada, é gerada uma lista de frete e as taxas de frete são transferidas para ela. As taxas de frete são particionadas como encargos diversos para o documento de origem relevante (ordem de compra, ordem de venda e ordem de transferência), dependendo da configuração que é usada para o processo normal de cobrança. O processo de reconciliação de frete (que também é conhecido como o processo de correspondência) pode começar assim que a fatura de frete for recebida da transportadora. A fatura pode ser recebida de forma eletrônica ou em papel. Se a fatura for recebida no papel, você pode gerar uma fatura eletrônica usando a cobrança de frete como um modelo. 

[![Processo de reconciliação de frete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Reconciliação manual
Se você estiver reconciliando o frete manualmente, você deve corresponder cada linha da fatura com a linha de cobrança de frete ou linhas para a carga que está sendo faturada. Você faz essa correspondência na página **Conciliação de faturas e notas de frete**. Se a quantidade na linha da fatura não coincidir com o valor de cobrança de frete, você deve selecionar um motivo de reconciliação para a diferença. Se existirem vários motivos para reconciliação, você pode dividir o valor incomparável entre elas. O motivo da reconciliação determina como os valores de diferença são lançados na contabilidade. Quando a reconciliação do valor da fatura inteira é contabilizada, ela é enviada para aprovação e o diário é lançado. A ilustração a seguir mostra como gerar uma fatura de frete e executar a reconciliação de frete no Microsoft Dynamics 365 for Finance and Operations. 
[![Tarefas de reconciliação de frete no Microsoft Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Reconciliação automática
Para usar a reconciliação automática, você deve especificar a agenda de reconciliação e as faturas e transportadoras a serem usadas. A correspondência das linhas da fatura e listas de frete é feita de acordo com a configuração de tipo de cobrança de frete e mestre de auditoria. Depois de executar a reconciliação automática, você deve lidar com todas as faturas que não são compatíveis com o sistema. Você deve processar essas faturas manualmente antes de lançar as faturas para pagamento.




