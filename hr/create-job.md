---
title: Configurar os componentes de um trabalho
description: "Este tópico descreve elementos conceituais que um trabalho podem incluir e oferece exemplos de como é possível usar os elementos na sua organização."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Configurar os componentes de um trabalho

Este tópico descreve elementos conceituais que um trabalho podem incluir e oferece exemplos de como é possível usar os elementos na sua organização. 

Para criar trabalhos, você deve configurar as informações de referência. Você pode criar um trabalho que estejam apenas um nome. Entretanto, incluindo informações adicionais, como um cargo, você oferece valores padrão para as posições atribuídas ao trabalho. Adicionalmente, algumas das informações inseridas podem ser usadas para filtrar planos de remuneração para trabalhos específicos. Se quiser configurar qualificação que você pode usar para filtrar planos de remuneração a um trabalho específico, você deve configurar funções de trabalho e o trabalho antes digitem trabalho configurados. Tendo esses valores padrão disponíveis, você obterá tempo quando você adiciona posições ao trabalho. 

Alguns detalhes do trabalho, como o cargo, tipo, e são funções, data efetiva. Se você criar um cargo atual mas não somar esses detalhes posteriormente, e até olhar nos trabalhos na data de criação, elas não aparecerão detalhes. Portanto, você deve criar algumas dessas informações de referência para que a variação. Essa maneira, você pode adicionar informações a novos trabalhos quando você cria os.

## <a name="job-titles"></a>Cargos
Antes de criar trabalhos, você deve configurar cargos para esses trabalhos. As posições herdam cargos dos trabalhos com os quais essas posições estão associadas. 

Manter cargos usando ** títulos ** a página, que pode ser aberto com a função de pesquisa. ** Títulos ** na página, insira títulos que você planeja usar para os trabalhos.

## <a name="job-types"></a>Tipos de trabalho
Use os tipos de trabalho para trabalhos semelhantes agrupar categorias. Os tipos de trabalho não são necessários. Entretanto, se planeja usar tipos de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar tipos de trabalho antes de configurar os trabalhos. Exemplos de tipos de trabalho são e completo a partir de meio expediente, pagamento ou trabalho e por hora. Você mantém tipos de trabalho usando ** ** tipos de trabalho a página. ** ** Tipos de trabalho na página, insira um nome e uma breve descrição do tipo de trabalho. ** O status de isenção ** campo, selecione uma das seguintes opções indicar o status de isenção (FLSA) da FLSA justo de padrões justos de trabalhos com esse tipo de trabalho:

-   ** ** – Trabalhos isentas são isentos de hora extra na FLSA.
-   ** ** – os trabalhos não isentos não estiverem isentas de hora extra na FLSA.
-   ** Não aplicável – ** cobertura da FLSA não é aplicável.

## <a name="job-functions"></a>Funções de trabalho
Os junções de trabalho descrevem categorias funcionais de alto nível e relacionados direitos de alto nível. As funções de trabalho não são necessárias. Você pode usar essas funções de trabalho, com tipos de trabalho, para filtrar planos de remuneração para trabalhos específicos. Você associa funções de trabalho e os tipos de trabalho a planos de remuneração configurando regras de eligibilidade ** regras de eligibilidade ** na página. Poderá anexar um conjunto de níveis a um plano de remuneração que se aplicam à determinada combinação de um tipo e de uma função de trabalho de trabalho definido com uma regra de qualificação. (Esses recursos se aplicam a planos de remuneração fixa e os planos de remuneração variáveis.) Entretanto, se você planeja usar outras funções de trabalho quando você agrupa qualificação configurada para o gerenciamento de remuneração, você deve configurar funções de trabalho antes de trabalho configuradas. A tabela mostra exemplos de funções de trabalho.

| Trabalho           | Função de trabalho         |
|---------------|----------------------|
| Gerente de vendas | Gerente de nível médio    |
| Contador    | Profissionais        |

Você mantém funções de trabalho usando ** funções de trabalho ** a página. ** ** Funções de trabalho na página, insira um código de identificação e uma breve descrição da função de trabalho.

## <a name="job-tasks"></a>Tarefas do trabalho
As tarefas de trabalho descrevem as tarefas básicas quais o trabalhador que esteja em uma posição para o trabalho deve terminar. A mesma tarefa do trabalho pode ser adicionada aos vários trabalhos, e cargos dos trabalhos que usam essas tarefas de trabalho. A tabela mostra exemplos de tarefas de trabalho.

<table>
<thead>
<tr class="header">
<th>Trabalho</th>
<th>Tarefa do trabalho</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Gerente de vendas</td>
<td><ul>
<li><strong>Perf-revisão</strong> Produção – leia o profissional vendedor de cada.</li>
<li><strong>Abs-revisão</strong> – Aprove ou rejeite solicitações ou registros de ausências vendedor de cada.</li>
</ul></td>
</tr>
<tr class="even">
<td>Contador</td>
<td><strong>Fin-relatório</strong> Relatórios financeiros – semanais atuais a chief financial officer.</td>
</tr>
</tbody>
</table>

Você mantém tarefas de trabalho usando ** tarefas de trabalho ** a página. ** ** Tarefas de trabalho na página, insira um nome e descrição para a tarefa de trabalho. ** O campo nota ** opcionalmente, você pode inserir informações adicionais. As notas podem ser atualizadas para um trabalho específico sem alterar notas inseridos aqui.

## <a name="areas-of-responsibility"></a>Áreas de responsabilidade
Use áreas de responsabilidade indicar as funções de trabalho, os processos, os produtos que um trabalhador que está em um cargo para um trabalho é responsável. Por exemplo, para trabalho que fossem nomeados contador “”, uma área de responsabilidade poderia ser “relatório financeiro para Aos produtos.” Você mantém áreas de responsabilidade ** usando áreas de responsabilidade ** a página, que você pode encontrar usando a função de pesquisa. ** Áreas de responsabilidade ** na página, insira um nome e uma descrição da responsabilidade. ** O campo nota ** opcionalmente, você pode inserir informações adicionais. As notas podem ser atualizadas para um trabalho específico sem alterar notas inseridos aqui.


