---
title: ​Organizar sua força de trabalho usando departamentos, trabalhos e posições
description: Departamentos, trabalhos e cargos são elementos organizacionais mantidos dentro da área de Recursos Humanos. Este artigo descreve informações conceituais sobre esses elementos.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cd50bf7e8e03d72d6d0e1e2b0b065a5d9c7a3ef44e96f92a5fc342a0d820d8e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778787"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organizar sua força de trabalho usando departamentos, trabalhos e posições

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Departamentos, trabalhos e cargos são elementos organizacionais mantidos dentro da área de Recursos Humanos. Este artigo descreve informações conceituais sobre esses elementos. 

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
<li><span class="input">Avaliação de desempenho</span> – avaliar o desempenho profissional de cada vendedor.</li>
<li><span class="input">Avaliação de ausências</span> – aprovar ou rejeitar as solicitações ou os registros de ausência de cada vendedor.</li>
</ul></td>
</tr>
<tr class="even">
<td>Contador</td>
<td><span class="input">Relatório financeiro</span> – apresentar relatórios financeiros semanais para o diretor financeiro.</td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a>Funções de trabalho

As funções de trabalho são como tarefas de trabalho. Uma função de trabalho descreve uma ou várias tarefas, obrigações ou responsabilidades atribuídas a um trabalho. As funções de trabalho podem ser atribuídas a trabalhos e usadas para definir e implementar regras de qualificação para planos de remuneração. Exemplos de funções de trabalho são listados na tabela a seguir.

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

Os cargos são elementos importantes do nível inferior de uma hierarquia organizacional. No formulário Cargo, você pode especificar o cargo ao qual um cargo está subordinado. Quando você atribui um trabalhador a um cargo que está subordinado a outro cargo, você cria uma relação de subordinação entre os trabalhadores atribuídos aos dois cargos. Por exemplo, o cargo "Contador-" está subordinado ao cargo "Supervisor de contabilidade". Kim Akers está atribuído ao cargo "Supervisor de contabilidade", e Sanjay Patel está atribuído ao cargo "Contador-A". Isso significa que Sanjay Patel está subordinado a Kim Akers. 

Se a organização usar uma hierarquia de matriz ou outra hierarquia personalizada, você poderá configurar tipos de hierarquia de cargos e adicionar relações de subordinação a cargos de cada tipo de hierarquia que você configurou. Por exemplo, Lori Penor é um gerente geral na Adventure Works e recebeu o cargo de "Gerente geral". Lori gerencia o desenvolvimento de um produto usado para limpar widgets. Lori precisa que um contador ajude com as finanças para desenvolver o produto. Portanto, ela recrutou Sanjay Patel como seu contador. Sanjay reporta-se diretamente a Kim Akers, mas também trabalha com Lori Penor em seu trabalho relacionado às finanças para desenvolver o limpador de widgets. 

Para o exemplo anterior, você executaria as seguintes tarefas para configurar a relação de subordinação entre Sanjay Patel e Lori Penor:
1.  Crie um tipo de hierarquia de cargos personalizado chamado "Widget" para criar uma hierarquia que inclui cargos responsáveis por trabalhar no limpador de widgets.
2.  Atribua o cargo Gerente geral como o cargo a quem o Contador-A se reporta na hierarquia Widget.

Use a hierarquia de cargos para exibir a estrutura de subordinação dos cargos. Se você tiver várias hierarquias de cargos, poderá exibir a hierarquia para cada tipo de hierarquia na hierarquia de cargos. Além disso, você poderá procurar um cargo por ID do cargo ou pelo nome do trabalhador que está atribuído ao cargo. A hierarquia de cargos é uma hierarquia organizacional.

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
<li>Atribuições de trabalhador</li>
<li>Durações da posição</li>
<li>Hierarquias do cargo</li>
</ul></td>
</tr>
</tbody>
</table>

Você pode modificar as informações mencionadas na tabela anterior para um cargo ou um trabalho e especificar uma data em que as modificações feitas no cargo ou no trabalho entrarão em vigor. Por exemplo, um cargo só pode ser atribuído a um trabalhador, mas Sanjay Patel, que está atribuído ao cargo Contador-A, sairá em duas semanas. Joe Healy substituirá Sanjay Patel quando Sanjay deixar a empresa. Mesmo que Sanjay ainda esteja atribuído ao cargo, você poderá atribuir Joe Healy ao mesmo cargo de forma que a atribuição entre em vigor somente após o último dia de Sanjay.







[!INCLUDE[footer-include](../includes/footer-banner.md)]