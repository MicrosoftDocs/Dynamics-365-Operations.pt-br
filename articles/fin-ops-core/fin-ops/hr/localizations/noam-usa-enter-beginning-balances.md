---
title: Inserir saldos iniciais de folha de pagamento
description: Este artigo descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos.
author: andreabichsel
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d14e7e0772c5b365818d3a8a230abe9f674a077e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850008"
---
# <a name="enter-payroll-beginning-balances"></a>Inserir saldos iniciais de folha de pagamento

[!include [banner](../../includes/banner.md)]

Este artigo descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos. Essas informações são importantes para parceiros que transferem dados de outro sistema para uma nova implementação de folha de pagamento. Para se preparar para inserir saldos iniciais de folha de pagamento, nós verificamos as seguintes informações:

- Os registros de funcionários são inseridos e estão disponíveis no sistema
- Os dados a seguir estão configurados e atribuídos aos funcionários:

    - Ciclos de pagamento e períodos de pagamento
    - Códigos de ganhos
    - Impostos
    - Benefícios e Deduções

- A empresa deve ter escolhido uma data em que os saldos iniciais de folha de pagamento podem ser definidos.
- As informações foram coletadas sobre todos os ganhos, benefícios/deduções, contribuições de benefícios, impostos de funcionários e impostos de empregadores, bem como os seus valores acumulados no ano referente ao sistema herdado.

Na medida em que você planeja inserir os saldos iniciais, considere a forma como os dados precisam ser detalhados. A maioria das empresas insere um valor acumulado único e consolidado. Entretanto caso seja necessário informações mais detalhadas, os saldos podem ser inseridos em incrementos trimestrais. Decidir o nível de detalhes necessário determina quantos demonstrativos manuais de pagamento devem ser criados para cada trabalhador. Para um único valor acumulado, somente um demonstrativo manual é necessário para cada funcionário. Para isso, use os valores acumulados do demonstrativo de pagamento final do sistema anterior como o valor inserido no novo sistema de folha de pagamento.

O exemplo a seguir mostra como você pode inserir os saldos iniciais da folha de pagamento dos funcionários, incluindo códigos de ganhos, benefícios/deduções e impostos. Em um exemplo do mundo real, você teria um item de linha para cada código de ganhos, dedução de benefícios, contribuição para benefícios, imposto de funcionário e imposto de empregador, sendo o valor inserido o valor acumulado no ano. Usando a lista de códigos e valores, siga as etapas para criar um demonstrativo manual de ganhos e pagamentos com contabilidade desabilitada para obter saldos iniciais para fins de folha de pagamento. Você desabilita a contabilidade por não desejar lançar esse demonstrativo de pagamento inicial na contabilidade. Isso foi feito no sistema herdado e virá para o novo sistema quando você definir os saldos iniciais na contabilidade.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Como configurar códigos de ganhos a serem usados nos saldos iniciais de folha de pagamento

Ao inserir os saldos iniciais de folha de pagamento, certifique-se de que os códigos de ganhos que serão utilizados estão configurados com a opção “Permitir edição das taxas do demonstrativo de ganhos" habilitada. Isso permitirá que você digite manualmente o valor do sistema herdado. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Criar demonstrativo de ganhos para que um funcionário tenha um saldo inicial

Esta etapa cria manualmente um demonstrativo de ganhos para cada trabalhador pelo último período de pagamento do sistema herdado, o que cria as linhas de demonstrativo de ganhos no novo sistema de folha de pagamento. Insira uma linha por código de ganhos e o valor e as horas acumulados no ano. As etapas de amostra são as seguintes:

1. Abra a página **Todos os demonstrativos de ganhos** e clique em **Novo**.

    Insira os itens a seguir: 

    | Campo      | Alíquota                 |
    |------------|-----------------------|
    | Trabalhador     | Michael Redmond       |
    | Ciclo de pagamento  | sm                    |
    | Período de pagamento | 16/6/2017 - 30/6/2017 |

2. Na guia **Linha do demonstrativo de ganhos**, insira o seguinte:

    Linha 1: guia **Linha do demonstrativo de ganhos**

    | Campo            | Alíquota       |
    |------------------|-------------|
    | Código de ganhos    | Pagamento regular |
    | Quantidade         | 1.00        |
    | Taxa             | 30,000      |
    | Guia Detalhes da linha |             |
    | Manual           | (marcado)    |

    Linha 2: guia **Linha do demonstrativo de ganhos**

    | Campo            | Alíquota    |
    |------------------|----------|
    | Código de ganhos    | Bônus    |
    | Quantidade         | 1.0000   |
    | Taxa             | 4250.00  |
    | Guia Detalhes da linha |          |
    | Manual           | (marcado) |

    Linha 3: guia **Linha do demonstrativo de ganhos**

    | Campo           | Alíquota      |
    |-----------------|------------|
    | Código de ganhos   | Comissão |
    | Quantidade        | 1.0000     |
    | Taxa            | !,299,00   |
    | Taxa            | 1.299,00   |
    | Guia Detalhe da linha |            |
    | Manual          | (Marcado)   |

    > [!NOTE]
    > A configuração do controle deslizante **Manual** como **Sim** na guia **Detalhes da Linha** para cada linha de declaração de ganhos é fundamental para a inserção dos saldos iniciais de folha de pagamento para cada trabalhador.

