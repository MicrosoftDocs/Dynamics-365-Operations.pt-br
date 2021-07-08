---
title: Calcular disponibilidade de estoque para canais de varejo
description: Este tópico descreve como uma empresa pode usar o Microsoft Dynamics 365 Commerce para verificar a disponibilidade estimada de produtos nos canais online e na loja.
author: hhainesms
ms.date: 04/23/2021
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
ms.openlocfilehash: 96a600279b7a90d6626d23ee8868de13e9dd0f14
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270876"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcular disponibilidade de estoque para canais de varejo

[!include [banner](../includes/banner.md)]

Este tópico descreve como uma empresa pode usar o Microsoft Dynamics 365 Commerce para verificar a disponibilidade estimada de produtos nos canais online e na loja.

## <a name="accuracy-of-inventory-availability"></a>Precisão da disponibilidade do estoque

O Commerce usa vários servidores e bancos de dados para garantir escalabilidade e desempenho. Portanto, é importante que você entenda que os valores de estoque disponíveis fornecidos pelo aplicativo de ponto de venda (PDV), pelas APIs (interfaces de programação de aplicativos de disponibilidade de estoque de comércio eletrônico) e pelas páginas de estoque disponíveis no Commerce headquarters podem não ser 100% precisos em tempo real. Se as transações criadas para produtos no canal online ou na loja ainda não foram sincronizadas com o headquarters, as páginas de estoque disponíveis no headquarters talvez não exibam o valor exato do estoque em tempo real desses produtos. Por outro lado, se você configurou sua empresa para que os usuários no headquarters ou em outros aplicativos integrados possam vender, receber, devolver ou ajustar o estoque de uma loja ou depósito online, talvez o PDV ou o canal online não tenha todas as informações necessárias para mostrar valores precisos em tempo real dos itens.

É fundamental que você entenda que todos os dados de disponibilidade fornecidos durante o dia operacional são considerados um valor estimado. Portanto, se você tentar comparar as informações de estoque disponíveis que o aplicativo fornece com o estoque físico real nas prateleiras ou se tentar comparar os valores disponíveis mostrados no PDV com os dados disponíveis encontrados no mesmo depósito na sede do headquarters, os valores podem ser diferentes. Essa diferença durante o dia operacional é esperada e não deve ser considerada um problema. Se você deseja auditar dados e garantir que os valores fornecidos em PDV, APIs e headquarters correspondam às unidades físicas reais encontradas nas prateleiras de sua loja ou depósito, o melhor momento para fazer isso é quando as operações do canal tiverem sido interrompidas durante o dia e todas as transações tiverem sido sincronizadas corretamente entre o headquarters e o canal.

## <a name="channel-side-inventory-calculation"></a>Cálculo de estoque do canal

O cálculo de estoque do canal é um mecanismo que pega os últimos dados de estoque de canal conhecidos no Commerce headquarters como uma linha de base e, em seguida, separa em alterações de estoque adicionais que ocorreram no canal, que não estão incluídas nessa linha de base, para calcular um estoque disponível previsto quase em tempo real. 

As alterações de estoque a seguir são consideradas atualmente na lógica de cálculo de estoque do canal:

- Estoque vendido por meio de ordens de cash and carry na loja
- Estoque vendido por meio de ordens de cliente na loja ou no canal online
- Estoque devolvido para loja
- Estoque atendido (separação, embalagem, remessa) do depósito da loja

Para usar o cálculo de estoque do canal, como um pré-requisito, um instantâneo periódico de dados de estoque do headquarters criado pelo trabalho **Disponibilidade do produto** deve ser enviado aos bancos de dados de canais. O instantâneo representa as informações que o headquarters tem sobre a disponibilidade de estoque quanto a uma combinação específica de um produto ou variante de produto e um depósito. Ele inclui somente as transações de estoque que foram processadas e lançadas no headquarters no momento em que o instantâneo foi obtido e talvez não seja 100% preciso em tempo real devido ao processamento de vendas constante que ocorre entre os servidores distribuídos.

- Se o estoque foi vendido para um produto em uma loja por meio de uma ordem de venda do cliente cash-and-carry ou assíncrona no aplicativo de PDV, o headquarters não terá imediatamente as informações sobre a transação de emissão de estoque relacionada da venda. O headquarters terá informações sobre o estoque vendido em relação a esses tipos de vendas da loja só após o trabalho P carregar a transação relacionada usando o banco de dados do canal da loja para o headquarters e as ordens de venda relacionadas serem criadas por meio do lançamento de demonstrativos ou dos processos de lançamento de fluxo constante. O processo de criação das ordens no headquarters cria as transações de estoque relacionadas. 
- Para ordens de canal de comércio eletrônico, o headquarters tem informações sobre as transações de estoque somente depois que as transações são enviadas ao headquarters por meio do trabalho P e o processo de sincronização da ordem é concluído.

