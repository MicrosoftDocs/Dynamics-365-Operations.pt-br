---
title: Organizar sua força de trabalho usando departamentos, trabalhos e posições
description: Este tópico descreve informações conceituais sobre departamentos, trabalhos e posições, que são elementos organizacionais mantidos nos Recursos Humanos.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2b4c1efac249b315de25348a104f00a613c32df9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071400"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organizar sua força de trabalho usando departamentos, trabalhos e posições


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Departamentos, trabalhos e cargos são elementos organizacionais mantidos dentro da área de Recursos Humanos. Este tópico descreve informações conceituais sobre esses elementos. 

O exemplo a seguir é usado para ilustrar os conceitos descritos neste artigo.

|**Departamento**|**Cargo**|**Trabalho**|
|---|---|---|
|**Vendas**|Gerente de vendas (Leste)|Gerente de vendas|
|**Vendas**|Gerente de vendas (Oeste)|Gerente de vendas|
|**Vendas**|Gerente de vendas (Central)|Gerente de vendas|
|**Contabilidade**|Supervisor de contabilidade|Gerente de contabilidade|
|**Contabilidade**|Contabilidade A|Contador|
|**Recursos Humanos**|Gerente de RH (Leste)|Gerente de RH|
|**Recursos Humanos**|Gerente de RH (Oeste)|Gerente de RH|
|**Recursos Humanos**|Gerente de RH (Central)|Gerente de RH|


##  <a name="departments"></a>Departamentos

Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização e que é responsável por uma área específica da organização, como vendas ou contabilidade. Um departamento é usado para relatar áreas funcionais, e pode ter responsabilidade por lucros e perdas. Além disso, um departamento pode incluir um grupo de centros de custo. Vendas, contabilidade e recursos humanos são exemplos de departamentos de uma organização.

## <a name="jobs-and-positions"></a>Trabalhos e cargos
Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho. Um cargo é uma instância individual de um trabalho. Aspectos como áreas de responsabilidade, tarefas de trabalho, funções de trabalho, habilidades, informações de formação educacional e certificados, que são necessários para um trabalho, também são necessários para os cargos associados a um trabalho.

### <a name="job-tasks"></a>Tarefas do trabalho

Você pode criar tarefas de trabalho que descrevem as tarefas básicas que devem ser realizadas por um trabalhador em um cargo desse trabalho. A mesma tarefa de trabalho pode ser adicionada a vários trabalhos, e os cargos desses trabalhos herdarão as tarefas de trabalho. Exemplos de tarefas de trabalho são listados na tabela a seguir.

| Trabalho           | Tarefa do trabalho                                                |
|---------------|-------------------------------------------------------------|
| Gerente de vendas | Avaliação de desempenho – avaliar o desempenho profissional de cada vendedor.    |
| Contador    | Avaliação de ausências – aprovar ou rejeitar as solicitações ou os registros de ausência de cada vendedor. |


### <a name="job-functions"></a>Funções de trabalho

As funções de trabalho são como tarefas de trabalho. Uma função de trabalho descreve uma ou diversas tarefas, obrigações ou responsabilidades atribuídas a um trabalho. As funções de trabalho podem ser atribuídas a trabalhos e usadas para definir e implementar regras de qualificação para planos de remuneração. Exemplos de funções de trabalho são listados na tabela a seguir.

| Trabalho           | Função de trabalho                                                |
|---------------|-------------------------------------------------------------|
| Gerente de vendas | Gerenciar pessoas – gerenciar pessoas que estão subordinadas a você.               |
| Contador    | Avaliação financeira – manter dados financeiros para um conjunto de contas. |

### <a name="job-types"></a>Tipos de trabalho

Use os tipos de trabalho para classificar trabalhos semelhantes em categorias. Os tipos de trabalho, assim como as funções de trabalho, podem ser atribuídos a trabalhos e usados para definir e implementar regras de qualificação para planos de remuneração. Alguns exemplos de tipos de trabalho estão incluídos na seguinte lista:
-   Horário integral
-   Meio período
-   Salário
-   Pagamento por hora

### <a name="areas-of-responsibility"></a>Áreas de responsabilidade

Use as áreas de responsabilidade para indicar as funções de trabalho, os processos e os produtos pelos quais um trabalhador será responsável em um cargo do trabalho. Um exemplo de uma área de responsabilidade para um trabalho chamado "Contador" poderia ser "Relatório financeiro do produto A".

## <a name="positions"></a>Cargos

