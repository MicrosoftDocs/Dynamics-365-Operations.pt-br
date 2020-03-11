---
title: Visão geral de gravação dupla
description: Este tópico fornece uma visão geral de gravação dupla. A gravação dupla é uma infraestrutura que fornece interação quase em tempo real entre aplicativos baseados em modelo do Microsoft Dynamics 365 e aplicativos do Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075970"
---
# <a name="dual-write-overview"></a>Visão geral de gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a>O que é gravação dupla?

A gravação dupla é uma infraestrutura pronta para uso que fornece interação quase em tempo real entre aplicativos baseados em modelo no Microsoft Dynamics 365 e aplicativos do Finance and Operations. Quando dados sobre clientes, produtos, pessoas e operações fluem além dos limites dos aplicativos, todos os departamentos de uma organização são capacitados.

A gravação dupla fornece integração bidirecional extremamente interligada entre aplicativos do Finance and Operations e Common Data Service. Qualquer alteração de dados nos aplicativos do Finance and Operations causa gravações no Common Data Service e qualquer alteração de dados no Common Data Service causa gravações nos aplicativos do Finance and Operations. Esse fluxo de dados automatizado fornece uma experiência de usuário integrada nos aplicativos.

![Relação de dados entre aplicativos](media/dual-write-overview.jpg)

A gravação dupla tem dois aspectos: um *infraestrutura* e um *aplicativo*.

### <a name="infrastructure"></a>Infraestrutura

A infraestrutura de gravação dupla é extensível e confiável e inclui os seguintes recursos principais:

+ Fluxo de dados síncrono e bidirecional entre aplicativos
+ Sincronização, juntamente com os modos de reprodução, pausa e recuperação para oferecer suporte ao sistema durante os modos online e offline/assíncrono.
+ Capacidade de sincronizar dados iniciais entre os aplicativos
+ Visualização consolidada de logs de atividades e erros para administradores de dados
+ Capacidade de configurar alertas e limites personalizados e assinar notificações
+ Interface de usuário (UI) intuitiva para filtragem e transformações
+ Capacidade de definir e exibir dependências e relacionamentos da entidade
+ Extensibilidade para mapas e entidades padrão e personalizadas
+ Gerenciamento confiável do ciclo de vida de aplicativos
+ Experiência de configuração pronta para uso para novos clientes

### <a name="application"></a>Solicitação de Emprego

A gravação dupla cria um mapeamento entre conceitos em aplicativos do Finance and Operations e conceitos em aplicativos baseados em modelo no Dynamics 365. Essa integração é compatível com os seguintes cenários:

+ Cliente mestre integrado
+ Acesso a cartões de fidelização de clientes e pontos de recompensa
+ Experiência unificada de controle de produtos
+ Consciência da hierarquia da organização
+ Fornecedor mestre integrado
+ Acesso a dados de referência financeira e tributária
+ Experiência de mecanismo de definição de preços sob demanda
+ Experiência integrada de pagamento à vista
+ Capacidade de atender ativos internos e clientes por meio de agentes de campo
+ Experiência integrada de compra ao pagamento
+ Atividades e notas integradas para dados e documentos do cliente
+ Capacidade de procurar disponibilidade e detalhes de estoque disponíveis
+ Experiência de projeto com pagamento à vista
+ Capacidade de lidar com vários endereços e funções por meio do conceito de participante
+ Gerenciamento de fonte única para usuários
+ Canais integrados de varejo e marketing
+ Visibilidade de promoções e descontos
+ Funções de solicitação de serviço
+ Operações de serviço simplificadas

## <a name="top-reasons-to-use-dual-write"></a>Principais motivos para usar a gravação dupla

A gravação dupla fornece integração de dados nos aplicativos do Microsoft Dynamics 365. Essa estrutura robusta vincula ambientes e permite que diferentes aplicativos comerciais trabalhem juntos. Aqui estão os principais motivos pelos quais você deve usar a gravação dupla:

+ A gravação dupla fornece integração bidirecional e extremamente interligada, em tempo quase real e bidirecional entre aplicativos do Finance and Operations e aplicativos baseados em modelo no Dynamics 365. Essa integração convertem o Microsoft Dynamics 365 no principal espaço para todas as suas soluções empresariais. Os clientes que usam o Dynamics 365 Finance e o Dynamics 365 Supply Chain Management, mas que usam soluções que não são da Microsoft para gerenciamento de relacionamento com o cliente (CRM), estão migrando para o Dynamics 365 para obter suporte para gravação dupla.
+ Os dados de clientes, produtos, operações, projetos e a Internet das Coisas (IoT) fluem automaticamente para o Common Data Service por meio de gravação dupla. Essa conexão é muito útil para empresas interessadas nas expansões do Microsoft Power Platform.
+ A infraestrutura de gravação dupla segue o princípio sem codificação/com pouca codificação. É necessário um esforço mínimo de engenharia para estender os mapas tabela a tabela padrão e incluir mapas personalizados.
+ A gravação dupla é compatível com os modos online e offline. A Microsoft é a única empresa que oferece suporte aos modos online e offline.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>O que a gravação dupla significa para usuários e arquitetos de produtos do CRM?

A gravação dupla automatiza o fluxo de dados entre os aplicativos do Finance and Operations e o Common Data Service. Em versões futuras, os conceitos em aplicativos baseados em modelo no Dynamics 365 (por exemplo, cliente, contato, cotação e ordem) serão dimensionados para clientes de mercados de classe média e média-superior.

Na primeira versão, a maior parte da automação é manipulada por soluções de gravação dupla. Em versões futuras, essas soluções se tornarão parte do Common Data Service. Ao entender as próximas alterações no Common Data Service, você pode poupar esforços em longo prazo. Veja algumas das mudanças cruciais:

+ O Common Data Service terá novos conceitos, como empresa e participante. Esses conceitos afetarão todos os aplicativos criados no Common Data Service, como Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service.
+ Atividades e notas são unificadas e expandidas para suportar C1s (usuários do sistema) e C2s (clientes do sistema).
+ Veja algumas das próximas mudanças no Common Data Service:

    - O tipo de dados decimal substituirá o tipo de dados monetários.
    - A efetividade da data oferecerá suporte a dados passados, presentes e futuros no mesmo local.
    - Haverá mais suporte para taxas de câmbio e moeda, e a interface de programação de aplicativos (API) **Taxa de Câmbio** será revisada.
    - Conversões de unidades serão compatíveis.

Para obter mais informações sobre as próximas alterações, consulte [Dados no Common Data Service – fase 1 e 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).
