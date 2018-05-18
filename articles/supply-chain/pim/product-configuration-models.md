---
title: "Visão geral dos modelos de configuração de produto"
description: "Esse artigo define condições e conceitos que são relevantes para configuração de produtos. Modelos de configuração de produto permitem criar uma estrutura de produtos genérica que pode ser usada para definir diversas variantes de produto para um único produto."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0ddc9d43f62df937a6fb18e15c718c37442bb9b4
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="product-configuration-models-overview"></a>Visão geral dos modelos de configuração de produto

[!include [banner](../includes/banner.md)]

Esse artigo define condições e conceitos que são relevantes para configuração de produtos. Modelos de configuração de produto permitem criar uma estrutura de produtos genérica que pode ser usada para definir diversas variantes de produto para um único produto.

Os modelos de produto são criados para representar a estrutura de produtos genérica. Depois de definir um modelo de configuração de produto, será possível configurar uma variante de produto distinta que tenha uma lista de materiais (BOM) exclusiva e um roteiro exclusivo. Os modelos de configuração de produto usam limitações declarativas e cálculos obrigatórios para tratar as relações e as limitações entre variantes de produto diferentes. É possível configurar itens em ordens de venda, cotações de venda, ordens de compra e, em ordens de produção. A tabela a seguir descreve os termos e os conceitos baseados em restrição de tabela.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Componentes</td>
<td>Os componentes são os blocos de construção principais de um modelo de configuração de produto. Os componentes são exibidos em uma estrutura de árvore na página <strong>Detalhes do modelo da configuração de produto baseada em restrições</strong>. Os componentes podem conter os seguintes elementos:
<ul>
<li>Atributos</li>
<li>Restrições</li>
<li>Cálculos</li>
<li>Subcomponentes</li>
<li>Requisitos de usuário</li>
<li>Linhas de BOM</li>
<li>Operações de roteiro</li>
</ul></td>
</tr>
<tr class="even">
<td>Atributos</td>
<td>Os atributos descrevem todos os recursos do modelo de configuração de produto. É possível usar atributos para especificar os recursos que podem ser selecionados quando um produto distinto é configurado. Os atributos são usados nas restrições e condições. Quando atributos são criados e adicionados a um modelo de configuração de produto, os tipos de atributo relacionados são referidos. Um valor padrão pode ser definido para um atributo. O valor padrão é usado na interface do usuário (UI) de configuração quando o modelo de configuração de produto é configurado. É possível especificar que um atributo é obrigatório, somente leitura, ou oculto.
<ul>
<li><strong>Obrigatório</strong> – um valor deve ser definido para o atributo quando o produto é configurado.</li>
<li><strong>Somente leitura</strong> – o valor do atributo é exibido durante uma sessão de configuração, mas não pode ser alterado.</li>
<li><strong>Oculto</strong> – o valor do atributo é incluído nas restrições e condições, mas não é exibido durante uma sessão de configuração.</li>
</ul>
Também é possível especificar uma condição para os atributos. Se a condição for atendida, é necessário inserir um valor para o atributo obrigatório. Condições são expressões que devem ser atendidas para os atributos, linhas da BOM, e as operações de roteiro a serem incluídas em um modelo de configuração de produto. Qualquer atributo que faça referência a uma condição torna-se obrigatório. Recomendamos selecionar atributos como obrigatórios na guia <strong>Atributos</strong>. Isso facilita na identificação de atributos obrigatórios. Os valores de atributo são uma parte importante da reutilização de configurações. O sistema usa os valores de atributo para determinar se existe uma configuração que corresponda às seleções feitas por um usuário durante uma sessão de configuração.</td>
</tr>
<tr class="odd">
<td>Tipos de atributos</td>
<td>Os tipos de atributo especificam o conjunto de tipos de dados para atributos que são usados em um modelo de produto. Os seguintes tipos de atributo são usados:
<ul>
<li><strong>Inteiro</strong> com ou sem um intervalo</li>
<li><strong>Decimal</strong></li>
<li><strong>Texto</strong> com ou sem uma lista fixa</li>
<li><strong>Booleano</strong></li>
</ul>
Se o tipo de atributo for <strong>Booliano</strong>, <strong>Inteiro</strong> com um intervalo ou <strong>Texto</strong> com uma lista fixa, o conjunto de valores estará disponível quando um modelo de configuração do produto for configurado. <strong>Observação:</strong> o Agente de solução de configuração de produto reconhece somente os seguintes tipos de atributo: <strong>Booliano</strong>, <strong>Texto</strong> com uma lista fixa e <strong>Inteiro</strong> com um intervalo. Portanto, somente esses tipos de atributo podem ser usados nas restrições e condições de expressão.</td>
</tr>
<tr class="even">
<td>Restrições</td>
<td>As restrições descrevem as restrições de configuração do modelo de produto. As restrições são usadas para garantir que somente os valores válidos sejam selecionados quando um produto estiver sendo configurado. As restrições podem ser restrições de expressão ou restrições de tabela:
<ul>
<li>As restrições de expressão podem ser usadas somente para o componente ao qual estão associadas. As restrições de expressão para um componente pode fazer referência a atributos dos subcomponentes do componente. O Agente de solução de configuração do produto é usado para resolver as restrições, e é necessário usar a sintaxe do agente de solução ao gravar as restrições. Para obter mais informações, consulte o link do tópico sobre restrições de expressão e restrições de tabela.</li>
<li>As restrições de tabela devem ser definidas antes que possam ser aplicadas a um componente em um modelo de configuração de produto. As restrições de tabela podem ser definidas pelo usuário ou pelo sistema. Uma restrição de tabela definida pelo usuário é um tipo de matriz que pode ser usada para descrever o conjunto de combinações para os valores de atributo que são definidos pelos tipos de atributo. Por exemplo, se forem produzidos alto-falantes, a matriz para uma restrição de tabela definida pelo usuário poderá ter colunas para o acabamento e para a grade do alto-falante.</li>
</ul>
<strong>Exemplo</strong> Os alto-falantes estão disponíveis em quatro acabamentos: Preto, Carvalho, Jacarandá, e Branco. Os alto-falantes podem ter uma de três grades de planejamento: Preto, Metal ou Branco. O acabamento preto está disponível para todas as grades, mas os outros acabamentos são limitados a grades específicas. A tabela a seguir mostra um exemplo das informações exibidas na guia <strong>Combinações permitidas</strong> na página <strong>Editar restrição de tabela</strong>.
<table>
<thead>
<tr class="header">
<th>Acabamento do gabinete</th>
<th>Grade frontal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Preto</td>
<td>Preto</td>
</tr>
<tr class="even">
<td>Preto</td>
<td>Metal</td>
</tr>
<tr class="odd">
<td>Preto</td>
<td>Branco</td>
</tr>
<tr class="even">
<td>Carvalho</td>
<td>Preto</td>
</tr>
<tr class="odd">
<td>Jacarandá</td>
<td>Branco</td>
</tr>
<tr class="even">
<td>Branco</td>
<td>Preto</td>
</tr>
<tr class="odd">
<td>Branco</td>
<td>Branco</td>
</tr>
</tbody>
</table>
Uma restrição de tabela definida pelo sistema representa um mapeamento entre um tipo de atributo e um campo em uma tabela do Finanças e Operações. Uma restrição de tabela definida pelo sistema vincula dinamicamente o tipo de atributo ao campo. O link habilita o atributo em um modelo de configuração de produto para refletir os dados do campo na tabela do Finanças e Operações.</td>
</tr>
<tr class="odd">
<td>Cálculos</td>
<td>Os cálculos representam um suplemento para as restrições. Você pode usar um cálculo para executar operações aritméticas em atributos dos tipos <strong>Decimal</strong> e <strong>Inteiro</strong> ou operações lógicas que envolvam atributos dos tipos <strong>Texto</strong> com uma lista fixa e <strong>Booliano</strong>. Um cálculo tem um atributo de destino que reterá o resultado da expressão de cálculo. A expressão de cálculo é criada usando o editor de expressões.</td>
</tr>
<tr class="even">
<td>Subcomponentes</td>
<td>Os subcomponentes refletem a estrutura de árvore do modelo de configuração de produto. É possível usar subcomponentes para compilar a estrutura do modelo de configuração de produto. Os subcomponentes fazem referência a componentes existentes. Portanto, os subcomponentes incentivam a reutilização de componentes em vários modelos de configuração de produto. Na página <strong>Detalhes da linha de BOM</strong> para um subcomponente, é possível selecionar um valor distinto para o subcomponente. Como alternativa, é possível selecionar um atributo para o qual o valor é selecionado quando o modelo de configuração de produto é configurado. Para incluir um produto como um componente ou um subcomponente, é necessário especificar as seguintes informações na página <strong>Criar produto</strong> quando você criar o produto:
<ul>
<li>No campo <strong>Tipo de produto</strong>, selecione <strong>Item</strong>.</li>
<li>No campo <strong>Subtipo do produto</strong>, selecione <strong>Produto mestre</strong>.</li>
<li>No campo <strong>Tecnologia de configuração</strong>, selecione <strong>Configuração baseada em restrições</strong>.</li>
</ul>
É possível ver se um produto liberado pode ser usado como um componente ou um subcomponente na guia <strong>Geral</strong> da página <strong>Detalhes do produto liberado</strong>. Se <strong>Configuração baseada em restrições</strong> for selecionado no campo <strong>Tecnologia de configuração</strong>, o produto poderá ser usado como um componente ou um subcomponente. É possível ocultar os subcomponentes para que não sejam exibidos ao usuário durante uma sessão de configuração. Os atributos, subcomponentes, e os requisitos de usuário relacionados ao subcomponente também são ocultos.</td>
</tr>
<tr class="odd">
<td>Requisitos de usuário</td>
<td>Os requisitos de usuário representam uma abstração entre os requisitos de usuário e os componentes e os atributos específicos. Não é possível mapear um requisito de usuário para um item. Por exemplo, um cliente está comprando um sistema de home theater. O representante de vendas pode perguntar sobre o tamanho da sala em que o cliente planeja instalar o sistema, para determinar quantos watts serão necessários. Neste exemplo, o tamanho da sala pode ser um requisito de usuário que ajuda a determinar o valor do atributo apropriado para um componente específico. É possível ocultar os requisitos de usuário para que não sejam exibidos para o usuário durante uma sessão de configuração. Os atributos, subcomponentes, e os requisitos de usuário relacionados ao requisito de usuário também são ocultos. É possível gravar uma condição para controlar se um requisito de usuário pode ser oculto. É necessário gravar a condição usando a sintaxe OML (Optimization Modeling Language).</td>
</tr>
<tr class="even">
<td>Linhas de BOM</td>
<td>As linhas da BOM representam os materiais individuais dos componentes do modelo de configuração de produto. Na página <strong>Detalhes da linha de BOM</strong>, todos os itens estão disponíveis para seleção. Uma condição pode ser adicionada à linha de BOM para que as linhas de BOM selecionadas para uma variante de produto distinta possam variar, com base na seleção do usuário quando o modelo de configuração de produto for configurado. Condições são expressões que devem ser atendidas para os atributos, linhas da BOM, e as operações de roteiro a serem incluídas em um modelo de configuração de produto. Na página <strong>Detalhes da linha de BOM</strong>, selecione um valor distinto. Como alternativa, é possível mapear para um atributo para o qual o valor é selecionado quando o modelo de configuração de produto é configurado.</td>
</tr>
<tr class="odd">
<td>Operações de roteiro</td>
<td>Na página <strong>Detalhes da operação de roteiro</strong>, você pode selecionar um valor distinto. Como alternativa, é possível mapear para um atributo para o qual o valor é selecionado quando o modelo de configuração de produto é configurado. As condições são gravadas como restrições de expressão. Condições são expressões que devem ser atendidas para os atributos, linhas da BOM, e as operações de roteiro a serem incluídas em um modelo de configuração de produto.</td>
</tr>
</tbody>
</table>






