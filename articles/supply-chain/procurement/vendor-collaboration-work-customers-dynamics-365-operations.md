---
title: ​Colaboração de fornecedores com clientes​
description: Este tópico descreve como você pode usar a colaboração do fornecedor para trabalhar com OCs e para monitorar o estoque em consignação.
author: GalynaFedorova
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5690630d4dde947798c925af66c73122c2efad3d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673764"
---
# <a name="vendor-collaboration-with-customers"></a>​Colaboração de fornecedores com clientes​

[!include [banner](../includes/banner.md)]

Este tópico descreve como você pode usar a colaboração do fornecedor para trabalhar com clientes no Microsoft Dynamics 365 Supply Chain Management. Os fornecedores podem concluir uma série de processos de negócios dos espaços de trabalho a seguir:

- **Confirmação de ordem de compra** – Monitora e responde às ordens de compra (OCs).
- **Lance do fornecedor** – Exibe solicitações de quotações (RFQs) e as responde inserindo lances.
- **Informações de fornecedor** – Exibe e atualiza dados mestre do fornecedor.
- **Faturamento** – Trabalha com faturas. Este tópico não cobre o espaço de trabalho **Faturamento**. Para obter mais informações sobre este espaço de trabalho, consulte [Espaço de trabalho de faturamento da colaboração de fornecedores](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md).

Os fornecedores também podem monitoram informações sobre o estoque em consignação.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Trabalhando com OCs no espaço de trabalho de confirmação da Ordem de compra

O espaço de trabalho **Confirmação de ordem de compra** permite que você responda a ordens de compra (OCs) enviadas para sua revisão. Ele também permite exibir informações sobre OCs que estão esperando uma ação do cliente e OCs que já foram confirmadas, mas ainda estão abertas.

Há três listas no espaço de trabalho **Confirmação de ordem de compra**:

- **Ordens de compra para revisão** – Essa lista mostra as OCs que foram enviadas você e estão aguardando uma resposta sua. Depois de responder, a PO desaparece da lista. Se o cliente enviar uma nova versão da OC antes de você responder à versão anterior, apenas a versão mais recente será exibida.
- **Aguardando ação do cliente** – essa lista mostra todas as OCs que você respondeu, mas que ainda não foram confirmadas pelo cliente. Se você aceitar a OC, você pode monitorá-la nessa lista até que o status mude para **Confirmada**. Se você rejeitar uma OC ou aceitá-la com alterações, você pode monitorá-la aqui até que o cliente envie uma nova versão.
- **Ordens de compra confirmadas em aberto** – Essa lista mostra todas as OCs de sua conta com status **Confirmada**. Quando produtos ou serviços são totalmente recebidos com relação à OC, ela desaparece da lista.

Você pode usar os seguintes páginas para trabalhar com OCs:

- **Ordens de compra para revisão** – Esta página contém as mesmas informações que a lista **Ordens de compra para revisão** no espaço de trabalho. Consulte a descrição anterior neste tópico.
- **Histórico de confirmação de fornecedor da ordem de compra** – Esta página todas as OCs e todas as versões das OCs que foram enviadas ao fornecedor. Também contém todas as respostas que foram devolvidas do fornecedor.
- **Ordens de compra confirmadas em aberto** Esta página contém as mesmas informações que a lista **Ordem de compra confirmada em aberta** no espaço de trabalho. Consulte a descrição anterior neste tópico.
- **Todas as ordens de compra confirmadas** – Esta página contém todas as OCs que foram confirmadas. As OCs desta página têm as OCs onde os produtos ou serviços foram recebidos. Você pode usar esta lista para monitorar as OCs para as quais você pode enviar faturas.

### <a name="responding-to-pos"></a>Respondendo OCs

As OCs que o cliente envia para revisão são exibidas no espaço de trabalho **Confirmação da ordem de compra** e na página **Ordens de compra para revisão**. Depois de abrir uma OC, pode aceitá-la, rejeitá-la ou aceitá-la com alterações. Podem haver anexos no cabeçalho da OC ou nas linhas individuais. Também é possível anexar informações sobre sua resposta no cabeçalho da OC ou nas linhas individuais. Por exemplo, você pode sugerir um item substituto para uma das linhas.

Você pode visualizar e imprimir a OC como um arquivo PDF usando a opção **Visualizar/Imprimir**. Você também pode usar a ação **Exibir dimensões** para ocultar ou mostrar as seguintes colunas da dimensão: **Local**, **Depósito**, **Cor**, **Tamanho**, **Estilo** e **Configuração**. 

