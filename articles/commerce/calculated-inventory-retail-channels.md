---
title: Calcular a disponibilidade de estoque em canais de varejo
description: Este tópico descreve as opções para mostrar o estoque disponível da loja e dos canais online.
author: hhainesms
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 29efccab017d9dff98872871bfe953fba19d2c30
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799676"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcular disponibilidade de estoque para canais de varejo

[!include [banner](../includes/banner.md)]

Este tópico descreve como uma empresa pode usar o Microsoft Dynamics 365 Commerce para verificar a disponibilidade estimada de produtos nos canais online e na loja.

## <a name="accuracy-of-calculation"></a>Precisão do cálculo

O Commerce usa vários servidores e bancos de dados para garantir escalabilidade e desempenho. Portanto, é importante que você entenda que os valores de estoque disponíveis fornecidos pelo aplicativo de ponto de venda (PDV), pelas APIs (interfaces de programação de aplicativos de disponibilidade de estoque de comércio eletrônico) e pelas páginas de estoque disponíveis na sede do Commerce podem não ser 100% precisos em tempo real. Se as transações criadas para produtos no canal online ou na loja ainda não foram sincronizadas com o servidor e o banco de dados da sede do Commerce, talvez as páginas de estoque disponíveis na sede do Commerce não exibam o valor exato do estoque em tempo real desses produtos. Por outro lado, se você configurou sua empresa para que os usuários na sede do Commerce ou em outros aplicativos integrados possam vender, receber, devolver ou ajustar o estoque de uma loja ou depósito online, talvez o PDV ou o canal online não tenha todas as informações necessárias para mostrar um valor preciso em tempo real dos itens.

Este tópico explica os processos de sincronização de dados que podem ser executados com frequência para ajudar a limitar a latência de dados entre aplicativos ou canais. Entretanto, é fundamental que você entenda que todos os dados de disponibilidade fornecidos durante o dia operacional são considerados um valor estimado. Portanto, se você tentar comparar as informações de estoque disponíveis que o aplicativo fornece com o estoque físico real nas prateleiras ou se tentar comparar os valores disponíveis mostrados no PDV com os dados disponíveis encontrados no mesmo depósito na sede do Commerce, os valores podem ser diferentes. Essa diferença durante o dia operacional é esperada e não deve ser considerada um problema. Se você deseja auditar dados e garantir que os valores fornecidos nas APIs de disponibilidade de estoque e na sede do Commerce correspondam às unidades físicas reais encontradas nas prateleiras de sua loja ou depósito, o melhor momento para fazê-lo é quando as operações do canal tiverem sido interrompidas durante o dia e todas as transações tiverem sido sincronizadas corretamente entre a sede do Commerce e o canal.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Usar APIs de pesquisa de estoque em solicitações de disponibilidade de estoque de comércio eletrônico

Você pode usar as seguintes APIs para mostrar a disponibilidade do estoque de um produto quando seus clientes realizarem compras em um site de comércio eletrônico.

- **GetEstimatedAvailability** – use esta API para saber a disponibilidade de estoque do item no depósito do canal de comércio eletrônico ou em todos os depósitos vinculados à configuração do grupo de atendimento para o canal de comércio eletrônico. Essa API também pode ser usada para depósitos em uma área ou raio de pesquisa específico, com base em dados de longitude e latitude.
- **GetEstimatedProductWarehouseAvailability** – Use esta API para solicitar estoque de um item em um depósito específico. Por exemplo, você pode usá-la para mostrar a disponibilidade do estoque em cenários que envolvem a retirada da ordem.

> [!NOTE]
> Essas APIs substituem as APIs **GetProductAvailabilities** e **GetAvailableInventoryNearby** na versão do Dynamics 365 Retail 10.0.7 e anterior.

Ambas as APIs buscam dados do servidor do Commerce e fornecem uma estimativa do estoque disponível para uma combinação específica de um produto ou variante de produto e um depósito. Embora outras APIs disponíveis no servidor do Commerce possam ser utilizadas diretamente na sede do Commerce para verificar a quantidade de produtos disponíveis, não recomendamos que elas sejam usadas em um ambiente de comércio eletrônico por causa de possíveis problemas de desempenho e impacto relacionado que essas solicitações frequentes podem ter nos servidores da sede do Commerce. Além disso, se o estoque disponível for calculado por meio do servidor do Commerce, é mais provável que o cálculo inclua o estoque vendido em transações recentes de comércio eletrônico que ainda não foram sincronizadas com a sede do Commerce. Embora a sede do Commerce possa carecer de informações sobre essas transações, o servidor do Commerce e o banco de dados do canal dispõem dos dados. Sendo assim, os dados serão levados em consideração e podem ajudar a fornecer uma estimativa mais precisa do estoque disponível de um produto.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Introdução à disponibilidade calculada de estoque do comércio eletrônico