Para obter um instantâneo do estoque no Commerce headquarters, siga as etapas a seguir.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Produtos e estoque \> Disponibilidade do produto**.
1. Selecione **OK** para executar o trabalho **Disponibilidade do produto**. Você também pode programar esse trabalho para que seja executado em lote.

Após a execução do trabalho **Disponibilidade do produto**, os dados coletados devem ser enviados para os bancos de dados do canal de comércio eletrônico, a fim de que o último instantâneo do estoque do headquarters possa ser considerado no cálculo do canal do estoque disponível estimado.

Para sincronizar os dados de instantâneo do headquarters com os bancos de dado de canal, siga estas etapas.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Execute o trabalho **1130** (**Disponibilidade do produto**) para sincronizar os dados do instantâneo que o trabalho **Disponibilidade do produto** criou do headquarters para os bancos de dados do canal.

## <a name="inventory-availability-apis-for-e-commerce"></a>APIs de disponibilidade de estoque para o comércio eletrônico

O Commerce fornece as seguintes APIs para cenários de comércio eletrônico para consultar a disponibilidade de estoque de um produto:

- **GetEstimatedAvailability** – Use esta API para consultar o estoque de um produto ou variante de produto no depósito de canal online ou nos depósitos vinculados ao grupo de preenchimento do canal online.
- **GetEstimatedProductWarehouseAvailability** – Use esta API para consultar estoque de um produto ou variante do produto de um depósito específico.

> [!NOTE]
> Essas APIs substituem as APIs **GetProductAvailabilities** e **GetAvailableInventoryNearby** na versão 10.0.7 e anterior do Commerce.

Ambas as APIs usam internamente a lógica de cálculo do canal e retornam a quantidade **física disponível** estimada, quantidade **disponível total**, **unidade de medida (UdM)** e o **nível de estoque** para o produto e o depósito solicitados. Os valores retornados podem ser mostrados no seu site de comércio eletrônico, se você preferir, ou podem ser usados para acionar outra lógica comercial no seu site de comércio eletrônico. Por exemplo, você pode impedir a compra de produtos com um nível de estoque "fora de estoque".

Embora outras APIs disponíveis no Commerce possam ser utilizadas diretamente no headquarters para buscar as quantidades de produtos disponíveis, não recomendamos que elas sejam usadas em um ambiente de comércio eletrônico por causa de possíveis problemas de desempenho e impacto relacionado que essas solicitações frequentes podem ter nos servidores da sede do headquarters. Além disso, com o cálculo do canal, as duas APIs mencionadas acima podem fornecer uma estimativa mais precisa da disponibilidade de um produto ao levar em conta as transações criadas nos canais que ainda não foram conhecidas pela matriz.

Para usar as duas APIs, você deve habilitar o recurso **Cálculo otimizado de disponibilidade de produtos** pelo espaço de trabalho **Gerenciamento de recursos** no headquarters. Se os canais online e de armazenamento usarem os mesmos depósitos de atendimento, você também deverá habilitar o recurso **Lógica de cálculo de estoque do canal de comércio eletrônico avançado** para ter a lógica de cálculo do canal dentro das duas APIs para levar em consideração nas transações não lançadas (cash-and-carry, ordens do cliente, devoluções) criadas no canal da loja. Será necessário executar o trabalho **1070** (**Configuração do canal**) após habilitar esses recursos.

Para definir como a quantidade de produto deve ser retornada na saída da API, siga estas etapas.

1. Vá para **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**.
1. Selecione a guia **Estoque** e, em seguida, na FastTab **APIs de disponibilidade de estoque para comércio eletrônico** configure o valor da configuração **Quantidade na saída da API**.
1. Execute o trabalho **1070** (**configuração do canal**) para sincronizar a última configuração para os canais.

A configuração **Quantidade na saída da API** fornece três opções:

- **Devolver quantidade de estoque** -quantidade disponível total e disponível física de um produto solicitado são devolvidas na saída da API.
- **Devolver quantidade de estoque subtraindo buffer de estoque** - A quantidade devolvida na saída da API é ajustada subtraindo-se o valor do buffer de estoque. Para obter mais informações sobre o buffer de estoque, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).
- **Não devolver quantidade de estoque** - Somente o nível de estoque é retornado na saída da API. Para obter mais informações sobre os níveis de estoque, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).

Você pode usar o parâmetro da API `QuantityUnitTypeValue` para especificar o tipo de unidade no qual você deseja que as APIs devolvam a quantidade. Esse parâmetro oferece suporte a opções de **unidade de estoque** (padrão), **unidade de compra** e **unidade de venda**. A quantidade devolvida é arredondada para a precisão definida da unidade de medida (UOM) correspondente na matriz.

