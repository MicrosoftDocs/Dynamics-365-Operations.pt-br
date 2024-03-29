---
title: Alternativas de entrega
description: Os tomadores de ordem de venda podem usar a página de Alternativas de entrega para descobrir opções alternativos de preenchimento da ordem.
author: Henrikan
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f58f7923d82f3aa371ba916352211195870f9a75
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572616"
---
# <a name="delivery-alternatives"></a>Alternativas de entrega

[!include [banner](../includes/banner.md)]

Os tomadores de ordem de venda podem usar a página de **Alternativas de entrega** para descobrir opções alternativas de preenchimento da ordem.

O layout da página **Alternativas de entrega** apresenta uma visão geral melhor de todas as opções alternativas. Também permite que os tomadores de ordem olhe além da empresa atual para obter oportunidades de atendimento. Eles agora podem exibir as oportunidades intercompanhia e as oportunidades dos fornecedores externos. Classificando as opções por data de entrega, os tomadores de ordem de venda podem exibir uma lista inteligente de alternativas de entrega. Além disso, os parâmetros nos ajudam a gerenciar melhor as entregas sugeridas. Como o tempo de transporte pode afetar datas de entrega, os tomadores de ordem de venda podem explorar várias opções de transporte que as transportadoras oferecem. Como as informações detalhadas são mostradas para cada sugestão, os tomadores de ordem podem tomar decisões diretamente da página **Alternativas de entrega**.

## <a name="open-the-delivery-alternatives-page"></a>Abra a página Alternativas de entrega

Você pode abrir a página **Alternativas de entrega** da linha de ordem de venda.

1. Selecione **Produtos e fornecimento \> Alternativas de entrega**.
1. Selecione **Detalhes da linha \> Entrega \> Alternativas de entrega.**

Outra forma de abrir a página **Alternativas de entrega** é abrir o espaço de trabalho **Processamento e consulta de ordem de venda** e clicar em **Ordens e favoritos \> Linhas de ordem atrasadas \> Alternativas de entrega** **Observação:** você só pode abrir a página **Alternativas de entrega** se as seguintes condições forem atendidas:

- Todas as informações da linha de venda obrigatórias são preenchidas.
- O campo **Controle da data de entrega** é definido para um valor diferente de **Nenhum**.

## <a name="delivery-date-control-methods"></a>Métodos de controle da data de entrega

O método de controle de data de entrega determina como o sistema estabelece as datas de entrega, como as alternativas de entrega são calculadas e quais informações são mostradas. Observe que o controle de datas de entrega leva em consideração os calendários. Portanto, os seguintes calendários podem afetar a data sugerida de recibo: calendário de depósito, calendário de transporte, calendário do fornecedor e calendário do cliente. A tabela a seguir descreve cada método de controle de data de entrega.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Método</strong></td>
<td><strong>Descrição</strong></td>
</tr>
<tr class="even">
<td><strong>Nenhuma</strong></td>
<td><ul>
<li>Alternativas de entrega para linhas de venda não são compatíveis. Esta opção desativa o controle de datas da entrega.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Prazo de entrega das vendas</strong></td>
<td><ul>
<li>As alternativas de entrega são calculadas com base no prazo de entrega das vendas predefinido. Os dias de transporte são calculados com base no modo de entrega.</li>
<li>As alternativas de entrega incluem depósitos que têm estoque disponível e ordens de suprimento/demanda.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>ATP</strong></td>
<td><ul>
<li>As alternativas de entrega são calculadas com base na lógica ATP - disponível para promessa. A disponibilidade atual e a disponibilidade futura prevista são consideradas. Os dias de transporte são calculados com base no modo de entrega.</li>
<li>As alternativas de entrega incluem depósitos que têm estoque disponível e ordens de suprimento/demanda.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>ATP + Margem de saída</strong></td>
<td><ul>
<li>As alternativas de entrega são calculadas para o método ATP, mas a margem de saída é incluída no cálculo.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>As alternativas de entrega são calculadas com base na lógica CTP (capacidade de comprometimento). A explosão de MRP é usada para determinar a disponibilidade. Observe que, pelo menos, o CTP compensa datas de entrega ao prazo de entrega de vendas. Os dias de transporte são calculados com base no modo de entrega.</li>
<li>As alternativas de entrega são sugestões para os seguintes depósitos:
<ul>
<li>Depósito atual</li>
<li>Depósito padrão</li>
<li>Todos os depósitos que têm estoque disponível</li>
<li>Todos os depósitos que têm ordens de suprimento</li>
<li>Todos os depósitos que têm versões da BOM (lista de materiais) ativa</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Exibir informações sobre alternativas de entrega