Antes de usar as duas APIs mencionadas anteriormente, você deve habilitar o recurso **Cálculo otimizado de disponibilidade de produtos** pelo espaço de trabalho **Gerenciamento de recursos** na Matriz do Commerce.

Antes que as APIs possam calcular a melhor estimativa de disponibilidade de estoque de um item, um instantâneo periódico da disponibilidade de estoque da sede do Commerce deve ser processado e enviado ao banco de dados do canal usado pela unidade de escala do Commerce de comércio eletrônico. O instantâneo representa as informações que a sede do Commerce tem sobre a disponibilidade de estoque quanto a uma combinação específica de um produto ou variante de produto e um depósito. Pode incluir ajustes ou movimentos de estoque devidos a recebimentos de estoque, remessas ou outros processos executados na sede do Commerce e sobre os quais o canal de comércio eletrônico tem informações apenas em razão do processo de sincronização.

O instantâneo do banco de dados criado pelo trabalho **Disponibilidade do produto** calcula apenas as transações de estoque que foram processadas e lançadas na sede do Commerce no momento em que o instantâneo foi obtido. Se o estoque foi vendido quanto a um produto em um depósito da loja por meio de uma ordem de venda do cliente cash-and-carry ou assíncrona no aplicativo de PDV, a sede do Commerce não terá imediatamente as informações sobre a transação de emissão de estoque relacionada da venda. Ela terá informações sobre o estoque vendido em relação a esses tipos de vendas da loja só após o trabalho P carregar a transação relacionada usando o banco de dados do canal da loja para a sede do Commerce e a ordem de venda relacionada ser criada por meio do lançamento de demonstrativos ou dos processos de lançamento de fluxo constante. O processo de criação da ordem na sede do Commerce cria as transações de estoque relacionadas. Em ordens de canal de comércio eletrônico, a sede do Commerce só tem informações sobre as transações de estoque depois que as transações são enviadas à sede do Commerce por meio do trabalho P e o processo de sincronização de pedidos é concluído. Portanto, é importante que você entenda que o valor do instantâneo de estoque fornecido no trabalho **Disponibilidade do produto** pode não ser 100% exato em tempo real por causa do constante processamento de vendas que ocorre nos servidores distribuídos.

Para obter um instantâneo do estoque na sede do Commerce, siga as etapas a seguir.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Produtos e estoque \> Disponibilidade do produto**.
1. Selecione **OK** para executar o trabalho **Disponibilidade do produto**. Você também pode programar esse trabalho para que seja executado em lote.

Após a execução do trabalho **Disponibilidade do produto**, os dados coletados devem ser enviados para os bancos de dados do canal de comércio eletrônico, a fim de que o último instantâneo do estoque da sede do Commerce possa ser considerado no cálculo do estoque disponível estimado.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Execute o trabalho **1130** (**Disponibilidade do produto**) para sincronizar os dados do instantâneo que o trabalho **Disponibilidade do produto** criou da sede do Commerce para os bancos de dados do canal.

Quando a disponibilidade de estoque é solicitada na API **GetEstimatedAvailability** ou **GetEstimatedProductWarehouseAvailability**, um cálculo é executado para tentar obter a melhor estimativa possível de estoque do produto. O cálculo faz referência a quaisquer ordens de clientes de comércio eletrônico que estão no banco de dados do canal, mas que não foram incluídas nos dados de instantâneo fornecidos pelo trabalho 1130. Essa lógica se dá por meio do rastreamento da última transação do estoque processada na sede do Commerce e da comparação desta com as transações no banco de dados do canal. Ela fornece uma linha de base para a lógica de cálculo de canal, para que os movimentos de estoque adicionais que ocorreram nas transações de ordens de venda do cliente no banco de dados do canal de comércio eletrônico possam ser considerados no valor de estoque estimado fornecido pela API.

A lógica de cálculo de canal retorna um valor fisicamente disponível estimado e um valor total disponível para o produto e o depósito solicitados. Os valores podem ser mostrados no seu site de comércio eletrônico, se você preferir, ou podem ser usados para acionar outra lógica comercial no seu site de comércio eletrônico. Por exemplo, você pode mostrar uma mensagem "fora de estoque" em vez da quantidade disponível real fornecida pela API.

