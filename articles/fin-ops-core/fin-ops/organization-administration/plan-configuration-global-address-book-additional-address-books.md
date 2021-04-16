---
title: Plano para o catálogo de endereços global e outros catálogos de endereços
description: Este tópico descreve as considerações e as decisões que você deve tomar durante o processo de planejamento.
author: msftbrking
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1d3a476a183453f170dae9b812949822ea60edd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747600"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Plano do catálogo de endereços global e outros catálogos de endereços

[!include [banner](../includes/banner.md)]

Este tópico descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de definir e configurar o catálogo de endereços global e todos os catálogos de endereços adicionais. Algumas das alterações exigem que você confirme as alterações que foram feitas para outras áreas do produto, como a hierarquia organizacional.

## <a name="global-address-book"></a>Catálogo de endereços global

Antes de começar a trabalhar com o catálogo de endereços global, você deve determinar os valores padrão para ele. Os valores padrão são usado para todos os catálogos de endereços adicionais que você criar.

**Decisões**

- Em que sequência os nomes que devem ser exibidos para os registros de participante do tipo **Pessoa**? Por exemplo, uma sequência é: último nome, nome do meio, e primeiro nome.
- Os registros de participante devem ser excluídos do catálogo de endereços quando a função de registro for excluída? Por exemplo, se um registro de cliente for excluído, o registro de participante também deve ser excluído?
- Quando um novo registro é criado, os usuários devem ser notificados se um registro duplicado for encontrado no catálogo de endereços global?
- O número do sistema de numeração universal de dados (DUNS) deve ser incluído nas informações de registro de um participante?
- Se o número de DUNS for incluído em um registro de participante, a exclusividade do número deve ser verificada?
- Quando um registro de participante é criado no catálogo de endereços global, você deseja que ele seja um tipo de participante padrão, de pessoa, ou de organização?
- Quais funções de usuário devem ter acesso aos endereços particulares e informações de contato dos registros de participante?

## <a name="additional-address-books"></a>Catálogos de endereços adicionais

Após criar o catálogo de endereços global, você pode criar catálogos de endereço adicionais conforme necessário, como um catálogo de endereço separado para cada empresa em sua organização ou para cada linha de negócios. Por exemplo, a Fabrikam é uma organização internacional com várias empresas e várias linhas de negócios. Ela planeja criar um catálogo de endereços para cada linha de negócios. Para linhas de negócios que ocorrem em mais de um local, como a empresa de ferramentas pneumáticas, a Fabrikam planeja criar um catálogo de endereços para cada local. Chris, gerente de TI na Fabrikam, criou a seguinte lista de catálogos de endereços que são necessários. Esta lista também descreve os registros de participante que cada catálogo de endereços deve incluir.

- **Contratos do Setor Público (PubSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor público que são mantidos pela Fabrikam.
- **Contratos do Setor Privado (PriSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor privado que são mantidos pela Fabrikam.
- **Ferramentas Eletrônicas (ET)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas eletrônicas, ou que interagem de alguma forma com ferramentas eletrônicas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.
- **Ferramentas Pneumáticas (PTJPN)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.
- **Ferramentas Pneumáticas (PTUSA)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa dos EUA.

**Decisão:**

- Quantos catálogos de endereços adicionais serão criados?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]