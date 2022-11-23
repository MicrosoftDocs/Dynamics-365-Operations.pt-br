---
title: Visão geral do Suplemento Inventory Visibility
description: Este artigo explica o que é Visibilidade de Estoque e descreve seus recursos.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762798"
---
# <a name="inventory-visibility-add-in-overview"></a>Visão geral do Suplemento Visibilidade de Estoque

[!include [banner](../includes/banner.md)]

O Suplemento Visibilidade de Estoque (também referido como *serviço de Visibilidade de Estoque*) oferece um microsserviço independente e altamente escalável que permite os lançamentos de alterações de estoque disponível em tempo real e o controle de visibilidade em todas as suas fontes de dados e canais. Ele fornece uma plataforma que permite gerenciar o seu estoque global usando uma funcionalidade que inclui (mas não se limitando a) a lista a seguir:

- Controlar centralmente o status de estoque mais recente (por exemplo, disponível, encomendado, comprado, em trânsito, devolvido e em quarentena) em todas as suas fontes de dados, depósitos e locais ao conectar seu Supply Chain Management ou fontes de dados de logística de terceiros (como sistemas de gerenciamento de ordens, planejamento de recursos corporativos de terceiros \[ERP\], sistemas de ponto de venda \[PDV\] e sistemas de gerenciamento de depósito) ao serviço de visibilidade do estoque.
- Consulte a disponibilidade e escassez de estoque disponível e obtenha respostas imediatas chamando diretamente ao serviço de visibilidade de estoque.
- Evite a venda a mais, especialmente quando a demanda vier de diferentes canais, fazendo reservas em tempo real no serviço de Visibilidade de Estoque.
- Gerencie melhor as ordens prometidas e as expectativas dos clientes fornecendo datas atuais ou próximas disponíveis precisas, para que o recurso do omnicanal disponível para promessa (ATP) possa calcular as datas esperadas de atendimento da ordem.

## <a name="extensibility"></a>Extensibilidade

O serviço de Visibilidade de Estoque é altamente extensível porque a entrada e a saída de dados não estão restritas a aplicativos do Microsoft. Os sistemas externos podem acessar o serviço por meio de APIs (interfaces de programação de aplicativo) de RESTful. Além de usar os mapeamentos prontos para uso fornecidos para a fonte de dados e as dimensões do Supply Chain Management, você pode integrar a Visibilidade de Estoque a vários sistemas de terceiros configurando fontes de dados adicionais, os status de estoque medem (chamadas de *medidas físicas* no serviço de Visibilidade de Estoque) e dimensões de estoque via aplicativo de configuração. Dessa forma, você pode fazer uma consulta flexível e alterar suas várias fontes de dados e dimensões de estoque predefinidas.

Além disso, como a Visibilidade de Estoque é criada no Microsoft Dataverse, seus dados podem ser usados para criar e integrar com o Power Apps. Você também pode usar o Power BI para criar painéis personalizados que atendam a seus requisitos de negócios.

## <a name="scalability"></a>Escalabilidade

O serviço de Visibilidade de Estoque pode ser ajustado para cima ou para baixo, dependendo do volume de dados. A experiência de escalabilidade é praticamente perfeita e é conduzida pela equipe da plataforma Microsoft, com base na detecção e avaliação automáticas do volume de dados de transações.

A ilustração a seguir mostra a arquitetura de Visibilidade de Estoque.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title="Arquitetura de Visibilidade de Estoque" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>Destaques do recurso

### <a name="get-a-global-view-of-real-time-inventory"></a>Obter uma exibição de estoque em tempo real

