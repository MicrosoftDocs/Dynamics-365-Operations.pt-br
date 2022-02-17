---
title: Configurar os componentes de um trabalho
description: Este tópico descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7e2c9421646dacc5523f40b28b550881dc4b25dd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068150"
---
# <a name="set-up-the-components-of-a-job"></a>Configurar os componentes de um trabalho


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve os elementos conceituais que um trabalho pode incluir e fornece exemplos de como você pode usar esses elementos na sua organização. 

Antes de você poder criar trabalhos, você deve configurar algumas informações de referência. Você pode criar um trabalho com apenas um nome. No entanto, ao incluir informações adicionais, como título do trabalho, você fornece valores padrão para as posições atribuídas ao trabalho. Além disso, algumas das informações inseridas por você podem ser usadas para filtrar planos de remuneração para trabalhos específicos. Se deseja configurar a qualificação que pode ser usada para filtrar planos de remuneração para um trabalho específico, você deve configurar funções e tipos de trabalho antes de configurar os trabalhos. Com esses valores padrão disponíveis, você economizará tempo ao adicionar posições ao trabalho. 

Alguns detalhes de trabalho, como o título, tipo e função do trabalho, são de data efetiva. Se você criar um trabalho hoje mas não adicionar esses detalhes posteriormente e verificar o trabalho a partir da data de criação, esses detalhes não aparecerão. Portanto, você deve criar algumas dessas informações de referência antes de solicitá-las. Dessa forma, você pode adicionar as informações a novos trabalhos ao criá-los.

## <a name="job-titles"></a>Títulos de trabalho
Antes de criar trabalhos, você deve configurar cargos para esses trabalhos. As posições herdam cargos dos trabalhos com os quais essas posições estão associadas. 

Manter títulos de trabalho usando a página **Títulos**, que você pode abrir por meio da função Pesquisar. Na página **Títulos**, insira os títulos que você planeja usar em seus trabalhos.

## <a name="job-types"></a>Tipos de trabalho
Você usa tipos de trabalho para agrupar trabalhos semelhantes em categorias. Tipos de trabalhos não são necessários. Entretanto, se planeja usar tipos de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar tipos de trabalho antes de configurar os trabalhos. Alguns exemplos de tipos de trabalho são horário integral e meio período ou salário e pagamento por hora. Você mantém tipos de trabalho usando a página **Tipos de trabalho**. Na página **Tipos de trabalho**, insira um nome e uma breve descrição para o tipo de trabalho. No campo **Status de isenção**, selecione uma das seguintes opções para indicar o status de isenção de trabalhos FLSA (Lei de Padrões Justos de Trabalho) que tem esse tipo de trabalho.

-   **Isenção** – Os trabalhos estão isentos de horas extras de acordo com a FLSA.
-   **Não isento** – Os trabalhos não estão isentos de horas extras de acordo com a FLSA.
-   **Não se aplica** – A cobertura da FLSA não é aplicável.

## <a name="job-family"></a>Família do trabalho
Uma família de trabalho é um grupo de trabalhos que envolve trabalho semelhante e que exige treinamento, habilidades, conhecimento e experiência semelhantes. Uma família de trabalho pode ser vinculada a um trabalho na guia rápida **Classificação de trabalho** da página **Trabalhos** e na guia **Geral** da página **Todas os cargos**. As famílias de trabalho podem ser amplas ou específicas, dependendo de suas necessidades comerciais e de relatórios. Alguns exemplos de famílias de trabalho amplas são **Mão-de-obra experiente** e **Mão-de-obra inexperiente**. Alguns exemplos de famílias de trabalhos específicas são **Contabilidade**, **Fabricação** e **Vendas**.

Mantenha famílias de trabalho usando a página **Famílias de trabalho**, que você pode abrir por meio da função de pesquisar. Na página **Família de trabalho**, insira um nome exclusivo para a família e digite uma descrição detalhada que você planeja usar para seus trabalhos.

