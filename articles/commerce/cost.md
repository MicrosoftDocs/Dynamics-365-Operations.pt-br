---
title: Configuração de custo para gerenciamento de ordem distribuído (GOD)
description: Este tópico descreve a funcionalidade de configuração de custo para o gerenciamento de ordem distribuído (GOD) do Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f3ed387bf7925785c33e2f0c07e9aba898334567
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795970"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Configuração de custo para gerenciamento de ordem distribuído (GOD)

[!include [banner](../includes/banner.md)]

As organizações consideram vários componentes de custo para determinar o local ideal do qual atender uma ordem. Alguns desses componentes de custo são os custos de remessa, os custos de manutenção e os custos de embalagem. Uma combinação desses custos é calculada para determinar o local de atendimento.

Quando a primeira iteração do gerenciamento de ordem distribuído (GOD) no Dynamics 365 Commerce otimizou a atribuição de ordens para os locais de atendimento, somente a distância foi fatorada. Embora a distância possa ser correlacionada com o custo, não é o mesmo que o custo. Por exemplo, um método de remessa de entrega em 24 horas custa mais que a remessa em três ou sete três dias para a mesma distância.

O recurso de configuração de custo permite que os varejistas definam e configurem componentes de custo adicionais de que serão calculados e fatorados para determinar o local ideal para atender linhas da ordem.

Quando os componentes de custo são configurados, o agente de resolução do GOD usa somente essas definições de custo para determinar o local ideal para o atendimento da ordem. Ele não considera o componente de distância como custo. No entanto, se nenhum componente de custo for configurado, o agente de resolução do GOD usará o componente de distância como um custo para determinar o local ideal para o atendimento da ordem.

## <a name="set-up-cost-components"></a>Configurar componentes de custo

Dois tipos principais de componentes de custo podem ser definidos no sistema: **Remessa** e **Outro**.

Ambos os tipos de componente de custo oferecem suporte a várias bases de cálculo, conforme mostrado na tabela a seguir.

<table>
<thead>
<tr>
<th>Tipo de componente de custo</th>
<th>Base de cálculo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Remessa</td>
<td>
<ul>
<li>Simples</li>
<li>Em Camadas</li>
</ul>
</td>
</tr>
<tr>
<td>Outro</td>
<td>
<ul>
<li>Ordem de venda</li>
<li>Linha de venda</li>
<li>Local</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Tipo de componente de custo de remessa

Esta seção explica como configurar cada combinação do tipo de componente de custo **Remessa** e uma base de cálculo para os custos de remessa. Ele também explica como o agente de resolução do GOD usa cada combinação.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Tipo de componente de custo = Remessa e Base de cálculo = Simples

Se uma combinação do tipo de componente de custo **Remessa** e a base de cálculo **Simples** for usada, os custos de remessa para um modo de entrega serão baseados em um custo ou uma distância simples.

Você deve configurar os seguintes campos para essa combinação:

- **Fator de custo** — insira um identificador exclusivo para o fator de custo.
- **Descrição** — insira o nome e a descrição do fator de custo.
- **Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico. Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.
- **Ativo** — indicar se o fator de custo está ativo. O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.
- **Empresa** — especifique a entidade legal para a qual o fator de custo está configurado. Todas as linhas dos critérios de cálculo devem estar para a mesma entidade legal.
- **Modos de entrega** — especifique os modos de entrega para os quais o custo está configurado.
- **Tipo de cálculo** — especifique como o custo deve ser calculado para um modo de entrega específico. Há suporte para dois tipos de cálculo:

    - **Fixo** — um custo simples é usado para o modo de entrega. Se você selecionar este tipo de cálculo, o campo **Custo** definirá o custo simples.
    - **Por unidade de distância** — os custos para o modo de entrega serão calculados como o valor de custo que é especificado no campo **Custo** vezes a distância entre o endereço de entrega e os locais.

- **Custo** — especifique o valor do custo que é usado em conjunto com o campo **Tipo de cálculo** para calcular o custo para um modo de entrega.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Tipo de componente de custo = Remessa e Base de cálculo = Em camadas

Se uma combinação do tipo de componente de custo **Remessa** e a base de cálculo **Em camadas** for usada, os custos de remessa para um modo de entrega serão baseados no custo ou na distância. No entanto, nessa combinação, a distância é baseada em um intervalo em camadas de distâncias.

Você deve configurar os seguintes campos para essa combinação:

