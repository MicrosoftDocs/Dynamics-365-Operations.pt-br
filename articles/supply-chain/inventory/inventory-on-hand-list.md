---
title: Lista de estoque disponível
description: Este tópico descreve como usar a página de listagem disponível para inspecionar os detalhes do estoque disponível. Ele mostra algumas das maneiras pelas quais as várias opções de filtragem e classificação funcionam juntas e como essas opções podem produzir resultados inesperados, às vezes quando são combinadas.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 94e54220a68889fd31ac3b269f7a7f6f8dd98c8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005193"
---
# <a name="inventory-on-hand-list"></a>Lista de estoque disponível

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar a página de **listagem disponível** para inspecionar os detalhes do estoque disponível. Ele mostra algumas das maneiras pelas quais as várias opções de filtragem e classificação funcionam juntas e como essas opções podem produzir resultados inesperados, às vezes quando são combinadas.

## <a name="query-your-on-hand-inventory"></a>Consulte seu estoque disponível

Para verificar a disponibilidade do estoque, vá para **Gerenciamento de estoque \> Consultas e relatórios \> Listagem disponível**.

A página **Listagem disponível** é atualizada automaticamente quando as transações são feitas no estoque. Essas transações podem ser previstas, físicas ou financeiras.

Use as seguintes ferramentas para localizar o conjunto de produtos que você está procurando:

