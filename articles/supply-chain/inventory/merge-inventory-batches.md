---
title: Mesclar lotes de estoque
description: Este artigo fornece informações sobre como consolidar dois ou mais lotes de estoque em um lote mesclado.
author: pjacobse
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4c9443c6e659602ae09e4744396651186874ad3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008007"
---
# <a name="merge-inventory-batches"></a>Mesclar lotes de estoque

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como consolidar dois ou mais lotes de estoque em um lote mesclado.

Quando você mescla lotes, os cálculos podem ajudar a otimizar as características e os atributos de lote do lote mesclado. Depois de selecionar os lotes de origem, você poderá examinar e alterar o lote mesclado antes de lançá-lo. Você também pode transferir a mesclagem de lote para um diário de estoque para aprovação. O estoque pode ser reservado ou lançado diretamente desse diário de estoque. Quando você lança um lote mesclado, o estoque é ajustado para os lotes de origem e o lote mesclado.

## <a name="are-there-any-prerequisites"></a>Existe algum pré-requisito?
Sim, há alguns aspectos que você deve configurar antes que seja possível usar as ferramentas do lote de mesclagem. A tabela a seguir descreve os pré-requisitos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Página</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nomes de diário, estoque</td>
<td>É necessário criar um nome de diário do tipo de BOM a ser usado por padrão quando você lança mesclagens de lote em diários de estoque. Opcional, mas recomendado: é possível especificar que as reservas sejam feitas automaticamente quando a mesclagem de lote é transferida para o diário de estoque. Caso contrário, haverá o risco de que o estoque disponível seja alterado após os detalhes de mesclagem de lote serem configurados e o diário for lançado. Para habilitar as reservas automáticas para o nome do diário, selecione <strong>Automática</strong> no campo <strong><strong>Reserva</strong></strong>.</td>
</tr>
<tr class="even">
<td>Parâmetros de gerenciamento de estoque e depósito</td>
<td>É necessário especificar o nome de diário padrão para o diário de estoque.</td>
</tr>
<tr class="odd">
<td>Produtos liberados</td>
<td>Veja as configurações recomendadas para o item:
<ul>
<li>Para gerar automaticamente números de lote para os lotes mesclados, é necessário atribuir os produtos liberados a um grupo de números de lote. Também é possível inserir um número de lote manualmente ao criar um lote mesclado, ou selecionar um número de lote existente. Se você selecionar um número de lote existente, verifique se o lote selecionado não foi incluído em nenhuma transação de estoque.</li>
<li>Se você estiver usando a validade ou datas de validade para os produtos liberados, as datas de um lote mesclado serão calculadas com base na seleção do campo <strong>Cálculo de data da mesclagem de lotes</strong>. As opções a seguir estão disponíveis:
<ul>
<li><strong>Mais anterior</strong> - o cálculo se baseia na primeira data especificada para um lote de origem que é selecionado para a mesclagem de lotes.</li>
<li><strong>Mais recente</strong> - o cálculo se baseia na data mais recente especificada para um lote de origem que é selecionado para a mesclagem de lotes.</li>
<li><strong>Manual</strong> – nenhum cálculo é realizado. Se a data for a mesma em todos os lotes de origem, uma data será sugerida. Você pode alterar essa data. Se a data não for a mesma nos lotes de origem, será possível inseri-la manualmente.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Grupo de números de lote</td>
<td>Opcionais: Para gerar um número do lote ao criar um lote mesclado, é necessário atribuir um grupo de números de lote aos produtos liberadas. Caso contrário, você poderá inserir um número do lote manualmente.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>Quando é recomendável mesclar os lotes de estoque?
Veja alguns exemplos de cenários onde pode ser útil mesclar lotes:

-   Samuel está andando pelo seu depósito e percebe que há vários lotes do mesmo item com baixa quantidades. Ele está aguardando receber várias remessas novas e percebe que poderá liberar um espaço mesclando as quantidades em um novo lote.
-   Samuel está recebendo o estoque e deseja combinar o novo lote com um que já possui para melhorar o valor do atributo de lote do lote existente. Fazendo isso, você cria um novo lote.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>Posso mesclar os lotes entre locais e entidades legais?
Não, você só poderá mesclar os lotes com as mesmas dimensões de estoque do site e depósito em uma entidade legal. No entanto, você pode especificar um local e uma identificação de palete diferentes para o lote mesclado.

## <a name="can-i-merge-partial-quantities"></a>Posso mesclar quantidades parciais?
Não, você só pode mesclar a quantidade total de lotes. A funcionalidade de mesclagem de lotes foi concebida como um recurso de estoque, não como um recurso de produção.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>E se os lotes possuírem valores de atributo de lote diferentes?
Quando você selecionar os lotes de origem para combinar no lote mesclado, o Supply Chain Management verificará se todos os lotes têm as características ou os valores de atributo. Quando um valor de atributo é o mesmo, um valor será sugerido para o lote mesclado. É possível alterar esse valor. Os valores de atributo que não são iguais são deixados em branco para o lote mesclado, e você pode inserir estes valores manualmente. Se o tipo de atributo de lote do valor do atributo for um número inteiro ou uma fração, e os valores forem diferentes para todos os lotes de origem, o valor será calculado usando o cálculo de média ponderada. O valor calculado é arredondado para cima ou para baixo até o incremento mais próximo. Se o valor estiver em branco para um lote de origem, o lote e sua quantidade não serão incluídos no cálculo. **Exemplo** O exemplo a seguir mostra um cálculo de média ponderada para um lote mesclado. Dois dos lotes de origem tem um valor em branco para um tipo de atributo de lote que é um número inteiro. O seguinte atributo é atribuído aos lotes de origem.

