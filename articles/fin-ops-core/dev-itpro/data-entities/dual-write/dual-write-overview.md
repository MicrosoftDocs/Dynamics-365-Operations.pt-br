---
title: Visão geral da gravação dupla
description: Este tópico traz uma visão geral da gravação dupla, que fornece interação quase em tempo real entre aplicativos do Customer Engagement e aplicativos do Finance and Operations.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 69abd2b6d4026ef1b5b85d52c561bb060cf82123
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781455"
---
# <a name="dual-write-overview"></a>Visão geral da gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a>O que é gravação dupla?

A gravação dupla é uma infraestrutura pronta para uso que fornece interação quase em tempo real entre aplicativos do Customer Engagement e aplicativos do Finance and Operations. Quando dados sobre clientes, produtos, pessoas e operações fluem além dos limites dos aplicativos, todos os departamentos de uma organização são capacitados.

A gravação dupla fornece integração bidirecional extremamente interligada entre aplicativos do Finance and Operations e Dataverse. Qualquer alteração de dados nos aplicativos do Finance and Operations causa gravações no Dataverse e qualquer alteração de dados no Dataverse causa gravações nos aplicativos do Finance and Operations. Esse fluxo de dados automatizado fornece uma experiência de usuário integrada nos aplicativos.

![Relação de dados entre aplicativos.](media/dual-write-overview.jpg)

A gravação dupla tem dois aspectos: um *infraestrutura* e um *aplicativo*.

### <a name="infrastructure"></a>Infraestrutura

A infraestrutura de gravação dupla é extensível e confiável e inclui os seguintes recursos principais:

+ Fluxo de dados síncrono e bidirecional entre aplicativos
+ Sincronização, juntamente com os modos de reprodução, pausa e recuperação para oferecer suporte ao sistema durante os modos online e offline/assíncrono.
+ Capacidade de sincronizar dados iniciais entre os aplicativos
+ Exibição combinada de logs de atividades e erros para administradores de dados
+ Capacidade de configurar alertas e limites personalizados e assinar notificações
+ Interface de usuário (UI) intuitiva para filtragem e transformações
+ Capacidade de definir e exibir dependências e relacionamentos da tabela
+ Extensibilidade para mapas e tabelas padrão e personalizadas
+ Gerenciamento confiável do ciclo de vida de aplicativos
+ Experiência de configuração pronta para uso para novos clientes

### <a name="application"></a>Solicitação de Emprego

A gravação dupla cria um mapeamento entre conceitos em aplicativos do Finance and Operations e conceitos em aplicativos do Customer Engagement. Essa integração é compatível com os seguintes cenários:

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

+ A gravação dupla fornece integração bidirecional e extremamente interligada, em tempo quase real e bidirecional entre aplicativos de finanças e operações e aplicativos de interação com o cliente. Essa integração convertem o Microsoft Dynamics 365 no principal espaço para todas as suas soluções empresariais. Os clientes que usam o Dynamics 365 Finance e o Dynamics 365 Supply Chain Management, mas que usam soluções que não são da Microsoft para gerenciamento de relacionamento com o cliente (CRM), estão migrando para o Dynamics 365 para obter suporte para gravação dupla.
+ Os dados de clientes, produtos, operações, projetos e a Internet das Coisas (IoT) fluem automaticamente para o Dataverse por meio de gravação dupla. Essa conexão é útil para empresas interessadas em expansões do Power Platform.
+ A infraestrutura de gravação dupla segue o princípio sem codificação/com pouca codificação. É necessário um esforço mínimo de engenharia para estender os mapas tabela a tabela padrão e incluir mapas personalizados.
+ A gravação dupla é compatível com os modos online e offline. A Microsoft é a única empresa que oferece suporte aos modos online e offline.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>O que significa a gravação dupla para desenvolvedores e arquitetos de aplicativos do Customer Engagement?

A gravação dupla automatiza o fluxo de dados entre aplicativos do Finance and Operations e aplicativos do Customer Engagement. A gravação dupla consiste em duas soluções AppSource instaladas no Dataverse. As soluções expandem o esquema da tabela, os plugins e os fluxos de trabalho no Dataverse para que possam ser escalados para o tamanho do ERP. Para uma implementação bem-sucedida, os desenvolvedores e arquitetos de aplicativos do Customer Engagement devem compreender essas alterações e colaborar com as contrapartes em aplicativos do Finance and Operations.

Para criar paridade com aplicativos do Finance and Operations, a gravação dupla faz algumas alterações cruciais no esquema do Dataverse. Se você entender o plano, poderá evitar retrabalho de design e desenvolvimento no futuro.

+ Quando o pacote de gravação dupla do AppSource for instalado, o Dataverse terá novos conceitos, como empresa e participante. Esses conceitos ajudam aplicativos criados no Dataverse, incluindo Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service, a interagir perfeitamente com aplicativos do Finance and Operations.

+ Atividades e notas são unificadas e expandidas para suportar C1s (usuários do sistema) e C2s (clientes do sistema).

+ Para evitar a perda de dados durante a transmissão de moeda entre aplicativos do Finance and Operations e o Dataverse, você poderá estender o número de casas decimais no tipo de dados de moeda de aplicativos do Customer Engagement. O recurso converte automaticamente as linhas existentes no novo estado estendido na camada de metadados. Durante esse processo, o valor da moeda é convertido em dados decimais em vez de dados monetários, e o valor da moeda oferece suporte a 10 casas decimais. Este recurso é opcional e apenas organizações que requeiram acima de 4 casas decimais de precisão deverão aceitá-lo. Para obter mais informações, consulte [Migração de tipo de dados de moeda para gravação dupla](currrency-decimal-places.md).

+ [Efetividade de data](../../dev-tools/date-effectivity.md) será adicionada ao Dataverse. Ela dará suporte a dados passados, presentes e futuros na mesma tabela.

+ As [conversões de unidades](../../../../supply-chain/pim/tasks/manage-unit-measure.md) de produto têm suporte para produtos, cotações, ordens e faturas.

Para obter mais informações sobre as alterações futuras, consulte [Novidades ou alterações em gravação dupla](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]