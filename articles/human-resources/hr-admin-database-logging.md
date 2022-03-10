---
title: Configurar e gerenciar o log de banco de dados
description: É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3cbe4c105b14935db6803e4bded0d891c564fb81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066431"
---
# <a name="configure-and-manage-database-logging"></a>Configurar e gerenciar o log de banco de dados


[!INCLUDE [PEAP](../includes/peap-2.md)]

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

1. Acesse **Administração do sistema > Links > Banco de dados > Configuração do log de banco de dados**. Selecione **Novo** para iniciar o assistente **Registrando alterações do banco de dados**.
2. Selecione **Avançar**. 
3. Na página **Tabelas e campos** do assistente, selecione as tabelas e os campos em que deseja habilitar o log de banco de dados e selecione **Avançar**.

   > [!Note]
   > O log de banco de dados não está disponível em todas as tabelas do banco de dados de Recursos Humanos. Selecionar **Mostrar todas as tabelas** abaixo da lista expande a lista de tabelas e campos para mostrar todas as tabelas do banco de dados para as quais o log de banco de dados está disponível, mas isso será um subconjunto da lista completa de tabelas de banco de dados.

4. Na página **Tipos de alteração** do assistente, selecione as operações de dados para as quais deseja rastrear alterações em cada uma das tabelas e dos campos e, em seguida, selecione **Avançar**. Consulte a tabela abaixo para obter uma descrição das operações de dados disponíveis para registro em log.
5. Na página **Concluir**, revise as alterações que serão feitas e selecione **Concluir**.

| Operação | descrição |
| -- | -- |
| Controlar novas transações | Crie um log para novos registros criados na tabela. |
| Atualização | Crie um log para atualizações em registros de tabela ou atualizações de campos selecionados individualmente na tabela. Se você optar por registrar em log as atualizações da tabela, um registro em log será criado sempre que uma atualização for feita em qualquer campo de qualquer registro na tabela. Se você optar por registrar em log as atualizações de campos específicos, um registro em log será criado somente quando atualizações forem feitas nesses campos de registros de tabela. |
| Delete | Crie um log para registros excluídos da tabela. |
| Renomear chave | Crie um registro em log quando uma chave da tabela for renomeada. |


## <a name="clean-up-database-logs"></a>Limpar logs do banco de dados

Você pode excluir todos os logs de banco de dados ou parte deles, usando as seguintes opções:

- Selecione todos os logs para uma tabela específica.
- Selecione tipos específicos de log de banco de dados.
- Selecione a data e a hora em que um log foi criado.

Para configurar a limpeza do log de banco de dados, siga estas etapas: 

1. Acesse **Administração do sistema > Links > Banco de dados > Log de banco de dados**. Selecione **Limpar log**.
2. No cabeçalho **Registros a serem incluídos**, selecione **Filtro**.
3. Escolha o método que será usado para selecionar os logs a serem excluídos. Insira uma das seguintes opções:

   - ID da tabela
   - Tipo de log
   - Data e hora de criação

4. Use a guia **Limpeza de log de banco de dados** para determinar quando a tarefa de limpeza de log deve ser executada. Por padrão, os logs do banco de dados ficam disponíveis por 30 dias.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