Se você usar a opção **Aceitar com alterações**, você pode aceitar ou rejeitar linhas individuais. Você também pode fazer as seguintes alterações em linhas:

- Alterar datas ou quantidades. Para atualizar a data de entrega confirmada em todas as linhas, use a opção **Atualizar data de entrega** no cabeçalho da OC.
- Dividir linhas para datas de entrega ou quantidades diferentes.
- Substituir um item. In the **Detalhes da linha**, informe uma descrição do item e o número do item no campo **Externo**.

Você não pode alterar informações de preço ou encargos, mas pode usar as notas para fazer sugestões para essas alterações.

Se o cliente enviar a você uma nova versão de uma OC, ela terá um sufixo de versão para indicar que é uma versão modificada de uma OC que foi enviada anteriormente. A página **Histórico de confirmações do fornecedor de ordens de compra** permite acompanhar o histórico de cada ordem.

## <a name="monitoring-consignment-inventory"></a>Monitorando o estoque em consignação

Se estiver usando o estoque em consignação, você poderá usar a interface de colaboração do fornecedor para exibir informações nas seguintes páginas:

- **Ordens de compra que consomem o estoque de consignação** - As OCs para inventário de consignação são geradas quando o cliente tem a propriedade do estoque. Essas OCs de consignação são mostradas somente nesta página. Elas não estão incluídas na página **Todas as ordens de compra confirmadas**.
- **Produtos recebidos de estoque de consignação** – essa página lista todas as transações em que a propriedade dos produtos foi transferida para a empresa que está consumindo o estoque. Use essas informações para faturar o cliente.
- **Estoque em consignação disponível** – essa página mostra o estoque em consignação disponível de propriedade da sua empresa, mas que está disponível no depósito do cliente.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Trabalhando com RFQs (solicitações de cotação) no espaço de trabalho de lance do fornecedor

O espaço de trabalho **Lance de fornecedor** permite que você exiba as RFQs (solicitações de cotação) que sua empresa foi convidada a responder. Você também pode responder às RFQs (solicitações de cotação).

O espaço de trabalho também mostra todas as RFQs (solicitações de cotação) que você ganhou ou perdeu. Além disso, se o sistema estiver configurado para o setor público, o espaço de trabalho mostrará as RFQs que estão disponíveis publicamente.

### <a name="viewing-rfqs"></a>Exibindo RFQs

Abra o espaço de trabalho **Lance de fornecedor** para acessar as seguintes informações:

- Selecione **Novos convites de lances** para ver as RFQs que sua empresa foi convidada a responder. Daqui, você pode exibir uma RFQ e iniciar o processo de lances. Você também pode consultar RFQs alteradas para as quais o novo lance deve ser enviado.
- Selecione **Lances retornados** para ver as RFQs que o cliente retornou, de forma que você pode fornecer mais informações ou atualizar o lance.
- Selecione **Lances em andamento** para ver as RFQs nas quais você ou a pessoa de contato que representa sua empresa estão trabalhando, mas ainda não enviaram.
- Selecione **Ofertas concedidas** para consultar quando o cliente concedeu pelo menos um item de linha em seu lance.
- Selecione **Lances perdidos** para consultar os lances nos quais todas as linhas foram rejeitadas.
- Selecione o link **Solicitação de cotações** para ver uma lista de todos os convites de RFQ do fornecedor e todos os lances que foram submetidos. A página **Solicitação de cotações** lista todos as RFQs nas quais um fornecedor foi envolvido. Você pode consultar por status.
- Selecione o link **Lances recusados** para ver uma lista de todos as RFQs nas quais a pessoa de contato de um fornecedor recusou o lance.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Trabalhando com RFQs que estão disponíveis publicamente

As pessoas que trabalham no setor público podem ver RFQs abertas e expiradas que foram disponibilizadas para o público.

