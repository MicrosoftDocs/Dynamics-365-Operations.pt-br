---
title: "Configurar parâmetros de RH entre entidades legais"
description: "Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: 5df6079605d2d8d320c38d302e8e5e2cba51a3f1
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-hr-parameters-across-legal-entities"></a>Configurar parâmetros de RH entre entidades legais

Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.

Alguns tipos de registros, como os registros de posição, são compartilhados entre empresas. Para esses registros, é necessário configurar parâmetros compartilhados. Por exemplo, você pode usar a página **Parâmetros compartilhados de recursos humanos** para configurar parâmetros de recursos humanos entre entidades legais. 

Na página **Parâmetros compartilhados de recursos humanos**, os parâmetros são agrupados em áreas, com base em sua funcionalidade. 

Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página. Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores. As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**. Para definir uma nova ID digitar ou revisar a lista de tipos existentes, clique ** recursos humanos ** &gt; ** de instalação ** &gt; ** tipos ** de identificação. Você pode inserir um código simples e uma descrição. 

Na guia **Sequências numéricas**, você pode selecionar as sequências numéricas usadas nos seguintes registros: Número da equipe, Posição, ID da solicitação de usuário, Documento I-9, Candidato, Discussão, ID do Benefício e Ação de pessoal (se esse tipo de registro estiver habilitado). Para manter as referências e os códigos de sequência numérica, use a página de lista **Sequências numéricas**. Para localizar essa página, use o recurso de pesquisa de página. 

Na guia **Posições**, indique se as novas posições estão disponíveis para atribuição por padrão:

-   ** Sempre ** – você pode atribuir trabalhadores a novas posições às posições são criadas. Quando as posições são criadas, ** disponível para a atribuição ** a data e hora ** ** na guia geral ** posição ** de página será definida automaticamente para a data e a hora de criação.
-   **Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas. Se você selecionar essa opção, precisará abrir a página **Posição** para cada nova posição à medida que ela for disponibilizada. Em seguida, na guia **Geral**, insira **Disponível para atribuição **para habilitar a atribuição de trabalhador.


<a name="see-also"></a>Consulte também
--------

[Parâmetros específicos configurados] de rh da empresa (setup-company-specific-hr-parameters.md)


