---
title: Gerenciamento de alteração de engenharia - Perguntas frequentes
description: Este artigo fornece respostas às perguntas frequentes sobre o recurso de gerenciamento de alteração de engenharia.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 16d29fa6485bae866a5209a855dfb928e8bc4783
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870772"
---
# <a name="engineering-change-management-faq"></a>Gerenciamento de alteração de engenharia - Perguntas frequentes

[!include [banner](../includes/banner.md)]

Este artigo fornece respostas às perguntas frequentes sobre o recurso de gerenciamento de alteração de engenharia.

## <a name="should-i-track-the-version-in-transactions"></a>Devo rastrear a versão nas transações?

Quando você cria uma categoria de alteração de engenharia, a página **Detalhes da categoria de alteração de engenharia** fornece uma opção chamada **Rastrear versão nas transações**. O que é essa configuração e qual a sua função?

- Se você definir a opção **Rastrear versão nas transações** como *Sim*, o campo **Grupo de dimensões** será filtrado para que mostre somente grupos de dimensões em que a versão seja uma dimensão ativa.
- Se você definir a opção **Rastrear versão nas transações** como *Não*, o campo **Grupo de dimensões** será filtrado, para que mostre somente grupos de dimensões em que a dimensão da versão **não** é uma dimensão ativa.

### <a name="if-you-track-the-version-in-transactions"></a>Se você rastrear a versão nas transações

Para categorias de engenharia em que você selecionou um grupo de dimensões em que a versão é uma dimensão ativa, você rastreará as versões nas transações de produtos dessa categoria. Neste caso, o produto da engenharia será um produto mestre e cada versão do produto será uma grade de produto que usa a dimensão da versão. Outras dimensões podem ser usadas juntamente com a dimensão da versão.

Nesse caso, cada versão de engenharia será tratada como uma grade em todos os processos. Portanto, se você tiver uma grade específica em uma transação (para que possa determinar qual grade foi vendida ou comprada), deverá gerenciar o estoque para cada versão, o planejamento mestre planejará a oferta de cada versão e assim por diante. Se você desativar uma versão do mercado, deverá ajustar manualmente suas datas de efetivação inicial e final para que reflitam a alteração. Você também deve gerenciar o estoque para verificar se você não tem versões não usadas dos itens em seus depósitos.

Embora esta opção exija mais esforço de gerenciamento, recomendamos ela se você precisar de rastreabilidade elevada das versões específicas usadas em cada transação.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Se você não rastrear a versão nas transações

Para categorias de engenharia em que você selecionou um grupo de dimensões em que a versão **não** é uma dimensão ativa, você **não** rastreará as versões nas transações de produtos dessa categoria. Nesse caso, se você não usar nenhuma outra dimensão, o produto de engenharia será um produto diferente. O produto ainda terá a versão e você poderá gerenciar informações sobre versões específicas (por exemplo, a lista de materiais \[BOM] e o roteiro), mas não poderá rastrear qual versão específica foi usada em cada transação. As datas de efetivação inicial e final indicam a validade de cada versão.

Esta opção é muito mais fácil de gerenciar, pois se você deseja alterar de uma versão para outra, basta fazer as alterações necessárias em uma ordem de alteração e atualizar as datas de efetivação inicial e final na versão de engenharia. Os processos de produção irão pegar a BOM e o roteiro necessários para o produto (e sua versão específica).

A maioria das empresas escolhe esta opção, pois ela oferece a versão e o gerenciamento de alterações, mas não adiciona a sobrecarga extra ao rastrear a versão em cada transação, no estoque e durante o planejamento mestre.

## <a name="which-fields-are-copied-from-the-released-item-template"></a>Quais campos são copiados do modelo de item liberado?

Quando uma empresa de engenharia cria um produto de engenharia, esse produto é criado como um produto liberado na empresa de engenharia. O produto liberado criado se baseia no *modelo de item liberado* selecionado. (O modelo de item liberado é um produto liberado existente.) O modelo de item liberado também é usado quando o produto é liberado para uma empresa operacional. Em cada caso, o modelo de item liberado define a maioria dos valores de campo para o produto liberado, e esses valores são provenientes da página **Detalhes de produtos liberados** associados.