- Selecione o link **Solicitações de cotações em aberto publicadas** para ver uma lista de RFQs abertas disponíveis ao público. Uma RFQ em aberto é aquela que ainda não expirou. Você pode encontrar a data de vencimento e a hora no cabeçalho da RFQ.

    Se você foi convidado para o lance, pode encontrar a mesma RFQ na página **Novos convites do lance**. Às vezes, você quer fazer um lance em uma RFQ em aberto, mas ainda não foi convidado para fazer o lance. Nesse caso, você pode se convidar, desde que o cliente tenha ativado o autoconvite para o caso de RFQ. 

    A página **Novos convites de lances** pode fornecer um filtro que permite exibir as RFQs abertas e identificar as que contêm linhas que correspondem às categorias de compras aprovadas. Para tornar este filtro disponível, você deve ativar o recurso *Permitir que os fornecedores pesquisem RFQs por categoria de aquisição* em seu sistema. Os administradores podem usar o espaço de trabalho **Gerenciamento de recursos** para verificar o status deste recurso e ativá-lo, se necessário. Lá, o recurso está listado da seguinte maneira:

    - **Módulo:** *Contas a pagar*
    - **Nome do recurso:** *Permitir que os fornecedores pesquisem RFQs por categoria de aquisição* <!-- KFM: I don't see this here, is this right? -->

    Você pode aprimorar a acessibilidade do link **Solicitações de cotações em aberto publicadas** ativando o recurso *Exiba o link "Solicitações de cotações em aberto publicadas" como um bloco*. Esse recurso converte o link em um bloco e o move para um local proeminente, de modo que seja fácil de encontrar. Os administradores podem usar o espaço de trabalho **Gerenciamento de recursos** para verificar o status deste recurso e ativá-lo, se necessário. (Desde a versão 10.0.21 do Supply Chain Management, o recurso é ativado por padrão.) Nesse caso, o recurso é listado da seguinte maneira:

    - **Módulo:** *Tarefas de compras e fornecimento*
    - **Nome do recurso:** *Exiba o link "Solicitações de cotações em aberto publicadas" como um bloco*

- Selecione o link **Solicitações de cotações fechadas publicadas** para ver uma lista de RFQs fechadas disponíveis ao público. Uma RFQ fechada é aquela que expirou. Você pode encontrar a data de vencimento e a hora no cabeçalho da RFQ.

    Uma RFQ fechada mostra todas as ofertas de fornecedor até o nível da linha. Como os lances são concedidos ou rejeitados, estas informações são refletidas na RFQ fechada. Todos os anexos que estão incluídos no lance também estão disponíveis.

> [!NOTE]
> Essa funcionalidade está disponível somente se a configuração do setor público estiver ativada.

### <a name="bidding"></a>Oferta

- Selecione **Lance** para começar a fazer o lance em uma RFQ.

    Quando a edição estiver ativada para os campos do lance nos cabeçalhos e linhas de uma RFQ, você pode inserir o lance diretamente na grade. Você também deve considerar qualquer informação adicional de lance que deve ser adicionada nos detalhes da linha.

    Quando você começar a trabalhar em um lance, ele aparecerá na seção **Lances em andamento**.

    A qualquer momento antes da data de vencimento, você poderá salvar um lance. Você poderá retornar posteriormente para concluir e a enviar o lance. Depois de enviar um lance, você pode chamá-lo novamente e atualizá-lo até a data de vencimento.

- Selecione **Redefinir de RFQ** para redefinir os dados inseridos para uma oferta e reverte para a RFQ original. Você pode redefinir o cabeçalho ou a linha.
- Selecione **Adicionar alternativa** ou **Remover alternativa** na grade de linha para trabalhar com alternativas.

    Algumas RFQs permitem lances alternativos. Você pode especificar lances alternativos somente para linhas do tipo **Categoria**, pois os itens específicos não podem ser adicionados como alternativas. 

- Selecione **Anexo da RFQ** ou **Anexo de linhas de RFQ** para abrir qualquer anexo que o cliente adicionou a uma RFQ. Selecione **Anexos do lance** ou **Anexos de linha do lance** para carregar os anexos com o lance.

    Pode haver os questionários que você deve responder antes de ter permissão para enviar um lance.

- Selecione **Recusar** se não quiser fazer o lance. Após selecionar **Recusar**, você não poderá cancelar a ação e inserir um lance.

Se uma RFQ for alterada, você deve inserir um novo lance. Você pode encontrar informações sobre a alteração na guia **Alterações** da página de RFQ. As RFQs aparecem na página **Novos convites do lance**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Acessando dados mestre de fornecedor no espaço de trabalho de informações de fornecedor

Como um fornecedor, você poderá acessar parte de informações que o cliente mantém no registro mestre do fornecedor. Portanto, você pode manter as informações atualizadas. Para atualizar as informações, você deve ter uma função (externa) administrativa de fornecedor.

As informações acessíveis são o nome do fornecedor, endereço, informações de contato, pessoas de contato e as informações de contato, números de identificação, números de registro de imposto, categorias de compras que o fornecedor foi aprovado para vender ao cliente, e informações sobre certificações.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
