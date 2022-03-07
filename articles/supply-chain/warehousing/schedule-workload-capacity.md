---
title: Agendar a capacidade da carga de trabalho
description: Este tópico explica como definir e planejar a capacidade de carga de trabalho para trabalhadores em um depósito ou para um depósito completo.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66eb1b2f35d19aba0f4f8f2804577a62ac14e79
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901937"
---
# <a name="schedule-workload-capacity"></a>Agendar capacidade da carga de trabalho

[!include[banner](../includes/banner.md)]

É possível programar a capacidade de carga de trabalho para depósitos, e você também pode projetar cargas de trabalho atuais e futuras para os trabalhadores em depósitos individuais. É possível projetar a carga de trabalho para todo o depósito ou projetar a carga de trabalho separadamente para as cargas de trabalho de entrada e saída.

Para projetar a carga de trabalho de saída para os depósitos selecionados, os dados do agendamento do planejamento mestre devem estar disponíveis para esses depósitos selecionados. Para obter mais informações, consulte [Visão geral de Planos mestre](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Programar e exibir cargas de trabalho para um depósito

Para programar a capacidade de carga de trabalho para um depósito, crie uma configuração de carga de trabalho para um ou mais depósitos e, em seguida, associe a configuração de carga de trabalho a um plano mestre. Na configuração da capacidade de carga de trabalho, é possível definir limites para o peso ou em volume para as transações de entrada e saída. É possível também criar mais de uma configuração para cada depósito e, em seguida, associar a configuração aos planos mestres individuais. Por exemplo, é possível usar essa abordagem para acomodar as alterações sazonais na força de trabalho.

Se os trabalhadores de um depósito trabalharem com transações de cargas de trabalho de entrada e saída, você pode definir a configuração da capacidade do depósito de forma a projetar a carga de trabalho em uma exibição combinada.

Para planejar e visualizar cargas de trabalho de depósitos, é necessário concluir as seguintes tarefas:

1. Criar uma configuração de capacidade de carga de trabalho e definir limites de capacidade de carga de trabalho para um ou mais depósitos.
2. Associar a configuração da capacidade da carga de trabalho a um plano mestre para criar projeções da carga de trabalho e especificar por quanto tempo essas projeções serão aplicadas.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Criar uma configuração de capacidade de carga de trabalho para um depósito

1. Selecione **Gerenciamento de estoque** \> **Configuração** \> **Monitoramento de depósito** \> **Capacidade de carga de trabalho**.
2. No Painel de Ação, selecione **Novo** para criar uma configuração da capacidade de carga de trabalho.
3. Na Guia Rápida **Depósitos**, selecione **Novo** e, em seguida, insira os valores na linha para associar um depósito à configuração da capacidade de carga de trabalho.
4. Marque a caixa de seleção **Cargas de trabalho de entrada e saída combinadas** se o relatório **Capacidade de carga de trabalho** deve ter a carga de trabalho total para transações de entrada e saída em uma exibição.
5. Na Guia Rápida **Tipos de transação**, selecione os tipos de transação de entrada e saída aos quais os limites de carga de trabalho serão aplicados.

    > [!NOTE]
    > É necessário selecionar pelo menos um tipo de transação para as cargas de trabalho de entrada e de saída.

#### <a name="define-limits-for-volume-or-weight"></a>Definir limites para volume ou peso

É possível configurar limites para volume ou peso, dependendo de quais limitações são relevantes para a força de trabalho do depósito. Os limites especificados são incluídos na projeção de capacidade de carga de trabalho que pode ser exibida no relatório **Capacidade de carga de trabalho**.

Para projetar informações sobre volume e peso dos itens, o volume padrão de um item de estoque e o peso de um item de estoque devem ser especificados para todos os produtos. Os campos necessários estão disponíveis nos seguintes grupos de campos na Guia Rápida **Gerenciar Estoque** da página **Detalhes do produto liberado**:

- Manuseio
- Dimensões físicas
- Medidas de peso

Se essas informações não forem especificadas corretamente, uma mensagem será recebida ao gerar o relatório **Capacidade de carga de trabalho**. A partir do relatório, é possível fazer uma busca detalhada para identificar as informações que estão faltando para projetar a carga de trabalho futura.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Associe uma configuração de capacidade de carga de trabalho a um plano mestre

1. Selecione **Gerenciamento de estoque** \> **Periódico** \> **Agendar carga de trabalho**.
2. No campo **Plano mestre**, selecione o plano mestre a ser usado para as projeções de carga de trabalho.
3. No campo **Número de dias**, especifique o número de dias que a projeção de carga de trabalho abrange.
4. No campo **Carga de trabalho**, selecione a configuração de carga de trabalho a ser associada ao plano mestre.

### <a name="view-workload-capacity"></a>Visualização da capacidade de carga de trabalho

1. Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Relatórios de estoque físico** \> **Capacidade de carga de trabalho**.
2. No campo **Número de colunas**, especifique o número de colunas a serem exibidas no relatório.
3. No campo **Tipo da ordem**, selecione **Confirmado e planejado**, **Planejado** ou **Confirmado** para indicar o tipo do projeto no relatório.
4. No campo **Tipo de carga**, selecione um tipo de carga para especificar se a capacidade de carga de trabalho deve ser projetada por volume ou peso.
5. No campo **Capacidade de carga de trabalho**, selecione uma configuração de capacidade de carga de trabalho.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]