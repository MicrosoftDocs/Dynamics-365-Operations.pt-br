---
title: Proposta de rescisão do arrendamento
description: Este tópico explica como propor a rescisão de um arrendamento.
author: moaamer
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseTerminateLeaseListPage
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2f6990177251418bece8c99a0f9befa333d6549f
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720492"
---
# <a name="propose-a-lease-for-termination"></a>Propor a rescisão de um arrendamento

[!include [banner](../includes/banner.md)]

Se um arrendamento for encerrado antecipadamente, o arrendamento de ativos poderá registrar uma entrada de diário de finalização para dar baixa na responsabilidade com arrendamento, do ativo de direito de uso (DDU) e da depreciação acumulada, bem como registrar um ganho ou perda. O processo de rescisão antecipada encerra um arrendamento e os registros de arrendamento associados. Ele não encerra os registros de arrendamento individuais. Este tópico descreve a funcionalidade que permite propor a rescisão de um arrendamento e processar a entrada do diário de rescisão de arrendamento.

Se um arrendamento não for classificado como arrendamento de tratamento de arrendamento diferido e não for associado a um ativo fixo, a concessão de ativo produzirá a seguinte entrada de diário de rescisão.

| Lançamento                           | Débito (Dr.) | Crédito (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Responsabilidade com arrendamento                   | X           |              |
| Dr. Depreciação acumulada          | X           |              |
| Dr. Ganho (perda) na modificação de arrendamento | X           |              |
| Cr. Ativo de arrendamento                       |             | X            |
| Cr. Ganho (perda) na modificação de arrendamento |             | X            |

Se o registro de arrendamento for classificado como um registro de arrendamento diferido, a entrada gravará o saldo do arrendamento diferido antes da rescisão na conta de ganhos ou perdas, conforme mostrado aqui.

| Transação                           | Débito (Dr.) | Crédito (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Arrendamento diferido                     | X           |              |
| Cr. Ganho (perda) na modificação de arrendamento |             | X            |
| Cr. Arrendamento diferido                     |             | X            |
| Dr. Ganho (perda) na modificação de arrendamento | X           |              |

Se o registro de arrendamento estiver conectado a um ativo fixo, o ativo DDU será contabilizado nos ativos fixos. Essa contabilidade inclui a contabilidade para encerramentos antecipados. O arrendamento de ativos gera a seguinte entrada de diário para dar baixa na responsabilidade com arrendamento.

| Transação                           | Débito (Dr.) | Crédito (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Responsabilidade com arrendamento                   | X           |              |
| Cr. Ganho (perda) na modificação de arrendamento |             | X            |

Para obter informações sobre a forma correta de descartar um ativo DDU, consulte [Descartar um ativo fixo como sucata](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Propor a rescisão de um arrendamento

1. Acesse o arrendamento que deve ser encerrado e, no Painel de Ações, selecione **Proposta de rescisão**.

    > [!NOTE]
    > O botão **Proposta de rescisão** não estará disponível se houver entradas de diário não lançadas em um registro. Antes de rescindir o arrendamento, você deve lançar ou excluir todas as entradas de diário que foram criadas no arrendamento.

2. Na caixa de diálogo exibida, defina os campos **Data de efetivação** e **Data de lançamento** para a entrada do diário de rescisão.
3. Selecione **Proposta de rescisão** para propor a rescisão de um arrendamento.
4. Selecione **Lançar rescisão de arrendamento** para lançar automaticamente a entrada do diário de rescisão de arrendamento.
5. Na página **Rescisões de arrendamento**, selecione a ID do arrendamento proposto para rescisão para exibir as linhas de rescisão. As linhas de rescisão mostram os valores de transporte do ativo DDU, responsabilidade da rescisão, depreciação acumulada, arrendamento diferido (se aplicável) e ganhos ou perdas que devem ser reconhecidos na rescisão do arrendamento.

O arrendamento está pronto para ser rescindido. O valor do campo **Status de rescisão** para o registro de arrendamento é alterado para **Pronto para rescisão**. Neste ponto, não é mais possível lançar entradas de diário em relação ao arrendamento, nem ajustá-las ou reduzi-las. 

## <a name="process-leases-that-are-ready-for-termination"></a>Processar arrendamentos prontos para rescisão

Para processar arrendamentos prontos para rescisão e lançar a entrada do diário de rescisão, siga estas etapas.

1. Na página **Rescisões do arrendamento**, selecione o arrendamento a ser processado e selecione **Rescindir**.
2. Na caixa de diálogo exibida, selecione **OK**.

O sistema lança a entrada do diário de rescisão. O campo **Status da arrendamento** para o registro de arrendamento é definido como **Rescindido** e o campo **Status da proposta de rescisão** é definido como **Concluído**.

## <a name="reverse-a-lease-termination"></a>Reverter uma rescisão do arrendamento

Para reverter uma entrada de diário de rescisão do arrendamento e abrir um arrendamento rescindido, siga esta etapa.

- Na página **Rescisões do arrendamento**, selecione o arrendamento rescindido a ser revertido e selecione **Reverter rescisão**.

O sistema reverte a entrada do diário de rescisão. O campo **Status da arrendamento** para o registro de arrendamento é definido como **Aberto**. O arrendamento não aparecerá mais na página **Rescisões de arrendamento** e sua rescisão poderá ser proposta novamente.

## <a name="example-of-a-lease-termination"></a>Exemplo de uma rescisão de arrendamento

Neste exemplo, o arrendamento é associado a um ativo não especializado e ele não transfere a propriedade do ativo, nem concede ao arrendatário a opção de comprar o ativo.

### <a name="setup"></a>Configurar

As tabelas a seguir mostram os valores definidos nas guias **Geral** e **Linhas da agenda de pagamento** para o arrendamento usado neste exemplo.

**Guia Geral**

| Campo                      | Alíquota            |
|----------------------------|------------------|
| Valor justo do ativo    | 600,000          |
| Moeda                   | USD              |
| Custos diretos iniciais       | 1.000            |
| Taxa incremental de empréstimo | 7%               |
| Intervalo de composição       | Anualmente         |
| Vida útil do ativo (meses) | 600              |
| Tipo de anuidade               | Anuidade comum |
| Data de início          | 1/1/2019         |

**Guia Linhas de agenda de pagamento**

| Campo             | Valor      |
|-------------------|------------|
| Data inicial        | 1/1/2019   |
| Intervalo do período   | Mensalmente    |
| Períodos           | 120        |
| Data de término          | 31/12/2028 |
| Frequência de pagamento | Anualmente   |
| Valor do pagamento    | 10.000     |

### <a name="steps-for-terminating-the-lease"></a>Etapas para rescindir o arrendamento

1. Depois de criar o arrendamento conforme descrito anteriormente neste tópico, Acesse o registro de arrendamento e confirme a agenda de pagamento. Em seguida, lance a entrada do diário de reconhecimento inicial. O ativo DDU inicial é de US$ 71.235,81 e a responsabilidade com arrendamento deve ser de US$ 70.235,81. Para este exemplo, o arrendamento foi classificado como um arrendamento operacional sob o ASC 842 (Tópico 842 da Codificação de Padrões Contábeis).
2. Execute o processo de diário de lotes três vezes para simular a passagem de três anos para pagamentos de arrendamento, despesas de juros e despesas de depreciação.
3. Ao concluir a execução de todos os três trabalhos em lote, volte para o registro de arrendamento e abra as tabelas de transações Responsabilidade e Ativo para exibir o valor atual de carregamento do ativo DDU e a responsabilidade com arrendamento. Depois de três anos, o valor da obrigação deve ser de aproximadamente US$ -53.893,00 e o valor do ativo deve ser de aproximadamente US$ 54.593,00.

    Passados os três anos, a empresa e o arrendador acordam mutuamente em rescindir o arrendamento. Portanto, o arrendamento deve ser rescindido agora.

4. Acesse o arrendamento que deve ser encerrado e, no Painel de Ações, selecione **Proposta de rescisão**. 
5. Na caixa de diálogo exibida, no campo **Data de efetivação** e **Data de lançamento**, insira **1/1/2021**.
6. Selecione **Proposta de rescisão** para propor a rescisão de um arrendamento.

    A página **Rescisões de arrendamento** é exibida e mostra o arrendamento que será rescindido.

7. Para exibir as linhas de arrendamento, selecione a ID do arrendamento proposto para rescisão. As linhas de rescisão mostram os valores de transporte do arrendamento. A tabela a seguir mostra como esses valores devem ser para este exemplo. 

    | Campo                                                 | Valor      |
    |-------------------------------------------------------|------------|
    | Saldo de transporte de passivo na moeda da transação | US$ 53.892,89 |
    | Ativo de direito de uso na moeda da transação            | US$ 71.235,81 |
    | Depreciação acumulada na moeda da transação      | US$ 16.642,92 |
    | Ganho (perda) na moeda da transação                   | US$ -700,00   |

8. Para lançar a entrada de diário de rescisão, selecione o arrendamento na página **Rescisões do arrendamento** e selecione **Rescindir**.
9. Na caixa de diálogo exibida, selecione **OK**.
10. Para exibir a entrada do diário de rescisão que foi criada e lançada, acesse o diário de arrendamento do ativo no registro de arrendamento. A tabela a seguir mostra como essa entrada deve ser para este exemplo.

    | Transação                           | Débito (Dr.) | Crédito (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. Responsabilidade com arrendamento                   | 53.892,89   |              |
    | Dr. Depreciação acumulada          | 16.642,92   |              |
    | Dr. Ganho (perda) na modificação de arrendamento | 700,00      |              |
    | Cr. Ativo de arrendamento                       |             | 71.235,81    |

11. Para exibir o efeito líquido da rescisão, em que o ativo DDU e a responsabilidade com arrendamento será 0 (zero), abra as tabelas de transações de ativos e passivos.

O status da arrendamento deve ser **Rescindido**. Nenhuma entrada de diário adicional será lançada nesse arrendamento, a menos que a rescisão seja revertida.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
