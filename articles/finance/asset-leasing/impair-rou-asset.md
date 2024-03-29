---
title: Reduzir ativos de direito de uso ao valor recuperável
description: Este artigo descreve a funcionalidade que registra uma redução ao valor recuperável e ajusta o plano de depreciação de ativo de um arrendamento operacional do Tópico 842 da ASC 842 (Codificação de Padrões Contábeis).
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f953b3a351859c6becba10a129bbb17b49be6290
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894103"
---
# <a name="impair-right-of-use-assets"></a>Reduzir ativos de direito de uso ao valor recuperável

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Se um valor de transporte do ativo de direito de uso (DDU) não for recuperável, talvez seja necessário testar se o ativo teve redução ao valor recuperável. Se você determinar que o ativo teve redução ao valor recuperável, o Arrendamento de ativos poderá registrar a redução ao valor recuperável e ajustar a agenda de depreciação de forma adequada. Este artigo descreve a funcionalidade que registra a redução ao valor recuperável e ajusta o plano de depreciação de ativo de um arrendamento operacional do Tópico 842 da ASC 842 (Codificação de Padrões Contábeis). O mesmo método também se aplica a arrendamentos do Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).

O saldo restante do ativo DDU será amortizado linearmente para o número de períodos restantes, independentemente de o arrendamento ter sido classificado como um arrendamento mercantil sob o IFRS 16 ou um arrendamento operacional sob o ASC 842.

## <a name="impair-an-rou-asset"></a>Reduzir um ativo DDU ao valor recuperável

1. Acesse o arrendamento com redução ao valor recuperável e selecione **Registros**.
2. No Painel de Ação, selecione **Redução ao valor recuperável**.
3. Na caixa de diálogo exibida, no campo **Valor de redução ao valor recuperável**, insira o valor da redução ao valor recuperável do ativo. Para diminuir o ativo DDU, você deve inserir um valor positivo.
4. No campo **Data da transação**, insira a data em que a entrada da redução ao valor recuperável deve ser lançada.
5. No campo **Períodos restantes**, insira o número restante de meses a amortizar.
6. Defina a opção **Visualizar** para exibir a entrada financeira e de ativos fixos proposta antes de sua criação ou lançamento.
7. Defina a opção **Fechar registro** como **Sim** para fechar o registro de arrendamento. Você pode desfazer essa ação usando o status **Reabrir arrendamento**. As entradas não podem ser lançadas em arrendamentos fechados e os arrendamentos fechados não podem ser ajustados. 
8. Selecione **Lançar** para criar ou lançar a entrada de redução ao valor recuperável.

    > [!NOTE]
    > Depois que a transação de redução ao valor recuperável for lançada, uma nova versão do registro será criada.

    > Se o arrendamento for classificado como um arrendamento operacional, a depreciação mensal após a redução ao valor recuperável será calculada usando a depreciação linear.

9. Para exibir a agenda de depreciação do ativo com redução ao valor recuperável, abra a agenda de depreciação de ativo para o registro de arrendamento. O ativo agora será depreciado linearmente sobre o número de meses que você inseriu no campo **Períodos restantes**.
10. Para exibir a entrada do diário de despesas com redução ao valor recuperável, selecione **Diário de arrendamento de ativo** no Painel de Ação do registro de arrendamento com redução ao valor recuperável. O sistema cria uma entrada de diário que gera um débito na conta de lançamento de despesas e credita na conta de lançamento de ativo de arrendamento. 
11. Para exibir o novo valor de transporte do ativo DDU, selecione **Transações de ativo** no Painel de Ação do registro de arrendamento.

## <a name="example-of-rou-asset-impairment"></a>Exemplo de redução ao valor recuperável do ativo DDU

Neste exemplo, o arrendamento é um ativo não especializado que não transfere a propriedade ou concede ao arrendatário a opção de compra.

### <a name="setup"></a>Configurar

As tabelas a seguir mostram os valores definidos nas guias **Geral** e **Linhas da agenda de pagamento** para o arrendamento usado neste exemplo.

**Guia Geral**

| Campo                      | Alíquota            |
|----------------------------|------------------|
| Valor justo do ativo    | 600,000          |
| Taxa incremental de empréstimo | 7%               |
| Intervalo de composição       | Anualmente         |
| Vida útil do ativo (meses) | 600              |
| Tipo de anuidade               | Anuidade comum |
| Data de início          | 01/01/2019       |

**Guia Linhas de agenda de pagamento**

| Campo             | Alíquota      |
|-------------------|------------|
| Data inicial        | 1/1/2019   |
| Intervalo do período   | Mensalmente    |
| Períodos           | 120        |
| Data de término          | 31/12/2028 |
| Frequência de pagamento | Anualmente   |
| Valor do pagamento    | 10,000     |

### <a name="steps"></a>Etapas

1. Depois de criar o arrendamento conforme descrito anteriormente neste artigo, acesse o registro de arrendamento e confirme a agenda de pagamento. Em seguida, lance a entrada do diário de reconhecimento inicial. O ativo DDU inicial e a responsabilidade com arrendamento devem ser US$ 70.235,81. Para este exemplo, o arrendamento foi classificado como um arrendamento operacional sob o ASC 842.
2. Execute o processo de diário de lotes três vezes para simular a passagem de três anos para pagamentos de arrendamento, despesas de juros e despesas de depreciação.
3. Depois de concluir a execução de todos os três trabalhos em lote, volte para o registro de arrendamento e abra as tabelas responsabilidade e transações de ativo para exibir o valor atual de carregamento do ativo DDU e da responsabilidade com arrendamento. Depois de três anos, o valor da obrigação deve ser de aproximadamente US$ -53.893,00 e o valor do ativo deve ser de aproximadamente US$ 53.893,00. 

    Depois de três anos, a empresa faz testes de redução ao valor recuperável e determina que o ativo DDU tem uma redução ao valor recuperável de US$ 35.000. Agora, você deve registrar essa redução ao valor recuperável.
    
4. Acesse o registro de arrendamento e, no Painel de Ação, selecione **Redução ao valor recuperável**.
5. Na página **Parâmetro de redução ao valor recuperável**, insira os detalhes a seguir.

    | Campo                  | Alíquota    |
    |------------------------|----------|
    | Valor de redução ao valor recuperável      | 35,000   |
    | Data da transação       | 1/1/2022 |
    | Períodos restantes      | 84       |
    | Lançar                   | Sim      |
    | Visualizar antes do lançamento | Não       |
    | Fechar registro             | Não       |

6. Uma entrada de diário de despesas de redução ao valor recuperável foi criada e lançada. Para exibi-la, Acesse o diário de arrendamento do ativo no registro de arrendamento. Observe que o valor da redução ao valor recuperável foi debitado da conta de lançamento de despesas de redução ao valor recuperável e a conta de lançamento do ativo DDU foi creditada.

7. Para exibir o efeito líquido da redução ao valor recuperável, acesse as tabelas de transações de ativos e passivos. Observe que a despesa de redução ao valor recuperável diminuiu o ativo DDU, mas o valor de carregamento da responsabilidade com arrendamento não foi alterado.

A redução ao valor recuperável tem um outro efeito que deve ser considerado. Como o valor do ativo DDU agora é muito menor do que a responsabilidade com arrendamento, o valor deverá ser depreciado de maneira diferente da de antes. Especificamente, o ativo agora é depreciado em um modo linear ao longo dos 84 meses restantes do arrendamento, a partir da data da transação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
