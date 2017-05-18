---
title: "Dimensões financeiras"
description: "Este artigo explica os diferentes tipos de dimensões financeiras e como elas são configuradas."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5ee2d132f0b23ceec2a79ee6b0ee33862d6a0518
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="financial-dimensions"></a>Dimensões financeiras

[!include[banner](../includes/banner.md)]


Este artigo explica os diferentes tipos de dimensões financeiras e como elas são configuradas.

Use a página Dimensões financeiras para criar as dimensões financeiras que você pode usar como segmentos de conta para os gráficos de contas compartilhados. Há dois tipos de dimensões financeiras, as dimensões personalizadas e as dimensões apoiadas por entidade. As dimensões personalizadas são compartilhadas pelas entidades legais e os valores são inseridos e mantidos pelo usuário. As dimensões apoiadas por entidade são aquelas cujos valores são definidos em outro lugar no sistema, como Clientes ou Lojas. Algumas dimensões apoiadas por entidade são compartilhadas entre entidades legais e algumas dimensões apoiadas por entidade são específicas da empresa. 

Depois de ter criado as dimensões financeiras, use a página Valores de dimensão financeira para atribuir propriedades adicionais para cada dimensão financeira. 

Embora seja possível usar dimensões financeiras para representar entidades legais sem criar entidades legais no Microsoft Dynamics 365 for Operations, as dimensões financeiras não são criadas para resolver as necessidades comerciais ou operacionais das entidades legais. A funcionalidade de contabilidade interunidade no Microsoft Dynamics 365 for Operations foi criada para tratar somente as entradas contábeis que são criadas para cada transação. 

Antes de configurar dimensões financeiras como entidades legais, avalia seus processos comerciais nas seguintes áreas para determinar se essa configuração funcionará para sua organização:

-   Estoque
-   Vendas e compras entre dimensões financeiras e entidades legais
-   Cálculo do imposto sobre vendas e relatórios
-   Relatório operacional

Alguns exemplos de limitações incluem o seguinte:

-   Você pode usar a funcionalidade de imposto sobre vendas apenas com entidades legais, e não com dimensões financeiras.
-   Alguns relatórios não incluem dimensões financeiras, portanto, você sem sempre poderá criar relatórios por dimensão financeira a menos que esses relatórios sejam alterados.

**Dimensões personalizadas** 

Para criar uma dimensão financeira definida pelo usuário, no campo Usar valores de, selecione &lt; Dimensão personalizada &gt;. Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão. Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen. Você também pode inserir sinais numéricos (\#) e o E comercial (&) como espaços reservados para as letras e números que mudarão sempre que um valor de dimensão for criado. Use um sinal numérico (\#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra. 

**Exemplo** 

Para limitar o valor de dimensão às letras CC e a três números, insira CC-\#\#\# como a máscara de formato. Esse campo só está disponível quando você seleciona &lt; Dimensão personalizada &gt; no campo Usar valores de. 

**Dimensões apoiadas por entidade** 

Para criar uma dimensão financeira apoiada por entidade, no campo Usar valores de, selecione uma entidade definida pelo sistema na qual a dimensão financeira será baseada. Valores de dimensão financeira são criados a partir dessa seleção. Por exemplo, para criar valores de dimensão para projetos, selecione Projetos. Um valor de dimensão será criado para cada nome de projeto. A página dos valores de dimensão mostra os valores para a entidade e se elas não forem específicas da empresa, a empresa para o valor. 

**Ativação da dimensão** 

A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser consumida em lugar algum até ser ativada. Por exemplo, você não pode adicionar uma dimensão financeira a uma estrutura de conta até a dimensão financeira ser ativada. Clicar em ativar atualizará todas as dimensões com alterações de status. 

**Traduções** 

A página Tradução de texto permite que você insira o texto a ser exibido em idiomas diferentes para a dimensão financeira selecionada. A página Tradução da conta principal é onde você pode inserir, na conta principal, o texto a ser exibido em diferentes idiomas. 

**Substituições de entidade legal** 

Nem todas as dimensões são válidas para todas as entidades legais e algumas podem ser relevantes apenas por um período específico. Neste cenário, a seção Substituições da entidade legal pode ser usada para identificar para quais empresas a dimensão deve ser suspensa, quem é o proprietário e há quanto tempo a dimensão está ativa.






