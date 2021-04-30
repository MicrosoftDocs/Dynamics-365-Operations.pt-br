---
title: Gerenciamento de custo de entrega x transporte
description: O Microsoft Dynamics 365 Supply Chain Management fornece dois módulos diferentes para trabalhar com transporte, TMS (gerenciamento de transportes) e custo de entrega. Este tópico resume a funcionalidade que os dois módulos têm em comum e realça as diferenças entre eles.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 244d378316caf639c3520a1179dd82955d94220a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909466"
---
# <a name="landed-cost-vs-transportation-management"></a>Gerenciamento de custo de entrega x transporte

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management fornece dois módulos diferentes para trabalhar com transporte: **TMS (gerenciamento de transportes)** e **custo de entrega**. Este tópico resume a funcionalidade que os dois módulos têm em comum e realça as diferenças entre eles. Você pode usar essas informações para decidir qual módulo melhor atende às suas práticas comerciais. Talvez você ache que algumas práticas comerciais funcionam melhor com TMS, enquanto outras funcionam melhor com custo de entrega. Dependendo das necessidades comerciais, você pode optar por usar um módulo de forma exclusiva ou combinar os dois módulos.

Este tópico não é uma revisão abrangente de todos os recursos de um dos módulos. Em vez disso, ele realça a funcionalidade disponível, pois pertence ao transporte de mercadorias de um fornecedor para o depósito comercial, onde pode ser consumido.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminologia, dados de referência e relatórios de diferenças

### <a name="terminology-comparison"></a>Comparação de terminologia

O TMS e o custo de entrega usam diferentes termos para conceitos semelhantes. A tabela a seguir resume esses termos e seu uso nos dois módulos.

| Termo de TMS | Termo de custo de entrega | Observação |
|----------|------------------|-------|
| **Carregar**<p>Uma *carga* é um conjunto de remessas que são transportadas simultaneamente na mesma unidade de transporte (como um caminhão ou um navio). As cargas podem ser de entrada ou de saída.</p> | **Viagem**<p>Normalmente, uma *viagem* é uma única embarcação que percorre um único *percurso*. Uma viagem pode conter vários *contêineres de remessa* e também pode incluir ordens de entrada de diferentes entidades legais da organização. As viagens só podem ser de entrada.</p> | TMS também usa o termo *número da viagem*, que se refere a um campo de informações no qual você pode inserir um identificador. No entanto, funcionalidades não estão associadas ao campo TMS e não estão relacionadas ao conceito de *viagem* no custo de entrega. |
| **Roteiro**<p>Um *roteiro* é o caminho físico de um transporte da origem para o destino.</p> | **Percurso**<p>Um *percurso* é o caminho físico de um transporte da origem para o destino. Cada viagem deve ser atribuída a um percurso.</p> | |
| **Segmentos de roteiro**<p>Um roteiro pode ter vários *segmentos de roteiro*, cada um representando uma etapa do percurso. Um roteiro pode incluir várias transportadoras ou serviços, cada uma considerada um segmento de roteiro.</p> | **Itinerários**<p>Cada percurso pode ter vários *trechos*, cada um representando uma etapa do percurso. Um trecho pode fazer parte do transporte, do manuseio de obrigações ou de outra atividade.</p> | |
| **Contêineres**<p>Um *contêiner* pode ser qualquer tipo de pacote ou embalagem usada pelo TMS.</p> | **Contêineres de remessa**<p>Um *contêiner de remessa* é um contêiner de remessa físico literal, como conhecido pelos navios de contêineres.</p> | |
| **Códigos de mercadoria**<p>No TMS (e em outros locais no Supply Chain Management), os *códigos de mercadoria* identificam os tipos de mercadoria. Eles podem afetar as tarifas, o manuseio de materiais perigosos e assim por diante.</p> | **Códigos de mercadoria**<p>No custo de entrega, os *códigos de mercadoria* são estabelecidos no nível da entidade legal. Eles são mais usados para relatórios.</p> | O custo de entrega também pode usar os códigos de mercadoria usados para TMS e outros locais no Supply Chain Management. No entanto, os códigos de mercadoria de custo de entrega são usados somente pelo custo de entrega. |