A Visibilidade do Estoque garante que você tenha acesso às quantidades de estoque mais atualizadas em todas as horas, em todos os canais, locais e depósitos. Você se beneficiará mais ao usá-la para apoiar seus negócios operacionais diários sempre que precisar obter registros de estoque. O estoque físico disponível, as quantidades vendidas e as quantidades compradas estão todas disponíveis de imediato. Você também pode configurar outras medidas de estoque físico (como retorno, quarentena e dados lançados) conforme necessário, para obter esses detalhes em tempo real. A Visibilidade do Estoque pode processar eficientemente milhões de postagens de alterações de estoque. Esses dados podem ser agregados e refletidos nas últimas quantidades de estoque no serviço imediatamente, por segundo ou por minuto, dependendo do intervalo em que os dados são lançados. Para obter mais informações, consulte [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Ajuste de estoque central

A Visibilidade de Estoque permite que os sistemas externos chamem sua API para lançar alterações de estoque. As alterações entrarão em vigor imediatamente na Visibilidade de Estoque. Portanto, o estoque físico é deduzido instantaneamente.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Reserva flexível para evitar a venda em todos os canais de ordem

Uma *reserva flexível* permite que você atribua ou sinalize quantidades específicas para preencher uma ordem ou demanda. Uma reserva temporária não afeta o estoque físico, mas deduz da quantidade de estoque *disponível para reserva* e fornece uma quantidade atualizada para atendimento de ordens futuras. Esse recurso será útil se as solicitações de venda ou ordens forem feitas na sua empresa a partir de um ou mais canais ou fontes de dados que estão fora do sistema de registro de recursos empresariais (ERP).

Se você não usar reservas flexíveis no serviço de Visibilidade de Estoque, você deve aguardar até que a ordem seja sincronizada e processada pelo sistema ERP para obter uma atualização de quantidade de estoque físico. Esse processo normalmente tem grande latência. No entanto, as reservas flexíveis terão efeito imediato toda vez que uma solicitação ou ordem de venda for gerada nos canais de venda. Portanto, elas ajudam a prevenir situações de venda a mais garantindo que suas ordens de omnicanal não interfiram entre si quando chegarem ao sistema ERP. As reservas flexíveis também garantem que você possa atender a todas as ordens que você prometeu. Portanto, elas ajudam a atender a expectativas do cliente e a manter a lealdade do cliente. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Resposta imediata de quantidade e datas de ATP

A visibilidade do estoque projetada futura (incluindo o fornecimento, a demanda e os detalhes disponíveis projetados) é importante, pois ajuda sua empresa a atingir os seguintes objetivos:

- Minimizar os níveis de estoque para reduzir os custos de gerenciamento de estoque.
- Facilitar o processamento interno de ordens, para que os vendedores possam calcular as datas de remessa e entrega, com base na disponibilidade dos produtos pedidos.
- Fornecer transparência sobre quando os clientes podem esperar que um item de indisponibilidade de estoque fique disponível, fornecendo a próxima data disponível.

O recurso ATP é fácil de adotar no seu processo diário de preenchimento de ordens. O mais importante, como outras ofertas de Visibilidade de Estoque, o recurso ATP é *global e em tempo real*. Portanto, você pode configurar várias fórmulas de cálculo de ATP para ter consultas de disponibilidade de estoque completo que abranjam todos os canais de negócios e fontes de dados. Para obter mais informações, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>Pré-aloque seu estoque para canais importantes ou clientes com a Alocação de Estoque

O recurso de alocação da Visibilidade de Estoque permite a você proteger seu valioso estoque disponível para canais importantes, grupos de clientes ou locais. Depois que o estoque é alocado, o consumo do estoque é restrito ao pool alocado, e as quantidades restantes no pool são deduzidas em tempo quase real para refletir a quantidade que ainda está disponível para consumo. Para obter mais informações, consulte [Alocação de estoque de visibilidade do estoque](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Compatibilidade com itens do WMS

A Microsoft pretende fornecer integração pronta com os processos de gerenciamento de depósito (WMS), de forma que os clientes de WMS também possam desfrutar das vantagens do serviço de Visibilidade de Estoque. De acordo com a versão 2022 do Wave 1 (demonstração pública em março), o serviço de estoque oferece suporte a consultas disponíveis do item de WMS e ATP. O recurso de reserva e alocação flexível terá suporte para clientes de WMS no próximo ciclo. Para obter mais informações, consulte [Suporte do Visibilidade de Estoque para itens WMS](inventory-visibility-whs-support.md).

A ilustração a seguir mostra um resumo de alto nível dos recursos existentes e como eles podem ser posicionados no fluxo de dados.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title="Visão geral do recurso Visibilidade de Estoque" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Licenciamento

O serviço de Visibilidade de Estoque está disponível nas seguintes versões:

- **Suplemento de Visibilidade de Estoque para o Microsoft Dynamics 365 Supply Chain Management** – para as empresas que têm uma licença do Supply Chain Management válida, a Visibilidade do Estoque está disponível sem custo extra. Como a Visibilidade de Estoque se baseia no Microsoft Power Platform, ela está sujeita à capacidade de armazenamento e aos limites de API do Microsoft Power Platform. A licença do Supply Chain Management deve incluir capacidade padrão de armazenamento e API. Se você precisar de mais capacidade de armazenamento e API, poderá adquirir uma licença profissional. Para obter detalhes sobre a alocação de API padrão e a licença profissional, consulte [Limites de solicitação e alocações ](/power-platform/admin/api-request-limits-allocations)e [Visão geral de licenciamento para o Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Com as alocações padrão de armazenamento e API, você pode começar a experimentar o suplemento de Visibilidade de Estoque hoje mesmo. Para obter detalhes de instalação, consulte [Instalar e configurar a Visibilidade do Estoque](inventory-visibility-setup.md). Se a API e o uso de armazenamento estimados excederem a alocação padrão, você poderá contatar seu representante de vendas e pedir que ele contate a equipe da plataforma para obter uma exceção.
- **Serviço de Visibilidade de Estoque como um componente de IOM** – Esta versão é para clientes do Intelligent Order Management (IOM) ou empresas que não estão usando o Supply Chain Management como seu sistema ERP. A licença está incluída no pacote Intelligent Order Management. Para obter mais informações, consulte [Visão geral do Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>Terminologia da Visibilidade de Estoque

É importante entender os seguintes conceitos e condições quando estiver trabalhando com o suplemento de Visibilidade de Estoque:

- **Fonte de dados** - representa o sistema de onde vêm seus dados.
- **Dimensões** – identificam as características do produto. Podem ser dimensões de armazenamento (como site ou depósito) ou dimensões de produtos (como cor, tamanho ou estilo).
- **Medidas físicas** – são quantidades que medem diferentes status de estoque, como disponível, comprado, em ordem ou vendido.
- **Medidas calculadas** – são medidas quantitativas calculadas a partir de um conjunto de medidas físicas. Por exemplo, a medida calculada *Total disponível* é calculada conforme *Física* + *Comprada* – *Em ordem* – *Vendida*.
- **Partição** – define uma hierarquia para a forma como a visibilidade de estoque distribuirá os dados recebidos. No momento, a partição padrão é site e local.
- **Hierarquia de índices** – define ainda mais a forma como você deseja consultar o estoque e obter resultados que tenham mais granularidade.

Para obter mais informações sobre esses termos e conceitos, consulte [Configurar a Visibilidade de Estoque](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
