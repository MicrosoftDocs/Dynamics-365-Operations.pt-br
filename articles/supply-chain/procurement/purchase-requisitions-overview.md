---
title: Visualização geral da requisição de compra
description: Este tópico descreve o fluxo de trabalho de requisição de compra e os diferentes status que uma requisição de compra pode ter.
author: RichardLuan
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage, PurchReqConsolidationPartByVendor, PurchReqConsolidationLineDetail, PurchReqConsolidationCreate, PurchReqConsolidationBulkEdit, PurchReqConsolidationAddLine
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2174
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d3cc8043062fe304ef8127a2abbaeb787c4761f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215928"
---
# <a name="purchase-requisition-overview"></a>Visualização geral da requisição de compra

[!include [banner](../includes/banner.md)]

Este tópico descreve o fluxo de trabalho de requisição de compra e os diferentes status que uma requisição de compra pode ter.

Dependendo da configuração da sua organização, você poderá criar requisições de compra para os produtos consumidos pela organização. Uma requisição de compra é um documento interno que autoriza o departamento de Compras a comprar produtos.  

Depois que uma requisição de compra for aprovada, ela poderá ser usada para gerar uma ordem de compra. As ordens de compra são os documentos externos equivalentes que o departamento de Compras envia aos fornecedores.

## <a name="creating-purchase-requisitions"></a>Criar requisições de compra
Você pode criar uma requisição de compra na página **Minhas requisições de compra** e selecione os itens e os serviços exigidos. Você pode selecionar itens de um catálogo de compras que sua organização criou ou pode solicitar os itens que não estejam localizados em um catálogo ao selecionar uma categoria de compras e inserir os detalhes do produto.  

Para que você possa enviar uma requisição de compra para revisão, os fluxos de trabalho deverão ser configurados. Use um sistema de fluxo de trabalho para mover uma requisição de compra por um processo de revisão com um status inicial **Rascunho** para um status final **Aprovado**.

### <a name="purchase-requisition-statuses"></a>Status de requisições de compra

Quando você cria uma requisição de compra, um status é atribuído à ela. Um status também é atribuído a todas as linhas adicionadas a uma requisição de compra. Ao enviar uma requisição de compra a um fluxo de trabalho para revisão, o status da requisição de compra e o status de cada linha serão atualizados à medida que as linhas passarem pelo processo de fluxo de trabalho.  

É possível configurar o processo de fluxo de trabalho da requisição de compra para passar uma requisição de compra pelo processo de revisão como um único documento. Como alternativa, as linhas de uma requisição de compra podem ser encaminhadas individualmente para os revisores apropriados. Se as linhas da requisição de compra forem revisadas individualmente, o status de cada linha da requisição de compra pode ser atualizado à medida que a linha passa pelo processo de revisão. Quando todas as linhas tiverem passado pelo processo de revisão e não houver nenhuma etapa de revisão restante para a requisição de compra, o status da requisição de compra inteira será atualizado.

### <a name="purchase-requisition-workflow"></a>Fluxo de trabalho de requisição de compra

O diagrama a seguir mostra os status que são atribuídos a uma requisição de compra e a uma linha da requisição de compra à medida que elas passam pelo processo de fluxo de trabalho.  