Esta seção descreve as informações sobre alternativas de entrega que estão disponíveis em cada guia rápida da página **Alternativas de entrega**.

### <a name="the-product-fasttab"></a>A guia rápida Produtos

Esta guia rápida mostra um resumo dos produtos e os detalhes da linha de venda atual.

### <a name="the-delivery-alternatives-fasttab"></a>A guia rápida Alternativas de entrega

Esta guia rápida mostra uma lista de alternativas de entrega classificada por data do recibo. Acima da lista, é possível selecionar em quais opções se baseiam as sugestões. Você também pode selecionar o modo de entrega, que determina os dias de transporte. As opções a seguir estão disponíveis:

- **Incluir outras variantes de produto** - Esta opção está disponível para produtos que têm variantes do produto. Incluirá alternativas de entrega para outras variantes do produto. Esta opção não está disponível para o CTP.
- **Incluir quantidade parcial** - Por padrão, somente as sugestões que atendem a quantidade total das linhas de venda são incluídas. Selecione esta opção para incluir as que atendem apenas parcialmente a linha de ordem. Essa opção é útil quando o cliente solicita uma data de entrega anterior e aceita a entrega parcial.
- **Incluir datas posteriores** - Por padrão, somente são mostradas as sugestões melhores (anteriores) que as datas atuais na linha de venda. Selecione esta opção para incluir as datas posteriores. Essa opção pode ser útil em situações onde os parâmetros diferente da data têm prioridade. Por exemplo, um fornecedor ou depósito específico podem ser preferenciais.
- **Modo de entrega** - Selecione o modo de entrega preferido para otimizar tempo e custo de transporte. Você verá imediatamente o efeito nas alternativas de entrega sugeridas. Portanto, é fácil comparar as alternativas.
- **Incluir compras** - Quanto compras for selecionada, as alternativas de entrega sugeridas incluirão opções para comprar de fornecedores externos e de outras companhias da empresa (intercompanhias). A opção **Incluir compras** é suportada para ATP e ATP + controle de data de entrega da margem de saída Estão inclusas as opções de compras do fornecedor de compra padrão do produto e de todos os fornecedores aprovados para o produto.
- Para fornecedores externos, o cálculo baseia-se no prazo de entrega da compra.
- Para intercompanhia, o cálculo considera o que está disponível na empresa de fornecimento, com base no controle de data de entrega na empresa de fornecimento.
- **Tipo de entrega** (Relevante para compras)
  - **Estoque** - Os produtos são enviados do depósito de fornecimento para o local/depósito na linha de venda. Em seguida, são enviados do depósito para o cliente.
  - **Entrega direta** - os produtos são enviados diretamente do depósito de fornecimento para o cliente.

### <a name="the-availability-information-fasttab"></a>A guia rápida Informações de disponibilidade

As informações desta guia rápida estão relacionadas à linha de entrega alternativa selecionada. As informações a seguir são mostradas, dependendo do controle da data de entrega da linha de venda:

- **Prazo de entrega das vendas**
  - **Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.
  - **Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.

- **ATP e ATP + margem de saída**
  - **Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.
  - **Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.
  - **Disponibilidade futura** - mostra uma representação gráfica da disponibilidade atual e futura para o local e depósito selecionados em **Alternativas de entrega**. Você pode selecionar as colunas do gráfico para ver mais informações detalhadas sobre a futura disponibilidade do produto. O controle deslizante mostra uma lista das ordens de suprimento e demanda relevantes dentro do limite de tempo de ATP.

- **CTP**
  - **Disponível hoje** - mostra o estoque físico disponível atual, físico reservado e físico disponível.
  - **Parâmetros** Mostra a unidade de estoque e o prazo de entrega de venda.
  - **Detalhamento** - mostra um detalhamento do suprimento da alternativa de entrega selecionada. É possível usar **Configuração** para alterar os campos e as dimensões de estoque mostradas no detalhamento.

### <a name="the-impact-of-selected-alternative-fasttab"></a>A guia rápida Impacto da alternativa selecionada

Esta guia rápida destaca o impacto da alternativa de entrega selecionada. Se você selecionar **OK**, a linha de venda será atualizada com valores destacados nas colunas SELECIONADAS. Observe que, se a quantidade na alternativa de entrega selecionada for menor que a quantidade na linha de vendas, uma agenda de entrega será criada, e a linha da ordem será dividida em duas linhas: uma linha para a quantidade selecionada e uma linha para a quantidade pendente. Você também pode atualizar a linha comercial, de forma que ela corresponda às linhas da agenda e afete o preço.

## <a name="additional-resources"></a>Recursos adicionais

[Promessa de ordem](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]