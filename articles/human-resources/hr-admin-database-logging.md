---
title: Configurar e gerenciar o log de banco de dados
description: É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d22ff9f3ce68c81f37840342c795d7d162eb027b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801326"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="b09f4-103">Configurar e gerenciar o log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b09f4-104">É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="b09f4-105">Este tópico descreve como:</span><span class="sxs-lookup"><span data-stu-id="b09f4-105">This topic describes how to:</span></span>

- <span data-ttu-id="b09f4-106">Gerenciar a segurança e o desempenho de log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="b09f4-107">Configurar log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-107">Set up database logging</span></span>
- <span data-ttu-id="b09f4-108">Limpar logs do banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="b09f4-109">Visão geral do log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-109">Overview of database logging</span></span>

<span data-ttu-id="b09f4-110">O log de banco de dados rastreia alterações específicas em tabelas e campos do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b09f4-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="b09f4-111">Essas alterações incluem inserções, atualizações ou exclusões.</span><span class="sxs-lookup"><span data-stu-id="b09f4-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="b09f4-112">O log de banco de dados armazena um registro de alterações em tabelas ou campos na tabela de log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="b09f4-113">Os usos comerciais de log de banco de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="b09f4-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="b09f4-114">Criar um registro de auditoria das alterações em tabelas específicas que contêm informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b09f4-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="b09f4-115">Rastrear transações únicas.</span><span class="sxs-lookup"><span data-stu-id="b09f4-115">Tracking single transactions.</span></span> <span data-ttu-id="b09f4-116">O log de banco de dados não foi projetado para rastrear transações automatizadas executadas em trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="b09f4-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="b09f4-117">Segurança para log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-117">Security for database logging</span></span>

<span data-ttu-id="b09f4-118">Os logs de bancos de dados podem conter dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b09f4-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="b09f4-119">Limite o acesso para incluir somente as funções de segurança que precisam de acesso aos dados do log.</span><span class="sxs-lookup"><span data-stu-id="b09f4-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="b09f4-120">Log de banco de dados e desempenho</span><span class="sxs-lookup"><span data-stu-id="b09f4-120">Database logging and performance</span></span>

<span data-ttu-id="b09f4-121">Embora o valor seja precioso da perspectiva de negócios, o log do banco de dados pode ser caro no gerenciamento e no uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="b09f4-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="b09f4-122">As implicações de desempenho do log de banco de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="b09f4-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="b09f4-123">A tabela de log do banco de dados pode crescer rapidamente e causar um aumento no tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="b09f4-124">O crescimento depende do valor dos dados registrados que você decide manter.</span><span class="sxs-lookup"><span data-stu-id="b09f4-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="b09f4-125">Por padrão, a tabela de log do banco de dados mantém somente 30 dias de dados de log.</span><span class="sxs-lookup"><span data-stu-id="b09f4-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="b09f4-126">O log de banco de dados pode afetar de forma adversa os processos automatizados de execução longa, como importações de dados de longa duração.</span><span class="sxs-lookup"><span data-stu-id="b09f4-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="b09f4-127">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="b09f4-127">Best practices</span></span>

<span data-ttu-id="b09f4-128">Para melhorar o desempenho, limite as entradas de log selecionando campos específicos para registro em vez de tabelas inteiras.</span><span class="sxs-lookup"><span data-stu-id="b09f4-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="b09f4-129">Para ajudar a manter o desempenho geral, o log do banco de dados é limitado a 20 tabelas.</span><span class="sxs-lookup"><span data-stu-id="b09f4-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="b09f4-130">Somente as atualizações podem ser registradas para campos individuais.</span><span class="sxs-lookup"><span data-stu-id="b09f4-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="b09f4-131">Configurar log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-131">Set up database logging</span></span>

