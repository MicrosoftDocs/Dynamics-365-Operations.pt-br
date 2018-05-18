---
title: "Visão geral de atendimento da ordem na loja"
description: "Este tópico fornece uma visão geral do atendimento da ordem da loja."
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 1ac73b50c6051ba7d3b96ae49cb7e33cf436ba9e
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---

# <a name="store-order-fulfillment"></a>Atendimento da ordem na loja

[!include [banner](includes/banner.md)]

Vários varejistas querem otimizar o atendimento da ordem permitindo que as lojas atendam as ordens. O atendimento da ordem em nível de loja pode ajudar a amenizar os cenários de estoque excessivo de uma loja específica ou pode ser necessário de um ponto de vista logístico, nos casos em que uma loja tem capacidade extra ou está em um local mais próximo do cliente. Para tratar esta necessidade, uma operação de atendimento unificado da ordem está disponível no ponto de venda.

O atendimento das ordens em uma loja específica tem o depósito da loja designado no cabeçalho ou nas linhas da ordem. 

A operação de atendimento da ordem no ponto de venda fornece uma área de trabalho única no ponto de venda que pode ser usada para processar as ordens. Isso inclui tudo, desde aceitar a ordem, marcá-la como remetida ou iniciar a retirada da loja. 

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Acessar atendimento unificado da ordem no ponto de venda

O atendimento da ordem, [ID 928 da Operação](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), pode ser usado para acessar a área de trabalho de atendimento da ordem da loja no ponto de venda. 

A operação de atendimento da ordem não tem sua própria permissão imediata, mas no futuro, os usuários poderão usar a permissão **Permitir recuperar ordem** para chamar a operação do ponto de venda.

Em nível de loja, a definição da configuração fica disponível para determinar se uma linha de ordem deve ser aceita manualmente de dentro do ponto de venda. Se esta opção de configuração não for definida, as linhas da ordem serão aceitas, por padrão. Se essa opção de configuração estiver ativada, os usuários no ponto de venda precisarão selecionar a permissão **Permitir ordem de aceitação** para aceitar ordens de dentro do ponto de venda.
As linhas de ordem também podem ser rejeitadas no ponto de venda. Rejeitar uma linha de ordem significa que ela não será atendida nessa loja e envia a linha de ordem de volta para reatribuição em outra loja ou depósito. A permissão de rejeição da linha de ordem é concedida através da permissão **Permitir rejeição da ordem**. 

## <a name="order-fulfillment-operation-parameters"></a>Parâmetros de operação de atendimento da ordem

O atendimento da ordem fornece parâmetros prontos que podem ser aplicados à operação quando ela é chamada no ponto de venda. Quando o parâmetro **Todas as ordens** for configurado, todas as ordens serão mostradas quando a operação for usada. O parâmetro **Ordens a serem remetidas** mostra somente ordens que devem ser remetidas da loja e **Ordens para retirada** mostra as ordens que serão retiradas na loja. 

## <a name="orders-for-fulfillment"></a>Ordens para atendimento

A operação de atendimento da ordem mostra somente as ordens que serão retiradas ou enviadas pela loja atual. As ordens para atendimento em outras lojas não são listadas ao usar a operação de atendimento da ordem. 

## <a name="line-selection"></a>Seleção de linha

As linhas podem ser selecionadas usando a função **Selecionar** no painel de ações. Quando a opção **Selecionar** estiver habilitada, várias linhas poderão ser selecionadas para processamento. Você pode desmarcar as linhas selecionadas clicando na mesma linha novamente. 

## <a name="line-details"></a>Detalhes da linha

Os detalhes da linha podem ser exibidos usando o menu suspenso de detalhes da linha. Quando esse menu é usado, três guias são fornecidas para mostrar informações adicionais da linha selecionada. A primeira guia, **Detalhes da linha** mostra detalhes da própria linha, como quantidade encomendada e restante. Detalhes adicionais são fornecidos incluindo a quantidade separada, embalada e faturada e também o modo de entrega e o endereço de entrega. A guia **Detalhes da ordem** fornece informações sobre cabeçalho da ordem, incluindo cliente, ID de cliente, número da ordem, total da ordem e saldo. A guia **Estoque** mostra informações da linha selecionada em relação a estoque físico disponível, estoque reservado e o estoque encomendado.

