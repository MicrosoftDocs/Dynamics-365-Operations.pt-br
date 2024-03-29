---
title: Configurar canais de call center
description: Este artigo oferece informações sobre como processar ordens de call centers usando o Dynamics 365 Commerce.
author: josaw1
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c6d21385d956534c799af5b9e20a54c9970da368
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854862"
---
# <a name="set-up-call-center-channels"></a>Configurar canais de call center

[!include [banner](includes/banner.md)]

Uma empresa pode definir vários canais call center no Dynamics 365 Commerce. Os canais de call center são configurados em **Retail e Commerce** \> **Canais** \> **Call center** \> **Todos os call centers** e são específicos de uma entidade legal.

Quando um novo canal de call center é criado, recebe sistematicamente um número de unidade operacional. Como os call centers são criados como unidades operacionais, os usuários podem vincular o canal de call center a vários recursos do Commerce, como classificações, catálogos e modos de entrega específicos.

Um depósito padrão pode ser configurado no canal de call center. Então, quando as ordens de venda forem criadas nesse canal, o depósito padrão será inserido automaticamente no cabeçalho da ordem de venda, a menos que outro depósito seja definido no cliente selecionado para a ordem de venda. Nesse caso, o depósito do cliente é inserido por padrão.

Os usuários deverão estar vinculados a um canal de call center para usar os recursos de call center. Qualquer ordem de venda que um usuário criar será automaticamente vinculada ao canal de call center do usuário. Atualmente, um único usuário não pode ser vinculado a vários de canais de call center simultaneamente.

Um perfil de notificação por email pode ser configurado no canal de call center. O perfil define o conjunto de modelos de email usado quando o email é enviado para os clientes que fazem pedidos por meio do canal de call center. Os disparos de email podem ser configurados em relação a eventos do sistema, como a emissão ou a remessa da ordem.

Antes que as vendas possam ser corretamente processadas em um canal de call center, os [métodos de pagamento](/dynamics365/unified-operations/retail/work-with-payments) e os modos de entrega corretos devem ter sido definidos para o canal.

No nível do canal de call center, você pode definir outros valores padrão relacionados às dimensões financeiras que serão vinculadas às ordens criadas pelo canal.

## <a name="options-for-order-processing-behavior"></a>Opções para comportamento de processamento de ordens

Três definições na configuração de um call center têm um efeito principal nos recursos e funções disponíveis para ordens de venda criadas no call center: **Habilitar conclusão de ordem**, **Habilitar venda direta** e **Habilitar controle de preços da ordem**.

### <a name="enable-order-completion"></a>Habilitar conclusão de ordem

A definição de **Habilitar conclusão de ordem** no canal de call center tem um efeito fundamental no fluxo de processamento das ordens de venda inseridas para o canal. Quando essa definição estiver ativada, todas as ordens de venda deverão passar por um conjunto de regras de validação antes que possam ser confirmadas. Execute essas regras selecionando o botão **Concluir** adicionado ao Painel de Ações da página da ordem de venda. Todas as ordens de venda criadas quando a definição **Habilitar conclusão de ordem** estiver ativada deverão passar pelo processo de conclusão de ordem. Esse processo impõe a captura da lógica de pagamento e de validação do pagamento. Além da imposição de pagamento, o processo de emissão da ordem pode disparar [verificações de fraude](/dynamics365/unified-operations/retail/set-up-fraud-alerts) configuradas no sistema. As ordens que falharem nas validações de pagamento ou de fraude serão colocadas em espera e não poderão ser liberadas para processamento adicional (como separação ou o envio) até que o problema que causou o bloqueio seja resolvido.

Quando a definição **Habilitar conclusão de ordem** estiver ativada para o canal de call center, se os itens de linha forem inseridos em uma ordem de venda e se o usuário do canal tentar fechar ou sair do formulário da ordem de venda sem selecionar **Concluir**, o sistema forçará o processo de conclusão da ordem ao abrir a página de recapitulação da ordem de venda, exigindo que o usuário emita a ordem corretamente. Se a ordem não puder ser emitida corretamente com o pagamento, o usuário poderá usar a funcionalidade [bloqueios da ordem](/dynamics365/unified-operations/retail/work-with-order-holds) para colocar a ordem em espera. Se o usuário estiver tentando cancelar a ordem, deverá cancelá-la corretamente usando a função Cancelar ou a função Excluir, dependendo da função permitida pela segurança do usuário.

Se a definição **Habilitar conclusão de ordem** estiver ativada para o canal de call center, o campo **Status do pagamento** será acompanhado na ordem. O sistema calcula o **Status do pagamento** quando a ordem de venda é emitida. Somente as ordens com um status de pagamento aprovado podem se mover pelo sistema para etapas adicionais de processamento de ordem, como separação e remessa. Se os pagamentos forem recusados, o sinalizador **não processar** será habilitado no status detalhado da ordem, colocando a ordem em espera até o problema com o pagamento ser resolvido.

Além disso, se a definição **Habilitar conclusão de ordem** estiver ativada, quando os usuários criarem ordens de venda e estiverem no modo de entrada de item de linha, o campo **Origem** estará disponível no cabeçalho principal da ordem de venda. O campo **Origem** é usado para capturar um [código-fonte de catálogo](/dynamics365/unified-operations/retail/call-center-catalogs) em um cenário de venda por marketing direto. Este código pode, então, resultar em preços especiais e promoções.