<span data-ttu-id="b09f4-132">Você pode usar o assistente **Registrando alterações do banco de dados** para configurar o log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="b09f4-133">O assistente fornece uma maneira flexível de configurar o log de tabelas ou campos.</span><span class="sxs-lookup"><span data-stu-id="b09f4-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="b09f4-134">Vá para **Administração do sistema > Links > Banco de dados > Configuração do log de banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="b09f4-135">Selecione **Novo** para iniciar o assistente **Registrando alterações do banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="b09f4-136">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-136">Select **Next**.</span></span> 
3. <span data-ttu-id="b09f4-137">Na página **Tabelas e campos** do assistente, selecione as tabelas e os campos em que deseja habilitar o log de banco de dados e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="b09f4-138">O log de banco de dados não está disponível em todas as tabelas do banco de dados de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="b09f4-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="b09f4-139">Selecionar **Mostrar todas as tabelas** abaixo da lista expande a lista de tabelas e campos para mostrar todas as tabelas do banco de dados para as quais o log de banco de dados está disponível, mas isso será um subconjunto da lista completa de tabelas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="b09f4-140">Na página **Tipos de alteração** do assistente, selecione as operações de dados para as quais deseja rastrear alterações em cada uma das tabelas e dos campos e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="b09f4-141">Consulte a tabela abaixo para obter uma descrição das operações de dados disponíveis para registro em log.</span><span class="sxs-lookup"><span data-stu-id="b09f4-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="b09f4-142">Na página **Concluir**, revise as alterações que serão feitas e selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="b09f4-143">Operação</span><span class="sxs-lookup"><span data-stu-id="b09f4-143">Operation</span></span> | <span data-ttu-id="b09f4-144">descrição</span><span class="sxs-lookup"><span data-stu-id="b09f4-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="b09f4-145">Controlar novas transações</span><span class="sxs-lookup"><span data-stu-id="b09f4-145">Track new transactions</span></span> | <span data-ttu-id="b09f4-146">Crie um log para novos registros criados na tabela.</span><span class="sxs-lookup"><span data-stu-id="b09f4-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="b09f4-147">Atualização</span><span class="sxs-lookup"><span data-stu-id="b09f4-147">Update</span></span> | <span data-ttu-id="b09f4-148">Crie um log para atualizações em registros de tabela ou atualizações de campos selecionados individualmente na tabela.</span><span class="sxs-lookup"><span data-stu-id="b09f4-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="b09f4-149">Se você optar por registrar em log as atualizações da tabela, um registro em log será criado sempre que uma atualização for feita em qualquer campo de qualquer registro na tabela.</span><span class="sxs-lookup"><span data-stu-id="b09f4-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="b09f4-150">Se você optar por registrar em log as atualizações de campos específicos, um registro em log será criado somente quando atualizações forem feitas nesses campos de registros de tabela.</span><span class="sxs-lookup"><span data-stu-id="b09f4-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="b09f4-151">Delete</span><span class="sxs-lookup"><span data-stu-id="b09f4-151">Delete</span></span> | <span data-ttu-id="b09f4-152">Crie um log para registros excluídos da tabela.</span><span class="sxs-lookup"><span data-stu-id="b09f4-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="b09f4-153">Renomear chave</span><span class="sxs-lookup"><span data-stu-id="b09f4-153">Rename key</span></span> | <span data-ttu-id="b09f4-154">Crie um registro em log quando uma chave da tabela for renomeada.</span><span class="sxs-lookup"><span data-stu-id="b09f4-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="b09f4-155">Limpar logs do banco de dados</span><span class="sxs-lookup"><span data-stu-id="b09f4-155">Clean up database logs</span></span>

<span data-ttu-id="b09f4-156">Você pode excluir todos os logs de banco de dados ou parte deles, usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b09f4-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="b09f4-157">Selecione todos os logs para uma tabela específica.</span><span class="sxs-lookup"><span data-stu-id="b09f4-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="b09f4-158">Selecione tipos específicos de log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b09f4-158">Select specific types of database log.</span></span>
- <span data-ttu-id="b09f4-159">Selecione a data e a hora em que um log foi criado.</span><span class="sxs-lookup"><span data-stu-id="b09f4-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="b09f4-160">Para configurar a limpeza do log de banco de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b09f4-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="b09f4-161">Vá para **Administração do sistema > Links > Banco de dados > Log de banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="b09f4-162">Selecione **Limpar log**.</span><span class="sxs-lookup"><span data-stu-id="b09f4-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="b09f4-163">Escolha um método de seleção de logs a serem excluídos, inserindo uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b09f4-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="b09f4-164">ID da Tabela</span><span class="sxs-lookup"><span data-stu-id="b09f4-164">Table ID</span></span>
   - <span data-ttu-id="b09f4-165">Tipo de log</span><span class="sxs-lookup"><span data-stu-id="b09f4-165">Type of log</span></span>
   - <span data-ttu-id="b09f4-166">Data e hora de criação</span><span class="sxs-lookup"><span data-stu-id="b09f4-166">Created date and time</span></span>

3. <span data-ttu-id="b09f4-167">Use a guia **Limpeza de log de banco de dados** para determinar quando a tarefa de limpeza de log deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="b09f4-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="b09f4-168">Por padrão, os logs do banco de dados ficam disponíveis por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b09f4-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
