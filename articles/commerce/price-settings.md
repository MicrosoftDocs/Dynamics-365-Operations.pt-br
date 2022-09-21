---
title: Configurações de preços
description: Este artigo descreve as várias configurações de preços e de gerenciamento de desconto no Microsoft Dynamics 365 Commerce headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 79130e0ef285d6bd5e544f2d6a6368c0393fa7fa
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474033"
---
# <a name="pricing-settings"></a>Configurações de preços

[!include [banner](../includes/banner.md)]

Este artigo descreve as várias configurações de preços e de gerenciamento de desconto no Microsoft Dynamics 365 Commerce headquarters. Essas configurações permitem que as organizações definam o comportamento de preços na solução do Commerce para atender a necessidades dos negócios específicas.

## <a name="company-level-pricing-settings"></a>Configurações de preços em nível de empresa

A maioria das configurações de preços está em nível de empresa e podem ser encontradas em **Parâmetros do Commerce \> Preços e descontos** no Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Melhor preço e modelo composto do controle de simultaneidade

A configuração **Melhor preço e modelo composto do controle de simultaneidade** determina como o mecanismo de preços processa vários descontos no modo de simultaneidade **melhor preço** ou **composto**. 

Se o parâmetro estiver definido como **Melhor preço e composto na prioridade, nunca composto entre prioridades**, todos os descontos **compostos** com a mesma prioridade de preços serão compostos. O resultado composto compete com descontos de **melhor preço** que têm a mesma prioridade de preços, o melhor preço é aplicado e todos os descontos com prioridade de preços mais baixa são ignorados.

Se o parâmetro estiver definido como **Melhor preço somente na prioridade, sempre composto entre prioridades**, todos os descontos **compostos** serão tratados como descontos de **melhor preço**. Em uma prioridade de preço, um único desconto vence. Se esse desconto único for o **melhor preço** ou um desconto **composto**, ele será composto com todos descontos adicionais de **melhor preço** ou **compostos** que tenham prioridade de preço mais baixa.

### <a name="discount-compound-behavior"></a>Comportamento da composição de descontos

A configuração do **Comportamento da composição de descontos** determina como o mecanismo de preços calcula vários descontos compostos.

Se o parâmetro estiver definido como **Composto**, um desconto será aplicado acima de outro de forma cumulativa. Se ele estiver definido como **Composto no preço original**, todos os descontos serão tratados de forma independente entre si e aplicados ao mesmo preço original.

Por exemplo, você deseja compor descontos de 10% e 20% para um produto com preço original de $100. Se você definir o parâmetro de **Comportamento da composição de descontos** como **Composto**, o preço final será $72 ($100 &times; 90% &times; 80%). Se você defini-lo como **Composto no preço original**, o preço final será $70 ($100 – $10 – $20).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Habilitar a concorrência entre limite exclusivo e outros descontos periódicos

Se o parâmetro **Habilitar a concorrência entre limite exclusivo e outros descontos periódicos** estiver definido como **Sim**, o mecanismo de preços fará com que descontos de limite exclusivos concorram com descontos sem limites exclusivos. A prioridade de preços ainda se aplica. O comportamento de descontos de limite de **melhor preço** e **composto** permanecem como estão. Em outras palavras, eles não competem com os descontos sem limite.

### <a name="manual-line-discount-and-system-discount"></a>Desconto manual de linha e desconto do sistema

A configuração de **Desconto manual de linha e desconto do sistema** determina como o mecanismo de preços aplica um desconto manual de linha e um desconto do sistema na mesma linha. O desconto manual de linha pode ser composto sobre o desconto do sistema ou pode substituir o desconto do sistema. Quando o desconto manual de linha e o desconto do sistema são compostos, a lógica de cálculo respeita a configuração do **Comportamento da composição de descontos**. Um desconto total manual que se aplica a toda a ordem não respeita essa configuração.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Manter itens na mesma linha de vendas para o arredondamento de preços com desconto

Às vezes, o valor de desconto por quantidade não pode ser igualmente dividido pela quantidade qualificada (por exemplo, se o valor do desconto for de $10 para três unidades compradas). Nesses casos, a configuração **Manter itens na mesma linha de vendas para o arredondamento de preços com desconto** determina como o mecanismo de preços se aplica e distribui o valor do desconto. Se o parâmetro estiver definido como **Sim**, o valor do desconto será aplicado como um todo e não será dividido. Se estiver definido como **Não**, o valor do desconto será dividido na quantidade qualificada e arredondada. Por exemplo, um valor de desconto de $10 para três unidades é dividido em menos $3,33 para uma unidade, menos $3,33 para a segunda unidade e menos $3,34 para a terceira unidade.

