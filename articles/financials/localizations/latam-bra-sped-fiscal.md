---
title: Arquivos fiscais SPED
description: Este tópico explica como configurar e gerar arquivos de exportação SPED para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: f58f69235d809c71bb7eefcac3d5e88657cdb4b1
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849365"
---
# <a name="sped-fiscal-files"></a><span data-ttu-id="b20c8-103">Arquivos fiscais SPED</span><span class="sxs-lookup"><span data-stu-id="b20c8-103">SPED fiscal files</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b20c8-104">Os arquivos de texto fiscais do Sistema Público de Escrituração Digital (SPED) contêm informações sobre todas as notas fiscais que foram recebidas e emitidas em um mês para um estabelecimento fiscal específico.</span><span class="sxs-lookup"><span data-stu-id="b20c8-104">Sistema Publico de Escrituração Digital (SPED) fiscal text files contain information about all fiscal documents that have been received and issued for a specific fiscal establishment during a month.</span></span> <span data-ttu-id="b20c8-105">As autoridades fiscais federais usam o sistema SPED para verificar os cálculos do Imposto Sobre Circulação de Mercadorias e Serviços (ICMS) e do Imposto sobre Produtos Industrializados (IPI).</span><span class="sxs-lookup"><span data-stu-id="b20c8-105">Federal tax authorities use the SPED system to verify tax calculations for Imposto Sobre Circulação de Mercadorias e Serviços (ICMS) and Imposto sobre Produtos Industrializados (IPI).</span></span>

## <a name="setup"></a><span data-ttu-id="b20c8-106">Configurar</span><span class="sxs-lookup"><span data-stu-id="b20c8-106">Setup</span></span>

<span data-ttu-id="b20c8-107">Para poder gerar um arquivo de texto fiscal SPED e enviá-lo às autoridades fiscais federais, você deve especificar os parâmetros que definem como o arquivo de texto fiscal SPED será salvo.</span><span class="sxs-lookup"><span data-stu-id="b20c8-107">Before you can generate a SPED fiscal text file and submit it to the federal tax authorities, you must specify parameters that define how the SPED fiscal text file will be saved.</span></span> <span data-ttu-id="b20c8-108">Esta seção explica como especificar esses parâmetros na página **Parâmetros do SPED Fiscal**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-108">This section explains how to specify these parameters on the **SPED fiscal parameters** page.</span></span>

1. <span data-ttu-id="b20c8-109">Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-109">Select **Fiscal books** \> **Setup** \> **Tax statements parameters**.</span></span>
2. <span data-ttu-id="b20c8-110">Selecione **SPED Fiscal** e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-110">Select **SPED Fiscal**, and then, on the **Setup parameters** FastTab, select **Open**.</span></span>
4. <span data-ttu-id="b20c8-111">Na página **Parâmetros do SPED Fiscal**, selecione o local no qual o arquivo de texto fiscal SPED deve ser salvo.</span><span class="sxs-lookup"><span data-stu-id="b20c8-111">On the **SPED fiscal parameters** page, select the location where the SPED fiscal text file should be saved.</span></span>
5. <span data-ttu-id="b20c8-112">Selecione uma apresentação de perfil.</span><span class="sxs-lookup"><span data-stu-id="b20c8-112">Select a profile presentation.</span></span> <span data-ttu-id="b20c8-113">Para a versão atual, apenas a apresentação de perfil **A** tem suporte.</span><span class="sxs-lookup"><span data-stu-id="b20c8-113">For the current release, only profile presentation **A** is supported.</span></span>
6. <span data-ttu-id="b20c8-114">Selecione a versão do formato de arquivo de texto fiscal SPED a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="b20c8-114">Select the version of the SPED fiscal text file format to generate.</span></span>
7. <span data-ttu-id="b20c8-115">Selecione o tipo de atividade a ser incluído no arquivo de texto fiscal SPED:</span><span class="sxs-lookup"><span data-stu-id="b20c8-115">Select the type of activity to include in the SPED fiscal text file:</span></span>

    - <span data-ttu-id="b20c8-116">**Industrial ou equivalente** – Inclui informações de atividades que estão relacionadas aos setores (por exemplo, a fabricação de mercadorias).</span><span class="sxs-lookup"><span data-stu-id="b20c8-116">**Industrial or equivalent** – Include information for activities that are related to industries (for example, the manufacture of goods).</span></span>
    - <span data-ttu-id="b20c8-117">**Outros** – Inclui informações para todos os outros tipos de atividades.</span><span class="sxs-lookup"><span data-stu-id="b20c8-117">**Others** – Include information for all other types of activities.</span></span>

