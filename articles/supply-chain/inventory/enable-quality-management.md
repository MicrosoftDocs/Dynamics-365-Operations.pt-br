---
title: Visão geral do gerenciamento de qualidade
description: Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2d51c659d9d06f075458359d81de978e7a6d14b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814389"
---
# <a name="quality-management-overview"></a>Visão geral do gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.

O gerenciamento de qualidade pode ajudar a gerenciar o tempo de resposta ao lidar com produtos fora de conformidade, independentemente do ponto de origem. Como os tipos de diagnóstico são vinculados ao relatório de correção, o Supply Chain Management pode agendar tarefas para corrigir problemas evitar que se repitam.

Além da funcionalidade para gerenciar a não conformidade, o gerenciamento de qualidade inclui a função de rastrear saídas por tipo de problema (até mesmo problemas internos), e para identificar soluções como a curto prazo ou a longo prazo. As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem ideias sobre o histórico de saídas anteriores de não conformidade e as soluções que foram usadas para corrigi-los. Você pode usar dados históricos para revisar a eficácia das medidas de qualidade anteriores e determinar as medidas apropriadas a serem usadas no futuro.

Ao configurar uma associação de qualidade, o Supply Chain Management pode gerar ordens de qualidade para vários processos comerciais, eventos, e condições. A associação de qualidade pode cobrir item específico, um grupo específico de itens ou todos os itens.

## <a name="examples-of-the-use-of-quality-management"></a>Exemplo de utilização do gerenciamento de qualidade
O gerenciamento de qualidade é flexível e pode ser implementado de várias maneiras para atender aos requisitos de níveis específicos das operações da cadeia de suprimento. Os exemplos a seguir ilustram as possíveis aplicações destes recursos:

-   Iniciar automaticamente um processo de controle de qualidade com base em critérios pré-definidos (após o registro do depósito de uma ordem de compra de um fornecedor específico).
-   Bloquear o estoque durante a inspeção para evitar que o estoque não aprovado seja utilizado (bloqueio total das quantidades da ordem de compra).
-   Use a amostragem do item como parte de uma associação de qualidade para definir o valor de estoque físico atual que deve ser inspecionado. A amostragem pode se basear em quantidades fixas ou em uma porcentagem.
-   Crie ordens de qualidade para recebimentos parciais. Para criar uma ordem de qualidade baseada na quantidade fisicamente recebida com uma ordem, marque a caixa de seleção **Por quantidade atualizada** no formulário **Amostragem de itens**.
-   Crie tipos de teste que incluem valores de teste mínimos, máximos, e de destino, e realizar testes qualitativos versos quantitativos que possuem resultados de validação pré-definidos.
-   Especifique um nível de qualidade aceitável (AQL) para controlar as tolerâncias da medição de qualidade.
-   Especifique os recursos que uma operação de inspeção requer, como uma área de teste e instrumentos de teste.

## <a name="working-with-quality-associations"></a>Trabalhando com associações de qualidade
O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.

Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas. Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios. Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado. Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado quando houver uma ordem de qualidade aberta, ou os processos seguintes, como o faturamento de ordem de compra, puderem ser bloqueados.

**Observação:** Enquanto houver ordens de qualidade abertas, as quantidades de destoque serão automaticamente impedidas de serem usadas. Dependendo da configuração de **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem.

Para um dado processo comercial, o registro de associação de qualidade identifica o evento e as condições para as quais uma ordem de qualidade é gerada. As condições podem ser específicas para um site ou uma entidade legal. Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.

Os exemplos a seguir ilustram como um registro de associação de qualidade é definido para as variações em cada processo comercial. Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.

