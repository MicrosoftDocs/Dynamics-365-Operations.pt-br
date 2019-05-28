---
title: Catálogos do call center
description: Este tópico descreve a funcionalidade específica de call center para catálogos no Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 65c1c3070aa48bf7a2016534071693716fabe831
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562732"
---
# <a name="call-center-catalogs"></a>Catálogos do call center

[!include [banner](includes/banner.md)]

Este tópico descreve a funcionalidade específica de call center vinculada a recursos de catálogo no Microsoft Dynamics 365 for Retail.

Os recursos de catálogo encontrados no Dynamics 365 for Retail podem ser usados para várias finalidades. Os recursos de catálogo foram inicialmente criados para dar suporte a integrações de comércio eletrônico de terceiros. O catálogo permitiu às empresas a criação de um agrupamento de produtos e atributos que podem ser publicados externamente para o consumo por uma solução de comércio eletrônico de terceiros.

Quando o suporte do canal de call center foi adicionado ao Dynamics 365 for Retail, o conceito de catálogo se expandiu para adicionar mais funcionalidades de suporte e gerenciamento de recursos relacionadas aos catálogos tradicionais de marketing direto ao consumidor. Uma empresa direta ao consumidor frequentemente produzirá catálogos impressos, enviados por email a um ou mais segmentos de clientes. Esses catálogos normalmente têm promoções ou ofertas específicas que somente serão liquidadas se o cliente fornecer um código de identificação do catálogo no momento da criação da ordem.

As empresas de marketing direto ao consumidor são muito focadas no rastreamento de resposta para esses catálogos para garantir que os custos para produzir e enviar e-mail para eles sejam justificados. Para rastrear a resposta, um código é impresso na parte de trás do catálogo e esse código é solicitado e aplicado quando o destinatário do catálogo ligar para fazer um pedido por telefone (ou agora o código pode ser inserido quando o cliente fizer um pedido online). Embora existam diferentes termos do setor que foram usados para identificar esse código de rastreamento de catálogo (incluindo código de tecla, código promocional, código de catálogo, código-fonte), nos referimos ao código no Dynamics 365 for Retail como a **ID do código-fonte**.

## <a name="basic-catalog-setup"></a>Configuração básica do catálogo

Vá para **Varejo** \> **Catálogos e sortimentos** \> **Todos os catálogos** para configurar o seu catálogo.

Ao criar um novo catálogo, você deve vincular o catálogo primeiro a um ou mais canais de varejo. Isso é feito na guia rápida **Canais de varejo** no formulário **Configuração de catálogo**. Clique em **Adicionar** e selecione um ou mais canais de varejo. Somente os itens vinculados ao canal selecionado [sortimentos](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) podem ser usados ao criar o catálogo.

Para adicionar produtos a um catálogo, uma hierarquia de navegação será escolhida. A hierarquia de navegação suportará a estrutura da categoria do catálogo. Você deve selecionar de uma das hierarquias de navegação vinculadas aos canais de varejo selecionados na guia rápida **Canais de varejo** da página **Catálogo**. Se um canal de navegação não tiver sido vinculado a um canal anteriormente, vá para **Varejo** \> **Configuração de canal** \> **Categorias de canal e atributos de produtos** para vincular a hierarquia de navegação padrão a cada um dos seus canais de varejo.

Na guia de menu **Catálogos**, na página **Configuração de catálogo**, clique em **Adicionar produtos** para configurar os produtos para adicionar ao catálogo, ou selecione um nó na hierarquia de navegação (selecionar um nó alterará a apresentação da tela e permitirá que você adicionar produtos diretamente a uma categoria no catálogo).

Clique no nó superior da hierarquia do catálogo para retornar à exibição do cabeçalho do catálogo principal. Configure datas efetivas e de vencimento, conforme necessário na guia rápida **Geral** .

Antes do catálogo ficar disponível para uso, ele deve ser publicado. Clique em **Validar catálogo** no menu **Catálogos** para processar a validação. Esta ação é necessária e validará se a configuração necessário é precisa. Clique em **Exibir resultados** para ver os detalhes da validação. Se forem encontrados erros, você deverá corrigir os dados e executar a validação novamente até que ela seja aprovada.

Depois que a validação for confirmada, clique em **Fluxo de trabalho** no menu para iniciar o fluxo de trabalho de aprovação. Clique em **Enviar** no menu **Fluxo de Trabalho** para executar o processo. Configure as etapas e os usuários autorizados para o fluxo de trabalho de **Varejo** \> **Configuração da sede** \> **Fluxos de trabalho de varejo**. O fluxo de trabalho definirá as etapas necessárias para obter o catálogo com um status **Aprovado** . Quando o catálogo estiver com um status **Aprovado** , clique na opção **Publicar** no menu **Catálogos** para concluir o processo. Depois do catálogo estiver em um status **Publicado** , ele poderá ser usado na entrada de ordem do call center e nos processo de envio do catálogo.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Use catálogos para impulsionar preços e promoções de ordem de venda