A lógica de cálculo que as APIs de comércio eletrônico de canal usam no valor de estoque estimado pode avaliar o estoque com base apenas em ordens de clientes que foram criadas no banco de dados do canal, mas que ainda não foram sincronizadas e publicadas na sede do Commerce. Se o banco de dados do canal também contiver dados transacionais de vendas cash-and-carry em depósitos específicos da loja, as vendas cash-and-carry não serão levadas em consideração no cálculo de comércio eletrônico do canal desses depósitos.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Configurar a operação de pesquisa de estoque no canal de PDV

No Retail versão 10.0.9 e anterior, a operação **Pesquisa de estoque** do PDV usava uma chamada de serviço em tempo real para a sede do Commerce para obter informações de estoque do produto selecionado, para a loja atual do usuário e quaisquer outras lojas que são configurados para o grupo de atendimento como parte da configuração do canal da loja. No Commerce versão 10.0.10 e posterior, é possível desativar as chamadas de serviço em tempo real para a sede do Commerce. Em vez disso, é possível usar o cálculo de canal no servidor do Commerce para determinar o estoque fisicamente disponível da loja e de qualquer outro local definido no grupo de atendimento. Essa configuração de estoque calculado por canal também é útil em locais nos quais a conexão com a Internet não é confiável, porque não é preciso estar online para fazer pesquisas de estoque na sede do Commerce.

Quando configurado e gerenciado corretamente, o cálculo de canal pode fornecer uma estimativa mais confiável do estoque atual da loja, já que usa os dados transacionais que estão no banco de dados do canal do Commerce, mas sobre os quais a sede do Commerce talvez ainda não tenha informações. Por exemplo, se você usar a chamada de serviço em tempo real existente em pesquisas de estoque no PDV, a sede do Commerce provavelmente ainda não terá informações sobre uma venda cash-and-carry de um produto que acabou de ocorrer. Sendo assim, o valor do estoque disponível que a sede do Commerce devolve em relação a esse produto provavelmente excederá o estoque disponível real da loja em uma unidade. Entretanto, se o cálculo de canal for usado, a venda cash-and-carry poderá ser levada em consideração no cálculo e deduzida do valor disponível que é mostrado. Embora os valores fornecidos pelo cálculo de canal e pela chamada de serviço em tempo real sejam apenas estimativas do estoque disponível, é muito mais provável que o valor fornecido pelo cálculo seja preciso em relação à loja atual.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Introdução à disponibilidade de estoque calculada de canal do PDV

Para usar a lógica de cálculo no lado do canal e desativar as chamadas de serviço em tempo real para pesquisas de estoque no aplicativo de PDV, primeiro você deve habilitar o recurso **Cálculo otimizado de disponibilidade de produtos** pelo espaço de trabalho **Gerenciamento de recursos** na Matriz do Commerce. Além de habilitar o recurso, você deve fazer alterações no **Perfil da funcionalidade**.

Para alterar o **Perfil da funcionalidade**, siga estas etapas:

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**.
1. Selecione um perfil de funcionalidade.
1. Na Guia Rápida **Funções**, na seção **Cálculo da disponibilidade de estoque**, altere o valor do campo **Modelo de cálculo da disponibilidade de estoque** de **Serviço em tempo real** para **Canal**. Por padrão, todos os perfis de funcionalidade usam chamadas de serviço em tempo real. Portanto, você deve alterar o valor desse campo se desejar usar a lógica de cálculo de canal. Toda loja de varejo vinculada ao perfil de funcionalidade selecionado será afetada por essa alteração.

Em seguida, você deve sincronizar as alterações no canal usando o processo de agenda de distribuição executando as seguintes etapas:

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Execute o trabalho **1070** (**Configuração do canal**).

Após a conclusão da configuração, as informações fornecidas sobre o estoque disponível fisicamente não usam mais uma chamada de serviço em tempo real quando um usuário no aplicativo de PDV usa a operação **Pesquisa de estoque** (exibições padrão e matriciais). Em vez disso, os dados sobre o estoque disponível fisicamente da loja atual e de todas as lojas do grupo de atendimento são calculados com base no último instantâneo conhecido fornecido ao banco de dados do canal na sede do Commerce. O valor do instantâneo é refinado ainda mais pelo cálculo de canal para ajustar o valor disponível fisicamente, com base em vendas adicionais ou transações de retorno existentes do produto selecionado no banco de dados do canal que não foram incluídas no último instantâneo sincronizado do trabalho 1130. Se o banco de dados do canal não contiver dados transacionais de nenhum dos depósitos ou lojas do grupo de atendimento, ele não conterá transações adicionais que possam ser fatoradas em um recálculo do valor. Com isso, a melhor estimativa de estoque disponível a ser mostrada sobre esses depósitos ou lojas são os dados do último instantâneo conhecido da sede do Commerce.

