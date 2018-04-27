---
title: "Designer de fórmulas"
description: "Este tópico explica como usar o designer de fórmulas para analisar e manter fórmulas em um modo de exibição de árvore."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a4cfd017fe10bbda6eda0e3a9a045e0832b08753
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="formula-designer"></a>Designer de fórmulas

[!INCLUDE [banner](../includes/banner.md)]

Este tópico explica como usar o designer de fórmulas para analisar e manter fórmulas em um modo de exibição de árvore.

Quando você abre a página **Designer de fórmulas** da página **Produtos liberados**, a árvore no painel esquerdo mostra a lista de coprodutos e a hierarquia de ingredientes dos produtos liberados. A estrutura é derivada da hierarquia de fórmulas ativas e aprovadas para o item selecionado e os ingredientes, o site padrão de ordem do item, e a data real.

Clique em **Configurar** para selecionar diferentes configurações e especificar quais informações aparecem nas linhas da árvore.

Clique em **Filtrar** em para alterar a seleção inicial na exibição. Se você definir o princípio de exibição como **Selecionado/Ativo** ou **Selecionado**, você pode selecionar a fórmula individual ou as versões de roteiro a serem usadas na exibição. Você pode selecionar as versões da fórmula não aprovadas e não ativas para mostrar ou manter no designer de fórmulas.  

> [!NOTE]
> Se você abrir a página **Designer de fórmulas** da página de listagem **Listas de materiais**, ela não exibirá as informações de roteiro. Atualmente, a seleção de uma fórmula ou a versão de roteiro se aplicam a todas as instâncias de designer de fórmulas.  

As seções a seguir descrevem a funcionalidade que está disponível no Designer de BOM.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analisar a estrutura da fórmula usando o designer de fórmulas
O Designer de fórmulas tem duas seções:

-   O modo de exibição de árvore da estrutura da fórmula.
-   A seção de detalhes, que mostra detalhes de dados selecionados. Quando você seleciona um nó no modo de exibição de árvore, as Guias Rápidas da seção de detalhes são atualizadas com base no nó:
    -   **Detalhes da linha da fórmula** – exibe os detalhes da linha da fórmula selecionada no modo de exibição de árvore.
    -   **Dados do item** – exibe os detalhes do item principal ou do item usado no nó selecionado. Você pode clicar em **Editar produto liberado** para manter o item selecionado.
    -   **Fórmula** – exibe o cabeçalho da fórmula que está relacionado ao nó selecionado.
    -   **Roteiro** – exibe o cabeçalho do roteiro que está relacionado ao nó selecionado.
    -   **Operações de roteiro** – exibe uma visualização de operações do roteiro. Quando uma lista de materiais (BOM) atribuída a uma operação específica é selecionada, a operação será marcada como **Componente necessário em operações**.

## <a name="select-a-formula-and-route"></a>Selecione uma fórmula e um roteiro
O filtro aplicado para que a fórmula e o roteiro sejam exibidos no cabeçalho do designer de fórmulas. Você pode alterar o filtro usando a caixa de diálogo **Filtro**. A tabela a seguir descreve os campos nesta caixa de diálogo.

<table>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dimensões do produto</td>
<td>Se o produto selecionado é um produto mestre, você pode definir as dimensões de produto ativas para a seleção principal. Observe que, se você abrir o designer de fórmulas para um produto que não é um produto mestre, as dimensões do produto não poderão ser selecionadas na caixa de diálogo <strong>Filtro</strong>.</p></td>
</tr>
<tr class="even">
<td>Site</td>
<td>Altere o local para o qual a árvore de ingrediente será exibida. O site padrão é o site padrão de estoque do item concluído.</td>
</tr>
<tr class="odd">
<td>Exibir princípio</td>
<td><p>Selecione o princípio de exibição de versão que se aplica à estrutura de fórmula e ao roteiro atuais:</p>
<ul>
<li>Quando o princípio estiver definido como <strong>Ativo</strong> ou <strong>Selecionado/Ativo</strong>, a fórmula ou versão do roteiro válida para essa data será encontrada.</li>
<li>Quando o princípio for definido como <strong>Selecionado/Ativo</strong> ou <strong>Selecionado</strong>, você poderá selecionar uma versão de fórmula ou uma versão de roteiro clicando em <strong>Fórmula</strong> &gt; <strong>Versões da Fórmula</strong> ou <strong>Roteiro</strong> &gt; <strong>Versões de roteiro</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data da versão</td>
<td>Insira a data de versão do roteiro e da fórmula. A versão identifica qual versão da fórmula é utilizada em uma data específica, com base nas datas de versão na configuração de versão da fórmula.</td>
</tr>
<tr class="odd">
<td>Da quantidade</td>
<td>Filtre as versões ao selecionar uma quantidade &quot;inicial&quot; específica. Se você definir um valor, versões diferentes de fórmula e de roteiro poderão ser selecionadas.</td>
</tr>
<tr class="even">
<td>Mostrar somente válido</td>
<td>Quando marca a caixa de seleção, a estrutura de árvore mostra somente as linhas de fórmula com datas válidas. Clique com o botão direito do mouse ou clique duas vezes em uma linha de fórmula para abrir a página <strong>Editar linha de fórmula</strong>, onde você pode ver as datas de validade para essa linha de fórmula.</td>
</tr>
</tbody>
</table>

