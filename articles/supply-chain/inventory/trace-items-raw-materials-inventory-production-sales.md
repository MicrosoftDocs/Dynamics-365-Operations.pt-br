---
title: "Item e rastreamento de matérias-primas em estoque, em produção e em vendas"
description: "Este tópico descreve como você pode usar o rastreamento de item para identificar onde os itens ou as matérias-primas foram usados, onde estão sendo usados ou onde serão usados em processos de produção e de vendas."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 60edc05bb45db973eb2e16dd833015c9a4873918
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Item e rastreamento de matérias-primas em estoque, em produção e em vendas

[!INCLUDE [banner](../includes/banner.md)]

Este tópico descreve como você pode usar o rastreamento de item para identificar onde os itens ou as matérias-primas foram usados, onde estão sendo usados ou onde serão usados em processos de produção e de vendas.

A funcionalidade de rastreamento do item fica disponível na página **Rastreamento do item**. As seções a seguir descrevem como você pode usar o rastreamento do item e quais são opções e as restrições.

## <a name="what-is-item-tracing"></a>O que é rastreamento de item?
O rastreamento de item é uma ferramenta de business intelligence (BI) que oferece visibilidade da origem e do destino de itens e matérias-primas na cadeia de suprimentos. Os fabricantes podem rastrear itens, matérias-primas ou ingredientes desde o fornecedor até a produção e a venda do produto acabado. O rastreamento de itens ajuda os fabricantes a cumprirem os requisitos regulatórios e, além disso, ajuda os responsáveis pela qualidade e gerentes de produção a analisar e tomar medidas para resolver variações de qualidade de produtos e materiais. Veja alguns exemplos de que formas os fabricantes podem usar o rastreamento do item:

-   Identificar o valor de um item ou de uma matéria-prima que esteja em estoque e o local onde está armazenado.
-   Determinar a quantidade do item ou da matéria-prima que foi enviada e para que clientes.
-   Identificar todas as remessas planejadas que incluírem o item ou a matéria-prima.
-   Localizar as ordens de produção que usam o item ou a matéria-prima e que sejam planejadas, que estejam em andamento ou que sejam relatadas como concluídas.
-   Descobrir onde o item ou a matéria-prima foi comprada.
-   Investigar onde um item ou uma matéria-prima foi consumida na produção de outro item.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>O que posso rastrear e existe alguma limitação?
Você pode rastrear transações de estoque históricas de itens e matéria-prima com base em um número de item e uma dimensão de rastreamento, como um número de série, número de lote ou número de lote de fornecedor. Você só poderá rastrear um item ou uma matéria-prima se não tiver uma dimensão de rastreamento atribuída a ele. Como o rastreamento se baseia em transações de estoque, existem algumas limitações ao rastrear itens. Por exemplo, existem limitações relacionadas a transações para projetos, ativos fixos e varejo. Além disso, os coprodutos são mostrados nos detalhes de rastreamento, mas subprodutos não estão incluídos. O rastreamento inclui todas as transações do depósito de um local para outro. Consequentemente, os usuários podem localizar a quantidade de excesso de informações. O rastreamento é exibido para uma entidade legal de cada vez. Não há nenhum recursos entre empresas em um contexto intercompanhia. Você deve iniciar um novo rastreamento para cada empresa onde um item é recebido ou emitido.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Quais critérios posso especificar para um rastreamento de item?
Os critérios necessários para um rastreamento de item são o número do item, uma dimensão de rastreamento (como um número de lote ou número de série) e a direção. A tabela a seguir descreve os critérios que podem ser usados em um rastreamento de item.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de campos</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nº do item</td>
<td>Insira o identificador do item ou da matéria-prima que você está rastreando.</td>
</tr>
<tr class="even">
<td>Dimensões do produto</td>
<td>Opcional: rastreie aspectos específicos da definição de produto, como uma configuração, um tamanho, uma cor ou um estilo.</td>
</tr>
<tr class="odd">
<td>Dimensões de rastreamento</td>
<td>Insira um número de lote, um número de lote de fornecedor ou uma dimensão de rastreamento de número de série. Quando você usa o número de lote como um critério, o número de lote de fornecedor será exibido caso você tenha capturado essas informações.</td>
</tr>
<tr class="even">
<td>Dimensões de armazenamento</td>
<td>Opcional: rastreie itens que foram armazenados em um local específico.</td>
</tr>
<tr class="odd">
<td>Período</td>
<td>Opcional: insira datas para limitar o rastreamento a um período específico. Os detalhes de rastreamento mostrarão somente documentos e transações criados entre essas datas.</td>
</tr>
<tr class="even">
<td>Avançar ou recuar</td>
<td>Selecione a direção para o rastreamento. Você pode rastrear para frente ou para trás:
<ul>
<li><strong>Recuar</strong> – rastreie de forma descendente para identificar a origem, a quantidade restante disponível e todas as ordens de produção que são relatadas como concluídas pelo menos parcialmente.</li>
<li><strong>Avançar</strong> – rastreie de forma ascendente para identificar o destino. Você pode encontrar as ordens de venda e os clientes para os os quais o item ou a matéria-prima rastreada foi enviada pelo menos parcialmente.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Quais informações são incluídas nos detalhes de rastreamento?
Os resultados de um rastreamento aparecem em ordem cronológica na árvore na Guia Rápida **Detalhes** na página **Rastreamento de item**. A ordem varia, dependendo da direção de rastreamento. Os detalhes incluem todas as transações, desde a compra do item do fornecedor até a venda do item para o cliente. Os resultados de rastreamento também incluem os produtos temporários relacionados ao item ou à dimensão de rastreamento especificada nos critérios de rastreamento. O nó superior mostra a quantidade do item, na unidade de estoque, que ainda está disponível com base nas dimensões de armazenamento especificadas nos critérios de rastreamento. **Observação:** os detalhes de rastreamento fornecem um instantâneo das informações disponíveis quando o rastreamento foi concluído. Os detalhes de rastreamento não serão atualizados caso as informações tenham sido alteradas após a conclusão do rastreamento.

