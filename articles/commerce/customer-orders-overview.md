---
title: Ordens de cliente no ponto de venda (PDV)
description: Este artigo fornece informações sobre ordens de cliente no ponto de venda (PDV). Ordens de cliente também são conhecidas como ordens especiais O artigo inclui uma discussão sobre parâmetros relacionados e fluxos de transação.
author: josaw1
ms.date: 08/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260594"
- intro-internal
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6051e0a18823b354dd9940aac70a086a0f317002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850373"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Ordens de cliente no ponto de venda (PDV)

[!include [banner](includes/banner.md)]

Este artigo fornece informações sobre como criar e gerenciar ordens de cliente no aplicativo do ponto de venda (PDV). As ordens de cliente podem ser usadas para capturar vendas nas quais os compradores desejam retirar os produtos em uma data posterior, retirar os produtos em um local diferente ou receber os itens. 

Em um mundo de canal omni de comércio, muitos varejistas oferecem a opção de ordens de cliente, ou ordens especiais, para cumprir vários requisitos de produto e atendimento. Estes são alguns dos cenários típicos:

- Um cliente deseja que produtos sejam entregues a um endereço específico em uma determinada data.
- Um cliente deseja retirar produtos de uma loja ou local que é diferente da loja ou local no qual ele comprou esses produtos.
- Um cliente em uma loja deseja encomendar os produtos hoje e retirá-los na mesma loja em uma data posterior.

Os varejistas podem usar ordens de cliente para minimizar perdas de venda que, de outra forma, poderiam ser causadas por faltas de estoque, já que a mercadoria pode ser entregue ou retirada em um horário ou local diferente.

## <a name="set-up-customer-orders"></a>Configurar ordens de cliente
Antes de tentar usar a funcionalidade de ordem de cliente no PDV, conclua todas as configurações necessárias no Commerce headquarters.

### <a name="configure-modes-of-delivery"></a>Configurar modos de entrega