3. No painel **Ação**, clique em **Liberar demonstrativo de ganhos** USA-FED-ER-FICA.
4. No painel **Ação**, clique em **Demonstrativo de pagamento** para abrir a página **Gerar demonstrativos de pagamento** e definir o seguinte:

    | Campo              | Alíquota     |
    |--------------------|-----------|
    | Data de pagamento       | 30/6/2017 |
    | Tipo de execução de pagamento   | Manual    |
    | Desabilitar contabilidade |   Sim     |

    > [!NOTE] 
    > Isso só está disponível quando o tipo de execução de pagamento é manual e o usuário deseja desabilitar a contabilidade na execução de pagamento

    Clique em **OK** e feche o **Log de Informações**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>Por que o controle deslizante Desabilitar Contabilidade precisa estar definido como Sim durante a geração de demonstrativos de pagamento?

A configuração do controle deslizante como **Sim** impede que as linhas do demonstrativo de pagamento sejam distribuídas na Contabilidade. Os valores da contabilidade eram atualizados antes da inserção dos saldos de conta do sistema herdado. A inserção dos saldos iniciais na Folha de pagamento permite gerar relatórios que incluem informações de anos anteriores, bem como para identificar limites para fins de benefício e de imposto.

### <a name="c-create-pay-statements-for-employees"></a>C. Gerar demonstrativos de pagamento para funcionários

Depois de gerar demonstrativos de pagamento com saldos iniciais, você deve verificar se os demonstrativos de pagamento refletem com precisão os dados da folha de pagamento. Você também deve atualizar manualmente as informações de benefícios e impostos para correspondam aos valores no sistema de folha de pagamento anterior. Depois de verificar que os valores do sistema de folha de pagamento anterior correspondem aos valores dos demonstrativos de pagamento atuais, você deve finalizar os demonstrativos de pagamento.

1. Abra a página **Todos os demonstrativos de pagamento**.
2. Destaque o último demonstrativo de pagamento gerado para Michael Redmond
3. Clique em **Editar** para abrir a página **Demonstrativo de pagamento**.
4. Abra a guia **Deduções de benefício** e insira o seguinte:

    | Campo             | Alíquota            |
    |-------------------|------------------|
    | Benefício           | Valor da dedução |
    | 401K              | Participar      |
    | Plano odontológico            | SubSp            |
    | Despesas com o dependente | Participar      |
    | Visão            | SupSp            |

5. Na guia **Contribuições para benefícios**, insira o seguinte:

    | Campo   | Alíquota               |
    |---------|---------------------|
    | Benefício | Valor de contribuição |
    | 401K    | Participar         |
    | Plano odontológico  | SubSp               |
    | Visão  | SubSp               |

6. Na guia **Deduções de imposto**, insira o seguinte:

    | Campo           | Alíquota            |
    |-----------------|------------------|
    | Código do Imposto        | Valor da dedução |
    | USA-FED-ER-FICA | 1600.00          |
    | USA-FED-ER-MEDI | 825.75           |

7. Na guia **Contribuições de imposto**, insira o seguinte:
8. Clique em **Calcular**.

    > [!IMPORTANT] 
    > Valide os totais do demonstrativo de pagamento ao trabalhador correspondentes ao acumulado do sistema herdado. Você pode querer adiar a finalização na próxima etapa para fazer uma validação geral de todos os demonstrativos de pagamento acumulados. Após a validação, reexamine todos os demonstrativos de pagamento e faça a finalização.

O mesmo processo pode ser feito em incrementos trimestrais, se necessário, para os trimestres anteriores de cada ano. Isso só é necessário se o cliente precisar conferir os dados por trimestre sem retornar ao sistema herdado.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Se você cometer um erro ao inserir saldos iniciais para um funcionário

É possível reverter e inserir novamente as transações. Para reverter a transação, tudo o que deve fazer é concluir as etapas a seguir na página **Todos os demonstrativos de pagamento**.

1. Clique em **Reverter**.
2. Clique em **Sim** quando a mensagem “Quando você reverte este demonstrativo de pagamento, uma reversão de demonstrativo de pagamento é criada para compensar este demonstrativo de pagamento. Não é possível editar os demonstrativos de pagamento. Deseja reverter este demonstrativo de pagamento?” for exibida. 

Depois de reverter o demonstrativo de pagamento, você poderá gerar um novo demonstrativo de pagamento para o trabalhador a partir da declaração de ganhos criada anteriormente. Corrija qualquer linha incorreta na declaração de ganhos antes de gerar o novo demonstrativo de pagamento e então gere novos demonstrativos de pagamento com os valores corretos. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]