## <a name="why-dont-some-nodes-contain-any-details"></a>Por que alguns nós não contêm detalhes?
Para reduzir a quantidade de informações nos detalhes do rastreamento, somente o nó da primeira instância do item ou da matéria-prima incluirá detalhes. Se um nó selecionado não contiver detalhes, você poderá exibir o nó que contém os detalhes clicando em **Ir para a linha rastreada**. Você pode voltar ao nó do qual saiu clicando em **Voltar**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>Posso exibir somente um tipo de documento em particular? Por exemplo, posso exibir somente ordens de produção, clientes ou fornecedores?
Sim, você pode abrir as páginas de listagem que incluem somente um tipo de documento ou de transação em particular dos detalhes de rastreamento. Você pode acessar essas páginas do item de menu **Rastreamento** no Painel de Ação, nos grupos **Item**, **Venda**, **Compra**, **Produção** e **Qualidade**. Por exemplo, para exibir uma lista dos fornecedores nos detalhes do rastreamento, clique em **Rastreamento** &gt; **Compra** &gt; **Fornecedores**. As páginas de listagem resumem os documentos ou as transações dos detalhes de rastreamento. As **Transações Pendentes**, **Ordens pendentes** e **Ordens de venda não remetidas** também mostram informações que não estão incluídas nos detalhes de rastreamento. Além disso, elas sempre mostram os resultados a partir da data atual, mesmo se um intervalo de datas tenha sido especificado. A tabela a seguir descreve os detalhes adicionais que essas páginas podem incluir.

| Listas                    | Descrição                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ordens de venda não remetidas | Exiba as linhas da ordem de venda que não foram separadas e que, portanto, não foram mostradas nos detalhes de rastreamento.                                                                                                                                                                                                                        |
| Ordens pendentes           | Exiba todas as ordens de produção pendentes do item rastreado, independentemente das dimensões de rastreamento usadas nos critérios de rastreamento. Você também pode exibir ordens de produção pendentes onde o item rastreado é um ingrediente, e em que nenhum registro foi feito e nenhuma transação foi relatada como concluída para a ordem. |
| Transações pendentes     | Exiba transações de estoque pendentes para o item rastreado que inclui as dimensões de rastreamento especificadas ou uma dimensão de rastreamento em branco. Você também pode exibir transações de estoque pendentes para itens e combinações de dimensão de rastreamento, ou um valor em branco, nos detalhes de rastreamento.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Quantos níveis posso rastrear para cima ou para baixo em uma BOM ou em uma fórmula?
Você pode rastrear um nível para cima ou para baixo em uma lista de materiais (BOM) ou em uma fórmula. Por exemplo, se você executar um rastreamento em matérias-primas, poderá ver o produto finalizado e todos os coprodutos. Entretanto, se você rastrear um coproduto, os detalhes do rastreamento não incluirão o produto finalizado.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Como posso exibir mais detalhes sobre um documento ou uma transação nos detalhes de rastreamento?
Na Guia Rápida **Detalhes**, não há formas de exibir mais informações sobre um documento ou uma transação selecionada nos detalhes de rastreamento:

-   Quando você seleciona um nó nos detalhes de rastreamento na Guia Rápida **Detalhes**, as outras Guias Rápidas da página exibirão informações sobre o documento ou transação no nó.
-   Abra a página de detalhes do documento em um nó selecionado clicando em **Exibir detalhes**. Por exemplo, se você selecionar um nó que descreva uma ordem de produção e clicar em **Exibir detalhes**, a página **Detalhes das ordens de produção** será exibido.

