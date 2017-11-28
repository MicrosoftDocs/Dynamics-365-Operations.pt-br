---
title: "Perguntas frequentes sobre cálculos para modelos de configuração de produto"
description: "Este tópico descreve os cálculos para os modelos de configuração de produto e explica como usar os cálculos juntamente com as restrições."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3a1bfd4bd5f396c05277159ac112eaa8197d5818
ms.openlocfilehash: 0763e5a02e7a14b6ef369103aa25e435559abe19
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="calculations-for-product-configuration-models-faq"></a>Perguntas frequentes sobre cálculos para modelos de configuração de produto

[!include[banner](../includes/banner.md)]


Este tópico descreve os cálculos para os modelos de configuração de produto e explica como usar os cálculos juntamente com as restrições.

Os cálculos podem ser usados para operações aritméticas ou lógicas. Eles complementam restrições de expressão e restrições em modelos de configuração do produto. Você pode definir cálculos na página **Detalhes do modelo de configuração de produto baseado em restrições** e depois criar expressões para os cálculos no editor de expressões. Para obter mais informações, consulte Criar cálculos.

## <a name="what-is-a-calculation"></a>O que é um cálculo?
Um cálculo é um elemento que pode ser usado em um modelo de configuração de produto. Os cálculos complementam as restrições, permitindo que você use números decimais para calcular valores ao configurar um produto. Além disso, os cálculos têm um conjunto de operadores disponíveis maior do que as restrições.  

Como uma restrição, um cálculo é associado a um determinado componente em um modelo de configuração de produto e não pode ser reutilizado ou compartilhado com outro componente. Uma diferença importante entre os cálculos e as restrições é que os cálculos são obrigatórios (unidirecionais), enquanto as restrições são declarativas (bidirecionais). Para obter mais informações sobre restrições, consulte [Restrições de expressão e restrições de tabela](expression-constraints-table-constraints-product-configuration-models.md).  

Um cálculo consiste em um atributo de destino e uma expressão de cálculo.

## <a name="what-is-a-target-attribute"></a>O que é um atributo de destino?
Um atributo de destino é um atributo que recebe o resultado da expressão de cálculo.  

Na expressão a seguir, o atributo de destino é uma medição de toalha de mesa:  

**Expressão:** If\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]  

**DecimalAttribute1** é o comprimento da tabela e **decimalAttribute2** é o comprimento da toalha de mesa. A expressão retornará o valor **True** para o atributo de destino se **decimalAttribute2** for maior ou igual a **decimalAttribute1**. Caso contrário, a expressão retornará um valor **False**. Portanto, a medição da toalha de mesa será aceitável se o comprimento da toalha de mesa for igual ou maior que o tamanho da mesa.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Quais tipos de atributo que podem ser definidos para atributos de destino?
Todos os tipos de atributo com o suporte do configurador de produtos podem ser definidos para os atributos de destino exceto para o texto sem uma lista fixa.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>É possível que um valor de destino restrinja os valores dos atributos de entrada em um cálculo?
Não, o valor de destino não pode restringir os valores dos atributos de entrada porque os cálculos são unidirecionais. Consequentemente, o valor do atributo de destino é ajustado com base em alterações no valor dos atributos de entrada, mas uma alteração no valor de destino não afeta o valor dos atributos de entrada. Esse comportamento é diferente do comportamento das restrições. As restrições ocorrem em ambas as direções.

### <a name="example"></a>Exemplo

Na expressão a seguir, o destino do cálculo é o comprimento de um cabo de alimentação e o valor de entrada é uma cor:  

**Expressão:** \[If Color == "Verde", 1,5, 1,0\]  

Quando você configura o item, o comprimento do cabo de alimentação é definido como **1,5** se você especificar **Verde** como o valor do atributo cor. Se outra cor for especificada, o tamanho será definido como **1,0**. No entanto, em decorrência dos cálculos serem unidirecionais, o cálculo não definirá o valor do atributo de cor como **Verde** quando você especificar um tamanho **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>O que acontece se um cálculo tiver um atributo de destino do tipo inteiro mas um cálculo gerar um número decimal?
Se um atributo de destino for o tipo inteiro, mas um cálculo gerar um número decimal, somente a parte inteira do resultado calculado será retornada. A parte decimal é removida e o resultado não é arredondado. Por exemplo, um resultado 12,70 é mostrado como 12.

## <a name="when-do-calculations-occur"></a>Quando os cálculos ocorrem?
Os cálculos ocorrem quando um valor tiver sido fornecido para todos os atributos de entrada.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>Posso substituir o valor calculado para o atributo de destino?
É possível substituir o valor que é calculado para o atributo de destino a menos que o atributo de destino esteja definido como oculto ou somente leitura.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-read-only"></a>Como defino um atributo de destino como oculto ou somente leitura?
Para definir um atributo como oculto ou somente leitura, siga estas etapas.

1.  Clique em **Gerenciamento de informações do produto** &gt; **Comum** &gt; **Modelos de configuração do produto**.
2.  Selecione um modelo de configuração do produto e, no Painel de Ação, clique em **Editar**.
3.  Na página **Detalhes do modelo de configuração do produto baseada em restrições**, selecione o atributo a ser usado como um atributo de destino.
4.  Na Guia Rápida **Atributos**, selecione **Oculto** ou **Somente leitura**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Um cálculo pode substituir os valores que eu defini?
Não. Os valores definidos quando você configura um produto são os valores que serão usados. O cálculo que ocorre quando os valores de entrada em um cálculo são alterados não pode substituir os valores fornecidos para um atributo específico.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Que ocorre se um valor de entrada for removido em um cálculo?
Se um valor de entrada for removido em um cálculo, o valor do atributo de destino também será removido.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Por que recebo uma mensagem de erro indicando que meu modelo está em contradição?
A mensagem é mostrada quando um cálculo inclui um erro ou quando uma contradição existe em uma ou várias restrições. Para obter mais informações sobre contradições em restrições, consulte [Restrições de expressão e restrições de tabela](expression-constraints-table-constraints-product-configuration-models.md). Veja a seguir algumas situações em que podem ocorrer erros nos cálculos:

-   Um valor é dividido por 0 (zero).
-   Há um conflito entre estes dois elementos:
    -   Os valores disponíveis para um atributo e que são limitados por uma restrição
    -   Um valor gerado por um cálculo
-   Os valores que são retornados pelo cálculo estão fora de domínio de atributos. Um exemplo é um número inteiro de \[1..10\] calculado em 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Por que recebo uma mensagem de erro mesmo quando valido com êxito meu modelo de produto?
Os cálculos não são incluídos na validação. É necessário testar o modelo de configuração do produto para localizar erros nos cálculos. Para testar um modelo de configuração do produto, siga estas etapas.

1.  Clique em **Gerenciamento de informações do produto** &gt; **Comum** &gt; **Modelos de configuração do produto**.
2.  Selecione um modelo de configuração do produto e, no Painel de Ação, no grupo **Executar**, clique em **Testar**.





