---
title: "Visão geral de pagamento positivo"
description: "Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5b88b940e7a590ff99b6ab8a99ce45d32dfe0505
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="positive-pay-overview"></a><span data-ttu-id="87c3f-103">Visão geral de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="87c3f-103">Positive pay overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="87c3f-104">Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.</span><span class="sxs-lookup"><span data-stu-id="87c3f-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="87c3f-105">O pagamento positivo é usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.</span><span class="sxs-lookup"><span data-stu-id="87c3f-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="87c3f-106">Os arquivos de pagamento positivo podem ajudar os bancos a impedir fraudes com cheques.</span><span class="sxs-lookup"><span data-stu-id="87c3f-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="87c3f-107">Você configura o pagamento positivo para gerar uma lista eletrônica de cheques todas as vezes que cheques forem impressos.</span><span class="sxs-lookup"><span data-stu-id="87c3f-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="87c3f-108">Em seguida, quando um cheque é apresentado ao banco, o banco compara o cheque à lista de cheques emitidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="87c3f-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="87c3f-109">Se o cheque corresponder a um cheque na lista, o banco o liberará.</span><span class="sxs-lookup"><span data-stu-id="87c3f-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="87c3f-110">Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.</span><span class="sxs-lookup"><span data-stu-id="87c3f-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="87c3f-111">O pagamento positivo é conhecido também como SafePay.</span><span class="sxs-lookup"><span data-stu-id="87c3f-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="87c3f-112">Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque.</span><span class="sxs-lookup"><span data-stu-id="87c3f-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="87c3f-113">Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco.</span><span class="sxs-lookup"><span data-stu-id="87c3f-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="87c3f-114">Os arquivos de pagamento positivos são baixados de acordo com as instruções de download para o navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="87c3f-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="87c3f-115">Os arquivos de pagamento positivo são criados usando entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="87c3f-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="87c3f-116">Antes de gerar um arquivo de pagamento positivo, você deverá configurar os formatos de transformação para o XML que traduz os dados em um formato que o banco pode consumir.</span><span class="sxs-lookup"><span data-stu-id="87c3f-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="87c3f-117">Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="87c3f-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="87c3f-118">Depois de gerar pagamentos, você poderá gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária.</span><span class="sxs-lookup"><span data-stu-id="87c3f-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="87c3f-119">Como alternativa, você pode gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="87c3f-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="87c3f-120">Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco.</span><span class="sxs-lookup"><span data-stu-id="87c3f-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="87c3f-121">Então, será possível confirmar o arquivo de pagamento positivo no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="87c3f-121">You can then confirm the positive pay file in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="87c3f-122">Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo.</span><span class="sxs-lookup"><span data-stu-id="87c3f-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="87c3f-123">Em seguida, para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido.</span><span class="sxs-lookup"><span data-stu-id="87c3f-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="87c3f-124">Para obter mais informações, consulte [Configurar e gerar arquivos de pagamento positivo](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="87c3f-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>




