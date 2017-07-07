---
title: Inserir saldos iniciais de folha de pagamento
description: "Este tópico descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos. Essas informações são importantes para que os Parceiros migrem ou transfiram dados de outro sistema para uma nova implementação de folha de pagamento."
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 911a51e2498800e7ee7b1562b66c56967eef0505
ms.openlocfilehash: e6213d2e01445b78c6d8f98fc6a55f7c551231b5
ms.contentlocale: pt-br
ms.lasthandoff: 06/19/2017


---

# <a name="enter-payroll-beginning-balances"></a>Inserir saldos iniciais de folha de pagamento

[!include[banner](../../includes/banner.md)]]

Este tópico descreve as etapas para inserir saldos iniciais para códigos de ganhos, deduções, benefícios e impostos. Essas informações são importantes para parceiros que transferem dados de outro sistema para uma nova implementação de folha de pagamento. Para se preparar para inserir saldos iniciais de folha de pagamento, nós verificamos as seguintes informações:

> * Os registros de funcionários são inseridos e estão disponíveis no sistema
> * Os dados a seguir estão configurados e atribuídos aos funcionários:

> > * Ciclos de pagamento e períodos de pagamento
> > * Códigos de ganhos
> > * Impostos
> > * Benefícios e Deduções

> * A empresa deve ter escolhido uma data em que os saldos iniciais de folha de pagamento podem ser definidos.

> * As informações foram coletadas sobre todos os ganhos, benefícios/deduções, contribuições de benefícios, impostos de funcionários e impostos de empregadores, bem como os seus valores acumulados no ano referente ao sistema herdado.

Na medida em que você planeja inserir os saldos iniciais, considere a forma como os dados precisam ser detalhados. A maioria das empresas insere um valor acumulado único e consolidado. Entretanto caso seja necessário informações mais detalhadas, os saldos podem ser inseridos em incrementos trimestrais. Decidir o nível de detalhes necessário determina quantos demonstrativos manuais de pagamento devem ser criados para cada trabalhador. Para um único valor acumulado, somente um demonstrativo manual é necessário para cada funcionário. Para isso, use os valores acumulados do demonstrativo de pagamento final do sistema anterior como o valor inserido no novo sistema de folha de pagamento.

O exemplo a seguir mostra como você pode inserir os saldos iniciais da folha de pagamento dos funcionários, incluindo códigos de ganhos, benefícios/deduções e impostos. Em um exemplo do mundo real, você teria um item de linha para cada código de ganhos, dedução de benefícios, contribuição para benefícios, imposto de funcionário e imposto de empregador, sendo o valor inserido o valor acumulado no ano. Usando a lista de códigos e valores, siga as etapas para criar um demonstrativo manual de ganhos e pagamentos com contabilidade desabilitada para obter saldos iniciais para fins de folha de pagamento.  Você desabilita a contabilidade por não desejar lançar esse demonstrativo de pagamento inicial na contabilidade. Isso foi feito no sistema herdado e virá para o novo sistema quando você definir os saldos iniciais na contabilidade.

> [!NOTE] 
> Se desejar reproduzir as mesmas etapas a seguir, você pode usar os Dados de demonstração. Os dados de demonstração podem ser baixados do PartnerSource

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
| Taxa             | 30.000      |
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
> Marcar a configuração da caixa de seleção na guia **Detalhes da linha** para cada linha de demonstrativo de ganhos é a chave para ter saldos iniciais de folha de pagamento inseridos para cada trabalhador.

3. No painel **Ação**, clique em **Liberar demonstrativo de ganhos** USA-FED-ER-FICA.

4. No painel **Ação**, clique em **Demonstrativo de pagamento** para abrir a página **Gerar demonstrativos de pagamento** e definir o seguinte:

| Campo              | Alíquota     |
|--------------------|-----------|
| Data de pagamento       | 30/6/2017 |
| Tipo de execução de pagamento   | Manual    |
| Desabilitar contabilidade | (marcado)  |

> [!NOTE] 
> Isso só está disponível quando o tipo de execução de pagamento é manual e o usuário deseja desabilitar a contabilidade na execução de pagamento

Clique em **OK** e feche o **Log de Informações**.

