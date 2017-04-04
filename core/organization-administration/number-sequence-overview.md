---
title: "Visão geral da sequência numérica"
description: "As sequências numéricas no Microsoft Dynamics 365 para operações são usadas para produzir os identificadores legíveis, exclusiva para registros de dados mestre e os registros de transação que necessitem identificadores. Um registro de dados mestres ou um registro de transação que exige um identificador é conhecido como <em>referência</em>."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: a812c93a13fd36f44e659c9976099af62793098f
ms.lasthandoff: 03/31/2017


---

# <a name="number-sequence-overview"></a>Visão geral da sequência numérica

As sequências numéricas no Microsoft Dynamics 365 para operações são usadas para produzir os identificadores legíveis, exclusiva para registros de dados mestre e os registros de transação que necessitem identificadores. Um registro de dados mestres ou um registro de transação que exige um identificador é conhecido como <em>referência</em>.

Antes de criar novos recordes de referência no Microsoft Dynamics 365 para as operações, você deve configurar uma sequência numérica e associar-la com a referência. É recomendável usar as páginas em **Administração da organização** para configurar sequências numéricas. Se as configurações específicas do módulo forem necessárias, você poderá usar a página de parâmetros em um módulo para especificar as sequências numéricas para as referências no módulo. Por exemplo, em **Contas a receber** e em **Contas a pagar**, você pode configurar grupos de sequências numéricas para alocar sequências numéricas específicas para clientes e fornecedores específicos. Ao configurar uma sequência numérica, você deve especificar um escopo, que define que organização usará a sequência numérica. O escopo pode ser **Compartilhado**, **Empresa**, **Entidade legal** ou **Unidade operacional**. Os escopos **Entidade legal** e **Empresa** também podem ser combinados com **Período de calendário fiscal** para criar sequências numéricas ainda mais específicas. Os formatos de sequências numéricas são compostos de segmentos. As sequências numéricas com um escopo diferente de **Compartilhado** podem conter os segmentos que correspondem ao escopo. Por exemplo, uma sequência numérica com um escopo **Entidade legal** pode conter um segmento da entidade legal. Ao incluir um segmento de escopo no formato de sequência numérica, você pode identificar o escopo de um registro específico examinando seu número. Além dos segmentos que correspondem a escopos, os formatos de sequências numéricas podem conter os segmentos **Constante** e **Alfanumérico**. Um segmento **Constante** contém um conjunto de letras, de números ou de símbolos que não muda. Um segmento **Alfanumérico** contém um conjunto de letras ou de números incrementado sempre que um número é usado. Use um símbolo de cerquilha (\#) representar incrementar números e um E comercial (&) para representar incrementar letras. Por exemplo, o formato \#\#\#\#\#\_2017 criará a sequência 00001\_2017, 00002\_2017, etc.
Exemplos de sequências numéricas
------------------------

Os exemplos a seguir mostram como usar segmentos para criar formatos da sequência numérica. Particularmente, os exemplos demonstram os efeitos de usar segmentos de escopo.
### <a name="expense-report-numbers"></a>Números do relatório de despesas

No exemplo a seguir, os números de relatório de despesas são configurados para a entidade legal chamada **CS**. **Área: **Viagem e despesas **Referência: **Número do relatório de despesas **Escopo: **Entidade legal **Entidade legal: **CS
| Segmentos  | Tipo de segmento | Valor     |
|-----------|--------------|-----------|
| Segmento 1 | Pessoa jurídica em geral | CS        |
| Segmento 2 | Constante     | -DESPESA- |
| Segmento 3 | Alfanumérico | \#\#\#\#  |

**Exemplo de número formatado**: CS-EXPENSE-0039 Você pode configurar um formato de sequência numérica semelhante para outras entidades legais. Por exemplo, para uma entidade legal denominada **RW**, se você alterar somente o valor do segmento da entidade legal, o número formatado será RW-DESPESA-0039. Você também pode alterar o formato de sequência numérica inteira para outras entidades legais. Por exemplo, você pode omitir o segmento de escopo da entidade legal para criar um número formatado como Exp-0001.

### <a name="sales-order-numbers"></a>Números da ordem de venda

No exemplo a seguir, os números da ordem de venda são configurados para a ID da empresa **CEU**. **Área: **Vendas **Referência: **Ordem de venda **Escopo: **Empresa **Empresa: **CEU
| Segmentos  | Tipo de segmento | Alíquota    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | OV-      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Exemplo de número formatado**: SO-0029 Mesmo que um segmento de escopo não seja incluído no formato, a numeração será reiniciada para cada ID da empresa. Se você usar o mesmo formato para todas as IDs da empresa, os mesmos números serão usados em cada empresa. Por exemplo, o número da ordem de venda SO-0029 é usado em cada empresa. Você também pode alterar o formato de sequência numérica inteira para outras IDs da empresa.

### <a name="purchase-requisition-numbers"></a>Números de requisição de compra

No exemplo a seguir, os números de requisição de compra destinam-se à organização inteira. **Área: **Compra **Referência: **Requisição de compra **Escopo: **Compartilhado
| Segmentos  | Tipo de segmento | Alíquota    |
|-----------|--------------|----------|
| Segmento 1 | Constante     | Solic.      |
| Segmento 2 | Alfanumérico | \#\#\#\# |

**Exemplo de número formatado**: Req0052 Como o escopo é **Compartilhado**, o formato da sequência numérica é usado pela organização. Não é possível configurar formatos de sequência numérica para diferentes partes da organização. Considerações de desempenho para sequências numéricas
-----------------------------------------------

Considere as seguintes informações sobre como a configuração de sequências numéricas pode afetar o desempenho do sistema antes da configuração de sequências numéricas.
### <a name="continuous-and-non-continuous-number-sequences"></a>Sequências numéricas contínuas e não contínuas

As sequências numéricas podem ser contínuas ou não contínuas. Uma sequência numérica contínua não ignora nenhum número, mas os números podem não ser usados sequencialmente. Os números de uma sequência numérica não contínua são usados sequencialmente, mas a sequência numérica pode ignorar números. Por exemplo, se um usuário cancela uma transação, um número é gerado, mas não usado. Em uma sequência numérica contínua, esse número é reciclado posteriormente. Em uma sequência numérica não contínua, o número não é usado. As sequências numéricas contínuas normalmente são necessárias em documentos externos, como ordens de compra, ordens de venda e faturas. Entretanto, as sequências numéricas contínuas podem ter um impacto negativo no tempo de resposta do sistema porque o sistema deve solicitar um número do banco de dados sempre que um novo documento ou um registro for criado. Se você usar uma sequência numérica não contínua, poderá habilitar **Pré-alocação** na Guia Rápida **Desempenho** da página **Sequências numéricas**. Quando você especifica uma quantidade de números a serem pré-alocados, o sistema seleciona esses números e os armazena na memória. Os novos números serão solicitados do banco de dados somente depois que a quantidade pré-alocada tiver sido usada. A menos que haja um requisito de regulamentação para usar sequências numéricas contínuas, é recomendável usar sequências numéricas não contínuas para obter um desempenho melhor.

### <a name="automatic-cleanup-of-number-sequences"></a>Limpeza automática das sequências numéricas

No caso de uma falha de energia, de um erro de aplicativo ou de outra falha inesperada, o sistema não pode reciclar números automaticamente para sequências numéricas contínuas. Você pode executar o processo de limpeza de forma manual ou automática para recuperar os números perdidos. Considere cuidadosamente o uso do servidor ao planejar o processo de limpeza. Recomendamos que você execute a limpeza como um trabalho em lotes fora do horário de pico.




