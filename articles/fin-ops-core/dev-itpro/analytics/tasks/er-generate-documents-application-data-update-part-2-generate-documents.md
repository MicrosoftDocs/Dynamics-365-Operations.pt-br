---
title: Criar configurações para gerar documentos com dados da solicitação de emprego
description: Este tópico descreve como criar configurações de relatório eletrônico (ER) para gerar um documento eletrônico. (Parte 1 - Importar configurações).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 217eca9bd1502d4327857720fb2d32a3ec3508ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563165"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="b97a6-104">Criar configurações para gerar documentos com dados da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="b97a6-104">Design configurations to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b97a6-105">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, ER Gerar documentos com atualização de dados de aplicativo (Parte 1: Importar configurações).</span><span class="sxs-lookup"><span data-stu-id="b97a6-105">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="b97a6-106">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b97a6-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="b97a6-107">Neste procedimento, você executa a configuração de formato importado do ER que foi criada para a empresa exemplo, Litware, Inc., para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="b97a6-107">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="b97a6-108">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b97a6-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="b97a6-109">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="b97a6-109">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="b97a6-110">Antes de começar, altere o contexto de país para a empresa de DEMF de DEU (Alemanha) para BEL (Bélgica).</span><span class="sxs-lookup"><span data-stu-id="b97a6-110">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="b97a6-111">Clique em Administração da organização > Organizações > Entidades legais para atualizar o código do país no endereço principal da entidade legal DEMF.</span><span class="sxs-lookup"><span data-stu-id="b97a6-111">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="b97a6-112">Reinicie o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b97a6-112">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="b97a6-113">Execute o formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="b97a6-113">Run imported ER format</span></span>
1. <span data-ttu-id="b97a6-114">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="b97a6-114">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="b97a6-115">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="b97a6-115">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="b97a6-116">Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.</span><span class="sxs-lookup"><span data-stu-id="b97a6-116">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="b97a6-117">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="b97a6-117">Click Run.</span></span>
    * <span data-ttu-id="b97a6-118">Execute a versão de rascunho de configuração de formato de ER para gerar o relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b97a6-118">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="b97a6-119">No campo Inserir nome do arquivo, digite 'intrastat.xml'.</span><span class="sxs-lookup"><span data-stu-id="b97a6-119">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="b97a6-120">Especifique o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b97a6-120">Specify the name of the file.</span></span>  
6. <span data-ttu-id="b97a6-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b97a6-121">Click OK.</span></span>
    * <span data-ttu-id="b97a6-122">Revise o arquivo XML gerado.</span><span class="sxs-lookup"><span data-stu-id="b97a6-122">Review the generated XML file.</span></span>  
7. <span data-ttu-id="b97a6-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b97a6-123">Close the page.</span></span>
8. <span data-ttu-id="b97a6-124">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b97a6-124">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="b97a6-125">Abra este formulário para exibir as transações Intrastat que são incluídas no documento eletrônico gerado.</span><span class="sxs-lookup"><span data-stu-id="b97a6-125">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="b97a6-126">Clique em Arquivo morto Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b97a6-126">Click Intrastat archive.</span></span>
    * <span data-ttu-id="b97a6-127">Como o formato de ER executado não contém qualquer configuração para a atualização de dados do aplicativo, os detalhes de relatório Intrastat concluídos não foram arquivados.</span><span class="sxs-lookup"><span data-stu-id="b97a6-127">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="b97a6-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b97a6-128">Close the page.</span></span>
11. <span data-ttu-id="b97a6-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b97a6-129">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]