<table>
<tbody>
<tr>
<th>Tipo de referência</th>
<th>Tipo de evento</th>
<th>Execução</th>
<th>Bloqueio do evento</th>
<th>Referência de documento</th>
</tr>
<tr>
<td>Estoque</td>
<td>Não aplicável</td>
<td>Não aplicável</td>
<td>Nenhum</td>
<td>Tudo</td>
</tr>
<tr>
<td rowspan="7">Venda</td>
<td rowspan="4">O processo de separação está agendado</td>
<td rowspan="4">Antes</td>
<td>Nenhum</td>
<td rowspan="22">ID específica, Grupo, ou Todos apenas</td>
</tr>
<tr>
<td>Processo de separação</td>
</tr>
<tr>
<td>Guia de remessa</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Guia de remessa</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Guia de remessa</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="15">Compra</td>
<td rowspan="7">Lista de recebimentos</td>
<td rowspan="4">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Lista de recebimentos</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Registro</td>
<td rowspan="3">Não aplicável</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="5">Recebimento de produtos</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="2">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="8">Produção</td>
<td rowspan="3">Registro</td>
<td rowspan="3">Não aplicável</td>
<td>Nenhum</td>
<td rowspan="12">Tudo</td>
</tr>
<tr>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="5">Relatar como concluído</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="2">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="4">Quarentena</td>
<td rowspan="3">Relatar como concluído</td>
<td rowspan="2">Antes</td>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td>Depois</td>
<td>Encerrar</td>
</tr>
<tr>
<td>Encerrar</td>
<td>Antes</td>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="3">Operação do roteiro</td>
<td rowspan="3">Relatar como concluído</td>
<td rowspan="2">Antes</td>
<td>Nenhum</td>
<td rowspan="3">ID específica, Grupo, ou Todos, e Específico de recurso, Grupo, ou Todos</td>
</tr>
<tr>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td rowspan="3">Produção de coprodutos</td>
<td>Registro</td>
<td>Não aplicável</td>
<td rowspan="3">Nenhum</td>
<td rowspan="3">Tudo</td>
</tr>
<tr>
<td rowspan="2">Relatar como concluído</td>
<td>Antes</td>
</tr>
<tr>
<td>Depois</td>
</tr>
</tbody>
</table>

A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Tipo de processo</th>
<th>Quando as ordens de qualidade podem ser geradas automaticamente</th>
<th>Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</th>
<th>Informações de condição</th>
<th>Informações de geração manual</th>
</tr>
<tr>
<td>Ordem de compra</td>
<td>Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</td>
<td>Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de quarentena</td>
<td>Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</td>
<td>Ordens de qualidade que exigem testes destrutivos não podem ser geradas. Presume-se que a funcionalidade de ordem de quarentena controla o descarte do material destruído.</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de venda</td>
<td>Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</td>
<td>Em qualquer etapa</td>
<td>O requisito para uma ordem de qualidade pode refletir um determinado site, ou cliente ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de produção</td>
<td>Antes ou depois, a quantidade concluída para a ordem de produção é relatada</td>
<td>Depois que a quantidade concluída para a ordem de produção é relatada</td>
<td>O requisito para uma ordem de qualidade pode refletir um site ou item particulares ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de produção que tem uma operação de rota</td>
<td>Antes ou depois da conclusão do relatório para uma operação</td>
<td>Depois da conclusão de produção de relatório para a última operação</td>
<td>O requisito para uma ordem de qualidade pode refletir em um site, item ou recursos de operações ou a combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</td>
</tr>
<tr>
<td>Estoque</td>
<td>Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para a transação de ordem de transferências.</td>
<td></td>
<td></td>
<td>Uma ordem de qualidade deve ser criada manualmente para a quantidade em estoque de um item. O estoque físico disponível do item é necessário.</td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a>Exemplos de geração automática de ordens de qualidade

### <a name="purchasing"></a>Comprando

Na compra, se você definir o campo **Tipo de evento** como **Recebimento de produtos** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados: 

- Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada para cada recebimento em relação à ordem de qualidade, com base na quantidade e nas configurações recebidas na amostra do item. Sempre que uma quantidade é recebida em relação à ordem de compra, novos pedidos de qualidade são gerados com base na quantidade recém-recebida.
- Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade será gerada para o primeiro recebimento em relação à ordem de qualidade, com base na quantidade recebida. Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento. Os pedidos de qualidade não são gerados para recebimentos subsequentes em relação à ordem de compra.

<table>
<tbody>
<tr>
<th>Especificação de qualidade</th>
<th>Quantidade por atualização</th>
<th>Por dimensão de rastreamento</th>
<th>Resultado</th>
</tr>
<tr>
<td>Porcentagem: 10%</td>
<td>Sim</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>
<p>Quantidade da ordem: 100</p>
<ol>
<li>Relatar como concluído para 30
<ul>
<li>Ordem de qualidade nº 1 para 3 (10% de 30)</li>
</ul>
</li>
<li>Relatar como concluído para 70
<ul>
<li>Ordem de qualidade nº 2 para 7 (10% da quantidade restante da ordem, que é igual a 70 neste caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Não</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>Quantidade da ordem: 100
<ol>
<li>Relatar como concluído para 30
<ul>
<li>A ordem de qualidade nº 1 é criado para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1).</li>
<li>Não são mais criadas ordens de qualidade em relação à quantidade restante.</li>
</ul>
</li>
<li>Relatar como concluído para 10
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
<li>Relatar como concluído para 60
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Sim</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 3
<ul>
<li>Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</li>
<li>Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</li>
<li>Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</li>
</ul>
</li>
<li>Relatar como concluído para 2
<ul>
<li>Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</li>
<li>Ordem de qualidade nº 5 para 1 do lote nº b5, série nº s5</li>
</ul>
</li>
</ol>
<p><strong>Observação:</strong> o lote pode ser reutilizado.</p>
</td>
</tr>
<tr>
<td>Quantidade fixa: 2</td>
<td>Não</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 4
<ul>
<li>Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1.</li>
<li>Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2.</li>
<li>Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3.</li>
<li>Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4.</li>
<li>Não são mais criadas ordens de qualidade em relação à quantidade restante.</li>
</ul>
</li>
<li>Relatar como concluído para 6
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a>Produção