A API **GetEstimatedAvailability** oferece os seguintes parâmetros de entrada para oferecer suporte a diferentes cenários de consulta:

- `DefaultWarehouseOnly` - Use este parâmetro para consultar o estoque de um produto no depósito padrão do canal online. 
- `FilterByChannelFulfillmentGroup` e `SearchArea` - Use esses dois parâmetros para consultar o estoque de um produto de todos os locais de retirada em uma área de pesquisa específica, com base em `longitude`, `latitude` e `radius`. 
- `FilterByChannelFulfillmentGroup` e `DeliveryModeTypeFilterValue` - Use esses dois parâmetros para consultar o estoque de um produto de depósitos específicos vinculados ao grupo de preenchimento do canal online e são configurados para dar suporte a certos modos de entrega. O parâmetro `DeliveryModeTypeFilterValue` oferece suporte às opções **tudo** (padrão), **remessa** e **retirada**. Por exemplo, em um cenário no qual uma ordem online pode ser executada a partir de vários depósitos de remessa, você pode usar esses dois parâmetros para consultar a disponibilidade de estoque de um produto em todos esses depósitos de remessa. Nesse caso, a API retorna a quantidade disponível e o nível de estoque do produto em cada depósito de remessa, além de uma quantidade agregada e um nível de estoque agregado de todos os depósitos de remessa no escopo da consulta.
 