### <a name="some-reference-data-isnt-shared"></a>Alguns dados de referência não são compartilhados

O TMS e o custo de entrega não compartilham dados de referência para entidades como configuração de custos, percursos e trechos. Se você usar os dois módulos, deverá recriar os dados de referência não compartilhados.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>Os relatórios intercompanhia não funcionam com mercadorias em trânsito

Os seguintes relatórios não funcionam em conjunto com o recurso mercadorias em trânsito fornecido pelo custo de entrega:

- [Relatório Totais de mercadorias em trânsito intercompanhia](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Relatório Totais de mercadorias em trânsito intercompanhia](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Esses relatórios supõem que as mercadorias são colocadas em trânsito logo que você emite uma guia de remessa de venda e que que são colocadas em estoque de trânsito após o recebimento. No entanto, as mercadorias em trânsito não são processadas dessa forma. Portanto, se você usar os recursos de mercadorias em trânsito e intercompanhia juntos, os resultados desses dois relatórios serão incorretos.

## <a name="using-the-two-modules-together"></a>Usar os dois módulos juntos

Você pode usar TMS para operações de entrada e saída. Embora o custo de entrega forneça a maioria das mesmas funcionalidades básicas do TMS para operações de entrada, ele também adiciona funcionalidade. Portanto, talvez você queira considerar o uso de TMS para operações de saída e Custo de entrega para operações de entrada.

Em geral, não recomendamos que você use os dois módulos juntos para operações de entrada. Você deve usar o módulo que melhor atenda às suas necessidades. Se você usar os dois módulos juntos, não deverá compartilhar documentos de origem entre eles. Por exemplo, não use a mesma ordem de compra para uma carga no TMS e uma viagem no custo de entrega. Em particular, você deve garantir que não configure o sistema para criar cargas de entrada automaticamente. Se os itens das ordens de compra forem incluídos em uma viagem, eles não poderão ser tratados como parte de uma carga.

## <a name="goods-in-transit"></a>Mercadorias em trânsito

Um dos principais recursos do custo de entrega é sua capacidade de processar mercadorias em trânsito. O processamento de mercadorias em trânsito permite que você obtenha a propriedade financeira de itens enviados antes que eles sejam fisicamente recebidos no depósito de destino. O processamento de mercadorias em trânsito geralmente é necessário para comércio internacional.

### <a name="tms-goods-in-transit-features"></a>Recursos de mercadorias em trânsito do TMS

O TMS no momento não oferece suporte ao processamento de mercadorias em trânsito.

### <a name="landed-cost-goods-in-transit-features"></a>Recursos de custo de entrega de mercadorias em trânsito

O processamento de mercadorias em trânsito é um aspecto principal do Custo de entrega e fornece a seguinte funcionalidade:

- **Depósitos de mercadorias em trânsito** – um depósito de mercadorias em trânsito pode ser associado a cada depósito no Supply Chain Management. As mercadorias são transferidas para depósitos de mercadorias em trânsito após a ordem de compra original ser faturada. Os itens reservados fisicamente ficam indisponíveis para consumo até que sejam recebidos no depósito físico. Portanto, você pode obter a propriedade financeira de mercadorias, faturando a ordem de compra.
- **Conta contábil de mercadorias em trânsito** – o custo de entrega adiciona uma conta de lançamento contábil específica ao perfil de lançamento da ordem de compra para lidar com o processamento de mercadorias em trânsito. Essa conta contábil de mercadorias em trânsito atua como uma conta do tipo "mercadorias faturadas não recebidas". Quando a ordem de compra original é faturada e a ordem de mercadorias em trânsito é criada, o custo da ordem de compra direta é lançado na conta contábil de mercadorias em trânsito até que as mercadorias sejam recebidas na localização física final.
- **Atualizações de controle de acompanhamento** – as ordens de mercadorias em trânsito dão suporte à funcionalidade de controle no custo de entrega. O controle de acompanhamento permite atualizar a data esperada da chegada de mercadorias em trânsito. O controle de acompanhamento atualiza a viagem e as linhas da ordem de compra associadas. A data de entrega esperada estará disponível para o planejamento mestre e a logística.
- **Disparo de transações excedentes/insuficientes** – se ocorrer uma variação entre as mercadorias previstas de uma linha de viagem e as mercadorias reais recebidas no depósito, o Custo de entrega solucionará isso por meio de transações excedentes/insuficientes. Você pode gerenciar essas transações, com base na forma que você deseja processá-las, por meio de uma ordem de compra ou um diário de movimentação. As transações excedentes/insuficientes fornecem um link para a viagem, a ordem de compra original e o novo diário de movimentação ou a ordem de compra para a variação.
- **Ordens de mercadorias em trânsito** – o custo de entrega apresenta um novo documento de origem conhecido como *ordem de mercadorias em trânsito*. Uma ordem de mercadorias em trânsito permite que você fature a ordem de compra original para assumir a propriedade financeira dos itens. Quando a ordem de compra é faturada, o novo documento de origem é criado para cada linha da ordem de compra que tenha uma combinação de dimensões de estoque. As mercadorias são fisicamente transferidas para um depósito de mercadorias em trânsito, em que são fisicamente reservadas na ordem de mercadorias em trânsito e não podem ser consumidas, a menos que as mercadorias em trânsito sejam recebidas.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Encargos diversos e custos de remessa

Um dos aspectos mais importantes do gerenciamento de envio e de remessa para mercadorias é o reconhecimento dos custos gerais indiretos associados a remessas. Esses custos gerais indiretos não são os custos de estoque direto associados a uma ordem de compra e uma remessa ou viagem. Em vez disso, eles são custos adicionais que são apresentados pela natureza da movimentação das mercadorias do fornecedor para a sua organização. Esses custos podem incluir custos de frete associados à remessa de mercadorias de um local físico para outro ou custos de imposto associados à importação de mercadorias de um fornecedor estrangeiro.

O custo de entrega controla esses custos criando um novo tipo de estrutura de custo conhecido como *custos automáticos*. O TMS trata esses custos usando a funcionalidade de encargos diversos.

### <a name="tms-charge-and-cost-features"></a>Recursos de encargos e custos do TMS

O TMS usa encargos diversos para gerenciar custos adicionais para cargas alocadas para as linhas de documento de origem relacionadas. Esses encargos diversos podem ser definidos em nível da linha da ordem de compra ou do cabeçalho da ordem de compra.

No TMS, os encargos diversos podem ser distribuídos, ou divididos, por peso, volume ou quantidade do estoque. Os encargos podem ser divididos por encargos de frete ou suplementares. O desenvolvimento adicional será necessário para usar métodos de divisão adicionais no TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Recursos de encargo de custo de entrega e de custo

O custo de entrega fornece um conjunto de funções de custo que lidam com custos adicionais associados à remessa de mercadorias. Esses custos são conhecidos como custos automáticos e são aplicados no momento do faturamento de remessa inicial usando o valor de custo estimado. Cada tipo de custo é gerenciado no seu próprio lançamento. Depois que as faturas reais para custos gerais indiretos são lançadas, os custos estimados são atualizados automaticamente para refletir os custos reais.

Além disso, os custos gerais indiretos associados à remessa de mercadorias podem ser faturados durante a viagem a partir da porta de origem ou a qualquer momento após o recebimento das mercadorias. Esse recurso oferece maior flexibilidade para o consumo de mercadorias.

A seguinte lista destaca alguns conceitos de aspectos de encargos e custos no Custo de entrega:

- **Área de custo** – custos e encargos podem ser atribuídos a diferentes níveis ou *áreas de custo* em uma viagem. O custo pode ser aplicado no nível da viagem e dividido em cada item da viagem. Além disso, os custos podem ser aplicados no nível de contêiner, ordem de compra, item ou ordem de transferência. Cada custo pode ser gerenciado separadamente nas várias áreas e é dividido para um custo por item.
- **Métodos de divisão** – vários métodos de divisão estão disponíveis no custo de entrega. Os encargos de custos podem ser distribuídos por quantidade, valor em dólar, valor, peso, volume, medição ou uma medida volumétrica definida pelo usuário.
- **Controle de compensação/variação** – os encargos de custo são configurados como seu próprio tipo de código de custo em Custo de entrega. Cada tipo de código de custo permite que você defina uma conta de compensação para encargos de custos estimados, além de contas de variação de preço de compra e de acumulação para variações em custos estimados versus custos reais. Quando os custos estimados são lançados inicialmente, há um crédito na conta de compensação. Após o lançamento das faturas reais, os encargos de custos reais são lançados e os custos estimados são debitados da conta de compensação.

## <a name="matching-freight-bills-and-invoices"></a>Coincidir notas de frete e faturas

### <a name="tms-bill-and-invoice-matching-features"></a>Recursos de conciliação de contas e faturas do TMS

O TMS pode conciliar contas de frete contendo custos estimados e faturas com o custo real do frete. As faturas podem ser recebidas de forma eletrônica ou em papel. A variação correspondente entre o custo estimado e o custo real não afeta a avaliação do estoque.

Para obter mais informações, consulte [Reconciliar frete no gerenciamento de transporte](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Recursos de conciliação de contas de custo de entrega e faturas

O custo de entrega pode conciliar as contas de frete para encargos de custo estimado e pode faturar os encargos de custo real para os custos estimados. No momento do faturamento, os encargos de frete estão em um diário de faturas e os custos estimados são limpos da conta de compensação. Além disso, os encargos de custos reais são lançados em relação ao custo de mercadorias vendidas para o item, junto com as variações entre os encargos estimados e os encargos reais. Esse comportamento permite a flexibilidade no processo de faturamento.

## <a name="tracking"></a>Rastreamento

Um recurso importante do TMS e do custo de entrega é a capacidade de rastrear mercadorias e identificar onde eles estão na jornada do ponto de origem até o depósito de destino final. O acompanhamento permite que você siga e atualize o local em que as mercadorias estão localizadas e quando elas devem chegar no depósito para consumo. Além do status das mercadorias durante o percurso, o custo de entrega fornece as datas esperadas e reais para cada etapa do percurso.

### <a name="tms-tracking-features"></a>Recursos de acompanhamento do TMS

O TMS fornece recursos limitados para rastrear cargas de entrada. Ele mostra datas e permite que uma integração seja criada para encontrar a posição exata (por exemplo, na página **Status do transporte**).

Para cada segmento de roteiro, você pode inserir agendas estimadas e horas de entrada.

### <a name="landed-cost-tracking-features"></a>Recursos do acompanhamento de custos de entrega

O custo de entrega pode fornecer controle de acompanhamento para cada viagem, da porta de origem para o destino final. O controle de acompanhamento define o status da viagem. O status indica se a viagem será por navegação, se está na alfândega para inspeção ou na entrega local a caminho do depósito final. O status pode ser definido no nível da linha da ordem de compra, do contêiner e do cabeçalho da viagem. Portanto, você tem um controle mais granular.

Além disso, uma data confirmada esperada que se baseia em prazos de entrega especificados é associada a cada etapa de um percurso. As datas de entrega confirmada e esperada são adicionadas à linha da ordem de compra e às ordens de mercadorias em trânsito e podem ser usadas para planejamento mestre e logística. Além das datas esperadas, as datas reais podem ser atualizadas. As etapas subsequentes em um percurso serão atualizadas de acordo.

## <a name="multi-leg-journeys"></a>Percursos de vários itinerários

O conceito de percurso identifica onde as mercadorias estão no processo e controla o status das mercadorias em trânsito. As mercadorias podem passar por vários trechos de um percurso, e você pode associar vários custos a um trecho específico. Exemplos incluem um custo de frete na navegação de uma embarcação e custos de transporte locais no transporte de mercadorias da porta para o destino.

### <a name="tms-multi-leg-journey-features"></a>Recursos de percurso de vários trechos do TMS

No TMS, os roteiros podem ser divididos em segmentos de roteiro para representar viagens com vários trechos. O TMS pode alocar taxas à vista e encargos de acesso a segmentos de roteiro individuais.

Para obter mais informações, consulte [Planejar roteiros de transporte de fretes com várias paradas](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Recursos do percurso de vários trechos de custo de entrega

O custo de entrega fornece uma estrutura para mover mercadorias do ponto de origem para o destino por meio de uma série de trechos, que são as paradas ou as etapas em um percurso. Os trechos são combinados para criar modelos de percurso, que definem como as mercadorias são movidas do fornecedor para a organização.

Em cada trecho de um percurso, você pode definir ainda mais o status de cada linha de ordem de compra e os prazos de entrega associados a ele. O prazo de entrega combinado para todos os trechos é usado para identificar a data de entrega estimada. No entanto, o processamento de mercadorias em trânsito é necessário para que percursos com vários trechos se apliquem. A percurso de mercadorias em uma viagem é gerenciado em uma tabela específica do Custo de entrega.

## <a name="receiving-by-container"></a>Recebimento por contêiner

Pode ser importante gerenciar como as mercadorias são divididas e armazenadas em uma embarcação. Em uma embarcação, as mercadorias podem ser mantidas em um ou vários contêineres. Quando as mercadorias são recebidas, elas são recebidas em contêineres e diferentes contêineres em uma viagem podem ser recebidos em horários diferentes ou em datas diferentes.

O TMS e o Custo de entrega fornecem funcionalidade para gerenciar o recebimento de mercadorias em um contêiner. O TMS usa o conceito de cargas para gerenciar as mercadorias, as ordens de compra e as ordens de transferência associadas a um contêiner de remessa. O TMS oferece suporte ao recebimento com base em uma estrutura de embalagem recebida por meio de um aviso de remessa antecipada (ASN). O Custo de entrega usa o conceito de contêineres de remessa para processar ordens de compra e controlar custos gerais indiretos que estão associados a um contêiner em uma embarcação.

### <a name="tms-receiving-by-container-features"></a>Recursos do recebimento do TMS por contêiner

O TMS oferece suporte a ASNs de entrada, a todas as grades de recebimento por meio do aplicativo móvel do Gerenciamento de Depósito e a todos os métodos de recebimento pelo cliente do Supply Chain Management.

### <a name="landed-cost-receiving-by-container-features"></a>Recursos do recebimento de Custo de entrega por contêiner

Para dar suporte ao recebimento por contêiner, o Custo de entrega cria registros de contêiner de remessa e associa ordens de compra a um contêiner de remessa específico usando a ID de contêiner. Os custos gerais indiretos podem ser aplicados a esse contêiner de remessa e divididos para que sejam associados às ordens de compra relevantes.

Os contêineres no Custo de entrega podem ser recebidos por meio de um novo tipo de recibo conhecido como *recebimento de mercadorias em trânsito*, por meio de diários de entrada ou por recebimento de dispositivo móvel. Quando são usados diários de entrada, as quantidades podem ser inicializadas a partir da ordem de mercadorias em trânsito ou das linhas da ordem de compra original no contêiner. O custo de entrega fornece dois tipos de trabalho para recebimento por meio do aplicativo móvel do Gerenciamento de Depósito.

O Custo de entrega não fornece um ASN para o recebimento eletrônico de mercadorias. Além disso, não há suporte para fluxos de aplicativo móvel do Gerenciamento de Depósito que processam recebimento de carga, recebimento de placa de licença ou recebimento de placa de licença mista.

## <a name="rate-shopping-by-vendor"></a>Comparação de taxas por fornecedor

A comparação de taxas permite que uma empresa selecione um fornecedor de transporte com base no preço mais baixo, no roteiro mais rápido ou em uma combinação de ambas as considerações.

### <a name="tms-rate-shopping-features"></a>Recursos de comparação de taxas do TMS

O TMS permite que você identifique as soluções de fornecedor e de roteiro para ordens de entrada e de saída. Por exemplo, você pode identificar o roteiro mais rápido ou a taxa menos dispendiosa para uma remessa.

O TMS fornece otimização total de comparação de taxas e de fretes por meio da bancada do roteiro de taxa, opções de classificação flexíveis por meio do mecanismo de classificação, uma API de mecanismo de classificação para integração com parceiros externos e suporte a peso volumétrico.

Para obter mais informações, consulte [Mecanismos de gerenciamento de transporte](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Recursos de comparação de taxas de custo de entrega

O custo de entrega oferece apenas suporte limitado para comparação de taxas por fornecedor. Embora seja possível inserir valores do controlador de frete, o custo de entrega não os compara entre vários fornecedores.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Check-in/check-out de driver com agendamento de compromisso

Os recursos de check-in/check-out de driver permitem que o sistema monitore as entradas e evite o congestionamento nas docas de carga.

### <a name="tms-driver-check-incheck-out-features"></a>Recursos de check-in/check-out de driver do TMS

O TMS permite criar *compromissos*. Um compromisso representa eventos que ocorrem em uma doca para recebimento de uma ordem de compra, envio de uma ordem de venda ou processamento de uma carga de entrada ou de saída em uma data e uma hora específicas. Os compromissos garantem que as docas estejam disponíveis para carregar e descarregar mercadorias, além de ajudar a prevenir situações nas quais várias transportadoras chegam a um local ao mesmo tempo.

O sistema oferece suporte para permitir que os drivers façam check-in em uma porta de doca específica.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Recursos de check-in/check-out de driver do custo de entrega

O custo de entrega pode armazenar estimativas para a data e a hora em que um contêiner será entregue.

## <a name="transfer-orders-and-additional-costs"></a>Ordens de transferência e custos adicionais

Geralmente, as empresas devem poder transferir mercadorias entre depósitos. Quando esse tipo de transferência ocorre, os custos são associados a ele e talvez você queira reconhecer esses custos. No custo de entrega, as ordens de transferência podem ser adicionadas a uma viagem ou embarcação para rastrear a movimentação de mercadorias de um depósito ou site para outro, estimar o tempo de entrega e a data de entrega esperada e adicionar custos gerais indiretos à transferência de mercadorias.

### <a name="tms-transfer-order-cost-features"></a>Recursos de custo da ordem de transferência do TMS

O TMS oferece suporte à criação de encargos de frete que estão conectados a transferências. Embora esses encargos possam ser exibidos a partir da ordem de transferência, o custo de entrega não é adicionado ao custo do item. A reconciliação de frete tem suporte por meio da criação de uma conta de frete baseada nesses encargos. Essa conta de frete corresponde a uma fatura de frete do fornecedor.

### <a name="landed-cost-transfer-order-cost-features"></a>Recursos de custo da ordem de transferência de custo de entrega

O custo de entrega permite adicionar ordens de transferência a uma embarcação ou viagem. Dessa forma, você pode adicionar custos de remessa à viagem como liquidações de estoque no momento do recebimento da ordem de transferência. Os custos gerais indiretos podem ser faturados para os custos reais e controlados em relação a uma viagem para atualizar o custo das mercadorias vendidas. Embora as ordens de transferência não usem o processamento de mercadorias em trânsito na versão padrão, elas podem ser adicionadas às viagens. O custo de entrega é adicionado ao custo total de cada item.