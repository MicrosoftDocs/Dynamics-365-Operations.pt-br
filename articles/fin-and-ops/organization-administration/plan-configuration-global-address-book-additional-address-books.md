---
title: "Plano para configuração do catálogo de endereços global e dos catálogos de endereços adicionais"
description: "Este tópico descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de definir e configurar o catálogo de endereços global e todos os catálogos de endereços adicionais no Microsoft Dynamics 365 for Finance and Operations. Algumas das alterações exigem que você confirme as alterações que foram feitas para outras áreas do produto, como a hierarquia organizacional."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b872603f987b72faacc0a987aa44c31e773636f8
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="plan-how-to-configure-the-global-address-book-and-additional-address-books"></a>Plano para configuração do catálogo de endereços global e dos catálogos de endereços adicionais

[!INCLUDE [banner](../includes/banner.md)]

Este tópico descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de definir e configurar o catálogo de endereços global e todos os catálogos de endereços adicionais no Microsoft Dynamics 365 for Finance and Operations. Algumas das alterações exigem que você confirme as alterações que foram feitas para outras áreas do produto, como a hierarquia organizacional.

<a name="global-address-book"></a>Catálogo de endereços global
-------------------

Antes de começar a trabalhar com o catálogo de endereços global, você deve determinar os valores padrão para ele. Os valores padrão são usado para todos os catálogos de endereços adicionais que você criar. 

**Decisões:**

-   Em que sequência os nomes que devem ser exibidos para os registros de participante do tipo **Pessoa**? Por exemplo, uma sequência é: último nome, nome do meio, e primeiro nome.
-   Os registros de participante devem ser excluídos do catálogo de endereços quando a função de registro for excluída? Por exemplo, se um registro de cliente for excluído, o registro de participante também deve ser excluído?
-   Quando um novo registro é criado, os usuários devem ser notificados se um registro duplicado for encontrado no catálogo de endereços global?
-   O número universal do sistema de numeração (DUNS) dos dados deve ser incluído nas informações de registro de um participante?
-   Se o número de DUNS for incluído em um registro de participante, a exclusividade do número deve ser verificada?
-   Quando um registro de participante é criado no catálogo de endereços global, você deseja que ele seja um tipo de participante padrão, de pessoa, ou de organização?
-   Quais funções de usuário devem ter acesso aos endereços particulares e informações de contato dos registros de participante?

## <a name="additional-address-books"></a>Catálogos de endereços adicionais
Após criar o catálogo de endereços global, você pode criar catálogos de endereço adicionais conforme necessário, como um catálogo de endereço separado para cada empresa em sua organização ou para cada linha de negócios. Por exemplo, a Fabrikam é uma organização internacional com várias empresas e várias linhas de negócios. Ela planeja criar um catálogo de endereços para cada linha de negócios. Para linhas de negócios que ocorrem em mais de um local, como a empresa de ferramentas pneumáticas, a Fabrikam planeja criar um catálogo de endereços para cada local. Chris, gerente de TI na Fabrikam, criou a seguinte lista de catálogos de endereços que são necessários. Esta lista também descreve os registros de participante que cada catálogo de endereços deve incluir.

-   **Contratos do Setor Público (PubSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor público que são mantidos pela Fabrikam.
-   **Contratos do Setor Privado (PriSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor privado que são mantidos pela Fabrikam.
-   **Ferramentas Eletrônicas (ET)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas eletrônicas, ou que interagem de alguma forma com ferramentas eletrônicas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.
-   **Ferramentas Pneumáticas (PTJPN)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.
-   **Ferramentas Pneumáticas (PTUSA)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa dos EUA.

**Decisão:**

-   Quantos catálogos de endereços adicionais serão criados?

### <a name="address-book-security"></a>Segurança do catálogo de endereços

Você pode criar catálogos de endereços a qualquer momento, e também poderá definir parâmetros de segurança para eles sempre que desejar. Não é necessário definir privilégios de segurança para um catálogo de endereços, mas se não o fizer, todos os funcionários da organização poderão visualizar todos os registros de participante no catálogo de endereços. Você pode definir privilégios de segurança para registros de participante no catálogo de endereços. Os privilégios de segurança são baseados em equipes. Esta abordagem garante que somente os trabalhadores de uma equipe com acesso a um catálogo de endereços podem visualizar os registros de participante nesse catálogo de endereços. Você deve selecionar as equipes que têm acesso a cada catálogo de endereços. Para cada catálogo de endereços, você pode definir os privilégios de segurança que permitem ou negam o acesso a equipes específicas. Se você conceder a uma equipe privilégios a um catálogo de endereços, todos os membros da equipe poderão visualizar os registros do catálogo de endereços. Se você não conceder a uma equipe acesso a um catálogo de endereços, os membros dessa equipe não poderão visualizar o catálogo de endereços nem seu conteúdo. 

**Decisão:**

-   Quais equipes devem ter acesso a todos os novos catálogo de endereços que serão criados?