- **Fator de custo** — insira um identificador exclusivo para o fator de custo.
- **Descrição** — insira o nome e a descrição do fator de custo.
- **Custo padrão**— especifique o custo que deve ser usado para um modo de entrega se a distância entre o endereço de entrega e o local não estiver em nenhuma das distâncias em camadas para o modo de entrega.
- **Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico. Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.
- **Ativo** — indicar se o fator de custo está ativo. O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.
- **Empresa** — especifique a entidade legal para a qual o fator de custo está configurado. Todas as linhas dos critérios de cálculo devem estar para a mesma entidade legal.
- **Modos de entrega** — especifique os modos de entrega para os quais o custo está configurado.
- **Tipo de distância** — especifique se a definição de distância em camadas é uma distância aérea ou uma distância rodoviária.
- **Unidades de distância** — especifique a unidade na qual a distância em camadas é medida.
- **Distância de** — especifique o intervalo de início da distância em camadas.
- **Distância para** — especifique o intervalo de término da distância em camadas.
- **Tipo de cálculo** — especifique como o custo deve ser calculado para um modo de entrega específico e a distância em camadas. Há suporte para dois tipos de cálculo:

    - **Fixo** — um custo simples é usado para o modo de entrega. Se você selecionar este tipo de cálculo, o campo **Custo** definirá o custo simples.
    - **Por unidade de distância** — o custo para o modo de entrega e a distância em camadas será calculados como o valor de custo que é especificado no campo **Custo** vezes a distância entre o endereço de entrega e os locais.

- **Custo** — especifique o valor do custo que é usado em conjunto com o campo **Tipo de cálculo** para calcular o custo para um modo de entrega.

> [!NOTE]
> - Quando você define distâncias em camadas, o sistema valida se não há distâncias ausentes ou sobrepostas.
> - O tipo de distância usado para um modo de entrega deve ser igual em todas as distâncias em camadas.

### <a name="other-cost-component-type"></a>Tipo de componente de custo Outro

Esta seção explica como configurar cada combinação do tipo de componente de custo **Outro** e outro tipo de custo para custos que não sejam de remessa. Ele também explica como o agente de resolução do GOD usa cada combinação.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Tipo de componente de custo = Outro e Outro tipo de custo = Ordem de venda

Uma combinação de tipo de componente de custo **Outro** e o outro tipo de custo **Ordem de venda** é usada para definir custos que não sejam de remessa no nível da ordem de venda.

Você deve configurar os seguintes campos para essa combinação:

- **Fator de custo** — insira um identificador exclusivo para o fator de custo.
- **Descrição** — insira o nome e a descrição do fator de custo.
- **Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico. Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.
- **Ativo** — indicar se o fator de custo está ativo. O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.
- **Custo** — especifique o valor de custo para um custo que não seja de remessa no nível da ordem de venda.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Tipo de componente de custo = Outro e Outro tipo de custo = Linha de venda

Uma combinação de tipo de componente de custo **Outro** e o outro tipo de custo **Linha de venda** é usada para definir custos que não sejam de remessa no nível da linha ordem de venda.

Você deve configurar os seguintes campos para essa combinação:

- **Fator de custo** — insira um identificador exclusivo para o fator de custo.
- **Descrição** — insira o nome e a descrição do fator de custo.
- **Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico. Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.
- **Ativo** — indicar se o fator de custo está ativo. O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.
- **Custo** — especifique o valor do custo para um custo que não seja de remessa no nível da linha da ordem de venda.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Tipo de componente de custo = Outro e Outro tipo de custo = Local

Uma combinação de tipo componente de custo **Outro** e o outro tipo de custo **Local** é usada para definir custos que não sejam de remessa para um grupo de locais ou de um local individual.

Você deve configurar os seguintes campos para essa combinação:

- **Fator de custo** — insira um identificador exclusivo para o fator de custo.
- **Descrição** — insira o nome e a descrição do fator de custo.
- **Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico. Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.
- **Ativo** — indicar se o fator de custo está ativo. O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.
- **Grupo de atendimento** — especifique o grupo de locais para o qual o custo que não seja de remessa está definido.
- **Local de atendimento** — especifique o local para o qual o custo que não seja de remessa está definido.

    > [!NOTE]
    > Não é possível especificar um grupo de atendimento e um local de atendimento na mesma linha de critérios de base de cálculo do local.

- **Custo** — especifique o valor do custo para um custo que não seja de remessa no nível do grupo de atendimento ou no nível do local de atendimento.

> [!IMPORTANT]
> Para que o GOD considere esses custos quando for executado, você deverá adicionar o fator de custo ao perfil de atendimento relevante.


[!INCLUDE[footer-include](../includes/footer-banner.md)]