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
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Dimensões financeiras

Este artigo explica os diferentes tipos de dimensões financeiras e como elas são configuradas.

Use a página Dimensões financeiras para criar as dimensões financeiras que você pode usar como segmentos de conta para os gráficos de contas compartilhados. Há dois tipos de dimensões financeiras, as dimensões personalizadas e as dimensões apoiadas por entidade. As dimensões personalizadas são compartilhadas pelas entidades legais e os valores são inseridos e mantidos pelo usuário. As dimensões apoiadas por entidade são aquelas cujos valores são definidos em outro lugar no sistema, como Clientes ou Lojas. Algumas dimensões apoiadas por entidade são compartilhadas entre entidades legais e algumas dimensões apoiadas por entidade são específicas da empresa. 

Depois de ter criado as dimensões financeiras, use a página Valores de dimensão financeira para atribuir propriedades adicionais para cada dimensão financeira. 

Embora você possa usar dimensões financeiras para representar entidades legais sem criar as entidades legais no Microsoft Dynamics 365 para operações, as dimensões financeiras não são criadas para atender as necessidades comerciais operacionais ou de entidades legais. A funcionalidade da contabilidade interunidade no Microsoft Dynamics 365 para operações é criada para abordar somente as escriturações criadas para cada transação. 

Antes de configurar dimensões financeiras como entidades legais, avalia seus processos comerciais nas seguintes áreas para determinar se essa configuração funcionará para sua organização:

-   Estoque
-   Vendas e compras entre dimensões financeiras e entidades legais
-   Cálculo do imposto sobre vendas e relatórios
-   Relatório operacional

Alguns exemplos de limitações incluem o seguinte:

-   Você pode usar a funcionalidade de imposto sobre vendas apenas com entidades legais, e não com dimensões financeiras.
-   Alguns relatórios não incluem dimensões financeiras, portanto, você sem sempre poderá criar relatórios por dimensão financeira a menos que esses relatórios sejam alterados.

**Custom dimensions** 

Para criar uma dimensão financeira definido pelo usuário, os valores de campo, o uso personalizado dimensão &lt; selecionada &gt;. Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão. Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen. Você também pode inserir símbolos de cerquilha (\#) E comercial (&) como espaços reservados para as letras e números que alterarão sempre que um valor de dimensão é criado. Use um símbolo de cerquilha (\#) como um espaço reservado para um número e um E comercial (&) como um espaço reservado para uma carta. 

**Exemplo ** 

Para limitar o valor de dimensão a CC de letras e números a três, insira o cúbico centímetro\#\#\# como a máscara de formato. Este campo está disponível somente quando você seleciona &lt; a dimensão personalizado &gt; em uso de valores de campo. 

** Dimensões entidade entidade ** 

Para criar uma voltou entidade a dimensão financeira, os valores de uso do campo, selecione uma entidade sistema definida para basear a dimensão financeira. Valores de dimensão financeira são criados a partir dessa seleção. Por exemplo, para criar valores de dimensão para projetos, selecione Projetos. Um valor de dimensão será criado para cada nome de projeto. A página dos valores de dimensão mostra os valores para a entidade e se elas não forem específicas da empresa, a empresa para o valor. 

** Ativando dimensões ** 

A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser consumida em lugar algum até ser ativada. Por exemplo, você não pode adicionar uma dimensão financeira a uma estrutura de conta até a dimensão financeira ser ativada. Clicar em ativar atualizará todas as dimensões com alterações de status. 

**Translations** 

A página de tradução de texto permite inserir texto a ser exibido em idiomas diferentes para a dimensão financeira selecionada. A página Tradução da conta principal é onde você pode inserir, na conta principal, o texto a ser exibido em diferentes idiomas. 

**Legal entity overrides** 

As dimensões não é válida para todas as entidades legais algumas só podem ser relevantes para um período específico. Neste cenário, a seção Substituições da entidade legal pode ser usada para identificar para quais empresas a dimensão deve ser suspensa, quem é o proprietário e há quanto tempo a dimensão está ativa.