#### <a name="why-disable-accounting-checkbox-needs-to-be-turned-on-when-generating-pay-statements"></a>Por que a caixa de seleção Desabilitar contabilidade precisa ser ativada ao gerar demonstrativos de pagamento?
Isso impede que qualquer linha do demonstrativo de pagamento seja distribuída e lançada na Contabilidade. Você não deseja lançar esse demonstrativo de pagamento inicial sendo que os valores estão na contabilidade do sistema herdado. Esse carregamento de saldos é usado somente para fins de relatório e limitação.

### <a name="c-create-pay-statements-for-employees"></a>C. Gerar demonstrativos de pagamento para funcionários
Depois de gerar demonstrativos de pagamento com saldos iniciais, você deve verificar se os demonstrativos de pagamento refletem com precisão os dados da folha de pagamento. Você também deve atualizar manualmente as informações de benefícios e impostos para correspondam aos valores no sistema de folha de pagamento anterior. Depois de verificar que os valores do sistema de folha de pagamento anterior correspondem aos valores dos demonstrativos de pagamento atuais, você deve finalizar os demonstrativos de pagamento.

1. Abra a página **Todos os demonstrativos de pagamento**.

2. Destaque o último demonstrativo de pagamento gerado para Michael Redmond

3. Clique em **Editar** para abrir a página **Demonstrativo de pagamento**.

4. Abra a guia **Deduções de benefício** e insira o seguinte:

| Campo                           | Alíquota            |
|---------------------------------|------------------|
| Benefício                         | Valor da dedução |
| 401K | Participar              | 3000.00          |
| Plano odontológico | SubSp                  | 495,00           |
| Despesas com o dependente | Participar | 2500.00          |
| Visão | SupSp                  | 500,00           |

5. Na guia **Deduções de benefício**, insira o seguinte: 

| Campo                           | Alíquota            |
|---------------------------------|------------------|
| Benefício                         | Valor da dedução |
| 401K | Participar              | 3000.00          |
| Plano odontológico | SubSp                  | 495,00           |
| Despesas com dependente | Participar | 2500.00          |
| Visão | SupSp                  | 500,00           |

6. Na guia **Contribuições para benefícios**, insira o seguinte:

| Campo              | Alíquota               |
|--------------------|---------------------|
| Benefício            | Valor de contribuição |
| 401K | Participar | 3000,00             |
| Plano odontológico | SubSp     | 495,00              |
| Visão | SubSp     | 500,00              |

7. Na guia **Deduções de imposto**, insira o seguinte:

| Campo           | Alíquota            |
|-----------------|------------------|
| Código do Imposto        | Valor da dedução |
| USA-FED-ER-FICA | 1600.00          |
| USA-FED-ER-MEDI | 825.75           |

8. Na guia **Contribuições de imposto**, insira o seguinte:

9. Clique em **Calcular**.
> [!IMPORTANT] 
> Valide os totais do demonstrativo de pagamento ao trabalhador correspondentes ao acumulado do sistema herdado. Você pode querer adiar a finalização na próxima etapa para fazer uma validação geral de todos os demonstrativos de pagamento acumulados. Após a validação, reexamine todos os demonstrativos de pagamento e faça a finalização.

O mesmo processo pode ser feito em incrementos trimestrais, se necessário, para os trimestres anteriores de cada ano. Isso só é necessário se o cliente precisar conferir os dados por trimestre sem retornar ao sistema herdado.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Se você cometer um erro ao inserir saldos iniciais para um funcionário
É possível reverter e inserir novamente as transações. Para reverter a transação, tudo o que deve fazer é concluir as etapas a seguir na página **Todos os demonstrativos de pagamento**.

1. Clique em **Reverter**.

2. Clique em **Sim** quando a mensagem “Quando você reverte este demonstrativo de pagamento, uma reversão de demonstrativo de pagamento é criada para compensar este demonstrativo de pagamento. Não é possível editar os demonstrativos de pagamento. Deseja reverter este demonstrativo de pagamento?” for exibida. 

Depois de reverter o demonstrativo de pagamento, você pode gerar um novo demonstrativo de pagamento para o trabalhador por meio do demonstrativo de ganhos que você criou anteriormente neste tópico, no procedimento "Gerar demonstrativo de ganhos e demonstrativos de pagamento com saldos iniciais". Certifique-se de corrigir todas as linhas incorretas do demonstrativo de ganhos antes de gerar o novo demonstrativo de pagamento e, em seguida, repita o procedimento "Atualizar demonstrativos de pagamento com saldo inicial referente a benefícios e impostos", neste tópico.

