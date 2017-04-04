---
title: "Lançar transações de ativo fixo nos níveis de lançamento"
description: "Este artigo oferece uma visão geral da funcionalidade de nível de lançamento para transações de ativo fixo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 4b112eee303604149c7609972a60c2014d4be423
ms.lasthandoff: 03/31/2017


---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Lançar transações de ativo fixo nos níveis de lançamento

Este artigo oferece uma visão geral da funcionalidade de nível de lançamento para transações de ativo fixo.

Um ativo fixo geralmente é depreciado de diferentes maneiras para diferentes finalidades. A depreciação para fins fiscais é calculada de acordo com as normas fiscais atuais para obter a mais alta depreciação possível antes dos impostos, mas a depreciação para fins de relatórios é calculada de acordo com as leis e padrões contábeis. Os vários tipos de depreciação são calculados e registrados separadamente nos níveis de lançamento.

Cada registro anexado a um ativo fixo é configurado para um nível específico de lançamento que tem um objetivo de depreciação geral. Há dez níveis de lançamento: Atual, operações, impostos, sete e níveis personalizados. Também é possível desabilitar o lançamento na contabilidade para o registro definindo o campo Lançar na contabilidade como Não. O campo Nível de lançamento é definido automaticamente como Nenhum. Normalmente, os registros ainda não lançados na contabilidade são usados para relatórios de imposto. Esta abordagem fornece flexibilidade adicional excluir transações históricas do registro de ativos, porque não foram confirmados a contabilidade.

Fixo diários de ativos são definidos usando a página Nomes de diários em Contabilidade > Configuração de diário > Nomes de diários. Cada diário onde você pode lançar depreciações será definido por seu nome de diário somente para um nível de lançamento. O nível de lançamento no diário não poderá ser alterado. Essa limitação ajuda a garantia que as transações de cada nível de lançamento serão mantidas separadas. Pelo menos, um nome de diário será criado para cada nível de lançamento. Se estiver usando registros que não lançados na contabilidade, também precisará criar um diário no nível de lançamento é definido como nenhum.

É possível designar contas contábeis para transações de ativo fixo na página Perfis de lançamentos de ativo fixo. Para cada perfil de postagem, selecione o tipo de transação e o registro relevantes, e designar as contas contábeis. Configurar uma registradora de postagem de perfil para cada registro que será lançada na contabilidade.

> [!NOTE] 
> Usando registros derivados, você pode lançar transações nos níveis de lançamento diferente ao mesmo tempo. Você cria as transações do registro primário em um diário com o nível de lançamento correspondente ao nível de lançamento do registro. Durante o lançamento, as transações do registro derivado serão lançadas em seus respectivos níveis de lançamento.

Para obter mais informações consulte, livros [] derived-books.md derivados (e) [postagem com livros derivados (post-derived-value-models.md]).


