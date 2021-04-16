---
title: Visão geral de organizações e hierarquias organizacionais
description: As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa.
author: sericks007
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efd34b01ab414b2282fd08d8d9329ae7f9a801ce
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747626"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>Visão geral de organizações e hierarquias organizacionais

[!include [banner](../includes/banner.md)]

Uma organização é um grupo da pessoas que está trabalhando em conjunto para realizar um processo comercial ou atingir uma meta. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa.

## <a name="organizations"></a>Organizações

Você pode definir os seguintes tipos de organizações internas: entidades legais, unidades operacionais e equipes.

Todas as organizações internas são tipos de entidades **participantes**. Portanto, essas organizações usam o catálogo de endereços para armazenar endereços e informações de contato. Um participante, que pode ser uma pessoa ou uma organização, pode pertencer a um ou mais catálogos de endereços.

### <a name="legal-entities"></a>Entidades legais

Uma entidade legal é uma organização que tem uma estrutura legal registrada ou legislada. As entidades legais podem participar de contratos legais e são obrigadas a preparar demonstrativos que registram seu desempenho.

Uma empresa é um tipo de entidade legal. Atualmente, empresas são o único tipo de entidade legal que você pode criar, e cada entidade legal está associada a uma ID de empresa. Essa associação existe porque todas as áreas funcionais do programa usam uma ID da empresa, ou IdÁreaDados, nos modelos de dados. Nessas áreas funcionais, as empresas são usadas como um limite para a segurança dos dados. Os usuários podem acessar somente os dados da empresa que estão conectados no momento.

### <a name="operating-units"></a>Unidades operacionais

Uma unidade operacional é uma organização usada para dividir o controle de recursos econômicos e os processos operacionais em uma empresa. As pessoas de uma unidade operacional têm um imposto para maximizar o uso de recursos escassos, melhorar os processos e a conta para o desempenho.

Os tipos de unidades operacionais incluem centros de custos, unidades de negócios, fluxos de valor, departamentos e canais de comércio. A tabela a seguir fornece mais informações sobre cada tipo de unidade operacional.

| Tipo de unidade operacional | descrição | Finalidade |
|---------------------|-------------|---------|
| Centro de custos         | Uma unidade operacional cujos gerentes são responsáveis pelas despesas orçadas e reais. | Usado para o gerenciamento e o controle operacional dos processos comerciais que englobam as entidades legais. |
| Unidade de negócios       | Uma unidade operacional semiautônoma criada para atender aos objetivos estratégicos de negócios. | Usado para relatórios financeiros baseados em setores ou nas linhas de produtos que a organização atua de forma independente das entidades legais. |
| Fluxo de valor        | Uma unidade operacional que controla um ou mais fluxos de produção. | Comumente usado em lean manufacturing para controlar as atividades e os fluxos necessários para fornecer um produto ou serviço para os consumidores. |
| Departamento          | Uma unidade operacional que representa uma categoria ou uma parte funcional de uma organização que execute uma tarefa específica, como vendas ou contabilidade. | Usado para registrar sobre as áreas funcionais. Um departamento pode ter a responsabilidade de lucros e perdas, e pode consistir de um grupo de centros de custo. |
| Canal do Commerce      | Uma unidade operacional que representa uma loja de tijolos e cimento, uma loja online ou um mercado online. | Usada para controle operacional e gerenciamento de uma ou mais lojas dentro das entidades legais ou por elas. |

### <a name="teams"></a>Times

Uma equipe é uma organização cujos membros compartilham uma responsabilidade, interesse ou objetivo comum. As equipes não podem ser usadas nas hierarquias organizacionais.

## <a name="organizational-hierarchies"></a>Hierarquias organizacionais

Configure as hierarquias organizacionais para exibir e fazer relatório da empresa sob perspectivas diferentes. Por exemplo, você pode configurar uma hierarquia de entidades legais para relatórios de impostos, legais ou estatutários. Configure uma hierarquia com base em unidades operacionais para relatar informações financeiras que não são necessárias legalmente, mas que são usadas para o controle interno. Por exemplo, é possível criar uma hierarquia de compra para controlar as diretivas de compras, regras e processos comerciais.

A cada hierarquia é atribuída uma finalidade. A finalidade de uma hierarquia determina os tipos de organizações que podem ser incluídos na hierarquia. A finalidade também define os cenários de aplicativo nos quais a hierarquia pode ser usada.

As organizações em uma hierarquia podem compartilhar parâmetros, políticas e transações. Uma organização pode herdar ou substituir os parâmetros de sua organização primária. No entanto, os dados mestres compartilhados, como produtos e catálogos de endereços, aplicam-se à organização inteira e não podem ser substituídos para organizações individuais. A criação de organizações e hierarquias exigem planejamento cuidadoso. Para obter mais informações, consulte [Planejar sua hierarquia organizacional](plan-organizational-hierarchy.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]