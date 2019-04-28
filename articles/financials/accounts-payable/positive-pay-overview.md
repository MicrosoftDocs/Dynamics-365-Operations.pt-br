---
title: Visão geral de pagamento positivo
description: Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 51603df2847f4c21910a718186accca27e30ca67
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2019
ms.locfileid: "896502"
---
# <a name="positive-pay-overview"></a><span data-ttu-id="5752e-103">Visão geral de pagamento positivo</span><span class="sxs-lookup"><span data-stu-id="5752e-103">Positive pay overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5752e-104">Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.</span><span class="sxs-lookup"><span data-stu-id="5752e-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="5752e-105">O pagamento positivo é usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.</span><span class="sxs-lookup"><span data-stu-id="5752e-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="5752e-106">Os arquivos de pagamento positivo podem ajudar os bancos a impedir fraudes com cheques.</span><span class="sxs-lookup"><span data-stu-id="5752e-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="5752e-107">Você configura o pagamento positivo para gerar uma lista eletrônica de cheques todas as vezes que cheques forem impressos.</span><span class="sxs-lookup"><span data-stu-id="5752e-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="5752e-108">Em seguida, quando um cheque é apresentado ao banco, o banco compara o cheque à lista de cheques emitidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5752e-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="5752e-109">Se o cheque corresponder a um cheque na lista, o banco o liberará.</span><span class="sxs-lookup"><span data-stu-id="5752e-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="5752e-110">Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.</span><span class="sxs-lookup"><span data-stu-id="5752e-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="5752e-111">O pagamento positivo é conhecido também como SafePay.</span><span class="sxs-lookup"><span data-stu-id="5752e-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="5752e-112">Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque.</span><span class="sxs-lookup"><span data-stu-id="5752e-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="5752e-113">Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco.</span><span class="sxs-lookup"><span data-stu-id="5752e-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="5752e-114">Os arquivos de pagamento positivos são baixados de acordo com as instruções de download para o navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="5752e-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="5752e-115">Os arquivos de pagamento positivo são criados usando entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="5752e-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="5752e-116">Antes de gerar um arquivo de pagamento positivo, você deverá configurar os formatos de transformação para o XML que traduz os dados em um formato que o banco pode consumir.</span><span class="sxs-lookup"><span data-stu-id="5752e-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="5752e-117">Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo.</span><span class="sxs-lookup"><span data-stu-id="5752e-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="5752e-118">Depois de gerar pagamentos, você poderá gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária.</span><span class="sxs-lookup"><span data-stu-id="5752e-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="5752e-119">Como alternativa, você pode gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5752e-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="5752e-120">Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco.</span><span class="sxs-lookup"><span data-stu-id="5752e-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="5752e-121">Em seguida, será possível confirmar o arquivo de pagamento positivo no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5752e-121">You can then confirm the positive pay file in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="5752e-122">Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo.</span><span class="sxs-lookup"><span data-stu-id="5752e-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="5752e-123">Em seguida, para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido.</span><span class="sxs-lookup"><span data-stu-id="5752e-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="5752e-124">Para obter mais informações, consulte [Configurar e gerar arquivos de pagamento positivo](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="5752e-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>