[![Status do cabeçalho e da linha da requisição de compra](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Cabeçalho da requisição de compra e relacionamentos de status da linha

O status geral de uma requisição de compra é determinado pelo status das linhas da requisição de compra. Portanto, o processo de revisão deverá ser concluído para todas as linhas da requisição de compra antes que o processo de revisão da requisição de compra inteiro possa ser concluído. A tabela a seguir descreve os status que são atribuídos a um cabeçalho e às linhas da requisição de compra à medida que a requisição de compra passa pelo processo de fluxo de trabalho.

<table>
<thead>
<tr class="header">
<th>Status de requisição de compra</th>
<th>Status da linha de requisição de compra</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Rascunho</td>
<td>Rascunho</td>
<td>A requisição de compra e a linha da requisição de compra foram criadas, mas não foram enviadas para revisão. Pode-se modificar requisições de compra e linhas de requisição de compra com status <strong>Rascunho</strong>. Uma requisição de compra ou uma linha da requisição de compra também tem um status <strong>Rascunho</strong> se foi cancelada, mas não foi reenviada para revisão. <strong>Observação:</strong> Você pode enviar ou cancelar uma requisição de compra no nível do documento. No entanto, você não pode enviar ou cancelar uma única linha da requisição de compra.</td>
</tr>
<tr class="even">
<td>Em revisão</td>
<td><ul>
<li>Em revisão</li>
<li>Rejeitada</li>
</ul></td>
<td>Se o fluxo de trabalho tiver sido configurado para encaminhar as linhas da requisição de compra aos revisores individuais, cada linha poderá ter um status <strong>Em revisão</strong> ou <strong>Rejeitado</strong>. O status da requisição de compra será atualizado quando o processo de revisão estiver concluído para todas as linhas da requisição de compra, e quando não houver mais etapas de revisão restantes para a requisição de compra.
<ul>
<li><strong>Em revisão</strong> – as linhas da requisição de compra foram enviadas para a revisão. Quando o processo de fluxo de trabalho estiver concluído para uma linha da requisição de compra, o status da linha permanecerá <strong>Em revisão</strong> até que todas as linhas da requisição de compra sejam revisadas.</li>
<li><strong>Rejeitado</strong> – Uma linha de requisição de compra foi rejeitada. As linhas da requisição de compra que são rejeitadas podem ser modificadas e reenviadas.</li>
</ul>
Se você reenviar uma linha da requisição de compra que foi rejeitada, o processo de revisão será iniciado novamente para todas as linhas na requisição de compra que ainda estão em revisão. </br><strong>Observação:</strong> é possível cancelar uma requisição de compra que já foi enviada. Quando você cancela uma requisição de compra, todas as outras linhas da requisição de compra também são canceladas. As linhas da requisição de compra que foram canceladas podem ser excluídas.</td>
</tr>
<tr class="odd">
<td>Rejeitada</td>
<td>Rejeitada</td>
<td>A requisição de compra e todas as linhas da requisição de compra foram rejeitadas. As requisições de compra e as linhas da requisição de compra que foram rejeitadas podem ser enviadas novamente.</td>
</tr>
<tr class="even">
<td>Aprovado</td>
<td><ul>
<li>Aprovado</li>
<li>Cancelado</li>
<li>Fechado</li>
</ul></td>
<td>Todas as linhas da requisição de compra passaram pelo processo de revisão e não há mais etapas de revisão para a requisição de compra.
<ul>
<li><strong>Aprovado</strong> – o processo de revisão para uma linha da requisição de compra foi concluído e a linha foi aprovada.</li>
<li><strong>Cancelado</strong> – a linha da requisição de compra foi aprovada, mas foi cancelada porque não é mais necessária. Somente as linhas de requisição de compra que foram aprovadas podem ser canceladas.</li>
<li><strong>Fechado</strong> – a linha de requisição de compra foi aprovada e os documentos foram gerados, dependendo da finalidade da requisição.
<ul>
<li>Se a finalidade da requisição for o consumo, uma ordem de compra foi gerada para a linha da requisição de compra.</li>
<li>Se a finalidade da requisição for reabastecimento, um ou mais documentos de atendimento serão gerados.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Cancelado</td>
<td>Cancelado</td>
<td>A requisição de compra e todas as linhas da requisição de compra foram canceladas.</br> <strong>Observação:</strong> Caso não precise mais de um item que está em uma linha da requisição de compra, cancele a linha da requisição de compra se ela já tiver sido aprovada. Somente as linhas de requisição de compra que foram aprovadas podem ser canceladas. Se qualquer linha da requisição de compra estiver em revisão, a requisição de compra também terá um status <strong>Em revisão</strong>. Nesse caso, você poderá cancelar a requisição de compra e excluir a linha da requisição de compra apropriada.</td>
</tr>
<tr class="even">
<td>Fechado</td>
<td><ul>
<li>Fechado</li>
<li>Cancelado</li>
</ul></td>
<td>A requisição de compra foi fechada, e um ou vários documentos de atendimento foram gerados.
<ul>
<li><strong>Fechado</strong> – a linha de requisição de compra foi aprovada e os documentos foram gerados, dependendo da finalidade da requisição.
<ul>
<li>Se a finalidade da requisição for o consumo, uma ordem de compra foi gerada para a linha da requisição de compra.</li>
<li>Se a finalidade da requisição for reabastecimento, um ou mais documentos de atendimento serão gerados.</li>
</ul></li>
<li><strong>Cancelado</strong> – a linha da requisição de compra foi aprovada, mas foi cancelada porque não é mais necessária. Somente as linhas de requisição de compra que foram aprovadas podem ser canceladas.</li>
</ul>
<strong>Observação:</strong> se um item em uma linha de requisição de compra fechada não for mais necessário, a linha gerada no documento de atendimento para a linha da requisição de compra deverá ser cancelada.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Custos de distribuição para várias contas financeiras
Você pode distribuir os custos de um produto incluso em uma requisição de compra para várias contas financeiras. Se a organização usar dimensões, como centros de custos e departamentos, você pode distribuir os custos de um produto para as dimensões em contas financeiras.

## <a name="requisition-purposes"></a>Finalidades da requisição
As finalidades da requisição tornam mais flexível o processo de atendimento à demanda da requisição. Quando você criar uma requisição, poderá atribuir um destes dois objetivos: consumo ou reabastecimento. Dependendo do objetivo da requisição e de como a sua organização está configurada, a demanda da requisição pode ser cumprida por uma ordem de compra, por ordem de transferência, por uma ordem de produção ou por um kanban.  

Nas políticas de compras, você pode controlar os objetivos da requisição que estão disponíveis quando uma requisição é criada para sua organização.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Requisições que têm um objetivo de consumo

Uma requisição com o objetivo de consumo representa a demanda para itens e serviços que serão usados internamente pela organização. A demanda criada com esse tipo de requisição é sempre cumprida por uma ordem de compra. Se o Supply Chain Management for configurado para gerar ordens de compra automaticamente, essas ordens serão criadas após aprovação da requisição de compra.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Requisições que têm um objetivo de reabastecimento

Uma requisição com o objetivo de reabastecimento representa a demanda para reabastecer o estoque. Por exemplo, você cria uma requisição para reabastecer itens para que possam ser vendidos em uma localização específica de varejo em um horário específico. A demanda criada por esse tipo de requisição pode ser executada por uma ordem de compra, uma ordem de transferência, uma ordem de produção ou um kanban.  

Quando o objetivo da requisição for reabastecimento, a demanda será expressa como uma quantidade em vez de um valor monetário. Portanto, a contabilidade de ônus, a auditoria de orçamento, as regras comerciais para a determinação de ativo fixo (BRAD), a contabilidade de projetos e qualquer outra regra relacionada não se aplicam. Somente os produtos em estoque e liberados para a entidade legal especificada podem atender à demanda de requisição do reabastecimento. Para definir os produtos disponíveis quando a finalidade da requisição for reabastecimento, use a página **Regras de política de acesso da categoria de reabastecimento**.  

Para usar as requisições de compra com a finalidade de reabastecimento, você deverá configurar o agendamento do planejamento mestre para incluir a demanda de requisição. O método de execução para a demanda criada por esse tipo de requisição é então determinado automaticamente, com base nas políticas de fornecimento, as quais foram configuradas para os itens em sua organização e planejadas com o uso do agendamento do planejamento mestre.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Requisições de compra e solicitações de cotação
Em alguns casos, você deve iniciar um processo de solicitação de cotação (RFQ) para identificar o fornecedor e o preço dos produtos solicitados em uma requisição de compra. Uma RFQ poderá ser gerada quando a requisição de compra estiver em revisão. Quando você aceita um lance, as informações sobre o fornecedor, o preço e assim por diante, são transferidas para a requisição.  

Você pode colocar uma requisição de compra em espera selecionando a caixa de seleção **Em espera** na página **Detalhes da requisição de compra**. Processamento da requisição de compra pode continuar somente depois que você remover o bloqueio desmarcando a caixa de seleção.  

> [!NOTE]
> Em compras eletrônicas, a RFQ da sua requisição de compra pode permitir que os fornecedores adicionem linhas alternativas. Nesse caso, sua requisição de compra refletirá as alternativas aprovadas.

## <a name="demand-consolidation"></a>Consolidação de demanda
Ao consolidar linhas de requisição de compra das diversas requisições de compra, você pode aumentar o seu poder de negociação com seus fornecedores para obter a melhor definição de preços, custos mais baixos de remessa e manuseio e reduzir custos gerais indiretos.  

As linhas de requisição de compra estarão qualificadas para consolidação de demanda somente se as seguintes instruções forem verdadeiras:

-   A requisição de compra foi aprovada.
-   A requisição de compra atende aos critérios de regras de política de compras para o processamento manual e a consolidação de demanda.

As linhas de requisição de compra aprovadas que atendem aos critérios para o processamento manual são listadas na página **Liberar requisições de compra liberadas**. Se uma linha de requisição de compra também atender aos critérios para consolidação de demanda, ela poderá ser adicionada a uma oportunidade de consolidação.  

Uma oportunidade de consolidação é um conjunto de linhas de requisição de compra que são agrupadas de forma que o profissional de compra possa negociar o melhor acordo com os fornecedores. As linhas de requisição de compra selecionadas para uma oportunidade de consolidação aparecem na página **Consolidação da requisição de compra**. Você poderá modificar as linhas dessa página, se alterações forem necessárias. Você também pode adicionar novas linhas à oportunidade de consolidação ou remover as linhas existentes.  

Depois de adicionar linhas de requisição a uma oportunidade de consolidação e fazer todas as alterações necessárias, você pode criar uma ordem de compra para as linhas de requisição de compra consolidadas.  

> [!NOTE]
> As alterações feitas em uma linha de requisição de compra na página **Consolidação da requisição de compra** serão refletidas na ordem de compra criada. Entretanto, a linha permanecerá inalterada na requisição de compra, de forma que o histórico seja preservado.  

Para criar uma ordem de compra para as linhas da requisição de compra não qualificadas para consolidação de demanda ou que não estejam selecionadas para uma oportunidade de consolidação, você deverá processar as linhas manualmente.

### <a name="consolidating-purchase-requisition-lines"></a>Consolidando linhas de requisição de compra

O processo de consolidação de demanda se inicia quando uma requisição de compra é aprovada em um fluxo de trabalho e, se o controle de orçamento estiver configurado para sua organização, quando as reservas de orçamento e os pré-ônus são registrados. O diagrama a seguir mostra o fluxo de processo para consolidação de demanda.  

[![Fluxo do processo para consolidação de demanda](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Para consolidar linhas de requisição de compra aprovadas, siga estas etapas:

1.  Revise as linhas de requisição aprovadas que foram mantidas para processamento manual e que estão qualificadas para consolidação de demanda.
2.  Selecione as linhas a serem adicionadas a uma oportunidade de consolidação.
3.  Crie uma nova oportunidade de consolidação ou adicione linhas de requisição a uma oportunidade de consolidação existente.
4.  Faça todas as alterações necessárias nas linhas da requisição e remova os itens de linha de requisição que você não deseja mais incluir na oportunidade de consolidação.
5.  Crie ordens de compra para as linhas de requisição consolidadas ou para linhas de requisição de compra em uma oportunidade de consolidação.


<a name="additional-resources"></a>Recursos adicionais
--------

[Criar uma requisição para consumo](tasks/create-requisition-consumption.md)

[Fluxo de trabalho de requisição de compra](purchase-requisitions-workflow.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]