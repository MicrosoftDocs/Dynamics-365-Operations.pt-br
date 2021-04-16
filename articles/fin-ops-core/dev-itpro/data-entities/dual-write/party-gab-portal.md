---
title: Usar o Power Portal com o modelo de dados do participante
description: Este tópico descreve as alterações nas funções Web do Power Portal devido ao modelo de dados do participante em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833081"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="a3c3e-103">Usar o Power Portal com o modelo de dados do participante</span><span class="sxs-lookup"><span data-stu-id="a3c3e-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3c3e-104">A versão 2.0.999.0 da solução de orquestração de aplicativos de gravação dupla e posterior inclui alterações no modelo de dados para o participante e para o catálogo de endereços global das tabelas Conta e Contato.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="a3c3e-105">As alterações permitem relacionamentos muitos para muitos que oferecem suporte a cenários comerciais avançados.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="a3c3e-106">Essas alterações não são compatíveis com as funções Web do portal, incluindo o portal do cliente, que são enviadas prontas ou que já estavam no seu ambiente antes de instalar a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="a3c3e-107">Para que as funções Web funcionem conforme o esperado, você precisa criar funções Web usando o novo modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="a3c3e-108">Em resumo, a forma como as tabelas interagem mudou, mas as permissões de tabela no portal do cliente não mudaram.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="a3c3e-109">Este tópico explica como criar funções Web que funcionam com o novo modelo de dados avançado.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="a3c3e-110">Este diagrama mostra a relação da tabela **sem** o modelo de dados do catálogo de endereços global e do participante:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![sem o modelo do participante](media/without-party-model.PNG)

<span data-ttu-id="a3c3e-112">Este diagrama mostra a relação da tabela **com** o modelo de dados do catálogo de endereços global e do participante:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![com o modelo do participante](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="a3c3e-114">Criar uma permissão de tabela</span><span class="sxs-lookup"><span data-stu-id="a3c3e-114">Create a new table permission</span></span>

<span data-ttu-id="a3c3e-115">Para criar essas permissões de tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="a3c3e-116">Entre em [Power Apps](https://make.powerapps.com) e acesse seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="a3c3e-117">Selecione o aplicativo de gerenciamento de portal.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="a3c3e-118">Na barra lateral, selecione **Segurança > Permissões de tabela**.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="a3c3e-119">Você deve criar três permissões:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="a3c3e-120">Conexão de Contato com Participante</span><span class="sxs-lookup"><span data-stu-id="a3c3e-120">Contact to Party connection</span></span>
    + <span data-ttu-id="a3c3e-121">Conexão de Participante com Conta</span><span class="sxs-lookup"><span data-stu-id="a3c3e-121">Party to Account connection</span></span>
    + <span data-ttu-id="a3c3e-122">Conexão de Conta com Pedido</span><span class="sxs-lookup"><span data-stu-id="a3c3e-122">Account to Order connection</span></span>

4. <span data-ttu-id="a3c3e-123">Crie e salve uma permissão para a conexão de Contato com Participante, definindo estes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3c3e-124">**Nome**: conexão de Participante com Conta (ou o que você escolher)</span><span class="sxs-lookup"><span data-stu-id="a3c3e-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="a3c3e-125">**Nome da tabela**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="a3c3e-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="a3c3e-126">**Site**: Portal do cliente</span><span class="sxs-lookup"><span data-stu-id="a3c3e-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3c3e-127">**Escopo**: contato</span><span class="sxs-lookup"><span data-stu-id="a3c3e-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="a3c3e-128">**Privilégios**: selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="a3c3e-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3c3e-129">**Funções Web**: usuários autenticados, representante do cliente (ou o que você escolher)</span><span class="sxs-lookup"><span data-stu-id="a3c3e-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="a3c3e-130">Crie e salve uma permissão para a conexão de Participante com Conta, definindo estes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3c3e-131">**Nome**: conexão de Participante com Conta (ou o que você escolher)</span><span class="sxs-lookup"><span data-stu-id="a3c3e-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="a3c3e-132">**Nome da tabela**: conta</span><span class="sxs-lookup"><span data-stu-id="a3c3e-132">**Table Name**: account</span></span>
    + <span data-ttu-id="a3c3e-133">**Site**: Portal do cliente</span><span class="sxs-lookup"><span data-stu-id="a3c3e-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3c3e-134">**Escopo**: responsável</span><span class="sxs-lookup"><span data-stu-id="a3c3e-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="a3c3e-135">**Privilégios**: selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="a3c3e-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3c3e-136">**Permissão da tabela principal**: conexão de Participante e Contato</span><span class="sxs-lookup"><span data-stu-id="a3c3e-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="a3c3e-137">Crie e salve uma permissão para a conexão de Conta com Pedido, definindo estes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a3c3e-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3c3e-138">**Nome**: conexão de Conta e Pedido (ou o que você escolher)</span><span class="sxs-lookup"><span data-stu-id="a3c3e-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="a3c3e-139">**Nome da tabela**: salesorder</span><span class="sxs-lookup"><span data-stu-id="a3c3e-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="a3c3e-140">**Site**: Portal do cliente</span><span class="sxs-lookup"><span data-stu-id="a3c3e-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3c3e-141">**Escopo**: responsável</span><span class="sxs-lookup"><span data-stu-id="a3c3e-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="a3c3e-142">**Privilégios**: selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="a3c3e-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3c3e-143">**Permissão da tabela principal**: conexão de Participante e Conta</span><span class="sxs-lookup"><span data-stu-id="a3c3e-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