### <a name="apply-discounts-to-key-in-price-products"></a>Aplicar descontos a produtos com preços inseridos

A definição **Aplicar descontos a produtos com preços inseridos** determina se os descontos podem ser aplicados com os "preços inseridos" que são inseridos no ponto de venda (PDV). A configuração **Preço inserido** na configuração do produto determina se e como um produto dá suporte ao preço inserido.

### <a name="apply-discounts-to-price-overrides"></a>Aplicar descontos a substituições de preços

A configuração **Aplicar descontos a substituições de preços** determina se os descontos podem ser aplicados junto com substituições de preços

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Distribuir descontos para descontos menos dispendiosos

Para descontos de compra combinada que usam o tipo de cálculo "menos caro", a configuração **Distribuir descontos para descontos menos dispendiosos** determina se o mecanismo de preços distribui o desconto pelas linhas.

Se o parâmetro estiver definido como **Não**, o desconto será aplicado somente às linhas menos caras. Por exemplo, para um desconto de compra combinada "comprar 2 obter 1 gratuito", o item menos caro será gratuito e os outros dois itens permanecerão com valor integral. Nesse caso, um cliente que devolver itens com valor integral ainda receberá o terceiro item gratuitamente. Esse cenário pode causar uma perda para o varejista.

Se o parâmetro estiver definido como **Sim**, o mecanismo de preço distribuirá o desconto em todas as linhas aplicáveis. Essa configuração pode ajudar a reduzir a perda em devoluções.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Calcular manualmente preços e descontos combinados

A configuração **Calcular manualmente preços e descontos combinados** controla se o mecanismo de preços usa o cálculo de preço e desconto atrasados para o aplicativo PDV e o canal do call center. Se o parâmetro estiver definido como **Sim**, o mecanismo de preços não calculará logo os descontos combinados (por exemplo, descontos por quantidade, descontos de limite e descontos de compra combinada) sempre que uma ordem de venda for criada ou editada no aplicativo PDV ou no canal do call center.

> [!NOTE]
> No Commerce versão 10.0.30 e anterior, a configuração **Calcular manualmente preços e descontos combinados** controla somente o canal do call center. Uma configuração **Calcular manualmente descontos de vários itens** no perfil de funcionalidade controla o comportamento do cálculo de preço no aplicativo PDV. No Commerce versão 10.0.31, as duas configurações são consolidadas em uma configuração em nível de empresa.

### <a name="retention-period-in-days"></a>Período de retenção em dias

A configuração **Período de retenção em dias** indica quantos dias após a data de vencimento (se uma data de vencimento for definida) ou a data desabilitada (se uma data de vencimento não estiver definida) um desconto deverá ser excluído sistematicamente. Se o parâmetro estiver definido como **0** (zero), nenhuma exclusão automática ocorrerá.

> [!NOTE]
> No Commerce versão 10.0.30 e anterior, essa configuração é denominada **Número de dias após os quais os descontos expirados devem ser excluídos**.

### <a name="coupon-bar-code"></a>Código de barras do cupom

