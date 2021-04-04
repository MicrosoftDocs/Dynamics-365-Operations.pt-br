---
title: Configurar e gerenciar o log de banco de dados
description: É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8057ebd0bc061c6bf78d8674c45e0885ffce681c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467640"
---
# <a name="configure-and-manage-database-logging"></a>Configurar e gerenciar o log de banco de dados

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados. Este tópico descreve como:

- Gerenciar a segurança e o desempenho de log de banco de dados
- Configurar log de banco de dados
- Limpar logs do banco de dados

## <a name="overview-of-database-logging"></a>Visão geral do log de banco de dados

O log de banco de dados rastreia alterações específicas em tabelas e campos do Microsoft Dynamics 365 Human Resources. Essas alterações incluem inserções, atualizações ou exclusões. O log de banco de dados armazena um registro de alterações em tabelas ou campos na tabela de log de banco de dados.

Os usos comerciais de log de banco de dados incluem:

- Criar um registro de auditoria das alterações em tabelas específicas que contêm informações confidenciais.
- Rastrear transações únicas. O log de banco de dados não foi projetado para rastrear transações automatizadas executadas em trabalhos em lotes.

## <a name="security-for-database-logging"></a>Segurança para log de banco de dados

Os logs de bancos de dados podem conter dados confidenciais. Limite o acesso para incluir somente as funções de segurança que precisam de acesso aos dados do log.

## <a name="database-logging-and-performance"></a>Log de banco de dados e desempenho

Embora o valor seja precioso da perspectiva de negócios, o log do banco de dados pode ser caro no gerenciamento e no uso de recursos. As implicações de desempenho do log de banco de dados incluem:

- A tabela de log do banco de dados pode crescer rapidamente e causar um aumento no tamanho do banco de dados. O crescimento depende do valor dos dados registrados que você decide manter. Por padrão, a tabela de log do banco de dados mantém somente 30 dias de dados de log. 

- O log de banco de dados pode afetar de forma adversa os processos automatizados de execução longa, como importações de dados de longa duração.

### <a name="best-practices"></a>Práticas Recomendadas

Para melhorar o desempenho, limite as entradas de log selecionando campos específicos para registro em vez de tabelas inteiras. Para ajudar a manter o desempenho geral, o log do banco de dados é limitado a 20 tabelas.

> [!NOTE]
> Somente as atualizações podem ser registradas para campos individuais.

## <a name="set-up-database-logging"></a>Configurar log de banco de dados

Você pode usar o assistente **Registrando alterações do banco de dados** para configurar o log de banco de dados. O assistente fornece uma maneira flexível de configurar o log de tabelas ou campos.

1. Vá para **Administração do sistema > Links > Banco de dados > Configuração do log de banco de dados**. Selecione **Novo** para iniciar o assistente **Registrando alterações do banco de dados**.
2. Conclua o assistente.

## <a name="clean-up-database-logs"></a>Limpar logs do banco de dados

Você pode excluir todos os logs de banco de dados ou parte deles, usando as seguintes opções:

- Selecione todos os logs para uma tabela específica.
- Selecione tipos específicos de log de banco de dados.
- Selecione a data e a hora em que um log foi criado.

Para configurar a limpeza do log de banco de dados, siga estas etapas: 

1. Vá para **Administração do sistema > Links > Banco de dados > Log de banco de dados**. Selecione **Limpar log**.

2. Escolha um método de seleção de logs a serem excluídos, inserindo uma das seguintes opções:

   - ID da Tabela
   - Tipo de log
   - Data e hora de criação

3. Use a guia **Limpeza de log de banco de dados** para determinar quando a tarefa de limpeza de log deve ser executada. Por padrão, os logs do banco de dados ficam disponíveis por 30 dias.


[!INCLUDE[footer-include](../includes/footer-banner.md)]