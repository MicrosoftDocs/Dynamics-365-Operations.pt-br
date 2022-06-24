---
title: Configurar atendimento da ordem para lojas
description: Este artigo fornece uma visão geral de como configurar atendimento da ordem da loja.
author: BrianShook
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 12c60de59f1007256b67a56a5ede0b83857b73bd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855021"
---
# <a name="set-up-order-fulfillment-for-stores"></a>Configurar atendimento da ordem para lojas

[!include [banner](includes/banner.md)]

Vários varejistas querem otimizar o atendimento da ordem permitindo que as lojas atendam as ordens. O atendimento da ordem em nível de loja pode ajudar a amenizar os cenários de estoque excessivo de uma loja específica ou pode ser necessário de um ponto de vista logístico, nos casos em que uma loja tem capacidade extra ou está em um local mais próximo do cliente. Para tratar esta necessidade, uma operação de atendimento unificado da ordem está disponível no ponto de venda.

O atendimento das ordens em uma loja específica tem o depósito da loja designado no cabeçalho ou nas linhas da ordem.

A operação de atendimento da ordem no ponto de venda fornece uma área de trabalho única no ponto de venda que pode ser usada para processar as ordens. Isso inclui tudo, desde aceitar a ordem, marcá-la como remetida ou iniciar a retirada da loja.

## <a name="set-up-the-order-fulfillment-operation"></a>Configurar a operação de atendimento da ordem

O atendimento da ordem, [ID 928 da Operação](pos-operations.md), pode ser usado para acessar a área de trabalho de atendimento da ordem da loja no ponto de venda.

Siga as etapas na grade [Adicionar a operação a um botão](pos-screen-layouts.md) para especificar qual parâmetro usar ao chamar o atendimento da ordem no ponto de venda. Por padrão, após especificar as operações de atendimento da ordem, a opção **Todas as ordens** é selecionada. Quando configurada com este parâmetro, a operação listará todas as linhas da ordem de atendimento na loja atual. Também disponível está **Ordens a serem remetidas**, que podem ser atribuídas a um botão e utilizadas quando o usuário só quer ver as ordens que serão remetidas à loja. Finalmente, há **Ordens para retirada**. Quando chamada no ponto de venda, lista somente ordens a serem retiradas na loja. Os diferentes parâmetros podem ser atribuídos a botões diferentes para fornecer ao usuários uma variedade de formas para exibir o atendimento da ordem.

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Habilitar usuários para que acessem o atendimento da ordem no ponto de venda

A operação de atendimento da ordem não tem sua própria permissão imediata, mas no futuro, os usuários podem exigir a permissão **Permitir recuperar ordem** para chamar a operação do ponto de venda.

Em nível de loja, a definição da configuração fica disponível para determinar se uma linha de ordem deve ser aceita manualmente de dentro do ponto de venda. Se esta opção de configuração não for definida, as linhas da ordem serão aceitas, por padrão. Se a opção de configuração estiver ativada, os usuários no ponto de venda precisarão ter a permissão **Permitir ordem de aceitação** para aceitar ordens de dentro do ponto de venda.

### <a name="enable-manual-order-acceptance"></a>Habilitar a aceitação manual de ordens

Por padrão, as linhas de ordem atribuídas a uma loja são marcadas como **Aceitas**. Isso significa que é considerado que elas serão atendidas da loja atribuída e não estarão sujeitas à atribuição adicional. Em alguns casos, os varejistas talvez queiram aceitar as ordens manualmente antes de elas serem preenchidas. Por exemplo, se a loja tiver uma equipe pequena e não puder atender as ordens, o gerente da loja só aceitará as ordens para processamento que ele puder processar adequadamente em determinado dia. Até uma ordem ser aceita, ela poderá ser reatribuída pelo back-office para uma loja diferente. Dessa forma, a aceitação da ordem também fornece uma maneira de indicar que a ordem foi confirmada por uma loja e será atendida.

As linhas da ordem para retirada na loja estão marcadas como **Pendentes** e não estão sujeitas à aceitação.