Mesmo se a configuração **Habilitar conclusão de ordem** estiver desativada, os usuários ainda poderão aplicar um código-fonte a uma ordem de venda. Entretanto, primeiro eles deverão abrir os detalhes do cabeçalho da ordem de venda para acessar o campo **Origem**. Em outras palavras, alguns cliques adicionais são necessários. O mesmo comportamento se aplica a recursos como remeter ordens concluídas e expedidas. Esses recursos estão disponíveis para todas as ordens criadas no call center. Entretanto, quando a definição **Habilitar conclusão de ordem** estiver ativada, os usuários poderão consultar a configuração desses recursos no cabeçalho de venda enquanto estiverem na exibição de entrada de linha. Eles não precisam detalhar o cabeçalho da ordem de venda para encontrar as definições e os campos apropriados.

> [!NOTE]
> Quando o recurso **Pagamentos de ordens de omnicanal do Commerce** está habilitado, o botão do call center **Habilitar conclusão de ordem** ficará oculto no headquarters na FastTab **Geral** do seu canal no **Varejo e Comércio \> Canais \> Call Centers**.

### <a name="enable-direct-selling"></a>Habilitar venda direta

Se a definição **Habilitar a venda direta** estiver ativada para o canal de call center, os usuários poderão aproveitar as vantagens dos recursos de venda adicional e de venda cruzada do Commerce. Neste caso, as janela pop-up aparecem durante a entrada de ordem e sugerem e outros produtos que o usuário de call center pode oferecer ao cliente. Os produtos sugeridos se baseiam no produto que acabou de ser encomendado na linha de ordem de venda. Atualmente, as sugestões de venda adicional e de venda cruzada são configuradas no nível do item em produtos ou catálogos. Se a definição **Habilitar venda direta** estiver desativada para o canal de call center, as janelas pop-up não aparecerão durante a entrada de ordem se uma venda adicional ou uma venda cruzada tiver sido definida para um item encomendado.

Quando a definição **Habilitar venda direta** estiver ativada, os scripts e os recursos de imagens da página de entrada de ordem de venda também estarão ativados. Neste caso, um painel de informações está disponível no lado direito da página durante a entrada de ordem. Esse painel pode mostrar os scripts relacionados ao processo genérico de entrada de ordem, o código-fonte do catálogo que foi aplicado ou os scripts relacionados aos itens que estão sendo encomendados. Adicionalmente, o painel de imagens podem mostrar uma imagem de produto para os itens que estão sendo encomendados, se uma imagem tiver sido definida para o item na configuração do produto.

### <a name="enable-order-price-control"></a>Habilitar controle de preço de ordem

Quando a definição **Habilitar o controle dos preços da ordem** está ativada, somente os usuários autorizados podem alterar o preço de venda de um item durante a entrada de ordem. As alterações devem estar dentro das tolerâncias definidas. Os usuários que não tiverem a autorização adequada deverão enviar uma solicitação de alteração de preço. A solicitação será então processada pelos fluxos de trabalho do sistema para revisão e aprovação.

## <a name="channel-users"></a>Usuários do canal

Quando você define o canal de call center, deve vincular usuários do canal ao call center Caso contrário, o call center não poderá ser usado no sistema. Quando os usuários iniciarem sessão no Commerce e inserirem ordens de venda ou ordens de devolução em uma página relacionada à entrada de ordem, a ID de usuário deles será validada em relação à definição do canal de call center. Se um usuário estiver vinculado a um canal de call center específico, as ordens criadas pelo usuário herdarão os traços e valores padrão do canal.

Por padrão, o sinalizador **Venda** no cabeçalho da ordem de venda está ativado para todas as ordens criadas pelos usuários do call center. As ordens podem então aproveitar as vantagens dos recursos de preço e promoções específicos do comércio do sistema.


Os usuários que não estiverem vinculados a um canal de call center usarão os recursos padrão de entradas de ordem do Microsoft Dynamics 365 Finance. As ordens inseridas por esses usuários por meio do formulário de entrada de ordem de venda não serão sistematicamente identificadas como Ordens do Commerce. Adicionalmente, essas ordens inseridas por esses usuários não estarão sujeitas a qualquer uma das regras de processamento de conclusão de ordem, lógica de preços ou outras validações de ordem que possam ser definidas na configuração do canal de call center ou nos parâmetros do sistema de call center.

Depois de concluir a configuração do canal call center e de definir os usuários de canal, para ajudar a garantir o comportamento do sistema desejado, verifique se todos os Parâmetros de call center necessários foram definidos em **Retail e Commerce** \> **Configuração de canal** \> **Configuração de call center** \> **Parâmetros de call center**. Verifique se as sequências numéricas relacionadas também foram definidas.

> [!NOTE]
> Para usar a funcionalidade do centro de chamada, a chave da configuração deve ser habilitada para **Diversos endereços de remessa**. Essa chave de configuração pode ser encontrada nas chaves **Configuração de troca** em **Administração do sistema**\> **Configuração** \> **Configurações do sistema**. Isso é necessário devido à funcionalidade do centro de chamada que executa várias validações com base no endereço de entrega configurado no nível da linha da ordem de venda. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
