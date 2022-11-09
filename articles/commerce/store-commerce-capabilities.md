---
title: Recursos do aplicativo Store Commerce
description: Este artigo descreve a funcionalidade disponível no aplicativo Store commerce para o Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: d713cc0e9537ae20ffddee6e77779a16e74bd779
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725629"
---
# <a name="store-commerce-app-capabilities"></a>Recursos do aplicativo Store Commerce

[!include [banner](includes/banner.md)]

O aplicativo Store Commerce é a experiência moderna de ponto de venda (PDV) para o Microsoft Dynamics 365 Commerce. Ele permite que as empresas processem transações na loja e gerenciem operações de back-office, como estoque e processamento da ordem. O aplicativo também permite que as empresas gerenciem relacionamentos com o cliente com fidelidade e depoimentos de clientes. 

Desenvolvido pela Commerce Scale Unit (CSU), o aplicativo Store Commerce fornece uma solução omnicanal completa. Por exemplo, um cliente pode comprar um produto online e retirá-lo em uma loja próxima, continuando assim sua jornada de compra pelos canais sem perder nenhum dado. 

Este artigo fornece uma visão geral dos recursos do aplicativo Store Commerce.

## <a name="platform"></a>Plataforma

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Omnicanal | O Dynamics 365 Commerce oferece uma solução omnicanal abrangente que unifica as experiências de back-office, na loja, no call center e digital. | [Visão Geral](index.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Commerce sem periféricos | O Commerce Scale Unit é um mecanismo do Commerce sem periféricos. O mecanismo do Commerce sem periféricos serve como ponto central para toda a lógica comercial do Commerce e ativa uma solução de omnicanal completa. | <p>[Visão geral da arquitetura](commerce-architecture.md)</p><p>[Arquitetura sem periféricos](dev-itpro/retail-server-architecture.md)</p> | [Tech talk](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce Headquarters | O Commerce Headquarters fornece recursos de back-office que permitem a configuração de produtos, funcionários, processos de negócios, preços e outras funcionalidades necessárias para a empresa. | [Visão geral da arquitetura](commerce-architecture.md) | |
| Ponto de venda (PDV) | O aplicativo Store Commerce é a experiência de PDV para o Dynamics 365 Commerce. Ele oferece recursos de PDV abrangentes e repletos de recursos que ajudam os parceiros de vendas, caixas e gerentes a fornecer um atendimento de clientes superior. Além disso, ele fornece várias opções de implantação aos varejistas, ajuda a melhorar o desempenho e oferece gerenciamento de ciclo de vida do aplicativo (ALM) aprimorado. | [Aplicativo Store Commerce](dev-itpro/store-commerce.md) | <p>[Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Vídeo](https://youtu.be/7B332XH_zfs)</p><p>[Migração do MPOS para o Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Implantação de nuvem | Várias instâncias do Commerce Scale Units podem ser implantadas para distribuição de carga e proximidade geográfica. | [Implantação de nuvem](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| ​Implantação local​ | Usando uma implantação de dados comerciais local, os clientes do Commerce podem ter maior propriedade e gerenciamento de ambientes do Dynamics 365. | [Implantação local](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Gerenciamento de dispositivos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Vários fatores forma | O aplicativo Store Commerce tem suporte em vários fatores forma de dispositivo, como PCs, tablets e dispositivos móveis. A interface do usuário (UI) responsiva permite que o layout seja redimensionado automaticamente e ajustado para o tamanho da tela. | [Configurações visuais](pos-screen-layouts.md) | |
| Plataforma cruzada | O aplicativo Store Commerce tem suporte nas plataformas Web, Windows, iOS e Android. | [Plataformas](dev-itpro/hybridapp.md) | |
| Identidade visual | O designer de tela permite que você personalize layouts de tela para atender às suas necessidades comerciais. Além disso, os temas, layouts, cores e imagens podem ser criados com base nas funções do funcionário e podem ser compartilhados por usuários para a consistência da identidade e a facilidade de uso. | [Configurações visuais](pos-screen-layouts.md) | [Vídeo](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topologia | Há suporte para diferentes topologias na loja, com base na disponibilidade da rede. | <p>[Topologia](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infográfico](dev-itpro/retail-in-store-topology.md)</p> | |
| Gerenciamento de vários dispositivos | Vários dispositivos nas lojas podem ser facilmente gerenciados no Commerce headquarters. | [Ativação](set-up-activation-accounts-validate-devices-hq.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Gerenciamento de funcionários

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Entrar | Cada funcionário da loja pode ter uma entrada dedicada. Os tipos de entrada incluem nome de usuário, código de barras, leitor de tarja magnética (MSR), biometria e Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Logon estendido](extended-logon.md)</p> | |
| Permissões | Os funcionários têm suporte para diferentes níveis de permissões, como permissão para criar ordens e permissão para editar ordens. | [Permissões](tasks/create-pos-permission-groups.md) | |
| Gerenciamento de horário e de presença | A presença pode ser gerenciada usando a função de Relógio de Ponto. Os dados de presença podem ser processados na folha de pagamento usando o aplicativo Dynamics 365 Human Resources. | [Gerenciamento de tempo](retail-time-attendance.md) | |
| Comissão de vendas | As vendas podem ser rastreadas por representantes de vendas para calcular comissões ou outros incentivos. | [Comissão](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Merchandising

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Gerenciamento de sortimentos | Os gerentes de mercadorias podem classificar produtos para que estejam disponíveis para venda em um canal específico e durante um período específico. | [Sortimentos](assortments.md) | |
| Catálogos | Os gerentes de mercadorias podem gerenciar catálogos para identificar os produtos que você deseja oferecer com preços específicos de catálogo. | [Catálogos](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Gerenciamento de categorias e produtos | No Commerce headquarters, os gerentes de mercadorias podem criar produtos que têm grades, atributos, uma unidade de medida e assim por diante. Eles também podem definir uma hierarquia de categorias para organizar os produtos. | [Produto](retail-hierarchies.md) | |
| Pacotes | Os gerentes de mercadorias podem agrupar produtos para que sejam vendidos como um pacote ou um kit. | [Kits](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Códigos de informação | Use códigos de informação para solicitar que o caixa insira informações durante diferentes ações no PDV, como vendas de itens, devoluções de itens ou seleção de clientes. | [Códigos de informação](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Itens vinculados | Use itens vinculados para revender produtos quando um item for adicionado à transação. | [Itens vinculados](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garantias | As garantias estendidas podem ser vendidas junto com produtos. | [Garantia](extended-warranty.md) | |
| Impressão de etiqueta | Podem ser geradas etiquetas contendo informações do produto, como número do lote, número de série e data de validade. | [Impressão de etiqueta](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Venda assistida

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Procura de produtos | Procurar produtos por categoria. | [Hierarquia de produtos](retail-hierarchies.md) | |
| Pesquisa do produto | Pesquisar produtos por nome e refinar pesquisas usando atributos de produtos como marca, preço e material. Esse recurso é fornecido pelo Azure Cognitive Search. | [Pesquisa habilitada para a nuvem](cloud-powered-search-overview.md) | |
| Página Detalhes de produto | As páginas de detalhes do produto avançado podem incluir imagens, uma descrição, atributos de produtos e produtos recomendados. As recomendações são ativadas pelo Serviço de Recomendações. | | |
| Comparação de produtos | Compare vários produtos e ajude os clientes a escolher um e adicioná-lo a uma transação. | | |
| Corredor infinito | Procure facilmente o estoque em outras lojas e crie ordens. | [Pesquisa de estoque](pos-inventory-lookup-operation.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Recomendações | Produtos com venda e venda cruzada usando o Serviço de Recomendações. Esse serviço usa tecnologia patenteada para sugerir recomendações, com base nas tendências de compra e características como recentemente recebidas, aparências semelhantes e mais vendidos. Essas recomendações estão disponíveis em páginas de detalhes do produto, na página **Detalhes do cliente** e na página **Transações**. | [Recomendações](product-recommendations.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Relacionamento do cliente

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Gerenciamento de clientes | Criar, editar e gerenciar contas do cliente. As contas do cliente podem ser gerenciadas no modo assíncrono para evitar processamento em tempo real. | [Gerenciamento](customer-mgmt-stores.md) | |
| Atributos de clientes | A estrutura de atributos do Cliente permite que dados adicionais relacionados ao cliente sejam capturados com base nos requisitos de negócios. | [Atributos](dev-itpro/customer-attributes.md) | |
| Página de detalhes do cliente | Uma página avançada de detalhes do cliente fornece uma exibição de omnicanal das interações do cliente em todos os canais. Essas interações incluem compras, listas de desejos e pontos de fidelidade. | | |
| Pesquisa do cliente habilitada para a nuvem | Pesquisar clientes por nome, número de telefone, endereço de email, cartão-fidelidade, endereço, etc. | [Pesquisa habilitada para a nuvem](pos-search-improvements.md#customer-search) | |
| Fidelidade e premiações | Os clientes podem participar de programas de fidelidade e conquistar e resgatar pontos de fidelidade em canais. | [Fidelidade](set-up-customer-loyalty-program.md) | |
| Clientela | Gerencie clientes principais usando um catálogo do cliente e controle atividades e notas sobre o perfil do cliente. A integração do Dynamics 365 Customer Insights permite que os funcionários da loja recebam dicas sobre a próxima melhor ação para cada cliente. | [Clientela](clienteling-overview.md#activities-and-notes) | |

## <a name="pricing-and-discounts"></a>Preços e descontos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Contratos Comerciais | Os gerentes de preços podem usar contratos comerciais para definir preços especiais, com base em acordos de longo prazo para clientes específicos. | [Definição de preços](price-management.md)| [Vídeo](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Contratos de venda | Os gerentes de preços podem usar contratos de venda para definir preços com base em contratos em cenários de comércio B2B (entre empresas). | [Definição de preços](price-management.md) | |
| Ajustes de preço | Os gerentes de preços podem usar o recurso de ajustes de preços para criar, rastrear e gerenciar remarcações de preços para seus produtos ao longo do tempo. | [Ajustes de preço](price-adjustments-discounts.md) | |
| Descontos | Os gerentes de preços podem configurar vários tipos de descontos para executar várias promoções. Esses descontos incluem descontos simples, descontos por quantidade, descontos por limite, descontos de compra combinada, descontos baseados em propostas e descontos de remessa. | [Descontos](retail-discounts-overview.md) | |
| Cupons | Os gerentes de preços podem configurar códigos de cupom ou códigos de barras, vinculá-los a descontos e distribuí-los aos clientes. Os associados de vendas podem adicionar cupons a transações de vendas ou removê-los. | [Cupons](coupons.md) | |
| Grupos de preços | Os gerentes de preços podem usar o recurso de grupo de preços para definir preços contextuais, com base em canais, catálogos, afiliações ou programas de fidelidade. | [Definição de preços](price-management.md) | |
| Promoções disponíveis | Os associados de vendas podem consultar facilmente promoções disponíveis para produtos da loja, produtos que foram adicionados a uma transação e assim por diante. | [Funções de definição de preços](pos-pricing-functions.md) | |
| Verificações de preço | Os associados de vendas podem verificar rapidamente os preços de venda ativos de produtos na loja. | [Funções de definição de preços](pos-pricing-functions.md) | |
| Substituições de preço | Os associados de vendas que têm as permissões necessárias podem substituir os preços calculados ou configurados pelo sistema. | [Funções de definição de preços](pos-pricing-functions.md) | |
| Descontos manuais | Os associados de vendas que têm as permissões necessárias podem aplicar descontos manuais a transações de vendas ou linhas de venda. | [Funções de definição de preços](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Pagamentos eletrônicos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Débito e crédito | O aplicativo Store Commerce suporta os principais pagamentos com cartão de crédito e débito por meio do Gateway de Pagamento de Adyen e atendimento da ordem por meio do PayPal. O SDK de pagamentos permite conexões de gateway externo suportadas por integrações do ISV (fornecedor de software independente). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Pagamentos](payment-methods.md)</p> | <p>[Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Suporte para carteira digital | O aplicativo Store Commerce oferece suporte a pagamentos por meio de métodos de pagamento de carteira digital que não usam intervalos de Número de Identificação do Banco (BIN) como os cartões de crédito e débito tradicionais. Os métodos de pagamento podem ser mapeados para pagamentos de carteira digital como Adyen. | [Carteira](wallets.md) | |
| Suporte a cartões-presente | Cartão-presente do Dynamics 365 com Número de Identificação do Banco, Soluções de Valor Armazenado (SVS) e cartões-presente Givex. Os cartões-presentes podem ser comprados e resgatados em uma ordem. | [Cartões-presente](dev-itpro/gift-card.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Proteção contra fraude | O Dynamics 365 Fraud Protection ajuda a prevenir atividades fraudulentas e a identificar lugares em que a fraude pode passar despercebida. | [Fraud Protection](dev-itpro/dfp.md) | [Vídeo](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Impostos e encargos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Impostos | O aplicativo Store Commerce dá suporte a muitos tipos de impostos indiretos, como imposto sobre vendas, imposto sobre valor agregado (VAT), imposto de bens e serviços (GST), taxas com base em unidades e retenção de imposto. | [Impostos](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Encargos | Os encargos podem ser configurados no nível de linha, no nível do cabeçalho, como encargos automáticos, por canal e assim por diante. | [Encargos](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Atendimento e processamento da ordem

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Criação de ordens | Uma ordem pode ser criada para remessa ou para retirada em uma loja próxima. Os intervalos de tempo podem ser fornecidos para a retirada. | [Visão Geral](customer-orders-overview.md) | |
| Modificação da ordem | Uma ordem pode ser modificada, devolvida, cancelada e assim por diante. | <p>[Cancelamento](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Volta](pos-returns.md)</p> | |
| Pesquisa | Pesquisar e filtrar ordens usando informações específicas da ordem. | [Pesquisa](enhancedorderrecall.md) | |
| Atributos da ordem | A estrutura de atributos da Ordem permite que informações adicionais relacionadas à ordem sejam capturadas com base nos requisitos de negócios. | [Atributos](dev-itpro/order-attributes.md) | |
| Entrega direta | Os itens podem ser marcados para entrega direta por um fornecedor para um endereço do cliente. A entrega direta também é conhecida como remessa direta. | [Entrega direta](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Cotação | Os funcionários da loja podem criar cotações para os clientes e podem especificar um preço especial, descontos manuais e uma data de validade da cotação. | [Cotação](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Processamento | As lojas podem separar, empacotar e remeter ordens. Uma guia de remessa pode ser adicionada aos pacotes que estão prontos para remessa. | [Processamento](order-fulfillment-overview.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021) |
| Gerenciamento de ordem distribuído | O aplicativo Store Commerce oferece suporte à otimização de atendimento de ordens inteligentes, na qual as estratégias comerciais podem ser configuradas com base na natureza da empresa, no tipo de cliente, na origem de uma ordem e no método de entrega de uma ordem. | [DOM](dom.md) | |

## <a name="inventory-management"></a>Gerenciamento de estoque

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Compra centralizada | Simplificar a distribuição do estoque disponível de um centro de distribuição para várias lojas ou depósitos. | [Compra centralizada](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Distribuição integrada | Simplificar a distribuição de estoque em ordens de compra de entrada para várias lojas ou depósitos. | [Distribuição integrada](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Estoque de entrada | Receber o estoque de um fornecedor por uma ordem de compra ou de outro depósito por uma ordem de transferência. Criar uma ordem de compra de entrada ou uma solicitação de ordem de transferência. | [Entrada](pos-inbound-inventory-operation.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Estoque de saída | Remeter estoque para outro depósito por uma ordem de transferência e criar uma solicitação de ordem de transferência de saída. | [Saída](pos-outbound-inventory-operation.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Pesquisa de estoque | Verificar o estoque disponível de produtos em lojas e depósitos e verificar o estoque disponível para promessa (ATP) em datas futuras. | [Pesquisa de estoque](pos-inventory-lookup-operation.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Ajuste de estoque | Ajustar o estoque dentro ou fora de um depósito da loja para atender a necessidades comerciais específicas sem usar uma venda, um recebimento ou uma reconta. | [Ajuste de estoque](work-with-store-inventory.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Contagens de estoque | Fazer contagem de estoque físico e ajustar o estoque de escrituração contábil do sistema para que seja correspondente. | [Contagem](work-with-store-inventory.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Movimentação de estoque | Mover estoque entre localizações em uma loja. | [Movimentação](work-with-store-inventory.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |

## <a name="financials"></a>Finanças

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Gerenciamento de caixa | O aplicativo Store Commerce oferece suporte ao gerenciamento de caixa e a outros meios e pagamentos especificados na loja. Além disso, a reconciliação de turnos na loja pode ser habilitada para recursos avançados de gerenciamento de caixa. | [Pagamento à vista](cash-mgmt.md) | |
| Reconciliação e demonstrativos financeiros | As transações de caixa e transacionais de uma loja são registradas no Commerce Headquarters por meio dos processos de lançamento do demonstrativo. | [Demonstrativos](retail-statements.md) | |
| Transações de receita e despesa | Processar transações de caixa pequeno na loja, e registrar renda que não está no modo tradicional, como dinheiro nos achados e perdidos, o compartilhamento de receita de uma cafeteria no seu lobby e serviços de limpeza de carpetes. | [Demonstrativos](retail-statements.md) | |
| Pagamentos de faturas | Capturar pagamentos com faturas. | [Fatura](payinvoice.md) | |

## <a name="employee-productivity"></a>Produtividade do funcionário

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Gerenciamento de tarefas | Criar listas de tarefas e tarefas e atribuí-las a lojas e funcionários. Rastrear o status das tarefas em lojas. A integração direta com o Microsoft Teams é fornecida. | <p>[Gerenciamento de Tarefas](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Vídeo](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Hardware e periféricos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Conectar periféricos | Conectar periféricos, como impressoras, caixas registradoras, scanners e dispositivos de pagamento a um terminal de PDV. | [Periféricos](retail-peripherals-overview.md) ||
| Compartilhar periféricos | As impressoras de recibo, as gavetas de caixa e os dispositivos de pagamento podem ser compartilhados entre vários terminais, conectando-os a uma estação de hardware compartilhada. | <p>[Estação de hardware](retail-peripherals-overview.md) ||
| Simulador de PDV e periférico | O simulador periférico dá suporte a testes de cenários que costumam exigir dispositivos periféricos físicos de PDV. Ele também inclui um simulador de PDV que pode ser usado para testar a compatibilidade de dispositivos periféricos físicos sem exigir a implantação do cliente PDV. | [Simulador](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Recebimentos

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Imprimir recibos | Os recebimentos de vários tipos, como recibos de vendas, recibos de cartão de crédito, recibos de brindes e notas fiscais podem ser impressos por padrão ou após a confirmação do caixa na finalização da compra. Eles também podem ser reimpressos do diário. | [Imprimindo](receipt-templates-printing.md) | |
| Recibos por email | Os recibos podem ser enviados por email no PDV quando a finalização da compra for concluída. | [Email](email-receipts.md) | |
| Criar recibos | Os recibos de lojas podem ser personalizados, de forma que mostrem os dados e layouts apropriados para o varejista e o tipo de transação. Os recibos também podem ser estendidos de modo que mostrem dados personalizados exigidos pelo varejista. | [Design](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Suporte offline

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Offline contínuo | O modo offline contínuo permite que você continue a fazer transações mesmo quando a conectividade com a Internet estiver limitada ou indisponível. A exclusão de dados ajuda você a reduzir o tamanho dos dados dos bancos offline e a maximizar o desempenho. | [Offline](pos-operations.md) | |
| Alternância baseada em desempenho | Alterne para offline quando a degradação do desempenho for detectada. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Vídeo](https://youtu.be/sQU-2pgHToI) |
| Painel offline | O painel **Status offline** mostra o status, os erros e os detalhes offline dos dados de cada dispositivo. Portanto, é fácil gerenciar o status de vários dispositivos. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Vídeo](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Extensibilidade

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Commerce Headquarters | As soluções do Commerce Headquarters podem ser personalizadas adicionando ou modificando processos comerciais. O Commerce Headquarters oferece suporte ao uso de metadados e um modelo de extensão orientado a código para adicionar funcionalidades personalizadas. Ele pode ser facilmente integrado a soluções externas. | [Visão Geral](dev-itpro/extend-customer-cdx-package.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Commerce sem periféricos | A estrutura da API do Omnicanal extensível pode ser usada para personalizar e adicionar lógica comercial. APIs que têm manipuladores de solicitação e padrões de extensão pré-gatilho e pós-gatilho. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| SDK do Commerce | O SDK do Commerce inclui o código, exemplos de código, modelos e ferramentas que são necessários para estender ou personalizar a funcionalidade do Dynamics 365 Commerce. O SDK é publicado em diferentes repositórios (Repos) no GitHub, dependendo dos componentes de extensão. | [SDK](dev-itpro/retail-sdk/sdk-github.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Ponto de venda | É possível estender o aplicativo Store Commerce independentemente, usando o recurso extensão PDV do SDK do Commerce. A estrutura oferece suporte à personalização da experiência do usuário (UX), fluxos de trabalho e lógica de negócios. | [PDV](dev-itpro/pos-extension/pos-extension-overview.md) | [Tech talk](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Relatório

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Relatórios de vendas | Os relatórios de vendas por equipe, registro, tipo de pagamento, devoluções, produto etc. estão disponíveis para os gerentes de loja. Os gerentes podem exibir esses relatórios e usá-los para alocar comissão e identificar tendências de produtos. | | |

## <a name="diagnostics"></a>Diagnóstico

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Insights operacionais | As métricas de confiabilidade e desempenho da integridade de serviço organizadas por loja estão disponíveis na subscrição do Application Insights do cliente. Recursos avançados de alerta e monitoramento estão disponíveis. | | |
| Verificação de integridade | A disponibilidade de periféricos conectados a um PDV pode ser verificada com a execução da operação de verificação de integridade. Os problemas de periféricos individuais podem então ser corrigidos e verificados. | [Verificação de integridade](pos-healthcheck.md) | [Vídeo](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalização

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Suporte a vários mercados | Recursos específicos do mercado, como integração fiscal, GST, faturamento avançado e pré-pagamentos, são suportados imediatamente. Esse recurso cobre vários mercados na Europa, nas Américas, Rússia, Ásia, Arábia Saudita, etc. | [Globalização](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Conformidade

| Capacidade | Descrição | Documentação | Conteúdo complementar |
|---|---|---|---|
| Padrões da Microsoft | O aplicativo Store Commerce atende aos padrões da Microsoft para segurança, privacidade, acessibilidade, o Regulamento Geral sobre a Proteção de Dados (RGPD), o limite de dados da União Europeia (UE) e assim por diante. | | |

