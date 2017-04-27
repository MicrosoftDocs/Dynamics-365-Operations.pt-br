---
title: Configurando os componentes de um trabalho
description: "Este tópico descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização."
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

# <a name="setting-up-the-components-of-a-job"></a>Configurando os componentes de um trabalho

[!include[banner](includes/banner.md)]


Este tópico descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização. 

Antes de você poder criar trabalhos, você deve configurar algumas informações de referência. Você pode criar um trabalho com apenas um nome. No entanto, ao incluir informações adicionais, como título do trabalho, você fornece valores padrão para as posições atribuídas ao trabalho. Além disso, algumas das informações inseridas por você podem ser usadas para filtrar planos de remuneração para trabalhos específicos. Se deseja configurar a qualificação que pode ser usada para filtrar planos de remuneração para um trabalho específico, você deve configurar funções e tipos de trabalho antes de configurar os trabalhos. Com esses valores padrão disponíveis, você economizará tempo ao adicionar posições ao trabalho. 

Alguns detalhes de trabalho, como o título, tipo e função do trabalho, são de data efetiva. Se você criar um trabalho hoje mas não adicionar esses detalhes posteriormente e verificar o trabalho a partir da data de criação, esses detalhes não aparecerão. Portanto, você deve criar algumas dessas informações de referência antes de solicitá-las. Dessa forma, você pode adicionar as informações a novos trabalhos ao criá-los.

## <a name="job-titles"></a>Títulos de trabalho
Antes de criar trabalhos, você deve configurar cargos para esses trabalhos. As posições herdam cargos dos trabalhos com os quais essas posições estão associadas. 

Manter títulos de trabalho usando a página **Títulos**, que você pode abrir por meio da função Pesquisar. Na página **Títulos **, insira os títulos que você planeja usar em seus trabalhos.

## <a name="job-types"></a>Tipos de trabalho
Você usa tipos de trabalho para agrupar trabalhos semelhantes em categorias. Tipos de trabalhos não são necessários. Entretanto, se planeja usar tipos de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar tipos de trabalho antes de configurar os trabalhos. Alguns exemplos de tipos de trabalho são horário integral e meio período ou salário e pagamento por hora. Você mantém tipos de trabalho usando a página **Tipos de trabalho**. Na página **Tipos de trabalho**, insira um nome e uma breve descrição para o tipo de trabalho. No campo **Status de isenção**, selecione uma das seguintes opções para indicar o status de isenção de trabalhos FLSA (Lei de Padrões Justos de Trabalho) que tem esse tipo de trabalho.

-   **Isenção** – Os trabalhos estão isentos de horas extras de acordo com a FLSA.
-   **Não isento** – Os trabalhos não estão isentos de horas extras de acordo com a FLSA.
-   **Não se aplica** – A cobertura da FLSA não é aplicável.

## <a name="job-functions"></a>Funções de trabalho
Junções de trabalho descrevem categorias funcionais de alto nível e direitos de alto nível relacionados. Junções de trabalho não são necessárias. Você pode usar essas funções, juntamente com tipos de trabalho, a fim de filtrar planos de remuneração para trabalhos específicos. Para associar funções e tipos de trabalho a planos de remuneração, configure regras de qualificação na página **Regras de qualificação**. Você então pode associar ao plano de remuneração um conjunto de níveis aplicáveis à combinação específica de tipo/função de trabalho definida por meio de uma regra de qualificação. (Esses recursos se aplicam aos planos de remuneração fixos e variáveis.) No entanto, se planeja usar funções de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar funções de trabalho antes de configurar os trabalhos. A tabela a seguir mostra alguns exemplos de funções de trabalho.

| Trabalho           | Função de trabalho         |
|---------------|----------------------|
| Gerente de vendas | Gerente de nível médio    |
| Contador    | Profissionais        |

Você mantém funções de trabalho usando a página **Funções de trabalho**. Na página **Funções de trabalho**, insira um código de identificação e uma breve descrição para a função de trabalho.

## <a name="job-tasks"></a>Tarefas do trabalho
Tarefas de trabalho descrevem as tarefas básicas que devem ser realizadas por um trabalhador em um cargo desse trabalho. A mesma tarefa de trabalho pode ser adicionada a vários trabalhos e posições para os trabalhos que usam essas tarefas de trabalho. A tabela a seguir mostra alguns exemplos de tarefas de trabalho.

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
<li><strong>Avaliação de desempenho</strong> – Avaliar o desempenho profissional de cada vendedor.</li>
<li><strong>Avaliação de ausências</strong> – Aprovar ou rejeitar as solicitações ou os registros de ausência de cada vendedor.</li>
</ul></td>
</tr>
<tr class="even">
<td>Contador</td>
<td><strong>Relatório financeiro</strong> – Apresentar relatórios financeiros semanais para o diretor financeiro.</td>
</tr>
</tbody>
</table>

Você mantém tarefas de trabalho usando a página **Tarefas de trabalho**. Na página **Tarefas de trabalho**, insira um nome e uma descrição para a tarefa de trabalho. No campo **Observação**, você tem a opção de inserir informações adicionais. As observações podem ser atualizadas para um trabalho específico sem a necessidade de alteração das observações que você inseriu aqui.

## <a name="areas-of-responsibility"></a>Áreas de responsabilidade
Use as áreas de responsabilidade para indicar as funções de trabalho, os processos e os produtos pelos quais um trabalhador é responsável em um cargo do trabalho. Por exemplo, para um trabalho denominado "Contador", uma área de responsabilidade pode ser "Relatório financeiro do produto A". Você mantém áreas de responsabilidade usando a página **Áreas de responsabilidade**, que você pode encontrar por meio da função Pesquisar. Na página **Áreas de responsabilidade**, insira um nome e uma descrição para a responsabilidade. No campo **Observação**, você tem a opção de inserir informações adicionais. As observações podem ser atualizadas para um trabalho específico sem a necessidade de alteração das observações que você inseriu aqui.




