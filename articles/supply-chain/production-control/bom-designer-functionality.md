---
title: Funcionalidade de designer de BOM
description: "Este tópico descreve como você pode usar a página do designer de BOM para criar e trabalhar com estruturas de árvore para listas de materiais (BOMs)."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b7d4530ecccf18d9370d84ff2b61be1514b80192
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="bom-designer-functionality"></a>Funcionalidade de designer de BOM

[!include [banner](../includes/banner.md)]

Este tópico descreve como você pode usar a página do designer de BOM para criar e trabalhar com estruturas de árvore para listas de materiais (BOMs). Você pode clicar em Configurar para selecionar diferentes configurações e especificar quais informações aparecem nas linhas da árvore.

Quando você abre a página **Designer de BOM** da página **Produtos liberados**, ela exibe a hierarquia de listas de materiais (BOMs) ativas e aprovadas para o item selecionado, o local padrão da ordem do item e a data real.  

Clique em **Filtrar** em para alterar a seleção inicial na exibição. Ao definir o princípio de exibição como **Selecionado/Ativo ou Selecionado**, você pode selecionar a BOM individual ou as versões de roteiro a serem usadas na exibição. Você pode selecionar as versões da BOM não aprovadas e não ativas para mostrar ou manter no Designer de BOM.  

**Observação:** se você abrir o Designer de BOM da página de listagem **Listas de materiais**, ele não exibirá as informações de roteiro. Atualmente, a seleção de uma BOM ou de uma versão de roteiro é uma propriedade da BOM e da versão de roteiro, e se aplica a todas as instâncias do Designer de BOM.  

As seções a seguir descrevem a funcionalidade que está disponível nas guias do Designer de BOM.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Análise de uma estrutura de BOM usando o Designer de BOM
O Designer de BOM tem duas seções:

-   O modo de exibição de árvore da estrutura da BOM.
-   A seção de detalhes, que mostra detalhes de dados selecionados. Quando você seleciona um nó no modo de exibição de árvore, as Guias Rápidas da seção de detalhes são atualizadas com base no nó:
    -   **Detalhes da linha de BOM** – mostra os detalhes da linha de BOM selecionada no modo de exibição de árvore.
    -   **Dados do item** – mostra os detalhes do item principal ou do item usado no nó selecionado. Você pode clicar em **Editar produto liberado** para manter o item selecionado.
    -   **BOM** – mostra o cabeçalho da BOM que está relacionado ao nó selecionado.
    -   **Roteiro** – mostra o cabeçalho do roteiro que está relacionado ao nó selecionado.
    -   **Operações de roteiro** – mostra uma visualização de operações do roteiro. Quando uma linha da BOM atribuída a uma operação específica é selecionada, a operação será marcada como **Componente necessário em operações**.

## <a name="selecting-a-bom-and-route"></a>Seleção de uma BOM e de um roteiro
O filtro aplicado para que a BOM e o roteiro sejam exibidos no cabeçalho do Designer de BOM. Você pode alterar o filtro usando a caixa de diálogo **Filtro**. A tabela a seguir descreve os campos nesta caixa de diálogo.

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
<td>Se o produto selecionado é um produto mestre, você pode definir as dimensões de produto ativas para a seleção principal. <strong>Observação:</strong> se você abrir o designer de BOM para um produto que não seja um produto mestre, as dimensões do produto não poderão ser selecionadas na caixa de diálogo <strong>Filtro</strong>.</td>
</tr>
<tr class="even">
<td>Local</td>
<td>Altere o local para o qual a árvore de BOM será exibida. O site padrão é o site padrão de estoque do item concluído.</td>
</tr>
<tr class="odd">
<td>Exibir princípio</td>
<td>Selecione o princípio de exibição de versão que se aplica ao roteiro e à estrutura de BOM atuais:
<ul>
<li>Quando o princípio estiver definido como <strong>Ativo ou Selecionado/Ativo</strong>, a versão válida do roteiro ou da BOM nesta data será encontrada.</li>
<li>Quando o princípio for definido como <strong>Selecionado/Ativo ou Selecionado</strong>, você poderá selecionar uma versão de BOM ou uma versão de roteiro clicando em <strong>BOM</strong> &gt; <strong>Versões de BOM</strong> ou <strong>Roteiro</strong> &gt; <strong>Versões de roteiro</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data da versão</td>
<td>Insira a data da versão do roteiro e da BOM. A versão identifica qual BOM será utilizada em uma data específica, conforme determinado pelas datas de versão na configuração de versão da BOM.</td>
</tr>
<tr class="odd">
<td>Da quantidade</td>
<td>Filtre as versões ao selecionar uma quantidade inicial específica. Se você definir um valor, versões diferentes de BOM e de roteiro poderão ser selecionadas.</td>
</tr>
<tr class="even">
<td>Mostrar somente válido</td>
<td>Quando marca a caixa de seleção, a estrutura de árvore mostra somente as linhas de BOM com datas válidas. Clique com o botão direito do mouse ou clique duas vezes em uma linha de BOM para abrir a página <strong>Editar linha de BOM</strong>, onde você pode ver as datas de validade para essa linha de BOM.</td>
</tr>
</tbody>
</table>