- No painel de ações, selecione [**Dimensões**](#dimensions) para abrir uma caixa de diálogo na qual é possível adicionar ou remover colunas que são mostradas na grade **disponível**.
- No painel [**Filtros**](#filters-pane), insira valores para campos específicos para mostrar somente os registros que correspondam a esses valores. Observe que os filtros definidos aqui se aplicam a tabelas de origem que podem ser agregadas posteriormente, de acordo com as dimensões que você selecionou para serem mostradas. Para obter informações sobre como esse comportamento pode afetar os resultados, consulte os [exemplos](#examples) posteriormente neste tópico.
- No painel **Filtros**, selecione **Aplicar** para gerar a lista de estoque disponível correspondente na grade **Disponível**.
- Na grade **Disponível** selecione qualquer cabeçalho de coluna para classificar ou filtrar por valores nessa coluna. Um filtro rápido na parte superior da grade fornece opções de filtragem adicionais. Esses filtros se aplicam aos resultados, não às tabelas de origem. Para obter informações sobre como esse comportamento pode afetar os resultados, consulte os [exemplos](#examples) posteriormente neste tópico.

Para cada item correspondente, a grade **Disponível** fornece as seguintes colunas de informações de estoque.

| Coluna | descrição |
|---|---|
| Estoque físico | A quantidade física disponível no estoque. |
| Reserva física | A quantidade total que foi fisicamente reservada. |
| Quantidade física disponível | A quantidade disponível (não reservada) que está disponível no estoque físico.<p>**Físico disponível** é um campo calculado. O valor é igual ao valor do **Estoque físico** menos o valor do **Reservado físico**.</p> |
| Físico disponível em dimensões extra | A quantidade física disponível para todas as dimensões mostradas na grade. |
| Total encomendado | A quantidade total incluída nas ordens de entrada ou que tem uma quantidade positiva em vários diários de estoque. |
| Em ordem | A quantidade total incluída nas ordens de saída ou que tem uma quantidade negativa em vários diários de estoque. |
| Ordem reservada | A quantidade total que está reservada em recebimentos encomendados. O valor neste campo representa a quantidade total de itens em transações de saída que têm um status de _Reservado encomendado_. Os itens que são reservados como encomendados não estão fisicamente disponíveis no estoque. Portanto, não podem ser diretamente separados e entregues. |
| Disponível para reserva | A quantidade total de estoque disponível de um item que pode ser reservada.<p>**Observação:** se a caixa de seleção **Reservar itens encomendados** estiver marcada na página **Parâmetros de gerenciamento de estoque e depósito**, o valor neste campo incluirá os recebimentos esperados. Se a caixa de seleção estiver desmarcada, o valor excluirá os recebimentos esperados.</p> |
| Total disponível | A quantidade total disponível.<p>**Total disponível** é um campo calculado. O valor é igual ao **Valor físico** somado ao valor **Total encomendado** menos o valor **Na ordem**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Aplicar filtros para localizar os registros que você está procurando

Use o painel **Filtros** para filtrar a lista de estoque disponível para que ela inclua somente registros nos quais os valores de campo correspondam aos critérios de filtragem. Para definir um filtro, siga estas etapas.

1. No painel **Filtros**, localize o campo que você deseja filtrar.
2. No campo abaixo do nome do campo de destino, selecione um operador lógico (por exemplo, *começa com*, *igual a* ou *maior que*).
3. Informe ou selecione o valor para consultar.

> [!IMPORTANT]
> A página **Listagem disponível** é montada em uma tabela de estoque disponível detalhada que inclui todas as dimensões disponíveis. No entanto, a lista nesta página é um resumo. Portanto, é possível combinar linhas da tabela de origem, agregando valores de acordo com as dimensões que são mostradas.
>
> Os filtros definidos no painel **Filtros** se aplicam à tabela de origem, não à lista agregada. Esse comportamento pode, às vezes, produzir resultados inesperados. Para obter informações sobre como esse comportamento pode afetar os resultados, consulte os [exemplos](#examples) posteriormente neste tópico.
> 
> No entanto, os [filtros fornecidos na grade](#grid-filters) *se* aplicam à lista agregada. Esses filtros incluem filtro rápido na parte superior da grade e o filtro para cada título de coluna.

Você pode modificar o conjunto de filtros disponíveis no painel **Filtros** seguindo essas etapas.

- Para remover um filtro do painel, selecione o botão **Fechar** (**X**).
- Para adicionar um filtro, selecione **Adicionar** na parte superior do painel **Filtros**. A caixa de diálogo **Adicionar campos de filtro** que aparece mostra uma lista dos campos disponíveis. Ela também mostra informações sobre o tipo de dados e a tabela para cada campo. Use os cabeçalhos de coluna para filtrar e classificar a lista, conforme necessário, e marque a caixa de seleção para cada campo que você deseja adicionar ao painel **filtros**. Quando terminar, selecione **Inserir** para aplicar as alterações.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Selecionar quais dimensões serão mostradas

As dimensões informam mais sobre cada item na lista de estoque disponível e fornecem mais formas de classificar e filtrar a lista. As dimensões selecionadas para serem mostradas também afetam a forma como as linhas são agregadas na página **Listagem disponível**. Essa agregação, por sua vez, pode afetar como as linhas das tabelas de origem são combinadas nos resultados exibidos. Para obter informações sobre como esse comportamento pode afetar os resultados, consulte os [exemplos](#examples) posteriormente neste tópico.

Para personalizar a seleção de dimensões de estoque mostradas, siga estas etapas.

1. No Painel de Ação, selecione **Dimensões**.

    A caixa de diálogo **Exibição da dimensão** que aparece mostra cada dimensão.

2. Marque a caixa de seleção correspondente a cada dimensão que você deseja incluir na grade.
3. Se você deseja que a seleção seja usada por padrão na próxima vez que abrir a página **Listagem disponível**, defina a opção **Salvar configuração** como **Sim**. Se você definir esta opção como **Não**, a seleção será usada somente durante a sessão atual. Portanto, na próxima vez em que você abrir a página, a seleção padrão atual será usada.
4. Selecione **OK** para fechar a caixa de diálogo e aplicar as alterações.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtrar na saída da lista de estoque disponível

Você pode selecionar qualquer título da coluna na grade **Disponível** para classificar ou filtrar por valores dessa coluna. Um filtro rápido na parte superior da grade fornece opções de filtragem adicionais. Esses filtros se aplicam aos resultados, não às tabelas de origem. Para obter informações sobre como esse comportamento pode afetar os resultados, consulte os [exemplos](#examples) posteriormente neste tópico.

> [!NOTE]
> Você não pode filtrar e classificar por todas as colunas. A maioria das colunas de quantidade não inclui controles de classificação e filtragem, pois são campos calculados. A coluna **Na ordem** é uma exceção.

## <a name="examples"></a><a name="examples"></a>Exemplos

O sistema inclui uma tabela de estoque detalhada (não agregada) que mostra o estoque disponível a seguir.

| Nº do Item | Site | Depósito | Estoque Físico | Físico disponível |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Cenário 1

A página **Listagem disponível** é configurada para mostrar as seguintes dimensões finais:

- Nº de itens
- Site
- Depósito

No painel **Filtros**, os seguintes critérios de filtragem são configurados:

- **Número do Item** \| **é exatamente** \| _IA0001_
- **Físico Disponível** \| **menor ou igual a** \| _1_

Esta é a saída resultante.

| Nº do Item | Site | Depósito | Estoque Físico | Físico disponível |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Cenário 2

A página **Listagem disponível** é configurada para mostrar as seguintes dimensões finais:

- Nº de itens
- Site

No painel **Filtros**, os seguintes critérios de filtragem são configurados:

- **Número do Item** \| **é exatamente** \| _IA0001_
- **Físico Disponível** \| **menor ou igual a** \| _1_

Esta é a saída resultante.

| Nº do Item | Site | Estoque Físico | Físico disponível |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Observe que as configurações no painel **Filtros** se aplicam à tabela de estoque detalhada (não agregada) que é mostrada no início desta seção. Portanto, o critério **Disponível Físico** \| **menor ou igual a** \| _1_ localiza duas linhas dessa tabela (a primeira e terceira linhas, cada uma mostra um valor **Físico Disponível** de _1_). No entanto, nesse cenário, a página **Lista disponível** não é configurada para mostrar a dimensão do **Depósito**. Portanto, ela agrega as duas linhas originais em uma única linha resultante, porque ambas as linhas têm valores idênticos em todas as dimensões que são mostradas. Essa linha parece violar o critério de filtragem, porque o valor **Físico Disponível** é mostrado como _2_. No entanto, o resultado está correto, pois as configurações no painel **Filtros** se aplicam à tabela de origem, não à tabela agregada que é mostrada na página **Lista disponível**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]