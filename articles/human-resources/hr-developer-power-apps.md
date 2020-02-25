---
title: Estender o Talent com o Power Apps e o Power Automate
description: Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Human Resources que usam o Microsoft Power Apps e o Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: Dynamics 365 Human Resources;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d4185b958ed35e9d2bc764db8ea77b3a2f53c37
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029856"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="bbcd7-103">Estender com o Power Apps e o Power Automate</span><span class="sxs-lookup"><span data-stu-id="bbcd7-103">Extend with Power Apps and Power Automate</span></span>

<span data-ttu-id="bbcd7-104">Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Human Resources que usam o Microsoft Power Apps e o Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="bbcd7-105">Você pode importar o pacote da solução associado a cada exemplo para o seu ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="bbcd7-106">Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbcd7-107">Se quiser usar os modelos e aplicativos descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bbcd7-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bbcd7-108">Prerequisites</span></span>

- <span data-ttu-id="bbcd7-109">Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="bbcd7-110">Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do Power Apps ou uma licença de avaliação do plano 2 do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-office-365-power-automate"></a><span data-ttu-id="bbcd7-111">Integração com o Office 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="bbcd7-111">Integration with Office 365, Power Automate</span></span>

<span data-ttu-id="bbcd7-112">O aplicativo **Integração com o Office 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-112">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="bbcd7-113">Ele faz referência a trabalhadores no Human Resources para extrair tipos de identificação de funcionário.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="bbcd7-114">Os gerentes podem verificar as datas de vencimento dos tipos de ID do funcionário.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="bbcd7-115">Eles também podem enviar um lembrete de email se o tipo de ID do funcionário expirar.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="bbcd7-116">O Power Automate integra-se ao Power Apps para enviar este lembrete.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="bbcd7-117">A confirmação será devolvida ao Power Apps do Power Automate quando o lembrete for enviado.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="bbcd7-118">Os tipos de identificação incluem a carteira do motorista, o passaporte e outros formulários aceitáveis de ID.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="bbcd7-119">Você pode estender esse aplicativo para outros cenários.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="bbcd7-120">Por exemplo, você pode usá-lo para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="bbcd7-121">Para baixar o aplicativo **Integração com o Office 365, Power Automate**, vá para [Integração com o Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-121">To download the **Integration with Office 365, Power Automate** app, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="bbcd7-122">Power Automate – Conectar ao SQL e executar</span><span class="sxs-lookup"><span data-stu-id="bbcd7-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="bbcd7-123">O modelo **Power Automate — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="bbcd7-124">Embora esse modelo leia e atualize tabelas SQL, você pode estendê-las e usá-las em outros cenários.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="bbcd7-125">Por exemplo, você pode usá-la para preencher uma tabela de preparação no Common Data Service com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-125">For example, you can use it to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="bbcd7-126">A consulta avançada é integrada ao fluxo para habilitar a transformação de dados e o push incremental.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="bbcd7-127">Para baixar o modelo **Power Automate — Conectar ao SQL e executar**, acesse [Power Automate — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbcd7-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbcd7-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bbcd7-128">Additional resources</span></span>

[<span data-ttu-id="bbcd7-129">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="bbcd7-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="bbcd7-130">Migrar aplicativos entre locatários e ambientes</span><span class="sxs-lookup"><span data-stu-id="bbcd7-130">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