## <a name="job-functions"></a>Funções de trabalho
Junções de trabalho descrevem categorias funcionais de alto nível e direitos de alto nível relacionados. Junções de trabalho não são necessárias. Você pode usar essas funções, juntamente com tipos de trabalho, a fim de filtrar planos de remuneração para trabalhos específicos. Para associar funções e tipos de trabalho a planos de remuneração, configure regras de qualificação na página **Regras de qualificação**. Você então pode associar ao plano de remuneração um conjunto de níveis aplicáveis à combinação específica de tipo/função de trabalho definida por meio de uma regra de qualificação. (Esses recursos se aplicam aos planos de remuneração fixos e variáveis.) No entanto, se planeja usar funções de trabalho ao configurar regras de qualificação para o gerenciamento de remuneração, você deve configurar funções de trabalho antes de configurar os trabalhos. A tabela a seguir mostra alguns exemplos de funções de trabalho.

| Trabalho           | Função de trabalho         |
|---------------|----------------------|
| Gerente de vendas | Gerente de nível médio    |
| Contador    | Profissionais        |

Você mantém funções de trabalho usando a página **Funções de trabalho**. Na página **Funções de trabalho**, insira um código de identificação e uma breve descrição para a função de trabalho.

## <a name="compensation"></a>Remuneração
Para atribuir um plano de remuneração fixa a um funcionário que tem um cargo em um trabalho, você deve definir os níveis de remuneração no trabalho. O **Nível salarial** é usado quando os valores mínimo, intermediário e máximo são definidos em uma estrutura de remuneração (grade de remuneração). Quando um plano de remuneração fixa é criado, a estrutura de remuneração é selecionada. A estrutura de remuneração também inclui o nível de remuneração. Quando você seleciona um plano de remuneração fixa para um funcionário, os níveis de remuneração disponíveis para seleção dependem do trabalho ao qual o cargo do funcionário está associado. Para obter mais informações sobre como configurar a remuneração, consulte [Planos de remuneração](hr-compensation-overview.md).

## <a name="job-skills"></a>Habilidades de trabalho
As habilidades de trabalho descrevem as habilidades necessárias para executar um trabalho. Um nível de habilidade deve ser associado a todas as habilidades de trabalho. Os níveis de habilidade são definidos pelo usuário. Eles indicam o nível de conhecimento ou proficiência necessário para a habilidade. Por exemplo, as empresas podem configurar níveis numéricos, como 1 a 5, em que **1** indica um principiante e **5** indica um especialista. Como alternativa, as empresas podem configurar níveis que são rotuladas como **Principiante**, **Intermediário** ou **Especialista**. Depois que o nível de habilidade é definido, a importância da habilidade também pode ser definida. Por exemplo, se for necessário que um contador tenha um bom conhecimento de Microsoft Excel, uma habilidade denominada **Conhecimento de Excel** poderá ser criada. O nível de habilidade pode ser definido como **Intermediário** e a importância pode ser definida como a **Mais alta**.

As habilidades que estão em um trabalho podem ser usadas no mapeamento de habilidades. O mapeamento de habilidades pode comparar o conjunto de habilidades necessário para um trabalho e as habilidades associadas a um trabalhador. Em seguida, ele pode determinar uma correspondência de porcentagem, com base nas habilidades sobrepostas. Para saber mais sobre o mapeamento de habilidades, consulte [Configurar habilidades](hr-develop-skills.md). 

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
<li><strong>Avaliação de desempenho</strong> – avaliar o desempenho profissional de cada vendedor.</li>
<li><strong>Avaliação de ausências</strong> – aprovar ou rejeitar solicitações ou registros de ausência de cada vendedor.</li>
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

## <a name="steps-for-creating-a-job"></a>Etapas para criar um trabalho
Consulte o artigo [Definir novos trabalhos](./hr-personnel-define-jobs.md) para obter o procedimento passo a passo para criar um novo trabalho. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