Quando você usa o Designer de BOM para revisar ou editar BOMs que consistem em um ou mais níveis de fantasmas, o roteiro associado ao item superior normalmente se estende pela hierarquia completa da BOM. Para simplificar a visão geral, você pode bloquear o roteiro de nível superior na exibição ao clicar em **Exibir** &gt; **Bloquear roteiro**. Para desbloquear o roteiro, clique em **Exibir** &gt; **Desbloquear roteiro**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Adicionar e editar BOMs e linhas de BOM
Use as funções **Linhas de BOM**ou **BOM** para alterar as linhas de BOM ou a BOM. Quando você seleciona um nó na árvore, o tipo de nó determina as funções disponíveis.

| Função                            | descrição                                                                                               | Tipo de nó e condições                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Linhas de BOM &gt; Editar                 | Abra uma caixa de diálogo na qual é possível editar os atributos da linha de BOM.                                             | Essa função estará disponível quando um nó da linha de BOM estiver selecionado.                                                                                                                                                                                                                                   |
| Linhas de BOM &gt; Excluir               | Excluir uma linha de BOM da BOM selecionada.                                                                  | Essa função estará disponível quando um nó da linha de BOM estiver selecionado, e a BOM não estiver bloqueada para edição.                                                                                                                                                                                             |
| Linhas de BOM &gt; Adicionar antes da linha      | Abra uma caixa de diálogo na qual é possível selecionar uma variante de produto a ser incluída antes da linha de BOM selecionada.         | Essa função estará disponível quando um nó da linha de BOM estiver selecionado.                                                                                                                                                                                                                                   |
| Linhas de BOM &gt; Adicionar à BOM de componentes | Abra uma caixa de diálogo na qual é possível selecionar uma variante de produto a ser incluída ao final da BOM selecionada.       | Essa função estará disponível quando o nó selecionado tiver uma BOM selecionada. Se essa função não estiver disponível, talvez haja uma versão da BOM ausente para a variante de item selecionada. Nesse caso, você pode clicar em **BOM** &gt; **Criar versão** para criar a versão ausente para o nó selecionado. |
| Linhas de BOM &gt; Adicionar após a linha       | Abra uma caixa de diálogo na qual é possível selecionar uma variante de produto a ser incluída depois da linha de BOM selecionada.          | Essa função estará disponível quando um nó da linha de BOM estiver selecionado.                                                                                                                                                                                                                                   |
| BOM &gt; Criar versão             | Crie uma nova versão da BOM ou a BOM para a variante de produto do nó selecionado.                             | Essa função estará disponível quando o nó da linha de BOM selecionado estiver vinculado a um item com o tipo de produção **BOM** ou **Fórmula**.                                                                                                                                                  |
| BOM &gt; Cálculo                | Abra uma caixa de diálogo onde você pode executar o custo ou o cálculo do preço de venda para a variante de produto selecionada. | Essa função estará disponível quando o nó selecionado estiver relacionado a uma versão de BOM.                                                                                                                                                                                                         |
| BOM &gt; Verificação                      | Valide e verifique a BOM selecionada.                                                                      | Essa função estará disponível quando o nó selecionado estiver relacionado a uma versão de BOM.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Configuração do modo de exibição de árvore
Clique em **Configuração** para personalizar as informações mostradas no modo de exibição de árvore do Designer de BOM.

| Grupo de campos | Descrição                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BOM         | Use as caixas de seleção para marcar os critérios mostrados na estrutura de árvore. O Designer de BOM exibe os critérios selecionados na parte inferior das duas guias. |
| Roteiro       | Use as caixas de seleção para marcar os critérios mostrados nos roteiros.                                                                                    |