Para ativar a aceitação manual de linhas da ordem, navegue até **Varejo e Comércio** \> **Canais** \> **Lojas** \> **Todas as lojas**. Selecione a loja e clique no ID para exibir os detalhes da loja. Clique em **Editar**. Na Guia Rápida **Geral**, localize o subcabeçalho **Atendimento da ordem** e altere **Aceitação manual** de **Não** para **Sim**.

### <a name="enable-reject-order-line-capability"></a>Habilitar o recurso da linha de ordem de rejeição

As linhas de ordem também podem ser rejeitadas no ponto de venda. Rejeitar uma linha de ordem significa que ela não será atendida nessa loja e envia a linha de ordem de volta para reatribuição em outra loja ou depósito. A permissão de rejeição da linha da ordem é concedida através da permissão **Permitir ordem de rejeição** no grupo de permissões de PDV associado ao trabalhador. Ao rejeitar uma linha, os varejistas podem obrigar seus trabalhadores a fornecerem um motivo para rejeição. Isso pode ser obtido utilizando códigos de informações do tipo **Atividade do código de informações** **Atendimendo da ordem** e atribuindo o código de informações **Rejeitar linha de ordem** no perfil de funcionalidade associado ao canal.

> [!NOTE]
> Apenas os códigos informativos da **Atividade de código informativo** tipo **Atendimento da ordem** podem ser atribuídos à ação **“Rejeitar linha de ordem**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações na base de dados do canal

Depois que a operação for atribuída à grade de botões, as permissões apropriadas forem atribuídas e o canal for configurado, as alterações deverão ser sincronizadas ao banco de dados do canal. Para fazer isso, navegue até **Varejo e Comércio** \> **TI de Varejo e Comércio** \> **Agenda de distribuição**. Selecione a agenda “” 1090-Registros" para sincronizar alterações na grade do botão e clique em **Executar agora**. Em seguida, sincronize as alterações de permissões selecionando "1060-Equipe" e clique em **Executar agora**. Em seguida, sincronize as alterações do canal selecionando "1070-Configuração do canal" e clique em **Executar agora**. Por fim, sincronize o código informativo criado recentemente para o motivo de rejeição selecionando "1110-Configuração global" e clique em **Executar agora**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Use o atendimento da ordem no ponto de venda

Abra o ponto de venda e selecione a operação de atendimento da ordem. Dependendo de como ela foi configurada, todas as linhas, as linhas de ordem para a retirada ou as linhas de ordem de remessa serão listadas.

### <a name="order-fulfillment-view"></a>Exibição de atendimento da ordem

A exibição de atendimento da ordem lista as linhas da ordem para atendimento na loja e tem as seguintes colunas:

- Número da ordem
- Número do produto
- descrição
- Quantidade encomendada
- Data de entrega solicitada
- Nome do Cliente
- Status do cumprimento

As informações adicionais de uma linha de ordem específica podem ser exibidas através da seleção da linha de ordem e pela abertura do menu suspenso localizado abaixo das informações do usuário conectado/turno mostradas no cabeçalho do ponto de venda. Esse menu inclui guias: 2 uma para detalhes da linha e outra para detalhes da ordem. A guia detalhes da linha inclui as seguintes informações:

- Quantidade encomendada
- Quantidade restante a ser remetida/retirada
- Quantidade separada
- Quantidade embalada
- Quantidade faturada (já retirada ou remetida)
- Modo de entrega
- Endereço de entrega

O menu suspenso de detalhes também tem uma guia que fornece mais detalhes em nível de ordem, incluindo:

- Nome do Cliente
- ID do cliente
- Número da ordem
- Total da ordem
- Saldo da ordem

Na parte inferior de exibição de atendimento da ordem há um Painel de Ação. Ele contém todas as ações que foram executadas em uma linha de ordem. Se uma ação não estiver disponível com base em um status da linha, essa ação ficará indisponível.