Um motivo essencial para definir um catálogo a ser usado em um call center é poder configurar preços e promoções específicos desse catálogo. Os clientes que fizerem pedidos a partir deste catálogo receberão esses preços e promoções na entrada de ordem do call center, se o **ID do código-fonte** for aplicado ao cabeçalho ou linhas da ordem.

Para configurar preços específicos do catálogo, selecione a opção **Grupos de preços** da guia **Catálogo** para vincular um ou mais grupos de preços ao catálogo. Todos os contratos comerciais, diários de ajuste de preço e descontos avançados de varejo (limite, quantidade, compra combinada) que forem vinculados ao mesmo grupo de preços serão aplicados quando os clientes solicitarem este catálogo.

Na guia rápida **Códigos-fonte**, clique em **Adicionar** para adicionar um ou mais identificadores de **ID de código-fonte** neste catálogo. Esse é o código que será aplicado durante a entrada da ordem do call center ao cabeçalho da ordem de venda (e linhas). Este código é usado para vincular a ordem de venda ao catálogo e, finalmente aos grupos de preços e a quaisquer preços especiais e promoções que foram configurados.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Use a ID de origem para rastrear custos e taxas de resposta

Ao definir a **ID do código-fonte**, você pode, como opção, vincular esta ID a uma **ID do mercado de destino**. A **ID do mercado de destino** pode ser definida em **Varejo** \> **Clientes** \> **Mercado de destino**. O mercado de destino é uma lista de clientes e/ou clientes potenciais que pertencem a um segmento definido pelo usuário. Vincular os dados do cliente ou do cliente potencial à ID do código-fonte permite a melhor visibilidade dos destinatários do catálogo. Se um cliente estiver vinculado a um mercado de destino e esse mercado de destino estiver vinculado à ID do código-fonte/catálogo ativos, os usuários do call center também poderão ver quais catálogos um cliente recebeu, selecionando a opção de menu **Códigos-fonte** na guia do menu **Clientes** na página **Atendimento ao cliente**. Durante a entrada de ordem, os usuários do call center também podem ver os catálogos específicos enviados ao cliente na lista suspensa **Origem** no cabeçalho da ordem de venda. Alterar o filtro de **Todos** para **Destinado** permitirá que o usuário veja os catálogos ativos específicos enviados ao cliente. Isso é útil em situações em que o cliente pode ter esquecido seu catálogo ou não consegue localizar ou ler o código de catálogo quando está chamando para criar uma ordem de venda.

É possível vincular várias IDs do código-fonte um catálogo. Geralmente, isso é necessário quando uma empresa quer rastrear a taxa de resposta por segmentos diferentes. A empresa fornecerá um código de catálogo exclusivo para diferentes segmentos de clientes, o que permitirá rastrear a taxa de resposta até o nível do segmento, dentro de um determinado evento de catálogo.

Selecionar um registro específico de **ID de código-fonte** e clicar na opção **Detalhes** na guia rápida **Códigos-fonte** fornecerá campos adicionais nos quais projeções de venda, custos com correspondência e datas da correspondência podem ser capturados. Esses dados são úteis para uma análise detalhada da eficácia do catálogo. Os usuários podem retornar a esta página ao longo do tempo e usar os botões **Análise de código-fonte** e **Comparar promoções** para acionar relatórios analíticos com base nos dados de vendas atuais e comparar custos e orçamento com os valores reais.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Configurar scripts de itens e ordens específicas de catálogo

Quando um usuário do call center estiver criando uma ordem de venda, eles podem usar scripts na tela. Esses scripts baseados em texto podem fornecer informações adicionais que o usuário deve informar ao cliente, ou podem ser notas/lembretes internos que o usuário do call center deve analisar e atuar, enquanto cria a ordem do cliente.

Geralmente, é bom ter diferentes conjuntos de scripts para diferentes catálogos. Na guia rápida **Scripts**, os scripts pré-definidos podem ser vinculados a um catálogo. Use o campo **Tempo** para determinar se o script aparecerá no início da ordem (assim que a ID do código-fonte for inserida no cabeçalho da ordem) ou no final da ordem (no formulário de resumo da ordem do cliente).

Ao selecionar um nó na hierarquia do catálogo e ao trabalhar com dados na guia rápida **Produtos**, os usuários também podem vincular scripts que são específicos para catálogos ou itens que usam a ação **Scripts**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Configurar itens de venda cruzada e venda específicos do catálogo