Se várias linhas forem selecionadas, o menu suspenso de detalhes da linha da ordem somente indicará que várias linhas foram selecionadas. Para exibir detalhes de uma única linha, desmarque-as até que apenas uma linha permaneça. 

## <a name="pending-order-lines"></a>Linhas de ordem pendentes

O atendimento unificado da ordem inclui a capacidade de aceitar as ordens manualmente. Por padrão, as ordens para atendimento na loja já foram aceitas. Porém, se os processos comerciais indicam que o trabalhador em nível de loja deve aceitar as ordens, a aceitação manual pode ser ativada em nível de loja de varejo. Para habilitar a aceitação da ordem, vá para **Varejo** > **Canais** > **Lojas de varejo** > **Todas as lojas de varejo**. Abra a loja desejada e na guia **Geral**, localize o subcabeçalho **Atendimento da ordem**. Este subcabeçalho tem uma opção **Aceitação manual** definida como **Não**, por padrão. Definindo esta opção como **Sim** e sincronizando as alterações para o banco de dados do canal, as linhas de ordem podem passar pelo processo de aceitação.

Os trabalhadores com a permissão **Permitir ordem de aceitação** podem abrir o atendimento da ordem e selecionar linhas para aceitação. Depois que as linhas forem aceitas, as alterações de status de **Pendente** para **Aceitas** e o restante do processo de atendimento de ordem podem continuar. Quando a **Aceitação manual** for ativada, as ordens não serão processadas enquanto não forem aceitas. 

As ordens para retirada na loja nunca têm o estado **Pendente**. Isso é feito para evitar um cenário no qual um cliente chega na loja e a linha da ordem não pode ser processada porque um trabalhador com o privilégio adequado não está disponível.

## <a name="accepted-order-lines"></a>Linhas de ordem aceitas

Ordens com o estado da linha **Aceita** podem continuar com o restante do processo de atendimento da ordem no ponto de venda. Depois que uma ordem for aceita, qualquer ação restante pode ser tomada em relação à linha da ordem. 

Por exemplo, uma linha de ordem aceita pode ser selecionada e depois retirada diretamente sem passar por separação e embalagem.

## <a name="line-actions"></a>Ações da linha

### <a name="pick"></a>Separar

A categoria de ações **Separar** é fornecida para ajudar no processo de separação de linhas de ordem nas prateleiras. A ação de separação só pode ser executada nas linhas de ordem que foram aceitas anteriormente. 

**Ação: Separação**

- Status resultante de PDV: Separação
- Status resultante do back-office: sem alterações

Depois que uma ordem for aceita, as linhas podem ser selecionadas e marcadas como **Separação**. Marcar uma linha como **Separação** é uma forma de indicar que o trabalho de separação já está sendo executado em uma linha. Isso evita que dois trabalhadores tentem separar as mesmas linhas de ordem ao mesmo tempo.  

**Ação: Imprimir lista de separação**

- Status resultante: Separação
- Status resultante do back-office: sem alterações

As listas de separação podem ser impressas no ponto de venda para auxiliar os trabalhadores a executarem o processo de separação. Uma lista de separação impressa pode ser executada com o trabalhador executando a separação, e conforme os produtos são separados, o trabalhador pode marcá-los manualmente como separados na lista de separação. 