As telas **Atendimento da ordem** do PDV também aproveitam o cálculo de canal para mostrar o estoque disponível de itens quando uma linha de atendimento de ordens é selecionada e um usuário visualiza o painel **Detalhes** do estoque disponível sobre o item selecionado.

## <a name="optimize-your-inventory-data"></a>Otimizar os dados de estoque

Para garantir a melhor estimativa de estoque possível, é essencial que você use os seguintes trabalhos em lotes do Commerce e os execute com frequência:

- **Trabalho P** – O trabalho P é encontrado na página **Agendas de distribuição** e deve ser executado com frequência. Tal trabalho reúne ordens de comércio eletrônico, ordens de clientes assíncronas criadas pelo PDV e ordens de cash-and-carry criadas pelo PDV dos bancos de dados do canal para a sede do Commerce, para que possam ser processadas posteriormente. Até que esses dados sejam sincronizados do canal para a sede do Commerce, a última não terá informações sobre ajustes de estoque de produtos nos depósitos resultantes dessas transações.
- **Sincronizar ordens** – Este trabalho processa os dados transacionais brutos na sede do Commerce, fornecidos pelo trabalho P, e converte transações de ordens de comércio eletrônico e de clientes assíncronas em ordens de venda na sede do Commerce. Até que tal trabalho seja processado e as ordens do cliente sejam criadas, nenhuma transação de estoque será gerada. Portanto, o estoque disponível na sede do Commerce não considerará as transações.
- **Calcular demonstrativos transacionais em lote** – Em transações cash-and-carry criadas na loja, o processo de lançamento de fluxo constante garante que o estoque relacionado às vendas seja atualizado com eficiência. Para obter o processamento mais eficiente de transações de estoque para ordens de cash-and-carry, configure seu sistema para usar [lançamento de fluxo constante](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Lançar demonstrativos financeiros em lote** – Este trabalho também é necessário para lançamento de fluxo constante. Segue o trabalho **Calcular demonstrativos transacionais em lote**. Esse trabalho lança sistematicamente os demonstrativos calculados, para que as ordens de vendas de cash-and-carry sejam criadas na sede do Commerce e esta reflita com mais precisão o estoque da loja.
- **Disponibilidade do produto** – Este trabalho cria o instantâneo do estoque da sede do Commerce.
- **1130 (Disponibilidade do produto)** – Este trabalho é encontrado na página **Agendas de distribuição** e deve ser executado imediatamente após o trabalho **Disponibilidade do produto**. Ele desloca os dados do instantâneo do estoque da sede do Commerce para os bancos de dados do canal.

Recomendamos não executar esses trabalhos em lote com muita frequência (em intervalos de alguns minutos). As execuções frequentes sobrecarregarão o Commerce Headquarters (HQ) e podem afetar o desempenho. Em geral, é uma boa prática executar a disponibilidade do produto e 1130 trabalhos por hora e agendar o trabalho P, sincronizar ordens e reduzir trabalhos relacionados à publicação de feed com a mesma frequência ou uma frequência superior.

> [!NOTE]
> Por razões de desempenho, quando os cálculos de disponibilidade de estoque de canal são usados para fazer uma solicitação de disponibilidade de estoque usando a API de comércio eletrônico ou a nova lógica de estoque do canal de PDV, o cálculo usa um cache para determinar se já passou tempo suficiente para justificar a execução da lógica de cálculo novamente. O cache padrão é definido como 60 segundos. Por exemplo, você ativou o cálculo do canal da sua loja e exibiu o estoque disponível de um produto na página **Pesquisa de estoque**. Se uma unidade do produto for vendida, a página **Pesquisa de estoque** não mostrará o estoque reduzido até que o cache tenha sido limpo. Depois que os usuários lançam transações no PDV, eles devem esperar 60 segundos antes de verificar se o estoque disponível foi reduzido.

Se o seu cenário comercial exigir um tempo de cache menor, entre em contato com o representante de suporte do produto para obter ajuda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]