A configuração de **Código de barras do cupom** determina qual código de barras é usado para gerar códigos de barra de cupom. Os usuários podem selecionar um dos códigos de barras predefinidos que são configurados na página **Configuração do código de barras**. Para obter mais informações sobre códigos de barras e máscaras de código de barras, consulte [Configurar códigos de barras](set-up-bar-codes.md) e [Configurar máscaras de código de barras](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>O código de cupom deve ser aplicado manualmente a transações de devolução

A configuração de **O código de cupom deve ser aplicado manualmente a transações de devolução** é aplicável somente a transações de devolução para as quais não há recebimento de vendas fornecido. Defina o parâmetro como **Não** se os códigos de cupom precisarem ser aplicados automaticamente à transação. Defina-o como **Sim** se for preciso adicionar manualmente códigos de cupom à transação.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Usar contratos de venda configurados para a organização

Para ordens B2B, se o parâmetro **Usar contratos de venda configurados para a organização** estiver definido como **Sim**, o mecanismo de preços usará os contratos de venda definidos para a organização na hierarquia do cliente do usuário para determinar o preço com base no contrato. Se o parâmetro estiver definido como **Não**, ou se a hierarquia do cliente não estiver definida, o mecanismo de preço procurará os contratos de venda definidos para o usuário determinar o preço com base no contrato. Para obter mais informações sobre hierarquias de cliente para comércio eletrônico B2B, consulte [Gerenciar parceiros de negócios B2B usando hierarquias do cliente](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Configurações de preços em nível de canal

As configurações a seguir permitem que as organizações controlem o comportamento de preços em canais de vendas específicos.

### <a name="enable-order-price-control"></a>Habilitar controle de preço de ordem

O parâmetro **Habilitar controle de preço de ordem** está localizado na FastTab **Geral** da página **Configuração do call center**. A configuração determina se o mecanismo de preço impõe uma restrição na operação de substituição de preço no canal do call center. Ela funciona junto com a configuração **Permitir ajuste de preço** em nível de produto.

Se o controle de preço da ordem estiver desativado, qualquer usuário do call center poderá fazer alterações de preço em linhas de venda no canal de call center, independentemente de os produtos correspondentes permitirem o ajuste de preço.

Se o controle de preço da ordem estiver ativado, somente os produtos em que o parâmetro **Permitir ajuste de preço** estiver definido como **Sim** permitirão substituições de preço em ordens de venda de canal de call center, e um código de motivo deverá ser fornecido em linhas de venda correspondentes. Um usuário do call center só pode alterar o preço de venda até o valor **Porcentagem de marcação de custo** que é definido em **Varejo e Comércio \> Configuração de canal \> Configuração de call center \> Substituir permissões**. Se uma substituição de preço exceder essa porcentagem, o usuário deverá enviar uma solicitação, que será processada por meio de um fluxo de trabalho predefinido do Commerce para revisão e aprovação. Para obter mais informações sobre fluxos de trabalho do Commerce, consulte [Visão geral do sistema de fluxo de trabalho](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Configurações de preços em nível de produto

As configurações a seguir aplicam regras de preços ao nível do produto e podem ser encontradas na página **Configuração do produto** de uma organização.

### <a name="allow-price-adjust"></a>Permitir ajuste de preço

Se o parâmetro **Permitir ajuste de preço** estiver definido como **Sim**, uma substituição de preço poderá ser aplicada ao produto em ordens de venda de canal de call center.

### <a name="key-in-price"></a>Inserir o preço

A configuração **Inserir preço** determina se é obrigatório inserir preço quando um produto é adicionado a uma transação de venda no PDV. Ela também define restrições de valores de preço correspondentes.

### <a name="zero-price-valid"></a>Preço zero válido

A configuração **Preço zero válido** determina se preços de venda predefinidos, calculados pelo sistema ou ajustados manualmente para um produto podem ser 0 (zero). Defina o parâmetro como **Sim** se for permitido um preço igual a zero. Essa configuração também pode ser especificada no nível da categoria a partir da hierarquia de produtos do Commerce.

### <a name="prevent-all-discounts"></a>Impedir todos os descontos

Ao definir o parâmetro **Impedir todos os descontos** como **Sim**, você impede que todos os tipos de descontos (incluindo descontos manuais) sejam aplicados a um produto. Essa configuração também pode ser especificada no nível da categoria a partir da hierarquia de produtos do Commerce.

> [!NOTE]
> Essa configuração não restringe a operação de substituição de preço, pois essa operação define o preço e não é tratada como um desconto.

### <a name="prevent-manual-discounts"></a>Impedir descontos manuais

Ao definir o parâmetro **Impedir descontos manuais** como **Sim**, você impede que descontos de linha manual ou de transação sejam aplicados a um produto. Todos os outros descontos ainda podem ser aplicados. Essa configuração também pode ser especificada no nível da categoria a partir da hierarquia de produtos do Commerce.

> [!NOTE]
> Essa configuração não restringe a operação de substituição de preço, pois essa operação define o preço e não é tratada como um desconto.

### <a name="prevent-retail-discounts"></a>Impedir descontos de varejo

Se o parâmetro **Impedir descontos de varejo** estiver definido como **Sim**, os descontos **simples**, **quantidade**, **limite**, **compra combinada** e **remessa** não poderão ser aplicados a um produto. Todos os outros descontos (inclusive descontos manuais) ainda podem ser aplicados.

### <a name="prevent-tender-based-discounts"></a>Impedir descontos baseados em meios de pagamento

Se o parâmetro **Impedir descontos baseados em meios de pagamento** estiver definido como **Sim**, um desconto **com base no meio de pagamento** não poderá ser aplicado a um produto. Todos os outros descontos (inclusive descontos manuais) ainda podem ser aplicados.

Os varejistas geralmente optam por excluir alguns produtos, como novos itens ou itens de demanda, dos descontos baseados em item (como descontos simples ou descontos por quantidade). No entanto, talvez eles ainda desejem aplicar descontos baseados em meios de pagamento se um cliente pagar usando o meio de pagamento preferencial. Para conseguir esse resultado, os varejistas podem definir os parâmetros **Impedir todos os descontos** e **Impedir descontos baseados em meios de pagamento** como **Não**, e os parâmetros **Impedir descontos de varejo** e **Impedir descontos manuais** como **Sim**.

## <a name="deprecated-or-removed-settings"></a>Configurações removidas ou preteridas

As configurações de preços a seguir foram removidas ou estão previstas para remoção do Dynamics 365 Commerce.

| Configuração | Motivo da depreciação ou remoção | Status da depreciação ou remoção |
|---------|-----------------------------------|-------------------------------|
| Manuseio de descontos sobrepostos | Fornecemos essa configuração em parâmetros do Commerce para controlar como o mecanismo de preços pesquisa e determina a melhor combinação de descontos a ser aplicada. A opção **Melhor desconto** força todas as combinações de desconto possíveis durante o cálculo de preços. A opção **Melhor desempenho** é uma opção otimizada que usa um algoritmo heurístico e um método de classificação de valor marginal para priorizar, avaliar e determinar a melhor combinação em tempo hábil. A opção **Cálculo equilibrado** na base de código funciona da mesma forma que o **Melhor desempenho**. Portanto, é essencialmente uma opção duplicada. Para ajudar a melhorar o desempenho, o mecanismo de preços foi atualizado para que use somente o **Melhor desempenho** como a opção padrão. Portanto, essa configuração não é mais aplicável. | Preterida na versão do 10.0.21 e será removida em outubro de 2022. |
| Permitir ajustes de preço para aumentar o preço do produto | Fornecemos essa configuração para controlar se a função de ajuste de preço pode aumentar os preços de produtos. Se o parâmetro for desativado, as organizações poderão usar a função de ajuste de preço apenas para definir o preço unitário de um produto para que eles seja menor do que o preço base e o preço de venda do contrato comercial. Preterimos essa configuração porque a função de ajuste de preço foi atualizada para dar suporte a ajustes bidirecionais (aumentar ou diminuir) prontos para uso. | Preterida na versão do 10.0.30 e será removida em outubro de 2023. |
| Habilitar o relatório de preços da loja de varejo | Fornecemos essa configuração para controlar se a função **Relatório de preço** está disponível para uso na página configuração da loja. Preterimos essa configuração porque a página de configuração da loja foi atualizada para que sempre forneça **Relatório de preços** como a função padrão. | Preterida na versão do 10.0.31 e será removida em outubro de 2023. |
| Usar a data de hoje para calcular preços | O mecanismo de preço do Dynamics 365 Supply Chain Management oferece suporte ao cálculo de preços que se baseia na data de remessa solicitada ou na data de recebimento solicitada, junto com a data atual. O mecanismo de preço do Commerce só oferece suporte ao cálculo de preços que se baseia na data atual. Para os clientes que usam os recursos do Supply Chain Management e do Commerce, fornecemos essa configuração e recomendamos que os clientes sempre a definam como **Sim**, para que os dois mecanismos de preços possam operar juntos. Preterimos essa configuração porque ela não altera fundamentalmente o comportamento do cálculo e, portanto, é redundante. | Preterida na versão do 10.0.31 e será removida em outubro de 2023. |
| Preço máximo | Fornecemos essa configuração no perfil de funcionalidade para controlar se somente os produtos que têm um preço de venda inferior ao preço máximo especificado podem ser vendidos por PDV em lojas específicas. Preterimos essa configuração devido ao baixo uso de recursos. | Preterida na versão do 10.0.31 e será removida em outubro de 2023. |
| Aplicar descontos ao preço unitário | A finalidade dessa configuração é controlar se os preços e descontos são arredondados em nível de preço unitário ou em nível da linha de venda durante o cálculo de preços. Nós a preterimos porque ela não está sendo consumida na base de código atual. | Preterida na versão do 10.0.31 e será removida em outubro de 2023. |
| Calcular manualmente descontos de vários itens | Fornecemos essa configuração para controlar se o mecanismo de preços usa o cálculo de preço atrasado para o canal de loja de varejo. Se o parâmetro estiver definido como **Sim**, o mecanismo de preços não calculará logo os descontos combinados (por exemplo, descontos por quantidade, descontos de limite e descontos de compra combinada) sempre que uma ordem de venda for criada ou editada no aplicativo PDV. Decidimos consolidar essa configuração com uma configuração semelhante em parâmetros do Commerce para criar um controle de omnicanal. | Preterida na versão do 10.0.31 e será removida em outubro de 2023. |

Para obter uma lista completa de recursos preteridos no Dynamics 365 Commerce, consulte [Recursos removidos ou preteridos no Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