Quando você usa o designer de fórmula para revisar ou editar fórmulas que consistem em um ou mais níveis de fantasmas, o roteiro associado ao item superior normalmente se estende pela hierarquia completa da fórmula. Para simplificar a visão geral, você pode bloquear o roteiro de nível superior na exibição ao clicar em **Exibir** &gt; **Bloquear roteiro**. Para desbloquear o roteiro, clique em **Exibir** &gt; **Desbloquear roteiro**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Adicionar e editar fórmulas e linhas da fórmula
Use as funções **Linhas de fórmula** ou **Fórmula** para alterar as linhas de fórmula ou a fórmula. Quando você seleciona um nó na árvore, o tipo de nó determina as funções disponíveis.

| Função                            | descrição                                                                                               | Tipo de nó e condições |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Linhas de BOM &gt; Editar                 | Abra uma caixa de diálogo na qual é possível editar os atributos da linha de fórmula.                                         | Essa função estará disponível quando um nó da linha de fórmula estiver selecionado. |
| Linhas de BOM &gt; Excluir               | Excluir a linha de fórmula da fórmula selecionada.                                                          | Essa função estará disponível quando um nó da linha de fórmula estiver selecionado, e a fórmula não estiver bloqueada para edição. |
| Linhas de BOM &gt; Adicionar antes da linha      | Abra uma caixa de diálogo na qual é possível selecionar uma grade de produto a ser incluída antes da linha de fórmula selecionada.     | Essa função estará disponível quando um nó da linha de fórmula estiver selecionado. |
| Linhas de BOM &gt; Adicionar à BOM de componentes | Abra uma caixa de diálogo na qual é possível selecionar uma grade de produto a ser incluída ao final da fórmula selecionada.   | Essa função estará disponível quando o nó selecionado tiver uma fórmula selecionada. Se essa função não estiver disponível, talvez haja uma versão da fórmula ausente para a variante de item selecionada. Nesse caso, você pode clicar em **Fórmula** &gt; **Criar versão** para criar a versão ausente para o nó selecionado. |
| Linhas de BOM &gt; Adicionar após a linha       | Abra uma caixa de diálogo na qual é possível selecionar uma grade de produto a ser incluída depois da linha de fórmula selecionada.      | Essa função estará disponível quando um nó da linha de fórmula estiver selecionado. |
| Fórmula &gt; Criar versão         | Crie uma nova versão da fórmula ou a fórmula para a grade de produto do nó selecionado.                     | Essa função estará disponível quando o nó da linha de fórmula selecionado estiver vinculado a um item com o tipo de produção **BOM** ou **Fórmula**. |
| Fórmula &gt; Cálculo            | Abra uma caixa de diálogo onde você pode executar o custo ou o cálculo do preço de venda para a variante de produto selecionada. | Essa função estará disponível quando o nó selecionado estiver relacionado a uma versão da fórmula. |
| Fórmula &gt; Cheque                  | Valide e verifique a fórmula selecionada.                                                                  | Essa função estará disponível quando o nó selecionado estiver relacionado a uma versão da fórmula. |

## <a name="configuring-the-tree-view"></a>Configuração do modo de exibição de árvore
Clique em **Configuração** para personalizar as informações mostradas no modo de exibição de árvore do designer de fórmulas.


| Grupo de campos |                                                                          descrição                                                                          |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     BOM     | Use as caixas de seleção para marcar os critérios mostrados na estrutura de árvore. O designer de fórmulas mostra os critérios selecionados na parte inferior das duas guias. |
|    Roteiro    |                                           Use as caixas de seleção para marcar os critérios mostrados nos roteiros.                                           |


