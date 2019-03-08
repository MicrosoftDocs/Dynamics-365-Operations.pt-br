---
title: Gerenciar modelos de email
description: Você pode transferir informações de base de dados da sua organização para indicadores em um novo documento e usá-las em modelos que o ajudam a eficientemente se comunicar com os candidatos.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8eface8fd47378e25c7baeca9a84fa41097dfbe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "309601"
---
# <a name="manage-email-templates"></a><span data-ttu-id="85ffd-103">Gerenciar modelos de email</span><span class="sxs-lookup"><span data-stu-id="85ffd-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85ffd-104">Você pode transferir informações de base de dados da sua organização para indicadores em um novo documento e usá-las em modelos que o ajudam a eficientemente se comunicar com os candidatos.</span><span class="sxs-lookup"><span data-stu-id="85ffd-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="85ffd-105">Para fazer isso, você cria um modelo que contém um texto padrão e alguns indicadores onde os dados do sistema devem ser inseridos.</span><span class="sxs-lookup"><span data-stu-id="85ffd-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="85ffd-106">Por exemplo, você pode inserir as informações de endereço e contato para um candidato em um documento do Microsoft Word que você possa usar para se comunicar com o candidato.</span><span class="sxs-lookup"><span data-stu-id="85ffd-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="85ffd-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="85ffd-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="85ffd-108">Selecione a marca um endereço da Internet para ser usada nos modelos de email</span><span class="sxs-lookup"><span data-stu-id="85ffd-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="85ffd-109">Vá para Indicadores de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="85ffd-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="85ffd-110">Na lista, localize e selecione o registro de correspondência desejado.</span><span class="sxs-lookup"><span data-stu-id="85ffd-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="85ffd-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="85ffd-111">Click Edit.</span></span>
4. <span data-ttu-id="85ffd-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="85ffd-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="85ffd-113">Selecione os campos que você gostaria de poder usar em um modelo de email para a ação de correspondência selecionada e mova os campos do indicador.</span><span class="sxs-lookup"><span data-stu-id="85ffd-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="85ffd-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="85ffd-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="85ffd-115">Criar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="85ffd-115">Create an email template</span></span>
1. <span data-ttu-id="85ffd-116">Vá para para Recursos humanos > Recrutamento > Comunicação > Modelos de email de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="85ffd-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="85ffd-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="85ffd-117">Click New.</span></span>
3. <span data-ttu-id="85ffd-118">No campo Ação de correspondência, selecione 'Entrevista'.</span><span class="sxs-lookup"><span data-stu-id="85ffd-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="85ffd-119">Selecione a ação de correspondência que contém os indicadores para usar este tipo de comunicação de email.</span><span class="sxs-lookup"><span data-stu-id="85ffd-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="85ffd-120">No campo Modelo de e-mail, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="85ffd-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="85ffd-121">No campo Assunto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="85ffd-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="85ffd-122">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="85ffd-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="85ffd-123">Na lista, localize e selecione o indicador desejado.</span><span class="sxs-lookup"><span data-stu-id="85ffd-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="85ffd-124">Continue digitando a mensagem de email inserindo os campos dos indicadores onde desejado.</span><span class="sxs-lookup"><span data-stu-id="85ffd-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="85ffd-125">Continue digitando a mensagem de email inserindo os campos dos indicadores onde desejado.</span><span class="sxs-lookup"><span data-stu-id="85ffd-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="85ffd-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="85ffd-126">Click Save.</span></span>

