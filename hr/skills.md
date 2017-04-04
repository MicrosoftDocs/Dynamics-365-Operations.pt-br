---
title: "Alinhe habilidades de força de trabalho com as necessidades comerciais"
description: "Você pode rastrear as habilidades que os trabalhadores, candidatos ou pessoas de contato têm ou devem ter, para atender suas funções efetivamente. Você também pode especificar as habilidades necessárias para um trabalho específico."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 720a1f272948eb310dc3cd02588aeec40b556d20
ms.openlocfilehash: 31dda85ff2e4a4e5380401b031b2dd74acff394b
ms.lasthandoff: 03/31/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Alinhe habilidades de força de trabalho com as necessidades comerciais

Você pode rastrear as habilidades que os trabalhadores, candidatos ou pessoas de contato têm ou devem ter, para atender suas funções efetivamente. Você também pode especificar as habilidades necessárias para um trabalho específico.

Os exemplos das habilidades que você pode rastrear incluem o seguinte:
-   Supervisão – capacidade de supervisionar o trabalho de terceiros.
-   Liderança – capacidade de liderar funcionários e setores empresariais.
-   Planejamento - capacidade de antever o futuro, formular visões e acompanhá-las.
-   HTML – Capacidade de gravar o código HTML.

Antes de atribuir uma habilidade a uma pessoa ou a um trabalho, criar uma pesquisa de mapeamento de habilidades ou criar um perfil de habilidades, você deve inserir informações sobre as habilidades na página **Habilidades**. Para cada habilidade, você pode selecionar um tipo de habilidade e um modelo de classificação.

## <a name="rating-models"></a>Modelos de classificação
Os modelos de classificação ajudam a avaliar o nível real de habilidades de uma pessoa, o nível que ela deveria atingir ou o nível de habilidades necessário para um trabalho. É possível inserir até 10 níveis para um modelo de avaliação.  Cada nível em um modelo de classificação é atribuído um fatora.  O valor de fatora será usado para normalizar contagens as habilidades que usam diferentes modelos de classificação.  O fatora deve ser um número entre 0-9 e cada nível deve ter um fatora exclusivo.  Os níveis com valores de fator mais altos têm mais peso em um modelo de avaliação.

## <a name="specify-job-skills"></a>Especifique as habilidades de trabalho
Quando você insere informações sobre um trabalho, você pode especificar as habilidades que a pessoa se tem para executar o trabalho necessários para o trabalho.  Além você pode especificar o nível desejado para cada habilidade também o nível de importância da habilidade. Diferentes trabalhos podem exigir diferentes níveis de importância para a mesma habilidade.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Insira habilidades para funcionários, candidatos ou contatos
Você pode inserir habilidades alvo ou habilidades reais para funcionários, candidatos ou contatos. Uma habilidade alvo é uma habilidade que uma pessoa planeja obter. Uma habilidade real é uma habilidade que uma pessoa tem atualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mapeamento de habilidades e perfis de mapeamento de habilidades
Você pode criar uma pesquisa de mapeamento de habilidades para localizar um trabalhador, ou um candidato, uma pessoa de contato que seja qualificada para executar um tipo específico de tarefa. as pesquisas de mapeamento de habilidades olham através de formação educacional, habilidades, certificados, experiência de posições de confiança e de projeto e os resultados retornarão que correspondem aos critérios inseridos.  Por exemplo, pode ser útil saber que funcionários de sua organização ganharam o CPA.

os perfis de mapeamento de habilidades permitem que você encontra funcionários atuais ou candidatos qualificações que atendem diretamente às necessidades comerciais.  Por exemplo, você pode criar um perfil de mapeamento de habilidades para uma vaga aberta na organização. Criando um perfil para um trabalho específico e copiando as habilidades, formação educacional e certificados desse trabalho para o perfil, é possível pesquisar rapidamente trabalhadores, candidatos e pessoas de contato que correspondem a um ou mais dos critérios inseridos no perfil e exibir uma lista dos candidatos cujas as habilidades mais correspondem às habilidades necessárias para o trabalho.

<table>
<thead>
<tr class="header">
<th><strong>Nota </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Somente os trabalhadores, os candidatos e as pessoas de contato selecionados para serem incluídos em pesquisas de mapeamento podem ser exibidos em uma lista dos resultados de um mapeamento de habilidades ou serem incluídos em um perfil de habilidades. Para incluir um trabalhador, candidato ou pessoa de contato em pesquisas de mapeamento de habilidades, defina a seleção <strong>Incluir no mapeamento de habilidades</strong> como Sim nas seguintes páginas:
<ul>
<li>Trabalhador</li>
<li>Funcionário</li>
<li>Candidato</li>
<li>Contatos</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Análise da lacuna de habilidades e análise do perfil de habilidades
Você pode criar uma análise de perfil de habilidades para exibir uma lista de competências de um trabalhador, candidato ou pessoa de contato como uma data específica. Você pode criar uma análise de lacuna de habilidades para comparar as habilidades de uma pessoa e as habilidades necessárias para um trabalho específico.  



<a name="see-also"></a>Consulte também
--------

[Human resources](index.md)