Os cargos são um elemento importante do nível inferior de uma hierarquia organizacional. Um cargo é uma instância individual de um trabalho. Por exemplo, a posição, "Gerente de vendas (Leste)", é apenas uma das posições associada ao cargo, "Gerente de vendas". As posições existem em um departamento e atribuídas aos funcionários.
### <a name="position-creation-and-maintenance"></a>Criação e manutenção de cargos

-   Você pode exibir um histórico de alterações do sistema relacionadas a cargos em uma página de listagem de acesso fácil.
-   Você pode criar códigos de motivo que poderão ser selecionados por seus usuários quando eles criarem ou modificarem cargos.
-   Você pode criar tipos de ação de pessoal e atribuir uma sequência numérica a ações de pessoal.
-   Você pode configurar o fluxo de trabalho de forma que as adições e alterações de cargo possam exigir aprovação.

### <a name="position-duration"></a>Duração da posição
Cada cargo tem um período em que permanece efetivo. Esse período é conhecido como duração. Por exemplo, os cargos de férias podem ter duração de 1º de maio de 2015 até 31 de agosto de 2015.

### <a name="worker-assignments"></a>Atribuições do trabalhador
Quando você atribui um trabalhador a um cargo, você preenche aquele cargo. Você pode atribuir trabalhadores a vários cargos, mas apenas um trabalhador pode ser atribuído a um cargo por vez.

### <a name="reporting-relationships"></a>Relações de subordinação
Os cargos são elementos importantes do nível inferior de uma hierarquia organizacional. Na página **Cargo**, você pode especificar o cargo ao qual um cargo é subordinado. Quando você atribui um trabalhador a um cargo que está subordinado a outro cargo, você cria uma relação de subordinação entre os trabalhadores atribuídos aos dois cargos. Por exemplo, o cargo "Contador-" está subordinado ao cargo "Supervisor de contabilidade". Ana Bowman foi atribuída ao cargo "Supervisor de contabilidade", e Felix Henderson foi atribuído ao cargo "Contador-A". Isso significa que Felix Henderson é subordinado a Ana Bowman. 

Se a organização usar uma hierarquia de matriz ou outra hierarquia personalizada, você poderá configurar tipos de hierarquia de cargos e adicionar relações de subordinação a cargos de cada tipo de hierarquia que você configurou. Por exemplo, Olivia Wilson é um gerente geral na Adventure Works e recebeu o cargo de "gerente geral". Olivia gerencia o desenvolvimento de um produto usado para limpar widgets. Olivia precisa que um contador ajude com as finanças para desenvolver o produto. Portanto, ela recrutou Felix Henderson como seu contador. Felix reporta-se diretamente a Ana Bowman, mas também trabalha com Olivia Wilson em seu trabalho relacionado às finanças para desenvolver o limpador de widgets. 

Para o exemplo anterior, você executaria as seguintes tarefas para configurar a relação de subordinação entre Felix Henderson e Ana Bowman:
1.  Crie um tipo de hierarquia de cargos personalizado chamado "Widget" para criar uma hierarquia que inclui cargos responsáveis por trabalhar no limpador de widgets.
2.  Atribua o cargo Gerente geral como o cargo a quem o Contador-A se reporta na hierarquia Widget.

Use a página **Hierarquia de posições** para exibir a estrutura de subordinação das posições. Se você tiver várias hierarquias de posições, poderá exibir a hierarquia para cada tipo de hierarquia na **Hierarquia de posições**. Além disso, você poderá procurar um cargo por ID do cargo ou pelo nome do trabalhador que está atribuído ao cargo. A **Hierarquia de posições** é uma hierarquia organizacional.

## <a name="date-effective-records"></a>Registros de data de efetivação
Para alguns registros, é possível especificar futuras alterações no registro. As informações a seguir são de data de efetivação.

<table>
<thead>
<tr class="header">
<th>Registros</th>
<th>Informações de data de efetivação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Trabalho</td>
<td><ul>
<li>Algumas informações detalhadas do trabalho</li>
<li>Informações de classificação do trabalho</li>
<li>Informações de remuneração</li>
</ul></td>
</tr>
<tr class="even">
<td>Cargos</td>
<td><ul>
<li>Algumas informações detalhadas do cargo</li>
<li>Atribuições do trabalhador</li>
<li>Durações da posição</li>
<li>Hierarquias do cargo</li>
</ul></td>
</tr>
</tbody>
</table>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
