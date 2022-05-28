---
title: Criar um pagamento de imposto
description: O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.
author: twheeloc
ms.date: 01/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c388a8f98cd4581abe2ec13d8922e232321e4039
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735926"
---
# <a name="create-a-sales-tax-payment"></a>Criar um pagamento de imposto

[!include [banner](../../includes/banner.md)]

O procedimento de trabalho de liquidação e lançamento de imposto liquida os saldos de imposto nas contas de imposto e os desloca para a conta de liquidação de imposto por um determinado período.

1. Acesse **Imposto > Declarações > Imposto > Liquidar e lançar imposto**.
2. No campo **Período de liquidação**, selecione no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo **Data inicial**, insira uma data. Se você não selecionar **Incluir correções** na página **Parâmetros da contabilidade**, a liquidação pode ser processada para várias versões. O **original** é o primeiro pagamento para um intervalo de período e pode ser processado apenas uma vez para um intervalo de períodos. As últimas correções estabelecerão as transações de imposto que foram lançadas depois que a versão original foi criada.
5. No campo **Data de transação**, insira uma data.
6. Selecione **OK**. O relatório de **Pagamentos de impostos sobre vendas** é impresso para revisar as transações de imposto sobre vendas liquidadas no período.

A partir da versão 10.0.24 do Finance, você pode omitir o relatório de **pagamentos de impostos sobre vendas** que é gerado diretamente depois que o procedimento periódico de **liquidação e lançamento de imposto sobre vendas** é implementado no recurso de **Separar geração de relatórios de pagamento de impostos sobre vendas da liquidação de impostos** no espaço de trabalho **Gerenciamento de recursos**.

Quando o recurso está habilitado, após a conclusão do processo de liquidação, nenhum relatório de pagamento de imposto sobre vendas é impresso. Em vez disso, você recebe a seguinte mensagem: "A liquidação e o lançamento do imposto sobre vendas foram concluídos. O comprovante 'xxxx, m/d/aaaa' foi lançado."

Você ainda pode executar manualmente o relatório de pagamento de impostos sobre vendas acessando **Impostos** > **Consultas e relatórios** > **Consultas e relatórios** > **Pagamentos de impostos sobre vendas**.

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