O formato da lista de separação é configurado no Dynamics 365 for Retail e adicionado ao perfil de recebimento. Para obter mais informações sobre a configuração dos perfis de recebimento, consulte [Modelos de recibo e impressão](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

Se as linhas forem selecionadas e uma lista de separação for impressa para essas linhas, elas serão atualizadas automaticamente com o status **Separação**. 

**Ação: Marcar como separado**

- Status resultante: Separado ou parcialmente separado
- Status resultante de back-office: Separado ou parcialmente separado

Após o processo de separação físico ser executado, as linhas podem ser marcadas como **Separadas**. Selecionar uma linha e marcá-la como **Separada** executa uma chamada em tempo real para atualizar a linha de ordem no Dynamics 365 for Retail. Depois que a linha for marcada como **Separada** no ponto de venda, o status no back-office também será atualizado para **Separada** e as transações de estoque refletirão se a quantidade especificada foi reduzida.

Quando as ordens são processadas ao longo do tempo, as quantidades parciais podem ser processadas para uma linha específica. Se uma linha for selecionada e a ação **Marcar como separado** for executada, e a quantidade for maior que um, será solicitada a quantidade ao usuário. A quantidade restante a ser separada é preenchida automaticamente. Se for especificada menos que a quantidade restante, o status da linha se tornará **Parcialmente separada**. Quando a linha de ordem for atualizada no back-office, ela também refletirá o status separado parcialmente e a quantidade inserida pelo usuário será usada para atualização de estoque. 

Se uma linha de ordem for separada por engano, o processo para desfazer a separação deve ser executado na linha da ordem no back-office. Atualmente não há nenhuma ação para desfazer separação com suporte no ponto de venda. 

As linhas de ordens diferentes podem ser selecionadas e marcadas como **Separação**, impressas na mesma a lista de separação ou marcadas como **Separadas**. 

### <a name="pack"></a>Pacote

As linhas de ordem podem ser embaladas em qualquer ponto depois que a linha da ordem for aceita. 

**Ação: Imprimir guia de remessa**

- Status resultante: Embalada ou parcialmente embalada
- Status resultante de back-office: Entregue ou parcialmente entregue

Esta ação marca as linhas como embalada ou parcialmente embaladas e imprime uma guia de remessa. Uma guia de remessa poderá ser impressa para validar os produtos que são embalados juntos. O formato de guia de remessa é configurado no Dynamics 365 for Retail e adicionado ao perfil de recebimento. Para obter mais informações sobre a configuração dos perfis de recebimento, consulte [Modelos de recibo e impressão](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing).

**Ação: Marcar como embalada**

- Status resultante: Embalada ou parcialmente embalada
- Status resultante de back-office: Entregue ou parcialmente entregue

A ação **Marcar como embalada** pode ser usada para indicar que as linhas são embaladas sem imprimir uma guia de remessa. Tanto **Imprimir guia de remessa** como **Marcar como embaladas** resultam em transações de estoque no back-office. As linhas de separação no ponto de venda resultarão em diários de guias de remessa produzidos no back-office. 

Se uma linha da ordem for embalada por engano, o diário da guia de remessa deverá ser corrigido no back-office. 

Somente as linhas da mesma ordem e com o mesmo modo de entrega podem ser embaladas ao mesmo tempo.

Atualmente a opção para marcar as linhas de retirada na loja como **Embalada** está desabilitada. Este recurso será adicionado em uma versão futura. O processo de criação da guia de remessa será aperfeiçoado para oferecer suporte à inserção de informações de entrega e terceiros no processo de guia de remessa.

### <a name="pick-up"></a>Separar

Ordens para a retirada na loja podem ser retiradas diretamente, depois que forem recuperadas no ponto de venda. As ordens para retirada na loja não estão sujeitas à aceitação. 

**Ação: Retirada**

- Status resultante: Faturada ou faturada parcialmente
- Status resultante do back-office: Faturada ou faturada parcialmente

Se uma linha for selecionada para retirada do atendimento unificado da ordem, toda a ordem será carregada no ponto de venda e a quantidade total da linha selecionada será marcada. Outras linhas da ordem também são carregadas na exibição da transação do ponto de venda, mas com a quantidade marcada como zero. 

Depois que as linhas para retirada forem carregadas na exibição de transações, a transação poderá ser oferecida como de costume. 

As linhas que foram totalmente faturadas por meio da retirada não serão mais exibidas no processamento unificado da ordem. As linhas que foram retiradas parcialmente continuarão sendo exibidas no atendimento unificado da ordem até serem retiradas por completo. 

Se uma linha for retirada por engano, uma devolução deve ser executada para corrigir o erro.  

Somente as linhas da mesma ordem e com o mesmo modo de entrega podem ser retiradas ao mesmo tempo. 

### <a name="shipping"></a>Remessa

As linhas de ordem a serem enviadas da loja podem ser processadas através do atendimento unificado da ordem usando a ação **Remeter**. Se a aceitação da linha de ordem manual for configurada em nível de canal, as ordem devem ser aceitas antes da remessa. Depois que uma linha da ordem foi aceita e tiver um status **Pendente** ou outro, as linhas poderão ser enviadas. 

**Ação: Remessa**

- Status resultante: Faturada ou faturada parcialmente
- Status resultante do back-office: Faturada ou faturada parcialmente

As linhas enviadas de atendimento unificado da ordem são faturadas do back-office, como se a ordem fosse faturada diretamente do back-office. As linhas que estão sendo enviadas do atendimento unificado da ordem não são carregadas para a exibição da transação e não há pagamento executado no momento em que as linhas são enviadas. 

As linhas de ordem que foram completamente enviadas não aparecem mais no atendimento unificado da ordem. As linhas enviadas parcialmente continuarão aparecendo no atendimento unificado da ordem até serem completamente enviadas. 

Somente linhas da mesma ordem podem ser enviadas ao mesmo tempo. Se as linhas da mesma ordem tiverem modos de entrega diferentes, elas ainda poderão ser selecionadas da remessa ao mesmo tempo. 

### <a name="reject"></a>Rejeitar

As linhas ou linhas parciais podem ser rejeitadas. Isso permite que elas sejam reatribuídas do back-office para outra loja ou depósito. As linhas só podem ser rejeitadas se não forem separadas ou embaladas. Para rejeitar uma linha que já foi separada ou embalada, essa linha deve ter a separação ou embalagem cancelada no back-office. 

**Ação: Rejeitar**

- Status resultante: Rejeitado
- Status resultante do back-office: sem alterações 

As linhas de ordem rejeitadas podem ser exibidas no espaço de trabalho **Consulta e processamento de ordem de venda**. Desmarque o filtro da pessoa no espaço de trabalho para exibir todas as linhas de ordens rejeitadas pelas lojas. A guia **Linhas de ordem rejeitadas** na seção **Ordens e favoritos** exibe os detalhes da linha de ordem. Além disso, os usuários podem clicar no botão **Linhas de ordem rejeitadas** na seção **Resumo** para navegar para uma exibição de ordem de venda. Serão mostradas todas as ordens que têm uma ou mais linhas de ordem rejeitadas. Se o Gerenciamento de Ordem Distribuída (DOM) for ativado, então essas ordens rejeitadas serão reatribuídas automaticamente para as lojas apropriadas para atendimento, porém essas linhas de ordem também podem ser reatribuídas manualmente. Para fazer isso, selecione a linha que mostra o **Status de atendimento** como **Rejeitado** e altere o local/depósito, quando necessário. Clique no menu suspenso **Atualizar linha** e em **Redefinir status de atendimento** para alterar o status de atendimento de **Rejeitada** para **Aceita** ou **Pendente**, dependendo da configuração de atendimento da ordem. Depois que o status de atendimento for redefinido, então os trabalhadores da loja poderão exibir as linhas da ordem no PDV.

## <a name="line-quantity-tracking"></a>Rastreamento de quantidade de linhas

Uma linha de ordem única de quantidade maior que um pode ser processada ao longo do tempo resultando em vários subestados de linhas da ordem. Por exemplo, se um construtor tiver um projeto que exige 500 placas, mas ele somente irá retirar ou ter algumas placas entregues uma vez ao longo do projeto, é provável que as quantidades estejam sendo retiradas, embaladas e entregues ao mesmo tempo. 

Sempre que uma linha for selecionada, o valor restante da linha será preenchido automaticamente para simular que a quantidade restante está sendo processada. Usando o exemplo acima, se 200 placas já foram separadas e a linha das placas for selecionada para separação, a quantidade restante de 300 será preenchida automaticamente na quantidade. O mesmo ocorre se 200 placas já foram faturadas. Nesse caso, somente a quantidade restante será preenchida automaticamente. 

Continuando com o exemplo anterior, se 200 placas foram marcadas como embaladas e a remessa for selecionada, a quantia total de 500 será preenchida automaticamente. Se apenas 200 placas forem enviadas, o sistema presumirá que as placas embaladas anteriormente estão sendo enviadas e a quantidade embalada será reduzida. Se 201 placas forem enviadas, as placas embaladas primeiro serão reduzidas e a placa única restante será reduzida da quantidade restante. 

## <a name="line-statuses"></a>Status da linha

As linhas de ordem no ponto de venda têm vários status para mostrar o status da linha de ordem. O status no ponto de venda e no back-office não são correspondentes em todos os casos. O status da linha de ordem pode ser visto através do ponto de venda usando as operações de atendimento da ordem. No back-office, as linhas de ordem podem ser visualizadas nos detalhes da ordem. Os detalhes da ordem podem ser acessados em **Varejo** > **Clientes** > **Todas as ordens do cliente**. Selecione o **ID da ordem** para exibir detalhes da ordem. Nos detalhes da ordem, selecione a guia **Ordem de venda**, depois **Status detalhado** no subcabeçalho **Exibir**. 

**Pendente** - As linhas de ordem que foram atribuídas a uma loja, mas não foram aceitas têm o status **Pendente** quando exibidas no ponto de venda. A aceitação de linhas pendentes no ponto de venda terão o status **Processamento de ordens** no back-office.

**Aceitas** - As linhas de ordem que foram aceitas manualmente ou automaticamente terão o status **Aceitas** quando exibidas no ponto de venda. As linhas com o status **Aceitas** serão mostradas como **Processamento da ordem** no back-office.

**Separação** - As linhas que estão sendo separadas em nível de loja têm o status **Separação**. Essas mesmas linhas, quando vistas no back-office, serão exibidas como **Processamento da ordem**.

**Separadas** e **Parcialmente separadas** - as linhas que foram separadas ou parcialmente separadas no ponto de venda terão o status **Separadas** ou **Parcialmente separadas**. As mesmas linhas no back-office também serão exibidas como **Separadas** ou **Parcialmente separadas**.

**Embaladas** e **Parcialmente embaladas** - As linhas que foram embaladas ou parcialmente embaladas no ponto de venda terão o status **Embaladas** ou **Parcialmente embaladas**. As mesmas linhas no back-office também serão exibidas como **Entregues** ou **Parcialmente entregues**.

**Parcialmente faturadas** - As linhas que foram parcialmente retiradas ou parcialmente entregues terão o status **Parcialmente faturadas** no ponto de venda e no back-office.

**Faturadas** - As linhas que foram totalmente faturadas no ponto de venda não serão mais exibidas para atendimento. No back-office o status dessas linhas será **Faturado**.

## <a name="order-fulfillment-filtering"></a>Filtragem de atendimento da ordem

O atendimento da ordem no ponto de venda inclui filtragem para ajudar o usuário a localizar facilmente o que ele precisa. Os filtros podem ser alterados no painel de ações na parte inferior da tela de **Ponto de venda**. Por padrão, o filtro **Tipo de entrega** é aplicado, com base em como a operação é configurada. Se a operação for configurada com o parâmetro **Todas as ordens**, então esse filtro será aplicado ao acessar o atendimento da ordem. O mesmo se aplica para os parâmetros **Retirada da loja** e **Remessa da loja**. Outros filtros que podem ser aplicados para a exibição de atendimento da ordem incluem:

  - Número do cliente
  - Nome do Cliente
  - Email do cliente
  - Número da ordem
  - Modo de entrega
  - COO
  - ID da referência do canal
  - Número da loja original
  - Status da linha
  - Data de criação
  - Data de entrega
  - Data de recebimento

