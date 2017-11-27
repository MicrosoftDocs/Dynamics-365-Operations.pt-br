--- 
title: Configurar tipos de documentos I-9
description: "Este procedimento mostra como visualizar e configurar tipos de documentos que são utilizados para a verificação do I-9."
author: ShielaSogge
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 950237499441e7f1d5b9e3355c4bd9513ad3783e
ms.openlocfilehash: b47998eccd7509154ee8863e2e19594cc59ac945
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="6b563-103">Configurar tipos de documentos I-9</span><span class="sxs-lookup"><span data-stu-id="6b563-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="6b563-104">Este procedimento mostra como visualizar e configurar tipos de documentos que são utilizados para a verificação do I-9.</span><span class="sxs-lookup"><span data-stu-id="6b563-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="6b563-105">Antes de configurar tipo de documentos I-9, você também deve configurar as agências emissoras e os tipos de identificação.</span><span class="sxs-lookup"><span data-stu-id="6b563-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="6b563-106">A empresa de dados de demonstração utilizada para criar esse procedimento é a USMF, a qual inclui exemplos das agências emissoras e dos tipos de identificação que são necessários para a conclusão do processo.</span><span class="sxs-lookup"><span data-stu-id="6b563-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="6b563-107">Vá para Recursos humanos > Trabalhadores > I-9 > Tipos de documento I-9.</span><span class="sxs-lookup"><span data-stu-id="6b563-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="6b563-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6b563-108">Click New.</span></span>
3. <span data-ttu-id="6b563-109">No campo Tipo de documento I-9, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6b563-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="6b563-110">Exemplo: ID da escola.</span><span class="sxs-lookup"><span data-stu-id="6b563-110">Example: School ID.</span></span>  
4. <span data-ttu-id="6b563-111">Selecione o tipo de identificação.</span><span class="sxs-lookup"><span data-stu-id="6b563-111">Select the identification type.</span></span>  <span data-ttu-id="6b563-112">Exemplo: ID da escola.</span><span class="sxs-lookup"><span data-stu-id="6b563-112">Example:  School ID</span></span>
    * <span data-ttu-id="6b563-113">Exemplos de tipos de identificação incluem o número da Previdência Social (SSN), o número do visto, o passaporte, ou a carteira de motorista.</span><span class="sxs-lookup"><span data-stu-id="6b563-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's license.</span></span>  
5. <span data-ttu-id="6b563-114">Selecione lista de documentos I-9 utilizada para o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="6b563-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="6b563-115">Como parte do processo I-9, os funcionários devem apresentar a documentação que mostra ao empregador a sua identidade e autorização para trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b563-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="6b563-116">O site de Serviços de Imigração e Cidadania dos EUA contém informações sobre quais documentos são aceitáveis, e a qual lista eles pertencem.</span><span class="sxs-lookup"><span data-stu-id="6b563-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="6b563-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="6b563-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="6b563-118">No campo Formulário, insira o número do formulário oficial para o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="6b563-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="6b563-119">Exemplo: ID da escola.</span><span class="sxs-lookup"><span data-stu-id="6b563-119">Example: School ID.</span></span>
    * <span data-ttu-id="6b563-120">Os números do formulário oficial podem ser encontrados no site de Serviços de Imigração e Cidadania dos EUA.</span><span class="sxs-lookup"><span data-stu-id="6b563-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="6b563-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="6b563-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="6b563-122">Marque ou desmarque caixa de seleção Ativo.</span><span class="sxs-lookup"><span data-stu-id="6b563-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="6b563-123">No campo Data de validade, defina a data como '27/10/2019'.</span><span class="sxs-lookup"><span data-stu-id="6b563-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="6b563-124">A data de validade é opcional.</span><span class="sxs-lookup"><span data-stu-id="6b563-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="6b563-125">Selecione a agência que emitiu o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="6b563-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="6b563-126">Exemplo: Território/província</span><span class="sxs-lookup"><span data-stu-id="6b563-126">Example: Province/territory</span></span>
10. <span data-ttu-id="6b563-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6b563-127">Click Save.</span></span>