Para usar ordens de cliente, você deve configurar os modos de entrega que o canal de loja pode usar. Você deve definir pelo menos um modo de entrega que possa ser usado quando as linhas de ordem forem remetidas a um cliente de uma loja. Você também deve definir pelo menos um modo de entrega de retirada que possa ser usado quando as linhas de ordem forem retiradas na loja. Os modos de entrega são definidos na página **Modos de entrega** no Commerce headquarters. Para obter mais informações sobre como configurar modos de entrega para canais do Commerce, consulte [Definir modos de entrega](./configure-call-center-delivery.md#define-delivery-modes).

![Página Modos de entrega.](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Configurar grupos de atendimento

Algumas lojas ou locais de depósito podem não conseguir atender a ordens de cliente. Ao configurar grupos de atendimento, uma organização pode especificar quais lojas e locais de depósito são exibidos como opções para os usuários que criam ordens de cliente no PDV. Os grupos de atendimento são configurados na página **Grupos de atendimento**. As organizações podem criar grupos de atendimento de acordo com a necessidade. Após a definição de um grupo de atendimento, vincule-o a uma loja selecionando **Atribuição de grupo de atendimento** na guia **Configurar** no Painel de Ações da página **Lojas**.

A partir da versão 10.0.12 do Commerce, as organizações podem definir se as combinações de depósito ou depósito e loja definidas em grupos de atendimento podem ser usadas para remessa, retirada ou ambas. Isso permite uma maior flexibilidade para a empresa a fim de determinar quais depósitos podem ser selecionados ao criar uma ordem de cliente para itens para remessa versus lojas selecionadas durante a criação de uma ordem de cliente para os itens a serem retirados. Para usar essas opções de configuração, ative o recurso **Capacidade para especificar locais como "Remessa" ou "Retirada" habilitada no Grupo de atendimento**. Se um depósito vinculado a um grupo de atendimento não for uma loja, ele poderá ser configurado somente como um local de remessa. Ele não poderá ser usado quando ordens para retirada forem configuradas no PDV.

![Página Grupos de atendimento.](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Definir configurações de canal

Ao trabalhar com ordens de cliente no PDV, você deve considerar algumas das configurações do canal de loja. Essas configurações são encontradas na página **Lojas** no Commerce headquarters.

- **Depósito** – este campo indica o depósito que será usado ao decrementar o estoque para ordens de retirada de caixa e de cliente ligadas a este armazenamento. Como prática recomendada, incentivamos o uso de depósitos exclusivos para cada canal de armazenamento, a fim de evitar problemas da lógica comercial conflitantes em todos os armazenamentos.
- **Depósito de Remessa** – este campo indica o depósito que será usado ao decrementar o estoque para ordens de cliente a serem remetidas do armazenamento selecionado. Se o recurso **Capacidade para especificar locais como "Remessa" ou "Retirada" no Grupo de atendimento** foi habilitado no seu ambiente, os usuários de PDV podem escolher um depósito específico a ser remetido no PDV, em vez de escolher um armazenamento de remessa. Portanto, quando esse recurso está habilitado, o depósito de remessa não é usado, pois o usuário selecionará o depósito específico para remeter a ordem quando a ordem for criada.
- **Atribuição de grupos de atendimento** – Selecione este botão (na guia **Configurar** no Painel de Ações) para vincular os grupos de atendimento referenciados para mostrar opções de locais de retirada ou origens de remessa quando as ordens de cliente forem criadas no PDV.
- **Usar imposto baseado no destino** – Esta opção indica se o endereço de remessa é usado para determinar o grupo de impostos que é aplicado às linhas de ordem remetidas ao endereço do cliente.
- **Usar imposto baseado no cliente** – Esta opção indica se o grupo de impostos definido para o endereço de entrega do cliente é usado para taxar ordens de cliente criadas no PDV para remessa à casa do cliente.

![Configuração de canal de loja na página Lojas.](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Configurar parâmetros de ordens de cliente

Antes de tentar criar ordens de cliente no PDV, você deve configurar os parâmetros adequados no Commerce headquarters. Esses parâmetros podem ser encontrados na guia **Ordens de cliente** da página **Parâmetros do Commerce**.

- **Tipo de ordem padrão** – Você pode especificar o tipo de ordem atribuído por padrão a ordens de cliente criadas no PDV. Essas ordens de cliente podem ser ordens de venda ou ordens de cotação. Independentemente do tipo de ordem padrão, os usuários ainda podem criar ordens de venda e ordens de cliente no PDV.
- **Percentual de depósito padrão** – Especifique o percentual do valor total da ordem que o cliente deve pagar como depósito antes que ela possa ser confirmada. Dependendo de seus privilégios, os associados da loja poderão substituir o valor usando a operação **Substituição de depósito** no PDV, se essa operação estiver configurada para o layout da tela de transação.
- **Modo de entrega Retirada** – Especifique o modo de entrega que deve ser aplicado às linhas da ordem de venda configuradas para retirada no PDV.
- **Modo de entrega Execução** – Especifique o modo de entrega que deve ser aplicado às linhas da ordem de venda que são consideradas linhas da ordem de execução quando um carrinho misto for criado, no qual algumas linhas serão retiradas ou remetidas e outras serão executadas imediatamente pelo cliente.
- **Percentual de encargo de cancelamento** – Se um encargo tiver que ser aplicado quando uma ordem de cliente for cancelada, especifique o valor desse encargo.
- **Código do encargo de cancelamento** – Especifique o código do encargo de Contas a receber que deve ser usado quando um encargo de cancelamento for aplicado a ordens de cliente canceladas por meio do PDV. O código do encargo define a lógica de lançamento financeiro para o encargo de cancelamento.
- **Código do encargo de remessa** – Se a opção **Usar encargos automáticos avançados** estiver definida como **Sim**, essa configuração de parâmetro não terá efeito. Se essa opção estiver definida como **Não**, os usuários serão solicitados a inserir manualmente um encargo de remessa quando criarem ordens de cliente no PDV. Use esse parâmetro para mapear um código de encargo de Contas a receber que será aplicado às ordens quando os usuários inserirem um encargo de remessa. O código do encargo define a lógica de lançamento financeiro para o encargo de remessa.
- **Usar encargos automáticos avançados** – Defina esta opção como **Sim** para usar encargos automáticos calculados pelo sistema quando ordens de cliente forem criadas no PDV. Esses encargos automáticos podem ser usados para calcular taxas de remessa e outros encargos específicos de ordens ou itens. Para obter mais informações sobre como configurar e usar encargos automáticos avançados, consulte [Encargos automáticos avançados de omnicanal](./omni-auto-charges.md).

![Guia Ordens de cliente na página Parâmetros do Commerce.](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Atualizar layouts da tela de transação no PDV

Verifique se o [layout de tela](./pos-screen-layouts.md) do PDV está configurado para oferecer suporte à criação e ao gerenciamento de ordens de cliente e se todas as operações de PDV necessárias estão configuradas. Veja a seguir algumas das operações de PDV recomendadas para oferecer suporte de forma correta à criação e ao gerenciamento de ordens de cliente:
- **Remeter todos os produtos** – Esta operação é usada para especificar que todas as linhas no carrinho de transação serão remetidas a um destino.
- **Remeter produtos selecionados** – Esta operação é usada para especificar que as linhas selecionadas no carrinho de transação serão remetidas a um destino.
- **Retirar todos os produtos** – Esta operação é usada para especificar que todas as linhas no carrinho de transação serão retiradas em uma loja selecionada.
- **Retirar produtos selecionados** – Esta operação é usada para especificar que as linhas selecionadas no carrinho de transação serão retiradas em uma loja selecionada.
- **Executar todos os produtos** – Esta operação é usada para especificar que todas as linhas no carrinho de transação serão executadas. Se esta operação for usada no PDV, a ordem de cliente será convertida em uma transação cash-and-carry.
- **Executar produtos selecionados** – Esta operação é usada para especificar que as linhas selecionadas no carrinho de transação estão sendo executadas pelo cliente no momento da compra. Essa operação é útil somente em um cenário de [ordem híbrida](./hybrid-customer-orders.md).
- **Cancelar ordem** – Esta operação é usada para procurar e recuperar ordens de cliente de modo que os usuários do PDV possam editar, cancelar ou executar operações relacionadas ao atendimento nessas ordens, conforme necessário.
- **Alterar modo de entrega** – Esta operação pode ser usada para alterar rapidamente o modo de entrega das linhas que já foram configuradas para remessa, sem exigir que os usuários passem pelo fluxo "remeter todos os produtos" ou "remeter produtos selecionados" outra vez.
- **Substituição de depósito** – Esta operação pode ser usada para alterar o valor de depósito que o cliente pagará pela ordem de cliente selecionada.

![Operações na tela de transação do PDV.](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Trabalhar com ordens de cliente no PDV

> [!NOTE]
> A funcionalidade de reconhecimento de receita no momento não tem suporte para uso em canais do Commerce (comércio eletrônico, PDV, call center). Os itens configurados com o reconhecimento de receita não devem ser adicionados a ordens criadas em canais do Commerce. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Criar uma ordem de cliente para produtos que serão remetidos ao cliente

1. Na tela de transação do PDV, adicione um cliente à transação.
2. Adicione produtos ao carrinho.
3. Selecione **Remeter selecionado** ou **Remeter tudo** para remeter os produtos a um endereço na conta do cliente.
4. Selecione a opção para criar uma ordem de cliente.
5. Confirme ou altere o local "remeter de", confirme ou altere o endereço de remessa e selecione um método de remessa.
6. Insira a data desejada de remessa da ordem do cliente.
7. Use as funções de pagamento para pagar por valores calculados devidos ou use a operação **Substituição de depósito** para alterar os valores devidos e, em seguida, aplicar o pagamento.
8. Se o total da ordem não foi pago, insira um cartão de crédito que será capturado para o saldo devido na ordem quando ela for faturada.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Criar uma ordem de cliente para produtos que o cliente retirará

1. Na tela de transação do PDV, adicione um cliente à transação.
2. Adicione produtos ao carrinho.
3. Selecione **Retirar selecionado** ou **Retirar tudo** para iniciar a configuração de retirada de ordens.
4. Selecione a loja em que o cliente retirará os produtos selecionados.
5. Selecione uma data em que o item será retirado.
6. Use as funções de pagamento para pagar por valores calculados devidos ou use a operação **Substituição de depósito** para alterar os valores devidos e, em seguida, aplicar o pagamento.
7. Se o total da ordem não foi pago, selecione se o cliente realizará o pagamento posteriormente (na retirada) ou se um cartão de crédito será indexado agora e, em seguida, usado e capturado no momento da retirada.

### <a name="edit-an-existing-customer-order"></a>Editar uma ordem de cliente existente

As ordens de varejo criadas no canal de loja ou online podem ser canceladas e editadas por meio do PDV, conforme necessário.

> [!IMPORTANT]
> Nem todas as ordens de varejo podem ser editadas por meio do aplicativo de PDV. As ordens criadas em um canal de call center não poderão ser editadas por meio do PDV se a configuração [Habilitar conclusão de ordem](./set-up-order-processing-options.md#enable-order-completion) estiver ativada para o canal de call center. Para garantir o processamento correto dos pagamentos, as ordens originadas em um canal de call center e que usam a funcionalidade Habilitar conclusão de ordem devem ser editadas por meio do aplicativo de call center no Commerce headquarters.

> [!NOTE]
> Recomendamos que você não edite ordens e cotações no PDV que sejam criadas por um usuário que não seja do call center no Commerce headquarters. Essas ordens e cotações não usam o mecanismo de preço do Commerce. Portanto, se forem editadas no PDV, o mecanismo de preço do Commerce alterará o preço delas.


Na versão 10.0.17 e posterior, os usuários podem editar ordens qualificadas por meio do aplicativo de PDV, mesmo que a ordem seja parcialmente preenchida. No entanto, as ordens faturadas integralmente ainda não podem ser editadas por meio do PDV. Para habilitar esse recurso, ative o recurso **Editar ordens parcialmente atendidas no Ponto de Venda** no espaço de trabalho **Gerenciamento de recursos**. Se esse recurso não estiver habilitado, ou se você estiver usando a versão 10.0.16 ou anterior, os usuários só poderão editar ordens de cliente em PDV se a ordem estiver totalmente aberta. Se o recurso estiver habilitado, você poderá limitar as lojas que podem editar ordens preenchidas parcialmente. A opção para desativar esse recurso para lojas específicas pode ser configurada por meio do **Perfil de funcionalidade** na FastTab **Geral**.


1. Selecione **Cancelar ordem**.
2. Use **Pesquisar** para inserir filtros para encontrar a ordem e, em seguida, selecione **Aplicar**.
3. Selecione a ordem na lista de resultados e, em seguida, selecione **Editar**. Se o botão **Editar** estiver indisponível, a ordem está em um estado no qual não pode ser editada.
4. No carrinho de transação, faça as alterações necessárias na ordem de cliente. Algumas alterações podem ser proibidas durante a edição.
5. Conclua o processo de edição selecionando uma operação de pagamento.
6. Para sair do processo de edição sem salvar as alterações, você pode usar a operação **Anular transação**.

#### <a name="pricing-impact-when-orders-are-edited"></a>Impacto do preço quando as ordens são editadas

Quando as ordens são colocadas no PDV ou em um site de comércio eletrônico do Commerce, os clientes se comprometem com um valor. Esse valor inclui um preço e também pode incluir um desconto. Um cliente que coloca uma ordem e posteriormente contata o call center para alterar essa ordem (por exemplo, para adicionar outro item), terá expectativas específicas sobre a aplicação de descontos. Mesmo que as promoções das linhas de ordem existentes tenham expirado, o cliente esperará que os descontos que foram originalmente aplicados a essas linhas permanecerão em vigor. No entanto, se nenhum desconto estivesse em vigor quando a ordem foi originalmente colocada, mas um desconto entrou em vigor posteriormente, o cliente esperará que o novo desconto seja aplicado à ordem alterada. Caso contrário, o cliente poderá apenas cancelar a ordem existente e criar uma nova ordem na qual o novo desconto seja aplicado. Como mostra este cenário, os preços e os descontos com os quais os clientes se comprometeram precisam ser preservados. Ao mesmo tempo, os usuários do PDV e do call center precisam ter a flexibilidade de recalcular os preços e os descontos para as linhas da ordem de venda, conforme necessário.

Quando as ordens são canceladas e editadas no PDV, os preços e os descontos das linhas de ordem existentes são considerados "bloqueados". Em outras palavras, elas não são alterados, mesmo que algumas linhas da ordem sejam canceladas ou alteradas, ou novas linhas da ordem sejam adicionadas. Para alterar os preços e os descontos das linhas de venda existentes, o usuário do PDV precisa selecionar **Recalcular**. O bloqueio de preço é então removido das linhas de ordem existentes. No entanto, antes da versão 10.0.21 do Commerce, esse recurso não estava disponível no call center. Em vez disso, as alterações nas linhas da ordem acarretavam o recálculo dos preços e dos descontos.

Na versão 10.0.21 do Commerce, um novo recurso chamado **Impedir o cálculo de preço não intencional para ordens comerciais** está disponível no espaço de trabalho **Gerenciamento de recursos**. Esse recurso está ativado por padrão. Quando ele é ativado, uma nova propriedade **Preço bloqueado** é disponibilizada para todas as ordens de comércio eletrônico. Depois da conclusão da captura de todas as ordens colocadas em qualquer canal, esta propriedade é automaticamente habilitada (ou seja, a caixa de seleção é marcada) para todas as linhas da ordem. O mecanismo de preço do Commerce então exclui essas linhas de ordem de todos os cálculos de preço e de desconto. Portanto, se a ordem for editada, as linhas da ordem serão excluídas do cálculo de preço e de descontos por padrão. No entanto, os usuários do call center podem desabilitar a propriedade (ou seja, desmarcar a caixa de seleção) para qualquer linha da ordem e, em seguida, selecionar **Recalcular** para incluir as linhas de ordem existentes nos cálculos de preço.

Mesmo quando estiverem aplicando um desconto manual a uma linha de venda existente, os usuários do call center precisam desabilitar a propriedade **Preço bloqueado** da linha de venda para que possam aplicar o desconto manual.

Os usuários do call center também podem desabilitar a propriedade **Preço bloqueado** para linhas de ordem em massa selecionando **Remover bloqueio de preço** no grupo **Calcular** na guia **Vender** do painel de ação da página **Ordem de venda**. Nesse caso, o bloqueio de preço é removido de todas as linhas de ordem, exceto daquelas que não podem ser editadas (em outras palavras, as linhas que têm um status de **Parcialmente faturado** ou **Faturado**). Depois de concluir e enviar as alterações à ordem, o bloqueio de preço é reaplicado a todas as linhas da ordem.

> [!IMPORTANT]
> Quando o recurso **Evitar cálculo de preço não intencional para ordens do Commerce** estiver ativado, a configuração da avaliação do contrato comercial será ignorada nos fluxos de trabalho de definição de preço. Em outras palavras, as caixas de diálogo de avaliação do contrato comercial não mostrarão a seção **Preço relacionado**. Esse comportamento ocorre porque a configuração da avaliação do contrato comercial e o recurso de bloqueio de preço têm uma finalidade semelhante: evitar alterações de preço não intencionais. No entanto, a experiência do usuário para a avaliação do contrato comercial não dimensiona bem para ordens grandes nas quais os usuários devem selecionar uma ou mais linhas da ordem para redefinir o preço.

> [!NOTE]
> A propriedade **Preço bloqueado** pode ser desabilitada para uma ou mais linhas selecionadas somente quando o módulo **Call center** é usado. O comportamento do PDV permanece inalterado. Em outras palavras, o usuário do PDV não pode desbloquear os preços das linhas de ordem selecionadas. No entanto, eles podem selecionar **Recalcular** para remover o bloqueio de preço de todas as linhas de ordem existentes.

### <a name="cancel-a-customer-order"></a>Cancelar uma ordem de cliente

1. Selecione **Cancelar ordem**.
2. Use **Pesquisar** para inserir filtros para encontrar a ordem e, em seguida, selecione **Aplicar**.
3. Selecione a ordem na lista de resultados e, em seguida, selecione **Cancelar**. Se o botão **Cancelar** estiver indisponível, a ordem está em um estado no qual não pode mais ser cancelada.
4. Se os encargos de cancelamento estiverem configurados, confirme-os. Você pode ajustar os encargos de cancelamento antes de confirmá-los, conforme necessário. 
5. No carrinho de transação, conclua o processo de cancelamento selecionando uma operação de pagamento. Se os depósitos que foram pagos excederem o encargo de cancelamento, pagamentos de reembolso podem ser devidos.
6. Para sair do processo de cancelamento sem salvar as alterações, você pode usar a operação **Anular transação**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Finalizar a remessa ou retirada da ordem de cliente no PDV

Após a criação de uma ordem, os itens serão retirados pelo cliente em uma loja ou remetidos, dependendo da configuração dessa ordem. Para obter mais informações sobre esse processo, consulte a documentação de [atendimento da ordem na loja](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Fluxo de transações assíncronas para ordens de cliente

As ordens de cliente podem ser criadas no PDV em modo síncrono ou assíncrono. Se você perceber problemas de desempenho ou atrasos de usuário ao criar ordens de cliente no PDV, considere ativar a criação assíncrona de ordens.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilitar ordens de cliente para serem criadas em modo assíncrono

1. No Commerce headquarters, na página **Perfis de funcionalidade**, selecione o perfil de funcionalidade que corresponde à loja que você deseja configurar.
2. Na Guia Rápida **Geral**, defina a opção **Criar ordem do cliente no modo assíncrono** como **Sim**.

Quando a opção **Criar ordem do cliente no modo assíncrono** é definida como **Sim**, as ordens de cliente sempre são criadas no modo assíncrono, mesmo se o Retail Transaction Service (RTS) está disponível. Se você definir essa opção como **Não**, as ordens de cliente sempre serão criadas em modo síncrono por meio de RTS. Quando as ordens de cliente são criadas no modo assíncrono, elas são retiradas e criadas como transações de varejo no Commerce headquarters com base nos trabalhos de pull (P) do Commerce. As ordens de venda correspondentes para as transações de varejo são criadas quando **Sincronizar ordens** é executado manualmente ou por meio de um processo em lote.

## <a name="additional-resources"></a>Recursos adicionais

[Ordens híbridas de cliente](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