Por padrão, as ordens terão o status **Aceitas**. O status da ordem pode ser exibido como uma coluna na lista de linhas de ordem. Se **Aceitação manual** estiver configurada em nível de canal, todas as linhas a serem remetidas serão mostradas como **Pendente** e devem ser aceitas antes de serem atendidas. As ordens para retirada na loja estão **Pendentes** por padrão e não precisam ser aceitas.

### <a name="order-fulfillment-line-actions"></a>Ações na linha de atendimento da ordem

- **Editar** – Se um status de ordem estiver pendente, ele poderá ser editado no ponto de venda. As ordens que já foram parcialmente separadas, embaladas ou faturadas não podem ser editadas na exibição de atendimento da ordem.
- **Aceitar** – Se **Aceitação manual** estiver configurada em nível de canal, as linhas deverão ser aceitas primeiro, antes de serem movidas pelo processo de atendimento da ordem.
- **Separar** – A opção de separação oferece suporte a várias ações. Primeiro, a **Separação** atualiza o status da linha de ordem, de forma que outras pessoas da loja não tentem separar a mesma linha. Em seguida, **Imprimir lista de separação** imprime uma lista de separação da linha ou linhas selecionadas e também atualiza o status para **Separação**. Os formatos de lista de separação são controlados como parte dos formatos de recebimento. Para obter mais informações sobre como configurar formatos de recebimento, consulte [Modelos de recibo e impressão](receipt-templates-printing.md). Por fim, **Marcar como separado** indica que a linha foi separada. **Marcar como separado** inicia transações de estoque correspondentes no back-office. Ações de separação podem ser executadas ao mesmo tempo para várias linhas da ordem por meio de ordens e para todos os modos de entrega.
- **Rejeitar** – As linhas ou linhas parciais podem ser rejeitadas. Isso permite que elas sejam reatribuídas do back-office para outra loja ou depósito. As linhas só podem ser rejeitadas se não forem separadas ou embaladas. Para rejeitar uma linha que já foi separada ou embalada, essa linha deve ter a separação ou embalagem cancelada no back-office.
- **Pacote** – A opção de pacote dá suporte a duas ações: **Imprimir guia de remessa** imprimirá uma guia de remessa para as linhas selecionadas e **Marcar como empacotado** marcará as linhas como empacotadas e marcará as linhas como entregues no back office. Somente as linhas de ordem que pertencem à mesma ordem e têm o mesmo modo de entrega podem ser embaladas simultaneamente. Os formatos de guia de remessa são controlados como parte dos formatos de recebimento. Para obter mais informações sobre como configurar formatos de recebimento, consulte [Modelos de recibo e impressão](receipt-templates-printing.md).
- **Remessa** – A ação de remessa marcará as linhas selecionadas como **Entregue** no back office. Depois que a linha for completamente remetida, ela não aparecerá mais na exibição de atendimento da ordem.
- **Retirada** – A ação de retirada adiciona as linhas à exibição da transação para retirada. Se houver outras linhas na ordem que não estejam sendo retiradas atualmente, elas serão adicionadas à exibição de transações com quantidade zero. Depois que a linha foi completamente retirada, ela não aparecerá mais na exibição de atendimento da ordem.

### <a name="order-fulfillment-filtering"></a>Filtragem de atendimento da ordem

O atendimento da ordem no ponto de venda inclui filtragem para ajudar o usuário a localizar facilmente o que ele precisa. Os filtros podem ser alterados no painel de ações na parte inferior da tela **Ponto de venda**. Por padrão, o filtro **Tipo de entrega** é aplicado, com base em como a operação é configurada. Se a operação for configurada com o parâmetro **Todas as ordens**, esse filtro será aplicado ao acessar o atendimento da ordem. O mesmo se aplica para os parâmetros **Retirada da loja** e **Remessa da loja**. Outros filtros que podem ser aplicados para a exibição de atendimento da ordem incluem:

- Número do cliente
- Nome do Cliente
- Email do cliente
- Número da ordem
- Modo de entrega
- COO
- ID da Referência do Canal
- Número da loja original
- Status da linha
- Data de criação
- Data de entrega
- Data de recebimento


[!INCLUDE[footer-include](../includes/footer-banner.md)]