A vinculação de sugestões de venda/venda cruzada a um item pode ser feita a partir da configuração de produtos, mas em alguns casos, uma empresa pode promover itens especiais de venda/venda cruzada a clientes que solicitam um produto específico de um catálogo específico Na guia rápida **Produtos**, selecione um item e clique em **Itens de venda adicional/venda cruzada** para configurar produtos para venda ou venda cruzada a clientes que compram o item selecionado do catálogo. Durante a entrada de ordem do call center, os itens de venda/venda cruzada específicos do catálogo serão exibidos na tela, em vez de produtos padrão de venda/venda cruzada que podem ter sido configurados para esse item por meio da configuração usual do produto.

Os itens de venda/venda cruzada também podem aproveitar os recursos de script para mostrar mensagens específicas que um usuário verá quando o item de venda/venda cruzada for exibido durante a entrada da ordem. Os scripts vinculados a produtos de venda/venda cruzada configurados especificamente para um produto de catálogo só aparecerão quando o código-fonte desse catálogo for aplicado na entrada de ordem do call center.

## <a name="catalog-page-analysis"></a>Análise da página do catálogo

Na guia **Catálogos**, as opções estão disponíveis para configurar as **Páginas do catálogo**. Esse recurso permite definir as páginas específicas e os tipos de páginas para o tipo de catálogo impresso e seus custos associados.

Ao configurar os produtos no catálogo, use a ação **Layout de página de produto** para definir as páginas específicas, a porcentagem da página e a posição dos detalhes da página para o item. A configuração desses dados permitirá que os usuários obtenham vantagem do **Relatório de análise de área de catálogo**. Para encontrar este relatório, navegue para **Varejo** \> **Relatórios de call center** \> **Relatório de análise de área de catálogo**. Este relatório analisa as vendas feitas em relação ao catálogo (ordens de vendas nas quais o código de origem do catálogo estava vinculado ao cabeçalho ou à linha da ordem) e sua porcentagem de página e custos associados para fornecer um relatório de marketing direto tradicional**Análise de polegada quadrada**.

## <a name="catalog-requests"></a>Solicitações de catálogo

Como os catálogos são configurados e publicados no Dynamics 365 for Retail, o recurso **Enviar catálogo** pode ser utilizado. Esse recurso ficará disponível nas páginas **Pesquisa de cliente** e **Atendimento ao cliente**. Depois de selecionar um registro de cliente através da **Pesquisa de cliente** ou enquanto exibe uma conta de clientes selecionados do **Atendimento ao cliente**, os usuários podem selecionar a opção **Enviar catálogo** que abrirá uma caixa de diálogo permitindo que o usuário escolha entre uma lista de catálogos publicados e ativos. Um usuário pode selecionar um catálogo e uma quantidade e um ID de código-fonte específico para enviar. Quando eles clicam no botão **Enviar**, uma solicitação é armazenada, que pode ser gerenciada imprimindo o relatório **Solicitações de catálogo**. Para encontrar este relatório, navegue para **Varejo** \> **Relatórios de call center** \> **Relatório de solicitações de catálogo**. Ele lista todas as solicitações de catálogo, incluindo o nome do cliente e os detalhes do endereço do cliente que solicitou o catálogo. Esse relatório pode ser usado internamente ou os dados podem ser transmitidos para um terceiro que suporta processos externos para enviar fisicamente o catálogo ao cliente.

## <a name="additional-features"></a>Recursos adicionais

Na guia **Catálogos**, as opções para configurar uma **Agenda de pagamento** e **Produtos liberados** também estão disponíveis. Se o ID do código-fonte vinculado ao catálogo for aplicado durante a entrada de ordem do call center, o cliente será elegível para os produtos gratuitos ou o uso das agendas de pagamento do catálogo específico, conforme definido. Se for necessário limitar o cliente para poder selecionar apenas as programações de pagamento vinculadas ao seu catálogo e nem todas as programações de pagamento ativas no sistema, a caixa de seleção **Permitir apenas planos de catálogo** pode ser selecionada para um ou mais das IDs do código-fonte definidos para aplicar essas restrições.

## <a name="additional-notes"></a>Notas adicionais

Atualmente, quando uma ID de código-fonte é aplicada a uma ordem de venda no call center, ela é usada para impulsionar preços, promoções, scripts e vendas/vendas cruzadas específicas do catálogo. O sistema não proibirá nem impedirá que um produto que não esteja no catálogo seja solicitado na ordem de venda. Se um item for ordenado e não fizer parte do catálogo, o sistema primeiro usará o **Grupo de preços** definido no canal de call center (**Varejo** \> **Canais** \> **Call centers** \> **Todos os call centers**) para o preço de item ou promoções. Se nenhum preço de canal específico for encontrado, o preço de venda base do item será usado.