Na produção, se você definir o campo **Tipo de evento** como **Relatar como concluído** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados:

- Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada com base em todas as quantidades e configurações finalizadas na amostra do item. Sempre que uma quantidade é relatada como concluída em relação à ordem de produção, novas ordens de qualidade são geradas com base na quantidade recém-concluída. Essa lógica de geração é consistente com a compra.
- Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade é gerada na primeira vez que uma quantidade é relatada como concluída, com base na quantidade concluída. Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento da amostra do item. As ordens de qualidade não são geradas para quantidades concluídas subsequentes.

<table>
<tbody>
<tr>
<th>Especificação de qualidade</th>
<th>Quantidade por atualização</th>
<th>Por dimensão de rastreamento</th>
<th>Resultado</th>
</tr>
<tr>
<td>Porcentagem: 10%</td>
<td>Sim</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>
<p>Quantidade da ordem: 100</p>
<ol>
<li>Relatar como concluído para 30
<ul>
<li>Ordem de qualidade nº 1 para 3 (10% de 30)</li>
</ul>
</li>
<li>Relatar como concluído para 70
<ul>
<li>Ordem de qualidade nº 2 para 7 (10% da quantidade restante da ordem, que é igual a 70 neste caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Não</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>Quantidade da ordem: 100
<ol>
<li>Relatar como concluído para 30
<ul>
<li>Ordem de qualidade nº 1 para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1)</li>
<li>Ordem de qualidade nº 2 para 1 (para a quantidade restante, que ainda possui um valor fixo de 1)</li>
</ul>
</li>
<li>Relatar como concluído para 10
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
<li>Relatar como concluído para 60
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Sim</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 3: 1 para nº b1, nº s1; 1 para nº b2, nº s2; e 1 para nº b3, nº s3
<ul>
<li>Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</li>
<li>Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</li>
<li>Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</li>
</ul>
</li>
<li>Relatar como concluído para 2: 1 para nº b4, nº s4; e 1 para nº b5, nº s5
<ul>
<li>Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</li>
<li>Ordem de qualidade nº 5 para 1 do lote nº b5, série nº s5</li>
</ul>
</li>
</ol>
<p><strong>Observação:</strong> o lote pode ser reutilizado.</p>
</td>
</tr>
<tr>
<td>Quantidade fixa: 2</td>
<td>Não</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 4: 1 para nº b1, nº s1; 1 para nº b2, nº s2; 1 para nº b3, nº s3; e 1 para nº b4, nº s4
<ul>
<li>Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</li>
<li>Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</li>
<li>Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</li>
<li>Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</li>
</ul>
<ul>
<li>Ordem de qualidade nº 5 para 2, sem referência a um lote e um número de série</li>
</ul>
</li>
<li>Relatar como concluído para 6: 1 para nº b5, nº s5; 1 para nº b6, nº s6; 1 para nº b7, nº s7; 1 para nº b8, nº s8; 1 para nº b9, nº s9; e 1 para nº b10, nº s10
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>Páginas de gerenciamento de qualidade
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Página</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Associações de qualidade</td>
<td>Consulte as seções anteriores deste artigo.</td>
<td>Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:
<ul>
<li>O evento da transação</li>
<li>O conjunto de testes que devem ser executados nos itens</li>
<li>O AQL</li>
<li>O plano de amostragem</li>
</ul>
É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade. Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.</td>
</tr>
<tr class="even">
<td>Testes</td>
<td>Use esta página para definir e exibir os testes individuais que determinam se seus produtos atendem às especificações de qualidade. Você pode atribuir um ou mais testes individuais a um grupo de teste. Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis. Os valores de medição são usados para testes quantitativos, e as variáveis de teste são usadas para testes qualitativos.
<ul>
<li>Um teste quantitativo tem um tipo de teste <strong>Inteiro</strong> ou <strong>Fração</strong>, e também tem uma unidade de medida designada. As especificações de qualidade e os resultados de teste são expressos em números.</li>
<li>Um teste qualitativo tem o tipo de teste <strong>Opção</strong>. Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas. As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.</li>
</ul></td>
<td>Uma fábrica realiza dois testes em material adquirido: um teste quantitativo sobre a qualidade do material e um teste qualitativo sobre danos de embalagem. A empresa define informações adicionais sobre o teste qualitativo para identificar a variável de teste (embalagem danificada) e seus resultados. A empresa usa a página <strong>Grupos de teste</strong> para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste. O grupo de testes é atribuído a uma ordem de qualidade, de tal modo que a empresa possa informar resultados de teste para os dois testes.</td>
</tr>
<tr class="odd">
<td>Grupos de teste</td>
<td>Use esta página para configurar, editar e exibir grupos de testes e testes individuais atribuídos a um grupo de testes. O painel superior exibe grupos de testes e o painel inferior exibe os testes atribuídos a um grupo de testes selecionado. Você atribui várias políticas a um grupo de testes, como um plano de amostragem, um AQL, e o requisito para testes destrutivos. Quando você atribui um teste individual a um grupo de testes, você define informações adicionais, como a sequência, os documentos, e as datas de validade. Para um teste quantitativo, as informações que você define também incluem os valores de medida aceitáveis. Para um teste qualitativo, as informações incluem a variável de teste e o resultado padrão. O grupo de testes atribuído a uma ordem de qualidade define o conjunto padrão de testes que devem ser realizados no item específico. No entanto, você pode adicionar, excluir, ou alterar os testes na ordem de qualidade. Os resultados do teste são relatados para cada teste em uma ordem de qualidade.</td>
<td>Uma fábrica define um grupo de testes para cada variação de suas diretrizes de qualidade. Os vários grupos de testes refletem diferenças nos planos de amostragem, nos conjuntos de testes que precisam ser executados juntos, na AQL, e em outros fatores. Para testes quantitativos, também existem diferenças nos valores de medida aceitáveis. Para impor suas diretrizes de qualidade, a empresa atribui um grupo de testes a cada regra para gerar automaticamente ordens de qualidade na página <strong>Associações de qualidade</strong>, e também atribui um grupo de testes às ordens de qualidade criadas manualmente.</td>
</tr>
<tr class="even">
<td>Grupos de qualidade de item</td>
<td>Use esta página para configurar, editar e exibir os itens atribuídos a um grupo de qualidade ou os grupos de qualidade atribuídos a um item. Um grupo de qualidade representa requisitos de teste comuns para itens. Após definir os requisitos de teste da página <strong>Grupos de teste</strong>, você pode definir as regras para gerar automaticamente as ordens de qualidade. Para simplificar o processo, você não define regras para itens individuais. Em vez disso, defina regras para um grupo de qualidade, usando a página <strong>Associações de qualidade</strong>. Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um grupo de qualidade selecionado atribua itens relevantes ao grupo. Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um item selecionado atribua grupos de qualidade relevantes ao item.</td>
<td>Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada. A empresa define um grupo de qualidade e então atribui os números de item associados com as matérias-primas ao grupo. Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste. Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente. A mesma fábrica também produz itens com os mesmos requisitos de teste de produção e remete os itens com o mesmo requisito para a execução de testes antes da remessa. A fábrica define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.</td>
</tr>
<tr class="odd">
<td>Teste de variáveis</td>
<td>Use esta página para definir e exibir as variáveis associadas a um teste qualitativo. Para cada variável, você define os resultados enumerados que representam as opções possíveis. Você define os testes na página <strong>Testes</strong>. Para testes qualitativos, você deve definir o tipo de teste como <strong>Opção</strong>. Use a página <strong>Grupos de teste</strong> para atribuir uma variável de teste a um teste individual.</td>
<td>Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado. Esse teste de inspeção tem várias variáveis. Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim. Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</td>
</tr>
<tr class="even">
<td>Resultados do teste de variável</td>
<td>Use esta página para configurar, editar e exibir os possíveis resultados de teste de uma variável de teste associada a um teste qualitativo. Para cada resultado, você atribui um status de <strong>aprovado</strong> ou <strong>reprovado</strong>. Você deve definir uma variável e seus resultados para cada teste qualitativo definido na página <strong>Testes</strong>. (Para testes qualitativos, o tipo de teste é definido como <strong>Opção</strong> na página <strong>Testes</strong>.) Use os <strong>Grupos de testes</strong> para atribuir uma variável de teste e o resultado padrão a um teste qualitativo individual.</td>
<td>Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado. Esse teste de inspeção tem várias variáveis. Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim. Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto. Um status de <strong>aprovado</strong> ou <strong>reprovado</strong> é atribuído a cada resultado. Durante o teste de inspeção de cada variável, o inspetor informa o resultado do teste selecionando um dos resultados.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Recursos adicionais
--------

[Processos de gerenciamento de qualidade](quality-management-processes.md)

[​Gerenciamento de não conformidade​](enable-nonconformance-management.md)
