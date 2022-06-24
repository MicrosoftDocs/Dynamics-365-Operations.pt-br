---
title: Reconciliar frete no gerenciamento de transporte
description: Este artigo descreve o processo de reconciliação de frete.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff29de62de12e8ca8bea0f374921a51b5819222e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844213"
---
# <a name="reconcile-freight-in-transportation-management"></a>Reconciliar frete no gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Este artigo descreve o processo de reconciliação de frete.

Reconciliação de frete pode ser feita manualmente, ou pode ser configurada para ocorrer automaticamente. Para usar a reconciliação automática de frete, você deve configurar um mestre de auditoria em que você possa definir os critérios que determinam quais listas de frete são comparadas automaticamente.

## <a name="the-freight-reconciliation-process"></a>O processo de reconciliação de frete

Taxas de frete são calculadas pelo mecanismo de taxa que está associado com o carro de entrega relevante. Quando uma carga é confirmada, é gerada uma lista de frete e as taxas de frete são transferidas para ela. As taxas de frete são particionadas como encargos diversos para o documento de origem relevante (ordem de compra, ordem de venda e ordem de transferência), dependendo da configuração que é usada para o processo normal de cobrança. O processo de reconciliação de frete (que também é conhecido como o processo de correspondência) pode começar assim que a fatura de frete for recebida da transportadora. A fatura pode ser recebida de forma eletrônica ou em papel. Se a fatura for recebida no papel, você pode gerar uma fatura eletrônica usando a cobrança de frete como um modelo.

[![Processo de reconciliação de frete.](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Reconciliação manual

Se você estiver reconciliando o frete manualmente, você deve corresponder cada linha da fatura com a linha de cobrança de frete ou linhas para a carga que está sendo faturada. Você faz essa correspondência na página **Conciliação de faturas e notas de frete**. Se a quantidade na linha da fatura não coincidir com o valor de cobrança de frete, você deve selecionar um motivo de reconciliação para a diferença. Se existirem vários motivos para reconciliação, você pode dividir o valor incomparável entre elas. O motivo da reconciliação determina como os valores de diferença são lançados na contabilidade. Quando a reconciliação do valor da fatura inteira é contabilizada, ela é enviada para aprovação e o diário é lançado. A ilustração a seguir mostra como gerar uma fatura de frete e executar a reconciliação de frete.

[![Tarefas de reconciliação de frete.](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Reconciliação automática

Para usar a reconciliação automática, você deve especificar a agenda de reconciliação e as faturas e transportadoras a serem usadas. A correspondência das linhas da fatura e listas de frete é feita de acordo com a configuração de tipo de cobrança de frete e mestre de auditoria. Depois de executar a reconciliação automática, você deve lidar com todas as faturas que não são compatíveis com o sistema. Você deve processar essas faturas manualmente antes de lançar as faturas para pagamento.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Corresponder as notas de frete às faturas de frete usando reconciliação automática ou manual

A *correspondência* é o processo de localização das notas de frete que correspondem a cada fatura de frete. Isso pode ser feito por meio da correspondência das linhas de fatura uma a uma (correspondência manual) ou por meio da correspondência de todas as faturas disponíveis de uma só vez (correspondência automática).

### <a name="auto-matching"></a>Correspondência automática

Ao corresponder várias faturas de frete à mesma nota de frete, o processo de correspondência automática funciona da seguinte maneira:

1. Todas as faturas de frete não correspondidas são classificadas por valor, com o maior valor primeiro.
1. As faturas de frete são correspondidas uma a uma, até que a nota de frete não tenha nenhum valor positivo restante.
1. Dependendo da configuração do mestre de auditoria e do valor restante nas faturas de frete, o valor restante é definido.

### <a name="manual-matching"></a>Correspondência manual

Todas as notas de frete com valores positivos estarão disponíveis para correspondência. De forma semelhante à correspondência automática, o usuário só poderá fazer a correspondência entre faturas de frete com valores negativos e notas de frete não correspondidas totalmente.

### <a name="example"></a>Exemplo

Suponha que você tenha uma nota de frete (FB) para um valor de 1500 e que tenha criado três faturas de frete para a nota de frete com uma linha de fatura para cada fatura com as seguintes configurações:

- Nota de frete original (FB): valor 1500
- Fatura 1 (Inv1): valor 1000
- Fatura 2 (Inv2): valor 600
- Fatura 3 (Inv3): valor -100

#### <a name="automatic-matching-result"></a>Resultado da correspondência automática

A correspondência automática será executada na seguinte ordem:

1. Classificar todas as faturas de frete em ordem decrescente por valor: Inv1 -> Inv2 -> Inv3.
1. Corresponder Inv1 com FB. Inv1 tem 1000 correspondido e FB tem um valor restante de 500, portanto, o status é definido como *Parcialmente correspondido*.
1. Corresponder Inv2 com FB. Inv2 tem 500 correspondido e FB tem um valor restante de 0, portanto, o status é definido como *Totalmente correspondido*.
1. Como FB agora foi totalmente correspondida, Inv3 não será processada.

#### <a name="manual-matching-result"></a>Resultado da correspondência manual

Para a correspondência manual, os resultados variam de acordo com a ordem da correspondência, conforme ilustrado nos casos de exemplo a seguir.

##### <a name="manual-matching-case-1"></a>Caso de correspondência manual 1

Uma forma de fazer a correspondência manual para esse exemplo é proceder da seguinte maneira:

1. Corresponder FB com Inv1. FB tem um valor restante de 500, portanto, o status é definido como *Parcialmente correspondido*.
1. Corresponder Inv2 com FB. Inv2 tem 500 correspondido e FB tem um valor restante de 0, portanto, o status é definido como *Totalmente correspondido*.
1. Ao fazer a correspondência manual de Inv3, você não encontrará nenhuma nota de frete não correspondida.

Esse caso é essencialmente igual à correspondência automática

##### <a name="manual-matching-case-2"></a>Caso de correspondência manual 2

Outra forma de fazer a correspondência manual para esse exemplo é proceder da seguinte maneira:

1. Corresponder Inv3 com FB. Agora, FB tem um valor restante de 1600, que é o mesmo que subtrair 100 negativo de 1500. FB e Inv3 têm uma quantidade correspondida de -100.
1. Corresponder Inv1 e Inv2 com FB uma após a outra. FB é totalmente correspondida.

Como mostra esse exemplo, a correspondência de faturas de frete com valores negativos só deve ser feita manualmente. Isso garantirá que sempre seja possível corresponder as faturas de frete com valores negativos a uma nota de frete não correspondida totalmente porque isso permite controlar a sequência de correspondência.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]