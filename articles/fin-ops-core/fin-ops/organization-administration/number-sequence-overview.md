---
title: Visão geral de sequências numéricas
description: As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores.
author: MargoC
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4de5cc79b5c1e38e10bb6a382b279459a64a03c7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559375"
---
# <a name="number-sequences-overview"></a>Visão geral de sequências numéricas

[!include [banner](../includes/banner.md)]

As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores. Um registro de dados mestres ou um registro de transação que exige um identificador é conhecido como *referência*.

Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência. É recomendável usar as páginas em **Administração da organização** para configurar sequências numéricas. Se as configurações específicas do módulo forem necessárias, você poderá usar a página de parâmetros em um módulo para especificar as sequências numéricas para as referências no módulo. Por exemplo, em **Contas a receber** e em **Contas a pagar**, você pode configurar grupos de sequências numéricas para alocar sequências numéricas específicas para clientes e fornecedores específicos.

Ao configurar uma sequência numérica, você deve especificar um escopo, que define que organização usará a sequência numérica. O escopo pode ser **Compartilhado**, **Empresa**, **Entidade legal** ou **Unidade operacional**. Os escopos **Entidade legal** e **Empresa** também podem ser combinados com **Período de calendário fiscal** para criar sequências numéricas ainda mais específicas.

Os formatos de sequências numéricas são compostos de segmentos. As sequências numéricas com um escopo diferente de **Compartilhado** podem conter os segmentos que correspondem ao escopo. Por exemplo, uma sequência numérica com um escopo **Entidade legal** pode conter um segmento da entidade legal. Ao incluir um segmento de escopo no formato de sequência numérica, você pode identificar o escopo de um registro específico examinando seu número.

Além dos segmentos que correspondem a escopos, os formatos de sequências numéricas podem conter os segmentos **Constante** e **Alfanumérico**. Um segmento **Constante** contém um conjunto de letras, de números ou de símbolos que não muda. Um segmento **Alfanumérico** contém um conjunto de letras ou de números incrementado sempre que um número é usado. Use um sinal numérico (\#) para representar o incremento de números e um e comercial (&) para representar o incremento de letras. Por exemplo, o formato \#\#\#\#\#\_2017 cria a sequência 00001\_2017, 00002\_2017, e assim por diante.

## <a name="number-sequence-examples"></a>Exemplos de sequências numéricas

Os exemplos a seguir mostram como usar segmentos para criar formatos da sequência numérica. Particularmente, os exemplos demonstram os efeitos de usar segmentos de escopo.

### <a name="expense-report-numbers"></a>Números do relatório de despesas

No exemplo a seguir, os números de relatório de despesas são configurados para a entidade legal chamada **CS**.

- **Área:** Viagem e despesas
- **Referência:** Número do relatório de despesas
- **Escopo:** Entidade legal
- **Entidade legal:** CS

| Segmentos  | Tipo de segmento | Valor     |
|-----------|--------------|-----------|
| Segmento 1 | Pessoa jurídica em geral | CS        |
| Segmento 2 | Constante     | -DESPESA- |
| Segmento 3 | Alfanumérico | \#\#\#\#  |

**Exemplo de número formatado**: CS-DESPESA-0039

Você pode configurar um formato semelhante de sequência numérica para outras entidades legais. Por exemplo, para uma entidade legal denominada **RW**, se você alterar somente o valor do segmento da entidade legal, o número formatado será RW-DESPESA-0039. Você também pode alterar o formato de sequência numérica inteira para outras entidades legais. Por exemplo, você pode omitir o segmento de escopo da entidade legal para criar um número formatado como Exp-0001.

### <a name="sales-order-numbers"></a>Números da ordem de venda

No exemplo a seguir, os números da ordem de venda são configurados para a ID da empresa **CEU**.

- **Área:** Vendas
- **Referência:** Ordem de venda
- **Escopo:** Empresa
- **Empresa:** CEU

| Segmentos  | Tipo de segmento | Alíquota    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | OV-      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Exemplo de número formatado**: SO-0029

Mesmo que um segmento de escopo não seja incluído no formato, a numeração é reiniciada para cada ID da empresa Se você usar o mesmo formato para todas as IDs da empresa, os mesmos números serão usados em cada empresa. Por exemplo, o número da ordem de venda SO-0029 é usado em cada empresa. Você também pode alterar o formato de sequência numérica inteira para outras IDs da empresa.

### <a name="purchase-requisition-numbers"></a>Números de requisição de compra

No exemplo a seguir, os números de requisição de compra destinam-se à organização inteira.

- **Área:** Compra
- **Referência:** Requisição de compra
- **Escopo:** Compartilhado

| Segmentos  | Tipo de segmento | Alíquota    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | Solic.      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Exemplo de número formatado**: Req0052

Como o escopo é **Compartilhado**, o formato da sequência numérica é usado na organização inteira. Não é possível configurar formatos de sequência numérica para diferentes partes da organização.

## <a name="performance-considerations-for-number-sequences"></a>Considerações de desempenho para sequências numéricas

Considere as seguintes informações sobre como a configuração de sequências numéricas pode afetar o desempenho do sistema antes da configuração de sequências numéricas.

### <a name="continuous-and-non-continuous-number-sequences"></a>Sequências numéricas contínuas e não contínuas

As sequências numéricas podem ser contínuas ou não contínuas. Uma sequência numérica contínua não ignora nenhum número, mas os números podem não ser usados sequencialmente. Os números de uma sequência numérica não contínua são usados sequencialmente, mas a sequência numérica pode ignorar números. Por exemplo, se um usuário cancela uma transação, um número é gerado, mas não usado. Em uma sequência numérica contínua, esse número é reciclado posteriormente. Em uma sequência numérica não contínua, o número não é usado.

As sequências numéricas contínuas normalmente são necessárias em documentos externos, como ordens de compra, ordens de venda e faturas. Entretanto, as sequências numéricas contínuas podem ter um impacto negativo no tempo de resposta do sistema porque o sistema deve solicitar um número do banco de dados sempre que um novo documento ou um registro for criado.

Se você usar uma sequência numérica não contínua, poderá habilitar **Pré-alocação** na Guia Rápida **Desempenho** da página **Sequências numéricas**. Quando você especifica uma quantidade de números a serem pré-alocados, o sistema seleciona esses números e os armazena na memória. Os novos números serão solicitados do banco de dados somente depois que a quantidade pré-alocada tiver sido usada.

A menos que haja um requisito de regulamentação para usar sequências numéricas contínuas, é recomendável usar sequências numéricas não contínuas para obter um desempenho melhor.

### <a name="automatic-cleanup-of-number-sequences"></a>Limpeza automática das sequências numéricas

No caso de uma falha de energia, de um erro de aplicativo ou de outra falha inesperada, o sistema não pode reciclar números automaticamente para sequências numéricas contínuas. Você pode executar o processo de limpeza de forma manual ou automática para recuperar os números perdidos.

Considere cuidadosamente o uso do servidor ao planejar o processo de limpeza. Recomendamos que você execute a limpeza como um trabalho em lotes fora do horário de pico.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]