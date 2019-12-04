---
title: Criar configurações para gerar documentos com dados da solicitação de emprego
description: Para concluir as etapas neste procedimento, você deve primeiramente concluir o procedimento, ER Gerar documentos com atualização de dados de aplicativo (Parte 1 – Importar configurações).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9aec1da7fe168b05af10470221ac745ec1c01f6b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182315"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="4b061-103">Criar configurações para gerar documentos com dados da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="4b061-103">Design configurations to generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4b061-104">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, ER Gerar documentos com atualização de dados de aplicativo (Parte 1: Importar configurações).</span><span class="sxs-lookup"><span data-stu-id="4b061-104">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="4b061-105">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4b061-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="4b061-106">Neste procedimento, você executa a configuração de formato importado do ER que foi criada para a empresa exemplo, Litware, Inc., para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="4b061-106">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="4b061-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4b061-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="4b061-108">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="4b061-108">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="4b061-109">Antes de começar, altere o contexto de país para a empresa de DEMF de DEU (Alemanha) para BEL (Bélgica).</span><span class="sxs-lookup"><span data-stu-id="4b061-109">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="4b061-110">Clique em Administração da organização > Organizações > Entidades legais para atualizar o código do país no endereço principal da entidade legal DEMF.</span><span class="sxs-lookup"><span data-stu-id="4b061-110">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="4b061-111">Reinicie o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4b061-111">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="4b061-112">Execute o formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="4b061-112">Run imported ER format</span></span>
1. <span data-ttu-id="4b061-113">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="4b061-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="4b061-114">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="4b061-114">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="4b061-115">Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.</span><span class="sxs-lookup"><span data-stu-id="4b061-115">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="4b061-116">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="4b061-116">Click Run.</span></span>
    * <span data-ttu-id="4b061-117">Execute a versão de rascunho de configuração de formato de ER para gerar o relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="4b061-117">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="4b061-118">No campo Inserir nome do arquivo, digite 'intrastat.xml'.</span><span class="sxs-lookup"><span data-stu-id="4b061-118">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="4b061-119">Especifique o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4b061-119">Specify the name of the file.</span></span>  
6. <span data-ttu-id="4b061-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4b061-120">Click OK.</span></span>
    * <span data-ttu-id="4b061-121">Revise o arquivo XML gerado.</span><span class="sxs-lookup"><span data-stu-id="4b061-121">Review the generated XML file.</span></span>  
7. <span data-ttu-id="4b061-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4b061-122">Close the page.</span></span>
8. <span data-ttu-id="4b061-123">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="4b061-123">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="4b061-124">Abra este formulário para exibir as transações Intrastat que são incluídas no documento eletrônico gerado.</span><span class="sxs-lookup"><span data-stu-id="4b061-124">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="4b061-125">Clique em Arquivo morto Intrastat.</span><span class="sxs-lookup"><span data-stu-id="4b061-125">Click Intrastat archive.</span></span>
    * <span data-ttu-id="4b061-126">Como o formato de ER executado não contém qualquer configuração para a atualização de dados do aplicativo, os detalhes de relatório Intrastat concluídos não foram arquivados.</span><span class="sxs-lookup"><span data-stu-id="4b061-126">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="4b061-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4b061-127">Close the page.</span></span>
11. <span data-ttu-id="4b061-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4b061-128">Close the page.</span></span>