8. <span data-ttu-id="b20c8-118">Defina a opção **Habilitar o bloco K** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-118">Set the **Enable block K** option to **Yes**.</span></span> <span data-ttu-id="b20c8-119">Se não habilitar o bloco K, apenas os registros K001 e K999 serão produzidos.</span><span class="sxs-lookup"><span data-stu-id="b20c8-119">If you don't enable block K, only records K001 and K999 will be generated.</span></span>
9. <span data-ttu-id="b20c8-120">Defina a opção **Habilitar ordens de produção** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-120">Set the **Enable production orders** option to **Yes**.</span></span> <span data-ttu-id="b20c8-121">Esta opção permite gerar os registros K230 e K235 do módulo de manufatura.</span><span class="sxs-lookup"><span data-stu-id="b20c8-121">This option lets you generate records K230 and K235 from the manufacturing module.</span></span> 

## <a name="generate-the-sped-fiscal-export-file-for-a-month"></a><span data-ttu-id="b20c8-122">Gerar o arquivo de exportação fiscal SPED para um mês</span><span class="sxs-lookup"><span data-stu-id="b20c8-122">Generate the SPED fiscal export file for a month</span></span> 

<span data-ttu-id="b20c8-123">O arquivo de texto fiscal do SPED fornece informações sobre as notas fiscais que foram recebidas e emitidas durante um mês específico.</span><span class="sxs-lookup"><span data-stu-id="b20c8-123">The SPED fiscal text file provides information about fiscal documents that were received and issued during a specific month.</span></span> <span data-ttu-id="b20c8-124">Essas informações são usadas pelas autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="b20c8-124">This information is used by tax authorities.</span></span> <span data-ttu-id="b20c8-125">O arquivo de texto fiscal SPED também inclui informações sobre apurações e pagamentos de impostos durante o mês.</span><span class="sxs-lookup"><span data-stu-id="b20c8-125">The SPED fiscal text file also includes information about tax assessments and payments during the month.</span></span> <span data-ttu-id="b20c8-126">Esta seção explica como gerar um arquivo de texto fiscal SPED usando a página de listagem **Período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-126">This section explains how to generate a SPED fiscal text file by using the **Booking period** list page.</span></span>

1. <span data-ttu-id="b20c8-127">Selecione **Livros fiscais** \> **Comum** \> **Período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-127">Select **Fiscal books** \> **Common** \> **Booking period**.</span></span>
2. <span data-ttu-id="b20c8-128">Selecione um período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="b20c8-128">Select a booking period.</span></span>
3. <span data-ttu-id="b20c8-129">No Painel de Ação, na guia **Obrigações fiscais**, selecione **SPED Fiscal**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-129">On the Action Pane, on the **Tax statements** tab, select **SPED Fiscal**.</span></span>
4. <span data-ttu-id="b20c8-130">Especifique o local e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b20c8-130">Specify the location and name of the file.</span></span> <span data-ttu-id="b20c8-131">O local padrão é especificado na página **Parâmetros do SPED Fiscal** e o nome do arquivo padrão será gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b20c8-131">The default location is specified on the **SPED fiscal parameters** page, and a default file name is automatically generated.</span></span> <span data-ttu-id="b20c8-132">Na maioria dos casos, você deve aceitar o nome do arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="b20c8-132">In most cases, you should accept the default file name.</span></span>
5. <span data-ttu-id="b20c8-133">No campo **Tipo de arquivo**, selecione **Original** ou **Substituto**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-133">In the **File type** field, select either **Original** or **Substitute**.</span></span>
6. <span data-ttu-id="b20c8-134">Selecione a versão.</span><span class="sxs-lookup"><span data-stu-id="b20c8-134">Select the version.</span></span> <span data-ttu-id="b20c8-135">A versão padrão é especificada na página **Parâmetros do SPED Fiscal** .</span><span class="sxs-lookup"><span data-stu-id="b20c8-135">The default version is specified on the **SPED fiscal parameters** page.</span></span>
7. <span data-ttu-id="b20c8-136">Defina a opção **Habilitar o bloco K** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-136">Set the **Enable block K** option to **Yes**.</span></span> <span data-ttu-id="b20c8-137">A definição padrão é especificada na página **Parâmetros do SPED Fiscal** .</span><span class="sxs-lookup"><span data-stu-id="b20c8-137">The default setting is specified on the **SPED fiscal parameters** page.</span></span>
8. <span data-ttu-id="b20c8-138">Opcional: Na Guia Rápida **Executar em segundo plano**, especifique as opções para o processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="b20c8-138">Optional: On the **Run in the background** FastTab, specify the options for batch processing.</span></span> <span data-ttu-id="b20c8-139">Você pode usar o processamento em lote se o arquivo tiver de ser gerado posteriormente ou em um servidor, e não no computador.</span><span class="sxs-lookup"><span data-stu-id="b20c8-139">You might use batch processing if the file should be generated later or on a server instead of on your computer.</span></span>
9. <span data-ttu-id="b20c8-140">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b20c8-140">Select **OK**.</span></span>
