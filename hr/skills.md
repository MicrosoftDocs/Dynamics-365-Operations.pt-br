---
title: "Alinhe habilidades de força de trabalho com as necessidades comerciais"
description: "Você pode rastrear as habilidades que os trabalhadores, candidatos ou pessoas de contato têm ou devem ter, para atender suas funções efetivamente. Você também pode especificar as habilidades necessárias para um trabalho específico."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ae940cdbab2166d8fe3f2f396c84ed4a09c2ca7e
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Alinhe habilidades de força de trabalho com as necessidades comerciais

[!include[banner](includes/banner.md)]


Você pode rastrear as habilidades que os trabalhadores, candidatos ou pessoas de contato têm ou devem ter, para atender suas funções efetivamente. Você também pode especificar as habilidades necessárias para um trabalho específico.

Os exemplos das habilidades que você pode rastrear incluem o seguinte:
-   Supervisão – capacidade de supervisionar o trabalho de terceiros.
-   Liderança – capacidade de liderar funcionários e setores empresariais.
-   Planejamento - capacidade de antever o futuro, formular visões e acompanhá-las.
-   HTML – Capacidade de gravar o código HTML.

Antes de atribuir uma habilidade a uma pessoa ou a um trabalho, criar uma pesquisa de mapeamento de habilidades ou criar um perfil de habilidades, você deve inserir informações sobre as habilidades na página **Habilidades**. Para cada habilidade, você pode selecionar um tipo de habilidade e um modelo de classificação.

## <a name="rating-models"></a>Modelos de classificação
Os modelos de classificação ajudam a avaliar o nível real de habilidades de uma pessoa, o nível que ela deveria atingir ou o nível de habilidades necessário para um trabalho. É possível inserir até 10 níveis para um modelo de avaliação.  Cada nível em um modelo de classificação é atribuído um fator.  O valor do fator será usado para normalizar pontuações das habilidades que usam diferentes modelos de avaliação.  O fator deve ser um número de 0 a 9, e cada nível deve ter um fator exclusivo.  Os níveis com valores de fator mais altos têm mais peso em um modelo de avaliação.

## <a name="specify-job-skills"></a>Especifique as habilidades de trabalho
Ao inserir informações sobre um trabalho, você pode especificar as habilidades que uma pessoa deve ter para que ela realize o trabalho.  Além disso, você pode especificar o nível desejado para cada habilidade, bem como o nível de importância da habilidade. Diferentes trabalhos podem exigir diferentes níveis de importância para a mesma habilidade.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Insira habilidades para funcionários, candidatos ou contatos
Você pode inserir habilidades alvo ou habilidades reais para funcionários, candidatos ou contatos. Uma habilidade alvo é uma habilidade que uma pessoa planeja obter. Uma habilidade real é uma habilidade que uma pessoa tem atualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mapeamento de habilidades e perfis de mapeamento de habilidades
Você pode criar uma pesquisa de mapeamento de habilidades para encontrar um trabalhador, solicitante ou pessoa de contato qualificada para executar um tipo específico de tarefa. Pesquisas de mapeamento de habilidades buscam habilidades, educação, certificados, posições de confiança e experiência de projeto e retornam resultados que correspondem aos critérios inseridos.  Por exemplo, pode ser útil saber quais os trabalhadores da sua organização obtiveram o CPA.

Os perfis de mapeamento de habilidades permitem que você encontre funcionários atuais ou candidatos com qualificações que correspondam diretamente às necessidades do negócio.  Por exemplo, você pode criar um perfil de mapeamento de habilidades para uma posição aberta na sua organização. Criando um perfil para um trabalho específico e copiando as habilidades, formação educacional e certificados desse trabalho para o perfil, é possível pesquisar rapidamente trabalhadores, candidatos e pessoas de contato que correspondem a um ou mais dos critérios inseridos no perfil e exibir uma lista dos candidatos cujas as habilidades mais correspondem às habilidades necessárias para o trabalho.

>**Observação** Somente os trabalhadores, os candidatos e as pessoas de contato selecionados para serem incluídos em pesquisas de mapeamento podem ser exibidos em uma lista dos resultados de um mapeamento de habilidades ou serem incluídos em um perfil de habilidades. Para incluir um trabalhador, candidato ou pessoa de contato em pesquisas de mapeamento de habilidades, defina a seleção **Incluir no mapeamento de habilidades** como Sim nas seguintes páginas:

> + Trabalhador
> + Funcionário
> + Candidato
> + Contatos

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Análise da lacuna de habilidades e análise do perfil de habilidades
Você pode criar uma análise de perfil de habilidades para exibir uma lista de competências de um trabalhador, candidato ou pessoa de contato como uma data específica. Você pode criar uma análise de lacuna de habilidades para comparar as habilidades de uma pessoa e as habilidades necessárias para um trabalho específico.  



<a name="see-also"></a>Consulte também
--------

[Recursos humanos](index.md)




