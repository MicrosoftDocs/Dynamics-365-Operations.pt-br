---
title: Configurar a funcionalidade de logon estendido para Cloud POS e MPOS
description: "Este tópico aborda as opções para configurar o logon estendido para Cloud POS e Retail Modern POS (MPOS)."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: d369b760047a18c82dd89f3452d94b9c62ba8841
ms.contentlocale: pt-br
ms.lasthandoff: 01/25/2018

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a><span data-ttu-id="e18ab-103">Configurar a funcionalidade de logon estendido para Cloud POS e MPOS</span><span class="sxs-lookup"><span data-stu-id="e18ab-103">Set up extended logon functionality for Cloud POS and MPOS</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="e18ab-104">Este tópico aborda as opções para configurar o logon estendido para Cloud POS e Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="e18ab-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

## <a name="setting-up-extended-logon"></a><span data-ttu-id="e18ab-105">Configurando o logon estendido</span><span class="sxs-lookup"><span data-stu-id="e18ab-105">Setting up extended logon</span></span>

<span data-ttu-id="e18ab-106">Você pode localizar a configuração das máscaras de código de barras em **Varejo** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="e18ab-106">You can find the setup for bar code masks at **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="e18ab-107">A Guia Rápida **Funções** inclui as seguintes opções relacionadas ao logon estendido.</span><span class="sxs-lookup"><span data-stu-id="e18ab-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="e18ab-108">Logon de código de barras da equipe</span><span class="sxs-lookup"><span data-stu-id="e18ab-108">Staff bar code logon</span></span>

<span data-ttu-id="e18ab-109">Quando a opção **Logon de código de barras da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando um código de barras.</span><span class="sxs-lookup"><span data-stu-id="e18ab-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="e18ab-110">Logon de código de barras da equipe requer senha</span><span class="sxs-lookup"><span data-stu-id="e18ab-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="e18ab-111">Quando a opção **Logon de código de barras da equipe requer senha** é habilitada, o logon de código de barras da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado.</span><span class="sxs-lookup"><span data-stu-id="e18ab-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="e18ab-112">Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.</span><span class="sxs-lookup"><span data-stu-id="e18ab-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="e18ab-113">Logon de cartão da equipe</span><span class="sxs-lookup"><span data-stu-id="e18ab-113">Staff card logon</span></span>

<span data-ttu-id="e18ab-114">Quando a opção **Logon de cartão da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando uma tarja magnética.</span><span class="sxs-lookup"><span data-stu-id="e18ab-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="e18ab-115">Logon de cartão da equipe requer senha</span><span class="sxs-lookup"><span data-stu-id="e18ab-115">Staff card logon requires password</span></span>

<span data-ttu-id="e18ab-116">Quando a opção **Logon de cartão da equipe requer senha** é habilitada, o logon de cartão da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado.</span><span class="sxs-lookup"><span data-stu-id="e18ab-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="e18ab-117">Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.</span><span class="sxs-lookup"><span data-stu-id="e18ab-117">Workers must still enter their password when this option is enabled.</span></span>

## <a name="assigning-an-extended-logon"></a><span data-ttu-id="e18ab-118">Atribuindo um logon estendido</span><span class="sxs-lookup"><span data-stu-id="e18ab-118">Assigning an extended logon</span></span>

<span data-ttu-id="e18ab-119">Por padrão, somente os gerentes podem atribuir o logon estendido aos trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="e18ab-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="e18ab-120">Para atribuir o logon estendido, acesse **logon estendido** no POS.</span><span class="sxs-lookup"><span data-stu-id="e18ab-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="e18ab-121">Em seguida, procure por um trabalhador inserindo a ID do operador no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e18ab-121">Then search for a worker by entering his or her operator ID in the search field.</span></span> <span data-ttu-id="e18ab-122">Selecione o trabalhador e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="e18ab-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="e18ab-123">Na página seguinte, passe o dedo ou digitalize o logon estendido para atribuir ao trabalhador.</span><span class="sxs-lookup"><span data-stu-id="e18ab-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="e18ab-124">Se essa ação for realizada com êxito, o botão **OK** será disponibilizado.</span><span class="sxs-lookup"><span data-stu-id="e18ab-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="e18ab-125">Clique em **OK** para salvar o logon estendido desse trabalhador.</span><span class="sxs-lookup"><span data-stu-id="e18ab-125">Click **OK** to save the extended logon for that worker.</span></span>

## <a name="deleting-an-extended-logon"></a><span data-ttu-id="e18ab-126">Excluindo um logon estendido</span><span class="sxs-lookup"><span data-stu-id="e18ab-126">Deleting an extended logon</span></span>

<span data-ttu-id="e18ab-127">Para excluir o logon estendido atribuído a um trabalhador, procure o trabalhador usando a operação **Logon estendido**.</span><span class="sxs-lookup"><span data-stu-id="e18ab-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="e18ab-128">Selecione o trabalhador e clique em **Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="e18ab-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="e18ab-129">Todas as credenciais de logon estendido associadas a esse trabalhador são removidas.</span><span class="sxs-lookup"><span data-stu-id="e18ab-129">All extended logon credentials that are associated with that worker are removed.</span></span>

## <a name="extending-extended-logon"></a><span data-ttu-id="e18ab-130">Estendendo o logon estendido</span><span class="sxs-lookup"><span data-stu-id="e18ab-130">Extending extended logon</span></span>

<span data-ttu-id="e18ab-131">O serviço de logon pode ser estendido para oferecer suporte a dispositivos de logon estendido adicionais, como scanners portáteis.</span><span class="sxs-lookup"><span data-stu-id="e18ab-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="e18ab-132">Para obter mais informações, consulte a documentação de extensibilidade do PDV.</span><span class="sxs-lookup"><span data-stu-id="e18ab-132">For more information, see the POS extensibility documentation.</span></span>

## <a name="using-extended-logon"></a><span data-ttu-id="e18ab-133">Usando o logon estendido</span><span class="sxs-lookup"><span data-stu-id="e18ab-133">Using extended logon</span></span>

<span data-ttu-id="e18ab-134">Quando o logon estendido for configurado, e um trabalhador receber um código de barras ou uma tarja magnética, o trabalhador precisará apenas passar o dedo ou digitalizar o cartão enquanto a página de logon é exibida.</span><span class="sxs-lookup"><span data-stu-id="e18ab-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan his or her card while the POS logon page is displayed.</span></span> <span data-ttu-id="e18ab-135">Se for necessário também uma senha para que o logon possa continuar, o trabalhador será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="e18ab-135">If a password is also required before logon can proceed, the worker is prompted to enter his or her password.</span></span>




