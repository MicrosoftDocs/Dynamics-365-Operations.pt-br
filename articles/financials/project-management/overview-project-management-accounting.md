---
title: Gerenciamento e contabilidade de projeto
description: A funcionalidade de gerenciamento de projetos e da contabilidade pode ser usada em várias indústrias para proporcionar um serviço, para produzir um produto, ou para obter um resultado.
author: KimANelson
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable; ProjProjectManagementWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82a2da882ba951c2ff6420b726e0546e9073d2e4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1530491"
---
# <a name="project-management-and-accounting"></a>Gerenciamento e contabilidade de projeto

[!include [banner](../includes/banner.md)]

A funcionalidade de gerenciamento de projetos e da contabilidade pode ser usada em várias indústrias para proporcionar um serviço, para produzir um produto, ou para obter um resultado.  

Um projeto é um grupo de atividades que visa oferecer um serviço, produzir um produto ou alcançar um resultado. Os projetos consomem recursos e geram resultados financeiros na forma de receitas ou ativos.

## <a name="projects-across-industries"></a>Projetos em indústrias
A funcionalidade de gerenciamento de projetos e de contabilidade pode ser usada em várias indústrias, conforme mostrado na ilustração.

[![Projetos entre indústrias](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

Em um call center, um bilhete pode ser usado para descrever o conjunto de ações que são necessárias para resolver uma chamada. As empresas de consultoria, como organizações de gerenciamento ou consulta técnica, ou agências de publicidade, referem-se a suas atividades como projetos. Em marketing, uma campanha representa um conjunto de trabalho que deve ser entregue. Na fabricação baseada em projeto, uma ordem de produção relaciona diversos trabalhos que devem ser feitos para gerar alguns bens acabados. Seja qual for o nome usado para eles, esses projetos envolvem recursos, agendamentos e custos, e a funcionalidade de gerenciamento de projeto e de contabilidade do Microsoft Dynamics 365 for Finance and Operations pode ajudar no planejamento, execução e análise desses projetos.

## <a name="project-phases"></a>Fases do projeto
Embora o seguinte fluxo de processo destine-se a projetos externos ou projetos que são concluídos para um ou mais clientes, a funcionalidade também se aplica a projetos internos, apenas de custo. 

![3 estágios de um projeto](./media/3-stages-of-a-project.png) 

Conforme mostra a ilustração acima, o gerenciamento de projetos e de contabilidade pode ser dividido em três fases:

1.  Inicialização
2.  Executar
3.  Analisar

## <a name="initiate-the-project"></a>Iniciar o projeto
Durante a iniciação do projeto, vários processos importantes ocorrem. Você pode usar uma cotação de projeto para comunicar o trabalho, despesas e materiais estimados para o cliente. Você pode registrar as condições de cobrança, limites e os contratos em um contrato de projeto. Você pode usar uma estrutura de detalhamento de trabalho (WBS) para planejar e estimar o trabalho. É possível configurar previsões e orçamentos para orientar a execução do projeto. A ilustração a seguir exibe a estrutura de um projeto.[![estrutura do projeto](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Criar cotações de projeto

Na fase inicial de vendas de um projeto, uma cotação de projeto permite fornecer a um cliente uma oferta não vinculativa. Uma cotação pode englobar elementos, como os itens e os serviços que são cotados, informações básicas de contato, contratos comerciais especiais, descontos e possíveis taxas e subtaxas.

Você também pode emitir uma carta de garantia para uma transação de cotação de projeto entre a organização e o cliente. Depois que a cotação de projeto é criada, você pode criar a solicitação de carta de garantia para o cliente e enviá-la para o banco. Depois que o banco aprova a solicitação, a carta de garantia é emitida ao cliente. 

Para obter mais informações, consulte [Cotações de projeto](project-quotations.md).

### <a name="create-project-contracts"></a>Criar contratos do projeto

Quando você participa de um contrato com um cliente ou outra fonte de financiamento para concluir um projeto, primeiro é necessário criar um contrato de projeto. Em seguida, ao criar o projeto, é necessário atribuí-lo ao contrato correspondente. O tipo de projeto que você cria para um contrato de projeto determina o método de faturamento que é usado para os clientes de projeto. Você pode modificar um contrato de projeto e o projeto relacionado, mas não é possível alterar o tipo de projeto. Para obter mais informações sobre os tipos de projeto, consulte a seção "Criando projetos".

Para obter mais informações sobre os contratos do projeto, consulte [Contratos de projeto](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Criar estruturas de detalhamento de trabalho

O nível de detalhe em uma WBS depende do nível de precisão exigido em estimativas e do nível de acompanhamento obrigatório em relação às estimativas. Projetos que têm tolerância muito baixa para deslizes na agenda ou no custo geralmente exigem uma WBS mais detalhada, e acompanhamento assíduo do progresso do trabalho e dos custos em relação à WBS. 

Para obter mais informações, consulte [Estruturas de detalhamento de trabalho](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Criar previsões de projetos e de orçamentos

Você pode usar a previsão se sua organização tiver uma perspectiva operacional e focar em receitas e custos derivados de transações específicas. No entanto, se a sua organização for mais focada nos valores financeiros, você pode usar o orçamento. Cada método tem suas vantagens. Para obter mais informações, consulte [Previsões de projeto e orçamentos](project-forecasts-budgets.md).

### <a name="create-projects"></a>Criar projetos

Você pode criar seis tipos de projetos no Microsoft Finance and Operations. Cada tipo de projeto é configurado de forma distinta para reconhecimento de custos e receita. A seleção de um tipo de projeto depende da finalidade do projeto. A tabela a seguir descreve o uso típico de cada tipo de projeto.
                                                                                                            
<table>
  <tr>
    <td>Tipo de projeto</th>
    <td>Descrição</th>
  </tr>
  <tr>
    <td>Tempo e material</td>
    <td>A projetos de tempo e material, o cliente for faturado para todos os custos que são contraídos em um projeto. Esses custos incluem custos de horas, despesas, itens e taxas.</td>
  </tr>
  <tr>
    <td>Preço fixo</td>
    <td>Em projetos de preço fixo, as faturas consistem em transações por conta. Um projeto de preço fixo é faturado de acordo com um plano de cobrança que se baseia em um contrato de projeto. A receita para um projeto de preço fixo pode ser calculada e lançada no projeto usando o método de porcentagem concluída. Como alternativa, a receita pode ser calculada e lançada quando o projeto for concluído, usando o método de contrato concluído. As empresas geralmente podem tirar proveito de usar o valor do trabalho em andamento (WIP) para calcular o nível de conclusão de um projeto ou um grupo de projetos.</td>
  </tr>
  <tr>
    <td>Investimento</td>
    <td>Projetos de investimento são os projetos que não geram ganhos imediatos. São usados nos projetos internos de longo prazo em que os custos devem estar capitalizados. Apenas o custo de itens, as horas e as despesas podem ser registrados em um projeto de investimento. Os custos em um projeto de investimento são rastreados e controlados com o recurso de previsão. Os projetos de investimento podem ser configurados com uma capitalização máxima opcional. Como um projeto de investimento em andamento, você registra os custos nas contas WIP, na qual os custos são mantidas até que o projeto foi preenchido. Quando o projeto é eliminado, transfere-se o valor do WIP a um ativo fixo, uma conta contábil ou a um novo projeto. <br></br> <strong>OBSERVAÇÃO:</strong> as transações em projetos de investimento não são mostradas nas páginas <strong>Lançar custos<strong>, <strong>Acumular receita</strong> ou <strong>Criar propostas de fatura</strong>.</td>
  </tr>
  <tr>
    <td>Projeto de custo</td>
    <td>Como projetos de investimento, os projetos de custo são usados normalmente rastrear projetos internos, e apenas as horas, despesas, e os itens podem ser registrados para projetos de custo. No entanto, os projetos de custo normalmente têm duração mais curta do que os projetos de investimento. Além disso, ao contrário dos projetos de investimento, os projetos de custo não podem ser capitalizados nas contas de balanço. Em vez disso, as transações do projeto são lançadas em contas de lucros e perdas. <br></br> <strong>OBSERVAÇÃO:</strong> as transações nos projetos de custo não são mostradas nas páginas <strong>Lançar custos</strong>, <strong>Acumular receita</strong> ou <strong>Criar propostas de fatura</strong>. Como os projetos de custo são usados normalmente para rastrear projetos internos, geralmente, não precisam ser associados a uma conta de cliente. No entanto, se sua configuração exigir que sejam criadas requisições de itens para ordens de compra, será necessário associar o projeto de custo a um cliente. Essa associação é necessária porque as requisições de itens são gerenciadas como linhas da ordem de venda, e o sistema requer que um cliente seja especificado. No entanto, essa configuração não resultará na criação automática de requisições de itens de uma ordem de compra. Para projetos de custo, a configuração <strong>Criar requisição de itens</strong> é ignorada. Se for necessária uma requisição de itens em um projeto de custo, será possível criar uma manualmente, desde que um cliente esteja associado ao projeto.</td>
  </tr>
  <tr>
    <td>Interno</td>
    <td>Os projetos internos são usados ao custo de controle em um projeto interno que é a sua organização. Projetos internos podem fornecer uma ferramenta de planejamento para gerenciar o consumo de recursos. <br></br><strong>OBSERVAÇÃO:<strong> as transações em projetos internos não são refletidas na página <strong>Acumular receita</strong> ou <strong>Criar propostas de fatura</strong>.</td>
  </tr>
  <tr>
    <td>Hora</td>
    <td>Os projetos por tempo são usados para controlar os tempos associados com as atividades não cobráveis e não produtivas, como um projeto rastrear horas doentes para trabalhadores. Os projetos das transações não são lançados no tempo até o razão. Em vez disso, é incluído nos relatórios de trabalho de utilização. Apenas as transações de hora podem ser registrados no tempo projetos. Use um diário ou uma folha de ponto de horas para registrar essas horas no projeto. Após as horas serem registradas, elas aparecem como transações de projeto, mas não tem transações de comprovante correspondentes. <br></br><strong>OBSERVAÇÃO:</strong> as transações nos Projetos de tempo não são refletidas nas páginas <strong>Lançar custos</strong>, <strong>Acumular receita</strong> ou <strong>Criar propostas de fatura</strong>.</td>
  </tr>
</table>


### <a name="assign-workers-categories-and-resources"></a>Atribuir funcionários, categorias, e recursos

É possível agendar recursos de funcionário com base nos requisitos e na programação de um projeto ou nas habilidades e disponibilidade dos funcionários. Ao usar o agendamento de recursos, você pode implantar de forma eficiente e efetiva trabalhadores da sua organização. Você pode encontrar rapidamente os funcionários os mais qualificados disponíveis para trabalhar no projeto. Você também pode ver facilmente como os funcionários podem ser utilizados de forma mais eficiente durante o projeto. 

Veja a seguir algumas das formas que você pode usar a funcionalidade de programação de recurso:

-   Usar informações sobre os atributos de um trabalhador, como formação educacional, habilidades, certificações e experiência em projetos, para corresponder o trabalhador aos requisitos de um projeto.
-   Usar informações sobre o calendário e a disponibilidade de um trabalhador para corresponder a agenda do trabalhador ao calendário do projeto.
-   Examine a capacidade de cada trabalhador e determinar como a capacidade está sendo usada. Por exemplo, se um trabalhador estiver parcialmente subutilizado, ele poderá ser atribuído a um projeto de acordo com sua disponibilidade e atributos.
-   Examine a disponibilidade do funcionário para verificar se não há conflitos de calendário com as atribuições.
-   Examine as informações sobre a utilização do funcionário de forma resumida (por exemplo, por departamento ou por funcionário), ou em uma exibição detalhada (por exemplo, por trabalhadores em um departamento ou por detalhe semanal de cada funcionário).
-   Modifique as atribuições de recursos para diversas unidades de tempo, como dia, semana ou mês, a fim de otimizar como os trabalhadores são usados.

## <a name="execute-the-project"></a>Executar o projeto
Durante a execução do projeto, os membros da equipe ou gestores registram o trabalho e as despesas que foram incorridos, usando a folha de ponto, relatórios de despesas, e outros documentos comerciais. Os gerentes de projeto têm as ferramentas que permitem monitorar o consumo dos valores orçados para o projeto. Os gerentes de projeto também podem solicitar, separar, ou obter materiais para projetos usando ordens de compra e outros documentos comerciais. As faturas são preparadas e aprovadas, de forma que os clientes possam ser cobrados pelo trabalho em andamento. Além disso, a receita é reconhecida durante esse processo para afetar as finanças da organização.

### <a name="manage-work-breakdown-structures"></a>Gerenciar estruturas de detalhamento de trabalho

Um WBS é uma descrição do trabalho que será concluído para um projeto. Um WBS é uma hierarquia de tarefas. Representa não apenas o trabalho para cada tarefa, mas também o tamanho, o custo, e a duração da tarefa. 

Para obter mais informações, consulte [Estruturas de detalhamento de trabalho](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Gerenciar previsões e orçamentos de projeto

Há duas maneiras de gerenciar e controlar seus projetos: previsões e orçamentos de projeto. Você pode usar a previsão se sua organização tiver uma perspectiva operacional e focar em receitas e custos derivados de transações específicas. No entanto, se a sua organização for mais focada nos valores financeiros, você pode usar o orçamento.

Para obter mais informações, consulte [Previsões de projeto e orçamentos](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Criar ordens de produção

Uma ordem de produção relacionada a um projeto pode ser vinculada a uma ordem de venda ou a uma requisição de item usando o método de item concluído ou método de item consumido. Além disso, se a ordem de produção tiver sido criada manualmente, não haverá vínculo entre a ordem de produção e a ordem de venda ou requisição de item (sem vínculo com a ordem). No entanto, se a ordem de produção for criada automaticamente para atender a uma ordem de venda ou uma requisição de item, haverá um link entre a ordem de produção e a ordem de venda ou requisição de item (vínculo com a ordem). 

Com base nas combinações desses fatores, use um dos seguintes métodos:

- **Item concluído/vincular a ordem** – Vincular o projeto a uma ordem de venda ou a uma requisição de item. Ao usar esse método, os custos reais do projeto são lançados quando a ordem de venda é faturada ou quando a guia de remessa é atualizada para a requisição de item. O custo é lançado como item concluído.
- **Item concluído/sem vínculo com a ordem** – Os custos reais não podem ser lançados até que o ciclo de produção de um item tenha o status de **Concluído**. O custo do item concluído é lançado como uma única transação.
- **Item consumido/vincular a ordem** – Vincular o projeto a uma requisição de item. Com esse método, você pode ver os custos reais do projeto quando a produção estiver com o status de **Iniciado** ou for reportada como concluída. Os custos são lançados como várias transações de item de projeto para matérias-primas e horas consumidas pela produção. Quando a guia de remessa é atualizada para a requisição de item, nenhum custo do projeto é lançado. Você também pode definir o nível de hierarquia da lista de materiais (BOM) em que os projetos da produção são controlados.
- *<strong><em>Item consumido/sem vínculo com a ordem</em></strong>* – Vincula o projeto a um requisito do item. Com esse método, você pode ver os custos reais do projeto quando a produção estiver com o status de <strong>Iniciado</strong> ou for reportada como concluída. Os custos são lançados como várias transações de item de projeto para matérias-primas e horas consumidas pela produção. Você também pode definir o nível de hierarquia da BOM em que os projetos da produção são controlados.

### <a name="procure-products-and-services"></a>Adquirir produtos e serviços

A compra e venda de itens são atividades comuns de muitas empresas concentradas em projetos.

#### <a name="purchase-orders-for-projects"></a>Ordens de compra para projetos

A finalidade da ordem de compra determina quando ela é consumida e, portanto, quando os itens são cobrados em um projeto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Finalidade</th>
<th>Consumo de itens</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Criar uma ordem de compra diretamente.</td>
<td>Comprar itens de um fornecedor externo para consumo em um projeto. Você pode criar a ordem de compra das seguintes maneiras:
<ul>
<li>No próprio projeto. Neste caso o projeto já está definido para a ordem de compra.</li>
<li>Navegando na ordem de compra de projeto. Você deve selecionar o fornecedor e o projeto para os quais a ordem de compra será criada.</li>
</ul></td>
<td>Os itens serão consumidos quando a fatura do fornecedor for atualizada.</td>
</tr>
<tr class="even">
<td>Criar uma ordem de compra a partir de uma ordem de venda.</td>
<td>Comprar itens ao criar uma ordem de venda a partir de um projeto.</td>
<td>Os itens serão consumidos quando a ordem de venda for faturada para o cliente.</td>
</tr>
<tr class="odd">
<td>Criar uma ordem de compra a partir de uma requisição de itens.</td>
<td>Comprar itens ao criar uma requisição de item a partir de um projeto.</td>
<td>Os itens serão consumidos quando a guia de remessa da requisição de itens for atualizada.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Ordens de venda para projetos

No gerenciamento de projetos e na contabilidade, você pode registrar o consumo de itens de várias maneiras. Você pode vender ou comprar itens de um projeto, ou reservar itens para um projeto. 

Você pode encomendar itens no estoque de uma empresa para o consumo em um projeto. Como alternativa, ou você pode comprar itens de um fornecedor externo. Os itens podem ser consumidos em todos os tipos de projeto, exceto os projetos por tempo. 

A maneira como você encomenda os itens depende de onde você está encomendando-os:

-   Para encomendar itens do estoque da empresa, você deve inserir a ordem como um requisito de item. Se usar a página **Requisitos de item**, poderá configurar o requisito de forma que receba os itens como entregas parciais. Portanto, você pode adiar o consumo de uma quantidade de itens até que eles sejam necessários.
-   Para encomendar itens de um fornecedor externo, você deve criar a ordem como uma ordem de compra na página **Ordem de compra**.

> [!NOTE] 
> A guia de remessa de uma ordem de venda relacionada a um projeto não poderá ser cancelada se os itens já tiverem sido marcados para remessa. 

A tabela a seguir lista os métodos para encomendar itens e descreve como os itens são consumidos.

| Método            | Finalidade                                                                                                                                                        | Consumo de transações de item                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Ordem de venda       | Inserir uma transação diretamente em um projeto por tempo ou material.                                                                                                   | As transações de itens são consumidas quando a fatura do cliente é lançada.                                                                               |
| Diário de estoque | Inserir e manter rapidamente registros de item. Se, por exemplo, você quiser inserir um requisito de item com base em uma lista impressa, o diário de estoque poderá ser aplicado. | As transações de itens são consumidas quando o diário é lançado.                                                                                        |
| Requisição de itens  | Insira os itens que não serão consumidos imediatamente. Esse método permite que você controle o número de itens que foram consumidos em um único registro de requisição de itens.    | As transações de itens são consumidas quando a guia de remessa é atualizada. Ou seja, a requisição de item é criada quando a guia de remessa é lançada. |
| Ordens de compra   | Insira transações em um dos três locais, dependendo do método de compra.                                                                              | As transações de itens são consumidas quando a guia de remessa é atualizada, ou quando o cliente ou fornecedor é faturado.                                      |

### <a name="process-project-invoices"></a>Processar faturas do projeto

O tipo de projeto determina qual procedimento de faturamento deve ser aplicado. Apenas os dois tipos de projeto externos, por tempo e material e de preço fixo, podem ser faturados. Os projetos por tempo e material e de preço fixo são sempre anexados a um contrato de projeto. 

Antes de criar uma fatura de cliente para um projeto, é possível criar uma fatura preliminar ou uma proposta de fatura. Em uma proposta de fatura, você pode selecionar as transações de projeto a serem incluídas em uma fatura de projeto. Você pode revisar os detalhes da fatura antes de lançar a fatura do projeto e enviá-la ao cliente ou a outra fonte de financiamento. 


Para obter mais informações sobre como processar faturas de projeto, consulte [Faturamento de projeto](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Calcular o custo de conclusão de um projeto

Ao criar uma previsão, é possível escolher o método usado para calcular o custo de conclusão do projeto. Selecione um método no campo **Método de custo até a conclusão** na página **Criar estimativa**. O método escolhido é aplicado individualmente para cada linha na estimativa de custo. Quando uma linha tiver um status de **Criado**, é possível alterar o método aplicado a ela na página **Previsão de custo**. 

A tabela a seguir descreve os métodos para calcular o custo para conclusão de um projeto.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Custo total – real</td>
<td>Os custos estimados devem ser inseridos manualmente. Após a coluna <strong>Custo total</strong> ou <strong>Quantidade total</strong> da página <strong>Estimativa de custo</strong> for completada, os custos reais são subtraídos dos totais inseridos pelo usuário. O resultado é o custo para concluir o projeto. Normalmente, o andamento de custos não é rastreado, por exemplo, com base no número de estadias de hotéis e refeições registradas em cada período. Em vez disso, o monitoramento se baseia em uma comparação entre o valor total de horas estimadas. Esta abordagem não exige um modelo de previsão e os custos totais ou a quantidade total podem ser alterados manualmente. Quando um valor é inserido na coluna <strong>Custo total</strong> ou <strong>Quantidade total</strong>, o Finance and Operations compara esse valor com as transações reais lançadas no período e, em seguida, reduz o valor na coluna <strong>Quantidade a ser concluída</strong> ou <strong>Custo até a conclusão</strong>.</td>
</tr>
<tr class="even">
<td>Orçamento total – Real</td>
<td>Os custos reais são comparados com o modelo de previsão que você selecionar para determinar o custo. Este método usa um modelo de orçamento total com transações de previsão. Para obter uma exibição mais precisa do projeto, você pode ajustar o modelo de orçamento quando o projeto estiver em andamento. Se você precisar ajustar a previsão, siga este processo geral:
<ol>
<li>Copiar transações de previsão em outro modelo de previsão.</li>
<li>Comparar transações de previsão com as transações reais.</li>
<li>Mantenha, reduza ou aumente as estimativas para o próximo período.</li>
</ol>
O Finance and Operations não diminui automaticamente as previsões esperadas. Portanto, recomendamos que você mantenha um modelo de previsão original no projeto de preço fixo para estabelecer uma linha de base para comparação quando o projeto for concluído. 
<br></br> <strong>OBSERVAÇÃO:</strong> ao selecionar este método, use pelo menos dois modelos de previsão. Um modelo deve conter a previsão original. Para o outro modelo, você deve copiar transações de previsão de outro modelo. Este método é válido somente para projetos de investimento e de preço fixo.</td>
</tr>
<tr class="odd">
<td>Orçamento restante</td>
<td>Este método usa um modelo de orçamento restante para calcular o custo para a conclusão do projeto. Ao usar esse método, os custos reais e os valores previstos no modelo de orçamento restante serão adicionados em conjunto. O resultado é um custo total. Antes de usar este método, um modelo de orçamento restante deverá ser configurado para deduzir as transações com base nas transações reais que são registradas no sistema. Na página <strong>Modelos de previsão</strong>, certifique-se de que os campos estejam marcados no grupo <strong>Redução automática de previsão</strong>. Normalmente, um orçamento restante é copiado do orçamento original. Quando as transações são inseridas, as transações do orçamento restante são reduzidas. Como o projeto em andamento, se você determina que o orçamento restante será ajustado, poderá carregar transações de previsão para o orçamento restante. <br></br> <strong>OBSERVAÇÃO:</strong> este método só pode ser aplicado caso um modelo de previsão esteja anexado à previsão.</td>
</tr>
<tr class="even">
<td>Conforme estimativa anterior</td>
<td>O mesmo método de previsão usado no período anterior é aplicado. Este método exige um modelo de previsão se o período anterior exigir um modelo de previsão.</td>
</tr>
<tr class="odd">
<td>Definir custo a ser concluído como zero</td>
<td>Normalmente, este método é usado antes da eliminação do projeto estimado. Este método corresponde as previsões totais com as transações reais lançadas e limpa a coluna <strong>Custo até a conclusão</strong>. A porcentagem resultante de conclusão é sempre 100 por cento. O campo <strong>Previsão</strong> não é marcado para cada linha de custo que você cria e a previsão total é copiada da previsão de custo anterior. O consumo real para o período previsto é deduzido do custo para concluir o projeto. Este método não exige um modelo de previsão.</td>
</tr>
<tr class="even">
<td>A partir do modelo de custo</td>
<td>O método de custo até a conclusão configurado no modelo de custo associado ao projeto previsto selecionado é aplicado.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analisar o projeto
No nível mais básico, um projeto é usado para agrupar as transações que registram custos, e lança esses custos na contabilidade. 

Geralmente, essas transações são o resultado de documentos comerciais, como folhas de ponto, relatórios de despesas, faturas de fornecedor, ou transações de estoque. O ciclo de vida de um projeto começa geralmente com estimativas, previsões, e orçamentos que ajudam a planejar e antecipar o trabalho e o impacto financeiro do projeto. Conforme você analisa um projeto, é possível avaliar não apenas as transações que ocorreram durante o projeto, mas também a exatidão de suas estimativas e previsões, as taxas de utilização dos membros da equipe do projeto, e o êxito total do projeto.

### <a name="analyze-cash-flow"></a>Analisar fluxo de caixa

O monitoramento do fluxo de caixa permite que você monitore tanto o fluxo de caixa previsto, como o real de um projeto. Você pode revisar fluxos de caixa quando um projeto está em progresso ou você pode exibir os fluxos de caixa de um projeto concluído. 

Monitorando fluxos de caixa, você pode avaliar um único projeto, usar relatórios para exibir vários projetos, e fluxos de caixa do projeto para transferir previsões de fluxo de caixa na contabilidade.

#### <a name="cash-inflow-forecasting"></a>Caixa na previsão de fluxo

Com base na sua configuração, é possível prever as entradas de pagamento à vista para um projeto selecionado. Por exemplo, se a data do projeto for 5 de março de 2012 e você faturar em 31 de março de 2012, será possível prever a data de vencimento e a data de pagamento de vendas esperada:

-   **Data do projeto:** 5 de março de 2012.
-   **Data da fatura:** 31 de março de 2012. Esta data é determinada com base na frequência da fatura. Neste exemplo, você pode definir a frequência da fatura para o mês atual. Isso significa que todas as transações lançadas no mês de março são faturadas no último dia do mês.
-   **Data de vencimento:** 14 de abril de 2012. Esta data é determinada com base nos termos do pagamento definidos para o projeto. Para este exemplo, você selecionou uma condições de pagamento de 14 dias. Sendo assim, 14 dias são adicionados à data da fatura para chegar em uma data de vencimento de 14 de abril de 2012.
-   **Data de pagamento de vendas estimado:** 27 de abril de 2012. Essa data é calculada adicionando o número de dias no campo **Dias de buffer gerais** na página **Gerenciamento de projeto e parâmetros de contabilidade**  ao número de dias no campo **Dias do buffer individual** na página **Contratos de projeto** e, em seguida, adicionando o total ao número de dias no campo **Data de vencimento**. Neste exemplo, você inseriu **3** no campo **Dias do buffer geral** e **10** no campo **Dias do buffer individual**. Sendo assim, 13 dias são adicionados à data de vencimento para chegar a uma data de pagamento de vendas esperada de 27 de abril de 2012.

Os dias de buffer geral dos podem substituir os dias de buffer ou serem adicionados aos dias de buffer individual:

-   Para usar os dias do buffer geral como uma substituição para os dias do buffer individual, insira o número médio de dias entre a data de vencimento e a data atual do pagamento dos clientes.
-   Para adicionar os dias do buffer geral aos dias do buffer individual, no campo **Dias do buffer geral**, insira sua previsão para o número de dias entre o dia que o cliente envia o pagamento e o dia que a organização recebe o pagamento.

Configurar os dias do buffer individual no contrato de projeto. Os dias são calculados com base nas datas de vencimento das duas faturas e na experiência da empresa com o padrão de pagamento do cliente.

#### <a name="actual-cash-inflow"></a>Entrada de caixa real

O fluxo de caixa real é semelhante à previsão, mas você pode iniciar os cálculos a partir da primeira data da fatura. Veja a seguir um exemplo:

-   **Data da fatura:** 2 de março de 2012.
-   **Data de vencimento:** 16 de março de 2012. As condições de pagamento são definidas para 14 dias.
-   **Data de pagamento de vendas estimado:** 29 de março de 2012. O cálculo inclui três dias de buffer geral e 10 dias de buffer individual.

#### <a name="cost-forecasting"></a>Previsão de custo

Com base nos dias definidos, a data do pagamento de custo pode ser diferente da data do projeto. Nesse caso, a data de pagamento de custo será calculada adicionando o número de dias da data do projeto ao número de dias nas condições de pagamento. 

Por exemplo, a data do projeto da transação é 5 de março de 2012, e os seguintes prazos de pagamento são definidos:

-   **Horas:** Mês atual (**M**)
-   **Despesas:** 14 dias (**D14**)
-   **Itens:** 30 dias (**D30**)

Com base nessas configurações, a data de pagamento de custo é apresentada a seguir para cada tipo de transação:

-   **Horas:** 31 de março de 2012, que é o último dia do mês selecionado.
-   **Despesas:** 19 de março de 2012, que é 14 dias após a data da transação.
-   **Itens:** 4 de abril de 2012, que é 30 dias após a data da transação.

> [!NOTE] 
> A data de vencimento da ordem de compra é baseada na transação de fornecedor quando a ordem de compra do projeto é criada. A data de vencimento não é determinada por quaisquer configurações padrão. 

A data de pagamento de custo não é calculada com base em dias de buffer. Após um projeto ser concluído, quando todos os custos e faturamentos estiverem concluídos, tanto os custos como as vendas são lançados nas contas de lucros e perdas. 

Quando todas as vendas e faturas de fornecedor forem concluídas, será possível exibir a relação entre os campos na página **Fluxo de caixa** e os campos da página **Demonstrativos de projeto**.

:::row:::
    :::column:::
        #### Cash flow page
        - Cash inflows 
        - Cash outflows
        - Net cash flows
    :::column-end:::
    :::column:::
        #### Project statements page
        - Revenue
        - Total cost
        - Gross margin
    :::column-end:::
:::row-end:::

### <a name="review-costs"></a>Analisar custos

Você pode monitorar os custos incorridos pela empresa durante um projeto na página **Controle de custos**. Comparando o custo orçado original do projeto com o custo real atual e o custo comprometido, você pode determinar se o projeto está sob controle, acima do orçamento ou no orçamento. 

> [!NOTE] 
> Ao usar a página **Controle de custos** para exibir o status atual dos custos do projeto, use os modelos de previsão selecionados para os orçamentos original e restante. Se você selecionar outros modelos de previsão durante o cálculo de custos, os resultados não serão exatos.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Exibindo os valores orçados restantes

Se **Orçamento restante** for selecionado como o método de controle de custos na página **Parâmetros de gerenciamento de projetos e de contabilidade**, página **Controle de custos** calcula os custos que não foram lançados como reais ou marcados como confirmados. Especificamente, os valores na guia **Geral** no painel inferior da página **Controle de custos** são calculados das seguintes formas:

-   **Custo real** – O valor total gasto no projeto na linha de custo selecionada. O valor do custo real é calculado na página **Atualizações do razão**.
-   **Custo comprometido** – O montante de despesas suplementares que a entidade legal se comprometeu a pagar. Os valores específicos do custo comprometido são calculados na página **Custos comprometidos**.
-   **Orçamento restante** – O valor orçado original que ainda está disponível para a linha de custo selecionada. O valor do orçamento restante é calculado na página **Exibição de contabilidade**.
-   **Custo total** – A soma dos valores de custo real, custo comprometido, e orçamento restante.

Na página **Controle de custos**, na guia **Desvio**, você pode exibir uma comparação do custo total esperado com o orçamento original. Essa comparação mostra todas as diferenças entre esses valores. Consequentemente, você pode ver onde os dados não coincidem. Os valores dos desvios são calculados destas maneiras:

-   **Orçamento original** – O valor orçados originalmente para a linha de custo selecionada. O valor do orçamento original é calculado na página **Exibição de contabilidade**.
-   **Custo total** – A soma do custo real, do custo comprometido e do orçamento restante, conforme relatada na guia **Geral**.
-   **Desvio** – A diferença entre o custo total e o orçamento original.
-   **Variação baseada em quantidade** – A diferença total entre a previsão original e a previsão total. Essa diferença pode ser expressa matematicamente como (Quantidade total da previsão) * (Preço médio original – Preço médio total). Este cálculo se aplica apenas às horas do projeto.
-   **Variação baseada em preço** – A diferença total entre a previsão original e a previsão total. Essa diferença pode ser expressa matematicamente como (Preço original da previsão) * (Quantidade original da previsão – Quantidade total da previsão). Este cálculo se aplica apenas às horas do projeto.

#### <a name="viewing-the-total-budgeted-amounts"></a>Exibindo os valores orçados totais

Se **Orçamento Total** for selecionado como o método de controle de custo na página **Parâmetros de gerenciamento de projetos e contabilidade**, a página **Controle de custos** calcula os custos reais e os custos totais do projeto para ajudar a detectar qualquer diferença entre os dois. Especificamente, na página **Controle de custos**, os valores nas colunas do painel inferior da guia **Geral** são calculados das seguintes formas:

-   **O custo total orçado** – O valor orçado total da linha de custo selecionada.
-   **Custo real** – O valor total dos custos incorridos no projeto até o momento para as linhas de custo selecionadas.
-   **Custo comprometido** – O valor total comprometido para a linha de custo selecionada.
-   **Variação** – A diferença entre a soma dos custos reais e comprometidos e o custo total. A variação mostra se os custos adicionais devem ser especificados para o orçamento total.

Na página **Controle de custos**, na guia **Desvio**, você pode exibir a diferença entre o orçamento total e o orçamento original com referência aos seguintes campos:

-   **Orçamento original** – O valor orçados originalmente para a linha de custo selecionada. O orçamento original é calculado na página **Exibição de contabilidade**.
-   **Custo total orçado** – O custo total orçado originalmente para a linha de custo. O custo total orçado é calculado na página **Exibição de contabilidade**.
-   **Desvio** – O desvio para a linha de custo. Este valor é calculado subtraindo-se o custo total do orçamento original.
-   **Variação baseada em quantidade** – A diferença total entre o orçamento original e o orçamento total. Esse valor é calculado subtraindo-se as horas do orçamento total das horas do orçamento original e, em seguida, multiplicando-se a diferença pelo preço de custo orçado original. Essa diferença pode ser expressa matematicamente como (Preço de custo orçado original) * (horas do orçamento original – horas do orçamento total). Este cálculo se aplica apenas às horas do projeto.
-   **Variação baseada em preço** – Este valor é calculado subtraindo-se o total de horas do orçamento das horas do orçamento original e, depois, multiplicando-se a diferença pelo número total de horas consumidas. Essa diferença pode ser expressa matematicamente como (Total de horas consumidas) * (horas do orçamento original – horas do orçamento total). Este cálculo se aplica apenas às horas do projeto.

### <a name="analyze-utilization"></a>Analisar utilização

A taxa de utilização é o percentual de tempo que um funcionário realiza trabalho produtivo ou faturável em um período específico. As horas faturáveis são as horas do funcionário que pode ser cobrado a um cliente específico. 

A taxa de utilização de um funcionário é calculada dividindo o número de horas faturáveis pelo número de horas de trabalho em um período específico. Por exemplo, se um funcionário tem 30 horas faturáveis em um período e o número de horas de trabalho no mesmo período de tempo for 40, a taxa de utilização do trabalhador é 75%. 

A o calcular a taxa de utilização de um funcionário, você pode calcular a taxa faturável ou a taxa de eficiência:

-   **Taxa faturável** – A diferença entre horas faturáveis e horas não faturável ou horas normais.
-   **Taxa de eficiência** – A diferença entre horas produtivas e horas não produtivas ou horas normais. Horas produtivas são as horas que o funcionário gasta contribuindo com um projeto específico. Horas produtivas são faturadas normalmente a clientes, exceto no caso de projetos internos. as horas não produtivas são faturadas nunca a um cliente.

Calcule as taxas de utilização na página **Utilização de horas**. Os cálculos se baseiam nas preferências padrão. Essas preferências também especificam como as horas são calculadas atribuindo **Utilização** ou **Carga** a cada tipo de projeto. Isso se aplica aos cálculos de taxa faturável e cálculos de taxa de eficiência.

-   **Utilização** – As horas relatados para o tipo de projeto selecionado são sempre consideradas para a utilização faturável ou de eficiência.
-   **Carga** – As horas relatados para o tipo de projeto selecionado são sempre consideradas para a utilização não faturável ou de não eficiência.
-   **De acordo com a propriedade de linha** – As propriedades da linha de uma transação de hora específica determinam se a hora é considerada para a utilização faturável e de eficiência.
-   **Não incluso** – As horas não são fatoradas no cálculo da utilização faturável e de eficiência.

Na página **Utilização de horas**, junto com a porcentagem da taxa de utilização geral de um funcionário ou projeto, você pode exibir o número de horas usado para os cálculos de taxa de utilização para cada um dos seguintes tipos de horas:

-   **Horas não inclusas** – Essas horas não estão inclusas na taxa de utilização de horas.
-   **Horas inclusas** – Essas horas são calculadas adicionando as horas de utilização e horas de carga. Essas horas são incluídas na taxa de utilização.
-   **Horas de carga** – Se você estiver calculando uma taxa faturável, essas horas são as mesmas que as horas não passíveis de cobrança. Se você estiver calculando uma taxa de eficiência, essas horas são as mesmas que as horas não produtivas.
-   **Horas de utilização** – Se você estiver calculando uma taxa faturável, essas horas são as mesmas que as horas passíveis de cobrança. Se você estiver calculando uma taxa de eficiência, essas horas são as mesmas que as horas produtivas.

A o calcular a taxa de utilização para um funcionário, você pode usar horas normais ou horas incluídas. Se você usar horas incluídas, será necessário garantir que os funcionários registrem todo o horário de trabalho para os períodos de folha de ponto, pois o cálculo é expresso como uma porcentagem das horas inseridas. A o calcular a taxa de utilização de horas para um projeto, um contrato de projeto, um registro de cliente, ou uma categoria, você deve usar horas incluídas para o cálculo.

### <a name="review-project-statements"></a>Revisar demonstrativos de projeto

Você pode criar um demonstrativo de projeto para exibir um instantâneo rápido do andamento de um projeto. Ao executar um demonstrativo de projeto, é possível especificar os critérios usados para calcular o demonstrativo fazendo seleções na guia **Geral** na página **Demonstrativos de projeto**. Você pode optar por incluir ou excluir as seguintes informações:

-   Tipos de projeto
-   Tipos de transação
-   Data do projeto/data do razão
-   Dados

Depois que o demonstrativo for calculado, você pode exibir as seguintes informações nas guias da página **Demonstrativos do projeto**:

-   **Geral** – Informações gerais sobre a estrutura básica de lucros e perdas do projeto.
-   **Lucro e perda** – Informações sobre receita acumulada.
-   **WIP** – Informações sobre saldos de conta WIP.
-   **Consumo** – Informações sobre o consumo de horas, itens, despesas, e de transações de folha de pagamento.
-   **Fatura** – Informações sobre faturas e faturamento por conta.
-   **Taxa horária** – Taxas horárias das horas lançadas nas contas de receita e custo.