Algumas Guias Rápidas oferecem acesso a informações adicionais sobre o nó selecionado. Por exemplo, na Guia Rápida **Não conformidades**, você pode clicar em **Consultas** para investigar se há um histórico de não conformidade. Na Guia Rápida **Lote**, você pode clicar na lista **Disponível** para exibir a quantidade de estoque físico disponível no momento e todas as transações de estoque que envolvem o lote.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>Posso executar mais de um rastreamento e então comparar os detalhes?
Depois de executar o rastreamento, você poderá usar as opções a seguir no botão **Rastreamento a partir do nó** para executar um novo rastreamento na transação no nó selecionado:

-   **Avançar** ou **Recuar** – inicie um novo rastreamento do nó selecionado e substitua os detalhes do rastreamento atual.
-   **Novo recuo** ou **Novo avanço** – inicie um novo rastreamento em uma nova janela e mantenha os detalhes do rastreamento atual.

Se você desejar usar a opção **Novo recuo** ou **Novo avanço**, deverá usar a funcionalidade **Abrir em uma nova janela** para que um novo rastreamento apareça em uma nova janela.

## <a name="can-i-save-the-trace-details"></a>Posso salvar os detalhes do rastreamento?
Você pode salvar as informações na guia <strong>Detalhes</strong> como um arquivo XML, clicando em <strong>Exportar</strong> abaixo da ação *<strong><em>Rastreamento</em></strong>* no Painel de Ação. Além dos detalhes de rastreamento, o arquivo XML inclui os critérios do rastreamento, o nó pai e a quantidade disponível. A capacidade de salvar os detalhes de um rastreamento será útil se, por exemplo, você quiser anexar informações a uma ordem de qualidade ou a outra documentação de conformidade. Você pode especificar onde o arquivo será salvo. Para exibir o arquivo imediatamente, marque a caixa de seleção <strong>Mostrar documento</strong>. <strong>Observação:</strong> o arquivo será sempre salvo, mesmo se você só quiser exibi-lo. Por padrão, o arquivo XML abre em uma janela do navegador. No entanto, você pode clicar com o botão direito do mouse no arquivo, selecionar <strong>Abrir com</strong> e selecionar o programa a ser usado para exibir o conteúdo.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>Posso calcular um saldo para um item ou ingrediente em particular?
Você pode exportar as informações das páginas de resumo para o Microsoft Excel. Abra a página relevante, clique no ícone **Abrir no Microsoft Office** e selecione **Exportar para o Microsoft Excel**. Essa funcionalidade é especialmente útil quando você deseja calcular um saldo em massa para um item ou um ingrediente da página **Resumo de transações**. Na página **Resumo de transações**, você pode filtrar pelo item ou ingrediente e, opcionalmente, por lote e então exportar as informações para o Excel. No Excel, você pode isolar, por exemplo, a quantidade disponível, a quantidade vendida e a quantidade usada em produção.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>Posso investigar se há um histórico de problemas com itens ou matérias-primas?
Os detalhes de rastreamento incluem informações sobre ordens de qualidade e não conformidades que envolvam o item ou a matéria-prima. Para exibir um resumo de ordens de qualidade e não conformidades, clique em **Ordens de qualidade** ou em **Não conformidades** no Painel de Ação. **Observação:** as ordens de qualidade destrutivas podem aparecer mais de uma vez nos detalhes de rastreamento. Quando uma ordem de qualidade destrutiva é criada para um documento, como uma ordem de compra, ela aparece para cada transação desse documento.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Existem recursos de relatório relacionados a rastreamento do item?
Você pode gerar o relatório **Remetido aos clientes** para identificar o valor do item ou da matéria-prima que foi enviado e os clientes aos quais ele foi enviado. Para uma consulta relacionada à conformidade, é possível gerar o relatório para todos os clientes. Para uma consulta relacionada ao atendimento ao cliente, é possível gerar o relatório para um cliente selecionado. Se o produto era uma matéria-prima usada na produção de um item finalizado, o item finalizado também serão incluído. **Observação**: se você estiver usando os recursos para a exclusão ou o arquivamento de ordens de venda, os resultados do relatório também incluirão todas as ordens de venda excluídas ou arquivadas.

## <a name="can-i-trace-coproducts-and-byproducts"></a>Posso monitorar coprodutos e subprodutos?
Você pode rastrear coprodutos, mas não é possível rastrear um subproduto porque as dimensões de rastreamento normalmente não são atribuídas por produtos. Quando você rastreia um item, os detalhes do rastreamento incluem todos os coprodutos relacionados. Um nó que contém um coproduto inclui a palavra "coproduto" nos detalhes. Você também pode exibir detalhes sobre um coproduto selecionando o nó nos detalhes de rastreamento e então clicando na Guia Rápida **Produção**.

