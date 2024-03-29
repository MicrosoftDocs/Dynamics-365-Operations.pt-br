---
title: Home page de administração da organização
description: Este artigo aponta para recursos que ajudarão você na sua organização.
author: sericks007
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "20421"
- intro-internal
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6d4320fb22f0354b33b44e731d22f3f763789ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882039"
---
# <a name="organization-administration-home-page"></a>Home page de administração da organização

[!include [banner](../includes/banner.md)]

Este artigo aponta para conteúdo que ajudará usuários avançados e administradores a configurar o sistema para trabalhar de forma suave e eficaz para sua organização e seus negócios.

A maior parte do conteúdo listado aqui se aplica aos recursos no módulo **Administração da organização**. Porém, há várias tarefas, como criar e usar um modelo de registro, que podem ser executadas em qualquer módulo para ajudar sua organização a atuar de forma mais eficiente.

## <a name="number-sequences"></a>Sequências numéricas

As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores. Um registro de dados mestres ou um registro de transação que exige um identificador é conhecido como *referência*. Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência.

- [Visão geral de sequências numéricas](number-sequence-overview.md)
- [Configurar sequências numéricas usando um assistente](tasks/set-up-number-sequences-wizard.md) (Guia de tarefas)
- [Configurar sequências numéricas em uma base individual](tasks/set-up-number-sequences-individual-basis.md) (Guia de tarefas)

## <a name="organizations"></a>Organizações

Uma organização é um grupo da pessoas que está trabalhando em conjunto para realizar um processo comercial ou atingir uma meta. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa.

Antes de configurar organizações e hierarquias organizacionais, certifique-se de planejar a forma como sua empresa será modelada. O modelo da organização tem um efeito significativo sobre a implementação e os processos comerciais.

- [Visão geral de organizações e hierarquias organizacionais](organizations-organizational-hierarchies.md)
- [Planejar sua hierarquia da organização](plan-organizational-hierarchy.md)
- [Criar uma hierarquia da organização](tasks/create-organization-hierarchy.md) (Guia de tarefas)
- [Criar uma entidade legal](tasks/create-legal-entity.md) (Guia de tarefas)
- [Criar uma unidade operacional](tasks/create-operating-unit.md) (Guia de tarefas)

## <a name="address-books"></a>Catálogos de endereços

O catálogo de endereços global é um repositório centralizado para os dados mestres que deve ser armazenado para todas as pessoas e organizações internas e externas que interagem com a empresa. Os dados associados aos registros do participantes incluem o nome, endereço e informações de contato do participante.

Após criar o catálogo de endereços global, você pode criar catálogos de endereço adicionais conforme necessário, como um catálogo de endereço separado para cada empresa em sua organização ou para cada linha de negócios.

- [Visão geral do catálogo de endereços global](overview-global-address-book.md)
- [Plano do catálogo de endereços global e outros catálogos de endereços](plan-configuration-global-address-book-additional-address-books.md)
- [Configurar o catálogo de endereços global](tasks/configure-global-address-book.md)
- [Perguntas frequentes sobre catálogos de endereços](qa-address-books.md)

## <a name="workflow"></a>Fluxo de Trabalho

O fluxo de trabalho é um sistema que você pode usar para criar fluxos de trabalho individuais ou processos comerciais. Ao criar um fluxo de trabalho, você especifica como um documento flui, ou se move, pelo sistema, mostrando quem deve concluir uma tarefa, tomar uma decisão ou aprovar um documento.

- [Visão geral do sistema de fluxo de trabalho](overview-workflow-system.md)
- [Elementos de fluxo de trabalho](workflow-elements.md)
- [Ações nos processos de aprovação do fluxo de trabalho](workflow-actions.md)
- [Visão geral de criação de fluxos de trabalho](create-workflow.md)

## <a name="electronic-signatures"></a>Assinaturas eletrônicas

Uma assinatura eletrônica confirma a identidade de uma pessoa que está prestes a iniciar ou aprovar um processo de computação. Em algumas indústrias, uma assinatura eletrônica tem o mesmo valor legal que a assinatura manuscrita. As assinaturas eletrônicas são um requisito de regulamentações de conformidade para diversos setores regulamentados, como as indústrias farmacêutica, alimentícia, aeroespacial e de defesa.

Você pode usar assinaturas eletrônicas para processos comerciais críticos. Alguns processos têm recursos internos de assinatura eletrônica. Você também pode criar requisitos de assinatura personalizados para qualquer tabela e campo de banco de dados.

- [Visão geral de assinaturas eletrônicas](electronic-signature-overview.md)
- [Configurar assinaturas eletrônicas](tasks/set-up-electronic-signatures.md) (Guia de tarefas)

## <a name="case-management"></a>Gerenciamento de casos

Ao planejar, rastrear e analisar os casos, será possível desenvolver resoluções eficientes que podem ser usadas para problemas semelhantes. Por exemplo, quando os representantes de serviço ao cliente ou especialistas em Recursos Humanos criam casos, eles podem encontrar informações em artigos de conhecimento para ajudá-los a trabalhar ou resolver um caso de forma mais eficiente.

- [Visão geral do gerenciamento de casos](cases.md)
- [Planejar segurança de categoria de casos, processos de casos e categorias de casos](plan-case-management.md)

## <a name="record-templates"></a>Modelos de registro

Os modelos de registro podem ajudá-lo a criar registros de forma mais rápida. Você pode criar um modelo de registro para que os valores de campo usados frequentemente não tenham que ser inseridos explicitamente para cada novo registro.

- [Visão geral de modelos de registro](record-templates.md)
- [Criar um modelo de registro para facilitar a entrada de dados](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guia de tarefas)
- [Usar um modelo de registro para criar um novo registro](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Guia de tarefas)

## <a name="general-organization-administration"></a>Administração da organização geral

- [Alterar a faixa ou o logotipo](../get-started/tasks/change-banner-or-logo.md) (Guia de tarefas)
- [Configurar gerenciamento de documentos](configure-document-management.md)
- [Configurar e enviar email](configure-email.md)
- [Dados de data/hora e fusos horários](date-time-zones.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]