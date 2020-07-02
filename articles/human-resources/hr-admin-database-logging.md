---
title: Configurar e gerenciar o log de banco de dados
description: É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.
author: Darinkramer
manager: AnnBe
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
ms.author: dkrame
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3dc4658a0a13af95978c66f5aab882902f754a2d
ms.sourcegitcommit: 88f38d584c5befb96e4d1daab4b28af5519ef125
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2020
ms.locfileid: "3443561"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="c7268-103">Configurar e gerenciar o log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-103">Configure and manage database logging</span></span>

<span data-ttu-id="c7268-104">É possível rastrear alterações em tabelas e campos no Dynamics 365 Human Resources com o log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7268-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="c7268-105">Este tópico descreve como:</span><span class="sxs-lookup"><span data-stu-id="c7268-105">This topic describes how to:</span></span>

- <span data-ttu-id="c7268-106">Gerenciar a segurança e o desempenho de log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="c7268-107">Configurar log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-107">Set up database logging</span></span>
- <span data-ttu-id="c7268-108">Limpar logs do banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="c7268-109">Visão geral do log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-109">Overview of database logging</span></span>

<span data-ttu-id="c7268-110">O log de banco de dados rastreia alterações específicas em tabelas e campos do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c7268-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="c7268-111">Essas alterações incluem inserções, atualizações ou exclusões.</span><span class="sxs-lookup"><span data-stu-id="c7268-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="c7268-112">O log de banco de dados armazena um registro de alterações em tabelas ou campos na tabela de log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7268-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="c7268-113">Os usos comerciais de log de banco de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="c7268-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="c7268-114">Criar um registro de auditoria das alterações em tabelas específicas que contêm informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="c7268-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="c7268-115">Rastrear transações únicas.</span><span class="sxs-lookup"><span data-stu-id="c7268-115">Tracking single transactions.</span></span> <span data-ttu-id="c7268-116">O log de banco de dados não foi projetado para rastrear transações automatizadas executadas em trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="c7268-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="c7268-117">Segurança para log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-117">Security for database logging</span></span>

<span data-ttu-id="c7268-118">Os logs de bancos de dados podem conter dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="c7268-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="c7268-119">Limite o acesso para incluir somente as funções de segurança que precisam de acesso aos dados do log.</span><span class="sxs-lookup"><span data-stu-id="c7268-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="c7268-120">Log de banco de dados e desempenho</span><span class="sxs-lookup"><span data-stu-id="c7268-120">Database logging and performance</span></span>

<span data-ttu-id="c7268-121">Embora o valor seja precioso da perspectiva de negócios, o log do banco de dados pode ser caro no gerenciamento e no uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="c7268-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="c7268-122">As implicações de desempenho do log de banco de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="c7268-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="c7268-123">A tabela de log do banco de dados pode crescer rapidamente e causar um aumento no tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7268-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="c7268-124">O crescimento depende do valor dos dados registrados que você decide manter.</span><span class="sxs-lookup"><span data-stu-id="c7268-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="c7268-125">Por padrão, a tabela de log do banco de dados mantém somente 30 dias de dados de log.</span><span class="sxs-lookup"><span data-stu-id="c7268-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="c7268-126">O log de banco de dados pode afetar de forma adversa os processos automatizados de execução longa, como importações de dados de longa duração.</span><span class="sxs-lookup"><span data-stu-id="c7268-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="c7268-127">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="c7268-127">Best practices</span></span>

<span data-ttu-id="c7268-128">Para melhorar o desempenho, limite as entradas de log selecionando campos específicos para registro em vez de tabelas inteiras.</span><span class="sxs-lookup"><span data-stu-id="c7268-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="c7268-129">Para ajudar a manter o desempenho geral, o log do banco de dados é limitado a 20 tabelas.</span><span class="sxs-lookup"><span data-stu-id="c7268-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="c7268-130">Somente as atualizações podem ser registradas para campos individuais.</span><span class="sxs-lookup"><span data-stu-id="c7268-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="c7268-131">Configurar log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-131">Set up database logging</span></span>

<span data-ttu-id="c7268-132">Você pode usar o assistente **Registrando alterações do banco de dados** para configurar o log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7268-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="c7268-133">O assistente fornece uma maneira flexível de configurar o log de tabelas ou campos.</span><span class="sxs-lookup"><span data-stu-id="c7268-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="c7268-134">Vá para **Administração do sistema > Links > Banco de dados > Configuração do log de banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="c7268-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="c7268-135">Selecione **Novo** para iniciar o assistente **Registrando alterações do banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="c7268-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="c7268-136">Conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="c7268-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="c7268-137">Limpar logs do banco de dados</span><span class="sxs-lookup"><span data-stu-id="c7268-137">Clean up database logs</span></span>

<span data-ttu-id="c7268-138">Você pode excluir todos os logs de banco de dados ou parte deles, usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c7268-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="c7268-139">Selecione todos os logs para uma tabela específica.</span><span class="sxs-lookup"><span data-stu-id="c7268-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="c7268-140">Selecione tipos específicos de log de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c7268-140">Select specific types of database log.</span></span>
- <span data-ttu-id="c7268-141">Selecione a data e a hora em que um log foi criado.</span><span class="sxs-lookup"><span data-stu-id="c7268-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="c7268-142">Para configurar a limpeza do log de banco de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c7268-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="c7268-143">Vá para **Administração do sistema > Links > Banco de dados > Log de banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="c7268-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="c7268-144">Selecione **Limpar log**.</span><span class="sxs-lookup"><span data-stu-id="c7268-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="c7268-145">Escolha um método de seleção de logs a serem excluídos, inserindo uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c7268-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="c7268-146">ID da Tabela</span><span class="sxs-lookup"><span data-stu-id="c7268-146">Table ID</span></span>
   - <span data-ttu-id="c7268-147">Tipo de log</span><span class="sxs-lookup"><span data-stu-id="c7268-147">Type of log</span></span>
   - <span data-ttu-id="c7268-148">Data e hora de criação</span><span class="sxs-lookup"><span data-stu-id="c7268-148">Created date and time</span></span>

3. <span data-ttu-id="c7268-149">Use a guia **Limpeza de log de banco de dados** para determinar quando a tarefa de limpeza de log deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="c7268-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="c7268-150">Por padrão, os logs do banco de dados ficam disponíveis por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c7268-150">By default, database logs are available for 30 days.</span></span>
