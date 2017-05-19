---
title: "Organizações e hierarquias da organização (fundamentos de comércio)"
description: "Os fundamentos do comércio têm três tipos de organizações internas que você pode definir para ajudar uma organização a atingir um processo comercial ou a atingir uma meta."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 50d29b6552cf7af5f2d9296b1d70b838a8edd637
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organizações e hierarquias da organização (fundamentos de comércio)

[!include[banner](includes/banner.md)]


Os fundamentos do comércio têm três tipos de organizações internas que você pode definir para ajudar uma organização a atingir um processo comercial ou a atingir uma meta. 

Uma organização é um grupo da pessoas que trabalha em conjunto para realizar um processo comercial ou para atingir uma meta. Uma hierarquia organizacional representa os relacionamentos entre as unidades de negócios que compõem sua organização.

## <a name="organizations"></a>Organizações
Em Fundamentos comerciais, é possível definir três tipos de organizações internas: entidade legal, unidades operacionais e equipes. No Microsoft Dynamics AX, todas as organizações internas são tipos da entidade Participante. Portanto, essas organizações usam um catálogo de endereços para armazenar endereços e outras informações de contato. Um participante, que pode ser uma pessoa ou uma organização, pode pertencer a um ou mais catálogos de endereços.
### <a name="legal-entities"></a>Entidades legais

Uma entidade legal é uma organização que tem uma estrutura legal registrada ou legislada. As entidades legais podem participar de contratos legais e são obrigadas a preparar demonstrativos que registram seu desempenho. A empresa é um tipo de entidade legal no Microsoft Dynamics AX e cada entidade legal está associada a uma ID da empresa. Essa associação existe porque uma ID da empresa, ou DataAreaId, é usada em alguns modelos de dados em que as empresas são usadas como um limite de segurança de dados. Os usuários podem acessar somente os dados da empresa que estão conectados no momento.

### <a name="operating-units"></a>Unidades operacionais

Uma unidade operacional é uma organização usada para dividir o controle de recursos econômicos e os processos operacionais em uma empresa. As pessoas de uma unidade operacional têm um imposto para maximizar o uso de recursos escassos, melhorar os processos e a conta para o desempenho. Em Fundamentos comerciais, os tipos de unidades operacionais incluem centros de custos, unidades de negócios, fluxos de valor, departamentos e canais de varejo. A tabela a seguir fornece mais informações sobre cada tipo de unidade operacional.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo de unidade operacional** | **Descrição**                                                                         | **Finalidade**                                                                                                                                 |
| Unidade de negócios           | Uma unidade operacional semiautônoma criada para atender aos objetivos estratégicos de negócios. | Use unidades de negócios para relatórios financeiros baseados em setores ou em linhas de produtos que a organização atua nas entidades legais. |
| Canal de varejo          | Uma unidade operacional que representa uma loja tradicional.                             | Use para gerenciar e controlar uma ou mais lojas nas entidades legais ou entre elas.                                                               |

## <a name="organizational-hierarchies"></a>Hierarquias organizacionais
Em Fundamentos comerciais, cada hierarquia obtém uma finalidade. A finalidade de uma hierarquia determina os tipos de organizações que podem ser incluídos na hierarquia. A finalidade também define os cenários de aplicativo nos quais a hierarquia pode ser usada. Por exemplo, uma hierarquia de varejo pode ser usada para comprar e vender produtos em uma loja. As organizações em uma hierarquia podem compartilhar parâmetros, políticas e transações. Uma organização pode herdar ou substituir os parâmetros de sua organização pai. No entanto, os dados mestres compartilhados, como produtos e catálogos de endereços, aplicam-se à organização inteira e não podem ser substituídos para organizações individuais.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Práticas recomendadas para configurar uma organização em uma hierarquia

Considere estas práticas recomendadas quando implementar uma hierarquia organizacional:
-   Crie um departamento para especificar a interseção entre uma entidade legal e uma unidade de negócios. Você poderá então acumular dados de um departamento para uma entidade legal para relatório estatutário, e de um departamento para uma unidade de negócios para relatório interno.
-   Em uma única entidade legal, não configure várias hierarquias para a mesma finalidade de hierarquia.
-   Não crie uma hierarquia para cada finalidade. Geralmente, você pode usar uma hierarquia para várias finalidades. Por exemplo, uma hierarquia de unidades operacionais pode ser atribuída a todas as finalidades relacionadas a políticas.
-   Crie hierarquias equilibradas. Em uma hierarquia, todos os nós que estão à mesma distância do nó raiz são definidos como um nível. Em uma hierarquia equilibrada, somente um tipo de unidade operacional pode ocorrer em cada nível, e a distância do nó raiz a cada nível é consistente. Se houver níveis intermediários entre um departamento e uma entidade legal ou uma unidade de negócios, as organizações do espaço reservado podem precisar criar uma hierarquia equilibrada.
-   Não configure uma hierarquia diferente de unidades operacionais se a estrutura das entidades legais também for sua estrutura organizacional. Uma hierarquia misturada da entidades legais e unidades operacionais pode servir às duas finalidades.
-   Antes que você configure grandes cenários de reestruturação, use as datas efetivas da hierarquia para realizar uma análise de impacto e um teste de validação.
-   Salve uma hierarquia como um rascunho caso haja a possibilidade de alterar uma hierarquia antes de publicá-la.
-   Limite o número de pessoas que têm permissões para adicionar ou remover organizações de uma hierarquia em um ambiente de produção. Um número menor reduz a chance de ocorrência de erros e a necessidade de correções.

## <a name="retail-store-management"></a>Gerenciamento de loja de Varejo
A tabela a seguir descreve os cenários de Fundamentos comerciais em que as hierarquias organizacionais podem ser usadas.
| Tarefa                                                                           | Descrição                                                                                                                                                                                                                                                                                                | Finalidade da hierarquia    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Gerenciar sortimentos de varejo                                                      | Identifique os produtos disponíveis em cada loja de varejo.                                                                                                                                                                                                                                             | Sortimento de varejo    |
| Gerenciar o reabastecimento de varejo                                                    | Agrupar as lojas para reabastecer o estoque com base nas regras de reabastecimento.                                                                                                                                                                                                                                          | Reabastecimento de varejo |
| Relatar dados para as lojas                                                         | Agrupar lojas para a geração de relatórios.                                                                                                                                                                                                                                                                                | Relatório de varejo     |
| Lançar estoque, calcular demonstrativos, ou lançar demonstrativos para um grupo de lojas | Criar um grupo de lojas que podem ser atribuídas a um trabalho em lotes. Ao definir um trabalho em lotes para lançar estoque, calcular demonstrativos, ou lançar demonstrativos, é possível especificar a hierarquia à qual o trabalho se aplica. Quando as lojas são adicionados ou removidos da hierarquia, não é necessário alterar o trabalho em lotes. | Lançamento do Retail POS   |