Os módulos do ícone do carrinho, caixa de compra, seletor de armazenamento, lista de desejos e carrinho do Commerce consomem as APIs e os parâmetros mencionados acima para exibir mensagens no nível de estoque no site de comércio eletrônico. O construtor de sites do Commerce fornece várias configurações de estoque para controlar o comportamento de compras e merchandising. Para obter mais informações, consulte [aplicar configurações de estoque](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Pesquisa de estoque de PDV com cálculo do canal

Na versão 10.0.9 e anterior do Commerce, a operação **Pesquisa de estoque** do PDV usava uma chamada de serviço em tempo real para o headquarters para obter informações de estoque do produto selecionado, para a loja atual do usuário e quaisquer outras lojas que são configuradas para o grupo de atendimento como parte da configuração do canal da loja. Na versão 10.0.10 e posterior do Commerce, você pode desativar as chamadas de serviço em tempo real para o headquarters e, em vez disso, usar o cálculo do canal no Commerce Server para determinar o estoque disponível que está fisicamente disponível para a loja e quaisquer outros locais definidos no grupo de atendimento. Essa configuração de estoque calculada por canal também é útil em locais nos quais a conectividade com a Internet não é confiável, porque não é preciso estar online para fazer pesquisas de estoque no headquarters.

Quando configurado e gerenciado corretamente, o cálculo de canal pode fornecer uma estimativa mais confiável do estoque atual da loja, já que usa os dados transacionais que estão no banco de dados do canal do Commerce, mas sobre os quais o headquarters talvez ainda não tenha informações. Por exemplo, se você usar a chamada de serviço em tempo real existente em pesquisas de estoque no PDV, o headquarters provavelmente ainda não terá informações sobre uma venda cash-and-carry de um produto que acabou de ocorrer. Sendo assim, o valor do estoque disponível que o headquarters devolve em relação a esse produto provavelmente excederá o estoque disponível real da loja em uma unidade. Entretanto, se o cálculo de canal for usado, a venda cash-and-carry poderá ser levada em consideração no cálculo e deduzida do valor disponível que é mostrado. Embora os valores fornecidos pelo cálculo de canal e pela chamada de serviço em tempo real sejam apenas estimativas do estoque disponível, é muito mais provável que o valor fornecido pelo cálculo seja preciso em relação à loja atual.

Para configurar a operação **Pesquisa de estoque** no PDV no headquarters para usar a lógica de cálculo do canal e desativar a chamada de serviço em tempo real, siga estas etapas.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**.
1. Selecione um perfil de funcionalidade.
1. Na FastTab **Funções**, na seção **Cálculo da disponibilidade de estoque**, altere o valor do campo **Modo de cálculo da disponibilidade de estoque** de **Serviço em tempo real** para **Canal**. Por padrão, todos os perfis de funcionalidade usam chamadas de serviço em tempo real. Você deve alterar o valor desse campo se quiser usar a lógica de cálculo do canal. Toda loja de varejo vinculada ao perfil de funcionalidade selecionado será afetada por essa alteração.

Você deve sincronizar as alterações nos canais usando o processo de agenda de distribuição no headquarters executando as seguintes etapas:

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Execute o trabalho **1070** (**Configuração do canal**).

Após a conclusão da configuração, as informações fornecidas sobre o estoque disponível fisicamente não usam mais uma chamada de serviço em tempo real quando um usuário no aplicativo de PDV usa a operação **Pesquisa de estoque** (exibições padrão e matriciais). Em vez disso, os dados sobre o estoque disponível fisicamente da loja atual e de todas as lojas do grupo de atendimento são calculados com base no último instantâneo conhecido fornecido ao banco de dados do canal na sede do Commerce. O valor do instantâneo é refinado ainda mais pelo cálculo de canal para ajustar o valor disponível fisicamente, com base em vendas adicionais ou transações de retorno existentes do produto selecionado no banco de dados do canal que não foram incluídas no último instantâneo sincronizado do trabalho 1130. Se o banco de dados do canal não contiver dados transacionais de nenhum dos depósitos ou lojas do grupo de atendimento, ele não conterá transações adicionais que possam ser fatoradas em um recálculo do valor. Com isso, a melhor estimativa de estoque disponível a ser mostrada sobre esses depósitos ou lojas são os dados do último instantâneo conhecido da sede do Commerce.

As telas **Atendimento da ordem** do PDV também aproveitam o cálculo de canal para mostrar o estoque disponível de itens quando uma linha de atendimento de ordens é selecionada e um usuário visualiza o painel **Detalhes** do estoque disponível sobre o item selecionado.

## <a name="optimize-your-inventory-data"></a>Otimizar os dados de estoque

Para garantir a melhor estimativa de estoque possível, é essencial que você use os seguintes trabalhos em lotes do Commerce e os execute com frequência:

- **Trabalho P** – O trabalho P é encontrado na página **Agendas de distribuição** e deve ser executado com frequência. Tal trabalho reúne ordens de comércio eletrônico, ordens de clientes assíncronas criadas pelo PDV e ordens de cash-and-carry criadas pelo PDV dos bancos de dados do canal para a sede do Commerce, para que possam ser processadas posteriormente. Até que esses dados sejam sincronizados do canal para a sede do Commerce, a última não terá informações sobre ajustes de estoque de produtos nos depósitos resultantes dessas transações.
- **Sincronizar ordens** – Este trabalho processa os dados transacionais brutos na sede do Commerce, fornecidos pelo trabalho P, e converte transações de ordens de comércio eletrônico e de clientes assíncronas em ordens de venda na sede do Commerce. Até que tal trabalho seja processado e as ordens do cliente sejam criadas, nenhuma transação de estoque será gerada. Portanto, o estoque disponível na sede do Commerce não considerará as transações.
- **Calcular demonstrativos transacionais em lote** – Em transações cash-and-carry criadas na loja, o processo de lançamento de fluxo constante garante que o estoque relacionado às vendas seja atualizado com eficiência. Para obter o processamento mais eficiente de transações de estoque para ordens de cash-and-carry, configure seu sistema para usar [lançamento de fluxo constante](./trickle-feed.md).
- **Lançar demonstrativos financeiros em lote** – Este trabalho também é necessário para lançamento de fluxo constante. Segue o trabalho **Calcular demonstrativos transacionais em lote**. Esse trabalho lança sistematicamente os demonstrativos calculados, para que as ordens de vendas de cash-and-carry sejam criadas na sede do Commerce e esta reflita com mais precisão o estoque da loja.
- **Disponibilidade do produto** – Este trabalho cria o instantâneo do estoque da sede do Commerce.
- **1130 (Disponibilidade do produto)** – Este trabalho é encontrado na página **Agendas de distribuição** e deve ser executado imediatamente após o trabalho **Disponibilidade do produto**. Ele desloca os dados do instantâneo do estoque da sede do Commerce para os bancos de dados do canal.

> [!NOTE]
> - É uma boa prática executar os trabalhos **Disponibilidade do produto** e **1130** por hora e agendar o trabalho P, sincronizar ordens e reduzir trabalhos relacionados à publicação de feed com a mesma frequência ou uma frequência superior.
> - Por motivos de desempenho, quando os cálculos de disponibilidade de estoque de canal são usados para fazer uma solicitação de disponibilidade de estoque usando a API de comércio eletrônico ou a lógica de estoque do canal de PDV, o cálculo usa um cache para determinar se já passou tempo suficiente para justificar a execução da lógica de cálculo novamente. O cache padrão é definido como 60 segundos. Por exemplo, você ativou o cálculo do canal da sua loja e exibiu o estoque disponível de um produto na página **Pesquisa de estoque**. Se uma unidade do produto for vendida, a página **Pesquisa de estoque** não mostrará o estoque reduzido até que o cache tenha sido limpo. Depois que os usuários lançam transações no PDV, eles devem esperar 60 segundos antes de verificar se o estoque disponível foi reduzido.

Se o seu cenário comercial exigir um tempo de cache menor, entre em contato com o representante de suporte do produto para obter ajuda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
