---
title: Criar um pagamento de imposto
description: O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.
author: twheeloc
ms.date: 10/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54132ca4775482b4a06ff7e73125e804aff40cb4
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700104"
---
# <a name="create-a-sales-tax-payment"></a>Criar um pagamento de imposto

[!include [banner](../../includes/banner.md)]

O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.

1. Acesse **Imposto > Declarações > Imposto > Liquidar e lançar imposto**.
2. No campo **Período de liquidação**, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo **Data inicial**, insira uma data.
    - Se você não selecionar **Incluir correções** na página **Parâmetros da contabilidade**, a liquidação pode ser processada para várias versões. O original é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos. As últimas correções estabelecerão as transações de imposto que foram lançadas depois que a versão original foi criada.
5. No campo **Data de transação**, insira uma data.
6. Clique em **OK**.

## <a name="performance-consideration"></a>Considerações de desempenho

O procedimento de pagamento do imposto pode levar muito tempo para ser concluído. Os principais fatores que afetam o desempenho do procedimento são o número de faturas no período de liquidação e o número de entradas que devem ser lançadas no comprovante de liquidação do imposto. Para ajudar a melhorar o desempenho, você pode optar por ignorar algumas funcionalidades que não são necessárias no seu processo.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Habilitar o recurso de Aperfeiçoamento do desempenho de pagamento de impostos

O recurso **Aperfeiçoamento do desempenho de pagamento de impostos** pode ajudar a melhorar o desempenho do procedimento de pagamento de impostos, ao agregar em uma linha o valor da moeda contábil e o valor da moeda do relatório nas linhas do comprovante de pagamento do imposto que tiverem as mesmas conta principal, dimensão contábil e moeda.

1. Acesse **Administrador do sistema** \> **Espaços de trabalho** \> **Gerenciamento de recursos**.
2. Na guia **Tudo**, procure e selecione **Aperfeiçoamento do desempenho de pagamento de impostos**.
3. Selecione **Habilitar**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Impedir a geração de transações de compensação de impostos

Por padrão, o comprovante de pagamento do imposto lança transações de compensação do imposto em cada transação de imposto liquidada no procedimento de pagamento do imposto. Essas transações de compensação de impostos são incluídas no relatório **Reconciliação de razão/impostos**. Elas mostram o saldo pendente das transações fiscais que não são liquidadas durante o período.

No entanto, as transações de compensação de impostos podem aumentar a carga do procedimento de pagamento de impostos. Portanto, uma liberação chamada **TaxReportGenOffsetTaxTransPerRecordSetFlighting** pode ser ativada sob demanda. Essa liberação pode ajudar a melhorar o desempenho da geração de transações de compensação de impostos para países e regiões, exceto: Tailândia, Polônia, Hungria, Lituânia, Malásia, Índia, Itália, Rússia, República Tcheca, Estônia e Letônia.

> [!NOTE]
> Se houver campos personalizados na tabela de transações de impostos, não será possível ativar a liberação.

Como o relatório **Reconciliação de razão/impostos** é geralmente usado apenas para fins de controle interno e não é necessário em muitos regimes fiscais, você pode optar por não gerar as transações de compensação de impostos no comprovante de pagamento do imposto.

1. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Períodos de liquidação de imposto**.
2. Selecione um período de liquidação.
3. Na guia rápida **Geral**, defina a opção **Impedir a geração de compensação de impostos** para **Sim**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
