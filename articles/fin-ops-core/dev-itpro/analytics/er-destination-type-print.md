---
title: Tipo de destino de ER da impressora
description: Este tópico explica como configurar um destino de impressora para cada componente de PASTA ou ARQUIVO de um formato de relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 19613d9dfba21d591d96a2df45bedb80c043b3a7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561941"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="a404d-103">Destino da impressora</span><span class="sxs-lookup"><span data-stu-id="a404d-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a404d-104">Você pode enviar um documento gerado diretamente para uma impressora da rede para impressão direta.</span><span class="sxs-lookup"><span data-stu-id="a404d-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a404d-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a404d-105">Prerequisites</span></span>

<span data-ttu-id="a404d-106">Antes de começar, você deve instalar e configurar o Agente de Roteamento de Documentos e registrar as impressoras da rede.</span><span class="sxs-lookup"><span data-stu-id="a404d-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="a404d-107">Para obter mais informações, consulte [Instalar o Agente de Roteamento de Documentos para habilitar a impressão de rede](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="a404d-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="a404d-108">Disponibilizar o destino da impressora</span><span class="sxs-lookup"><span data-stu-id="a404d-108">Make the Printer destination available</span></span>

<span data-ttu-id="a404d-109">Para disponibilizar o destino da **Impressora** na instância atual do Microsoft Dynamics 365 Finance, vá para o espaço de trabalho **Gerenciamento de recursos** e ative os seguintes recursos, nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="a404d-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="a404d-110">Converta os documentos de saída do Relatório Eletrônico de formatos do Microsoft Office em PDF.</span><span class="sxs-lookup"><span data-stu-id="a404d-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="a404d-111">Agente de Roteamento de Documentos como destino do Relatório Eletrônico para documentos de saída</span><span class="sxs-lookup"><span data-stu-id="a404d-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="a404d-112">[![Ativando o recurso de destino da impressora do ER no Gerenciamento de recursos](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="a404d-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="a404d-113">Aplicabilidade</span><span class="sxs-lookup"><span data-stu-id="a404d-113">Applicability</span></span>

<span data-ttu-id="a404d-114">O destino da **Impressora** pode ser configurado somente para componentes de arquivo usados para gerar saída no formato PDF imprimível (elementos de formato de arquivo PDF ou Fusão de PDFs) ou Microsoft Office Excel/Word (arquivo do Excel).</span><span class="sxs-lookup"><span data-stu-id="a404d-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="a404d-115">Quando a saída é gerada no formato PDF, ela é enviada para uma impressora.</span><span class="sxs-lookup"><span data-stu-id="a404d-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="a404d-116">Quando a saída é gerada no formato do Microsoft Office, ela é automaticamente convertida no formato PDF e enviada a uma impressora.</span><span class="sxs-lookup"><span data-stu-id="a404d-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="a404d-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="a404d-117">Limitations</span></span>

<span data-ttu-id="a404d-118">O destino da **Impressora** é implementado somente para implantações em nuvem.</span><span class="sxs-lookup"><span data-stu-id="a404d-118">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="a404d-119">Usar o destino da Impressora</span><span class="sxs-lookup"><span data-stu-id="a404d-119">Use the Printer destination</span></span>

1. <span data-ttu-id="a404d-120">Defina a opção **Habilitado** como **Sim** para enviar um documento gerado para uma impressora.</span><span class="sxs-lookup"><span data-stu-id="a404d-120">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="a404d-121">No campo **Nome da impressora**, selecione a impressora de rede necessária.</span><span class="sxs-lookup"><span data-stu-id="a404d-121">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="a404d-122">Defina a opção **Salvar em arquivo de impressão?** como **Sim** para armazenar a saída gerada no arquivo de impressão, de modo que ela esteja disponível para impressão futura.</span><span class="sxs-lookup"><span data-stu-id="a404d-122">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="a404d-123">Para acessar posteriormente a saída arquivada, vá para **Administração da organização** \> **Consultas e relatórios** \> **Arquivo de relatório**.</span><span class="sxs-lookup"><span data-stu-id="a404d-123">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="a404d-124">[![Usando o destino da Impressora](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="a404d-124">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="a404d-125">A opção **Converter em PDF** não precisa ser ativada quando você configura o destino da **Impressora**.</span><span class="sxs-lookup"><span data-stu-id="a404d-125">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="a404d-126">A conversão em PDF para fins de impressão ocorrerá mesmo que a opção seja desativada.</span><span class="sxs-lookup"><span data-stu-id="a404d-126">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="a404d-127">Para usar uma [orientação de página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica ao imprimir um documento de saída no formato Excel, você deve ativar a opção **Converter para PDF**.</span><span class="sxs-lookup"><span data-stu-id="a404d-127">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="a404d-128">Quando você definir a opção **Converter para PDF** como **Sim**, o campo **Orientação da página** ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="a404d-128">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="a404d-129">No campo **Orientação da página**, você pode selecionar uma orientação de página.</span><span class="sxs-lookup"><span data-stu-id="a404d-129">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a404d-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a404d-130">Additional resources</span></span>

- [<span data-ttu-id="a404d-131">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="a404d-131">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="a404d-132">Destinos de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="a404d-132">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