As tabelas a seguir mostram os campos copiados durante esses processos.

| FastTab | Campos copiados na criação de produtos na empresa de engenharia | Campos copiados na liberação para uma empresa operacional |
|---|---|---|
| **Geral** | Todos os campos na seção **Administração** | Os mesmos campos que são copiados para a empresa de engenharia |
| **Compra** | Todos os campos | Todos os campos exceto **Unidade** |
| **Vender** | Todos os campos nas seções a seguir: **Ordem de venda**, **Administração**, **Tributação**, **Atualização de preço**, **Preço base de venda**, **Encargos**, **Descontos** e **Produto alternativo** | Todos os mesmos campos que são copiados para a empresa de engenharia, exceto **Unidade** |
| **Comércio exterior** | Todos os campos | Todos os campos |
| **Gerenciar Estoque** | Todos os campos e seções *exceto* **Dimensões físicas** e o **Peso variável** | Todos os mesmos campos que são copiados para a empresa de engenharia, exceto **Unidade** |
| **Engenheiro**, **Plano**, **Gerenciar custos**, **Gerenciar projetos**, **Dimensões financeiras** e **Depósito** | Todos os campos | Todos os campos exceto **Unidade de BOM** |
| **Variantes de produtos** | Todos os campos na seção **Variante do produto padrão** | Os mesmos campos que são copiados para a empresa de engenharia |

Além dos campos mostrados na tabela anterior, todas as configurações de ordem padrão são copiadas do modelo de item liberado, quando o produto é criado na empresa de engenharia e quando é liberado para uma empresa operacional. (Para exibir as configurações de ordem padrão para um modelo de item liberado, abra a página relevante **Detalhes do produto liberado** e, no Painel de Ações, na guia **Gerenciar estoque**, selecione **Configurações de ordem padrão**.)

> [!NOTE]
>
> - A unidade é padronizada de acordo com o modelo.
> - Para varejistas que usam a funcionalidade do Dynamics 365 Commerce, ao atribuírem uma categoria de varejo a um produto, a categoria de varejo aplica os valores padrão a muitos dos campos para o nível de produto lançado. Esses padrões substituem valores padrão que podem já ter sido definidos pelo modelo ou copiados da engenharia.

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Devo criar uma entidade legal separada para produtos de engenharia ou usar uma entidade legal existente?

Os requisitos comerciais determinam se você deve criar uma nova entidade legal para produtos de engenharia.

Ao criar uma empresa de engenharia separada, você pode manter os dados de engenharia separados e depois adicionar modificações, conforme necessário para as empresas operacionais locais. Dessa forma, você pode atingir as seguintes metas:

- Manter uma entidade separada na qual os produtos de engenharia são criados e gerenciados.
- Impedir que produtos de engenharia apareçam juntamente com os demais produtos liberados até que estejam prontos e lançados.
- Distinguir claramente os dados ditados pela engenharia e pelos dados locais.

Por outro lado, você provavelmente deve usar uma entidade legal existente como uma empresa de engenharia, se as seguintes condições se aplicarem a você:

- Você tem apenas uma entidade legal no seu sistema e/ou não precisa de uma separação clara entre produtos que estão sendo fabricados.
- Você não deseja duplicar alguns dados, como grupos de recursos, recursos, operações e (talvez) sites.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Qual é a nomenclatura para versões e grades de engenharia?

A nomenclatura para produtos de engenharia e grades de produtos funcionam da seguinte maneira:

- Para o produto de engenharia (ou seja, o produto distinto, se nenhuma dimensão for usada ou o produto mestre, se for usada alguma), a nomenclatura da regra de número será definida na categoria de produto de engenharia. Nela, você tem a opção de usar uma sequência numérica, constantes de texto e valores e nomes de atributos.
- Para cada variante de um produto de engenharia (se o produto de engenharia for um produto mestre, as grades são configuradas na categoria de produto de engenharia em que você especifica o grupo de dimensões), a nomenclatura da regra de número para cada grade é definida no grupo de dimensões. Nesse caso, você pode usar a ID de produto do mestre e os valores e nomes de dimensão.