| Atributo | Mínimo | Incremento | Máximo |
|-----------|---------|-----------|---------|
| Pontuação     | 3       | 3         | 30      |

Os lotes de origem têm os seguintes valores de atributo para o atributo **Lote de classificação**.

| Lote | Quantidade | Atributo | Valor do atributo |
|-------|----------|-----------|-----------------|
| B1    | 10       | Pontuação     | Em Branco           |
| B2    | 15       | Pontuação     | 15              |
| B3    | 20       | Pontuação     | 20              |
| B4    | 25       | Pontuação     | Em Branco           |
| B5    | 30       | Pontuação     | 25              |

Quando você adiciona esses lotes como lotes de origem, os seguintes valores são atribuídos ao lote mesclado.

| Lote | Quantidade | Atributo | Valor do atributo |
|-------|----------|-----------|-----------------|
| B6    | 100      | Pontuação     | 21              |

Os valores e as quantidades dos lotes B1 e B4 não são incluídos no cálculo de média ponderada. Consequentemente, veja como o valor do lote mesclado é calculado.

| Valor | Quantidade (peso)                              | Peso relativo | Peso relativo × Valor                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Total:** 65, que é a soma dos pesos |                 | **Total:** 21,5384615, que é arredondado para 21 (o incremento mais próximo) |

## <a name="what-if-the-batches-have-different-batch-dates"></a>E se os lotes tiverem datas diferentes de lote?
Se os lotes tiverem datas de lote diferentes, qualquer uma das datas será calculada com base nos valores do grupo **Datas de lote** na Guia Rápida **Lote mesclado** da página **Mesclagem de lote**. O sistema calcula os valores dos campos no grupo **Datas de lote**. Esses valores incluem a data de fabricação, a data de vencimento, a data de aviso de tempo de prateleira e a data de validade. As datas são calculadas com base nas configurações do item no grupo de campos **Dados do item** da página **Detalhes do produto liberado**. Você pode alterar os valores ou inseri-los manualmente. Para todas datas restantes, nenhum cálculo é feito. O mesmo princípio é usado para os valores de atributo de lote. Se uma data for a mesma para todos os lotes de origem, essa data será sugerida para o lote mesclado. Se a data não for a mesma para todos os lotes de origem, a data ficará em branco no lote mesclado e você poderá inseri-la manualmente.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>E se as dimensões forem diferentes nos lotes que eu desejo mesclar?
Veja como as dimensões de produto, dimensões de rastreamento, e as dimensões de estoque são tratadas:

-   **Dimensões do produto** – todas as dimensões de produto para o item selecionado devem ser iguais. Não é possível mesclar lotes pelas dimensões de produto.
-   **Dimensões de rastreamento** - um novo número de lote será gerado automaticamente se um grupo de números de lote for especificado para o item. Se um grupo de números de lotes não estiver atribuído a um item, é possível selecionar um lote existente ou inserir o número manualmente. Os números de série são transferidos do lote de origem para as linhas do diário de estoque do lote mesclado.
-   **Dimensões de armazenamento** – as dimensões de estoque do site e depósito devem ser iguais para todos os lotes de origem e o lote mesclado. No entanto, você pode especificar um local e uma identificação de palete novos para o lote mesclado.

## <a name="how-does-posting-work"></a>Como o lançamento funcionará?
O lançamento trabalha de duas maneiras, dependendo se você usar um processo de aprovação para diários. É possível usar os botões **Transferir para diário** e **Lançar a mesclagem de lotes** para transferir a mesclagem de lotes a um diário onde ela possa ser verificada e lançada, ou você pode lançar a mesclagem de lotes diretamente. A principal diferença entre as duas ações é que a transferência para um diário não lança a mesclagem de lotes. Ambas as ações criarão um novo lote se um lote existente não for selecionado, atualizarão todos os detalhes do lote e valores de atributo, e criarão um diário de estoque.

-   **Transferir para diário** - transfere os detalhes da mesclagem de lotes para um novo diário de estoque. Se você tiver configurado reservas automáticas, as quantidades nos lotes de origem serão reservadas. Os detalhes da mesclagem de lotes não podem ser alterados. Para modificar a mesclagem de lotes, exclua o diário. O diário pode ser usado como uma tarefa que outro funcionário deverá executar posteriormente. A reserva da quantidade do lote para a linha do diário é protegida. Essa alocação permite que um planejador de qualidade ou um gerente de depósito crie tarefas para os funcionários.
-   **Lançar a mesclagem de lote** – lança a mesclagem de lotes diretamente. Essa ação pode ser executada depois que a mesclagem física ocorrer.

É possível aprovar o diário de estoque para a mesclagem de lotes da página de listagem **Todas as mesclagens de lotes**. Clique em **Diário** &gt; **Lançar**. Depois que um diário é lançado, não será possível alterar os detalhes do lote mesclado. Após transferir uma mesclagem de lotes a um diário de estoque, será possível modificar os detalhes somente se o diário for excluído.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>Após mesclar um item de peso variável, por que eu não consigo ver as informações de peso variável no diário de estoque?
Você pode mesclar lotes de itens de peso variável da mesma maneira que todos os outros itens. Entretanto, as informações de peso variável não aparecem no diário de estoque. Recomendamos que você verifique as informações de peso variável antes de transferir a mesclagem de lotes para o diário de estoque.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]