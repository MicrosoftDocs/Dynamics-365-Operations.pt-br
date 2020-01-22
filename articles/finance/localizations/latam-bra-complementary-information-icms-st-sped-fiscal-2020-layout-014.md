---
title: SPED fiscal 2020 - informações complementares do ICMS-ST para o layout 014 do SPED fiscal 2020
description: Este tópico fornece informações sobre como utilizar o complemento e a compensação do ICMS-ST para o ano civil de 2020.
author: gionoder
manager: AnnBe
ms.date: 12/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 972961647d24e45a05f86a21544319a4226b6572
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915285"
---
# <a name="sped-fiscal-2020---complementary-information-of-the-icms-st-for-sped-fiscal-2020-layout-014"></a><span data-ttu-id="5da34-103">SPED fiscal 2020 - informações complementares do ICMS-ST para o layout 014 do SPED fiscal 2020</span><span class="sxs-lookup"><span data-stu-id="5da34-103">SPED fiscal 2020 - Complementary information of the ICMS-ST for Sped fiscal 2020 layout 014</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5da34-104">Quando uma empresa desejar utilizar o complemento e a compensação do ICMS-ST para o ano civil de 2020, ela precisará começar a registrar as informações adicionais do ICMS-ST durante o recebimento do modelo 55 de notas fiscais eletrônicas, a partir de 1º de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="5da34-104">When a company wants to utilize the complement and compensation of the ICMS-ST for the 2020 calendar year, they need to start registering the additional ICMS-ST information during the receipt of electronic fiscal documents model 55 starting January 1, 2020.</span></span>

<span data-ttu-id="5da34-105">Somente para o Dynamics 365 Finance, esse recurso deve ser habilitado usando o Gerenciamento de Recursos.</span><span class="sxs-lookup"><span data-stu-id="5da34-105">For Dynamics 365 Finance only, this feature must be enabled using Feature Management.</span></span> <span data-ttu-id="5da34-106">Conclua as seguintes etapas para habilitar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="5da34-106">Complete the following steps to enable this feature.</span></span>

1. <span data-ttu-id="5da34-107">No Finance, no painel **Início**, selecione **Gerenciamento de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="5da34-107">In Finance, on the **Home** dashboard, select **Feature Management**.</span></span>
3. <span data-ttu-id="5da34-108">Procure e selecione *Informações complementares do ICMS-ST*.</span><span class="sxs-lookup"><span data-stu-id="5da34-108">Search for and select *Complementary information of ICMS-ST*.</span></span>
4. <span data-ttu-id="5da34-109">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="5da34-109">Select **Enable now**.</span></span>

<span data-ttu-id="5da34-110">Quando a nota fiscal de fornecedor ou de transferência incluir um produto sujeito à tributação ICMS-ST na UF (estado) do endereço de destino, e se o estabelecimento fiscal de recebimento utilizar o complemento e a compensação do ICMS-ST, os seguintes atributos da nota fiscal devem ser inseridos.</span><span class="sxs-lookup"><span data-stu-id="5da34-110">When the vendor fiscal document or transfer fiscal document includes a product that is subject to ICMS-ST taxation on the UF (state) of the destination address, and if the receiving fiscal establishment utilizes the complement and compensation of the ICMS-ST, the following attributes of the fiscal document must be entered.</span></span>

- <span data-ttu-id="5da34-111">O participante responsável pela retenção do ICMS-ST:</span><span class="sxs-lookup"><span data-stu-id="5da34-111">The party responsible for withholding the ICMS-ST:</span></span>
        
    - <span data-ttu-id="5da34-112">**Direto** - quando um emissor de estabelecimento fiscal ou de terceiros da nota fiscal é diretamente responsável pela retenção do ICMS-ST para o produto presente na nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="5da34-112">**Direct** - When a third-party or fiscal establishment issuer of the fiscal document is directly responsible for withholding the ICMS-ST for the product that is present in the fiscal document.</span></span>
    - <span data-ttu-id="5da34-113">**Indireto** - quando um emissor de estabelecimento fiscal ou de terceiros da nota fiscal já recebeu o produto e o ICMS-ST foi retido de sua cadeia de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="5da34-113">**Indirect** - When a third-party or fiscal establishment issuer of the fiscal document has already received the product and the ICMS-ST has been withheld from its supply chain.</span></span>
    - <span data-ttu-id="5da34-114">**Próprio declarante** - quando o estabelecimento fiscal de recebimento é responsável pela retenção do ICMS-ST que deveria ter sido retido pelo emissor de terceiros, mas não foi.</span><span class="sxs-lookup"><span data-stu-id="5da34-114">**Own declarant** - When the receiving fiscal establishment is responsible for withholding the ICMS-ST that should have been withheld by the third-party issuer, but was not.</span></span>
    
- <span data-ttu-id="5da34-115">O modo de pagamento de coleta do ICMS-ST:</span><span class="sxs-lookup"><span data-stu-id="5da34-115">The ICMS-ST collection payment mode:</span></span>
        
    - <span data-ttu-id="5da34-116">**Documento do estado da coleta** - quando o ICMS-ST é retido por meio da apuração de imposto ICMS-ST regular e o pagamento ocorre após o final do período da transação.</span><span class="sxs-lookup"><span data-stu-id="5da34-116">**State document of collection** - When the ICMS-ST is withheld through the regular ICMS-ST tax assessment and payment occurs after the end of the transaction period.</span></span>
    - <span data-ttu-id="5da34-117">**GNRE** - quando a nota fiscal de recebimento é acompanhada por um GNRE que mostra que o ICMS-ST devido já foi retido e pago pelo emissor da nota fiscal quando o documento foi gerado.</span><span class="sxs-lookup"><span data-stu-id="5da34-117">**GNRE** - When the receiving fiscal document is accompanied by a GNRE that shows the due ICMS-ST was already withheld and paid by the fiscal document issuer when the document was generated.</span></span>
    
- <span data-ttu-id="5da34-118">O número de pagamento de coleta do ICMS-ST:</span><span class="sxs-lookup"><span data-stu-id="5da34-118">The ICMS-ST collection payment number:</span></span> 
    - <span data-ttu-id="5da34-119">O número de GNRE usado para liquidar o valor do pagamento do ICMS-ST pelo emissor da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="5da34-119">The number of GNRE used to settle the ICMS-ST payment amount by the fiscal document issuer.</span></span>

<span data-ttu-id="5da34-120">Quando uma linha de nota fiscal incluir um produto sujeito ao ICMS-ST no destino de recebimento, a retenção do ICMS-ST será determinada analisando o código de tributação do ICMS-ST na nota fiscal de recebimento.</span><span class="sxs-lookup"><span data-stu-id="5da34-120">When a fiscal document line that includes a product that is subject to ICMS-ST on the receiving destination, the withholding of the ICMS-ST will be determined by reviewing the taxation code of the ICMS-ST in the receiving fiscal document.</span></span> <span data-ttu-id="5da34-121">Isso é comparado à linha equivalente do ICMS-ST no XML da NF-e emitida pelo remetente da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="5da34-121">This is compared with the equivalent ICMS-ST line in the NF-e XML issued by the sender of the fiscal document.</span></span>

![GSTINs anexados a um grupo de registro de impostos com código de tributação indireta](media/complementary-info-figure-01.PNG)

![GSTINs anexados a um grupo de registro de impostos com código de tributação direta](media/complementary-info-figure-02.PNG)

<span data-ttu-id="5da34-124">Um valor padrão para o campo **Responsável pela retenção do ICMS-ST** pode ser configurado concluindo as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5da34-124">A default value for the **Responsible for withholding the ICMS-ST** field can be set up by completing the following steps.</span></span>

1. <span data-ttu-id="5da34-125">Acesse **Imposto** > **Configurar** > **Imposto sobre vendas** > **Responsável pela retenção do ICMS-ST**.</span><span class="sxs-lookup"><span data-stu-id="5da34-125">Go to **Tax** > **Set up** > **Sales tax** > **Responsible for withholding the ICMS-ST**.</span></span>
2. <span data-ttu-id="5da34-126">No campo **Código CFOP**, selecione **Tabela**, **Grupo** ou **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="5da34-126">In the **CFOP Code** field, select **Table**, **Group**, or **All**.</span></span>
3. <span data-ttu-id="5da34-127">No campo **Relação CFOP**, insira a relação definida pelo Código CFOP.</span><span class="sxs-lookup"><span data-stu-id="5da34-127">In the **CFOP Relation** field, enter the relation defined by the CFOP Code.</span></span>
4. <span data-ttu-id="5da34-128">No campo **Emissor da nota fiscal**, selecione **Estabelecimento fiscal** ou **Terceiro** para definir a origem da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="5da34-128">In the **Fiscal document issuer** field, select **Fiscal establishment** or **Third party** to define the origin of the fiscal document.</span></span>
5. <span data-ttu-id="5da34-129">No campo **Código de tributação do destinatário**, insira o código de tributação do ICMS-ST configurado para a linha de nota fiscal de recebimento na qual o produto está sujeito à substituição tributária do ICMS.</span><span class="sxs-lookup"><span data-stu-id="5da34-129">In the **Receiver taxation code** field, enter the taxation code of the ICMS-ST configured for the receiving fiscal document line where the product is subject to ICMS tax substitution.</span></span>
6. <span data-ttu-id="5da34-130">No campo **Código de tributação do remetente**, insira o código de tributação do ICMS-ST presente na linha de nota fiscal do emissor na qual o produto está sujeito à substituição tributária do ICMS.</span><span class="sxs-lookup"><span data-stu-id="5da34-130">In the **Sender taxation code** field, enter the taxation code of the ICMS-ST present in the issuer's fiscal document line, where the product is subject to ICMS tax substitution.</span></span>
7. <span data-ttu-id="5da34-131">Para uma relação CFOP e um Emissor da nota fiscal, e com base na relação entre o **Código de tributação do destinatário** e o **Código de tributação do remetente**, no campo **Responsável pela retenção do ICMS-ST**, selecione **Direto**, **Indireto** ou **Próprio declarante**.</span><span class="sxs-lookup"><span data-stu-id="5da34-131">For a CFOP relation and Fiscal document issuer, and based on the relation between the **Receiver taxation code** and the **Sender taxation code**, in the **Responsible for withholding the ICMS-ST** field, select **Direct**, **Indirect** or **Own declarant**.</span></span>

<span data-ttu-id="5da34-132">Os novos campos, **Responsável pela retenção do ICMS-ST**, **Modo de pagamento de coleta do ICMS-ST** e **Número de pagamento de coleta do ICMS-ST**, estão incluídos nas seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="5da34-132">The new fields, **Responsible for withholding the ICMS-ST**, **ICMS-ST collection payment mode**, and **ICMS-ST collection payment number** are included on the following pages:</span></span>

- <span data-ttu-id="5da34-133">Página **Faturas de fornecedor** na guia **Informações fiscais**.</span><span class="sxs-lookup"><span data-stu-id="5da34-133">**Vendor invoices** page on the **Fiscal information** tab.</span></span>
- <span data-ttu-id="5da34-134">Página **Ordem de transferência** na guia **Informações fiscais de recebimento**.</span><span class="sxs-lookup"><span data-stu-id="5da34-134">**Transfer order** page on the **Fiscal information of receiving** tab.</span></span>
- <span data-ttu-id="5da34-135">Página **Fatura de cliente** na guia **Informações fiscais**. Isso é somente para devoluções de clientes.</span><span class="sxs-lookup"><span data-stu-id="5da34-135">**Customer invoice** page on the **Fiscal information** tab. This is only for customer returns.</span></span>

> [!NOTE]
> <span data-ttu-id="5da34-136">Durante o recebimento de uma nota fiscal, quando o ICMS-ST é tributável usando o código de tributação 10, apesar de estarem inseridas no campo **Responsável pela retenção do ICMS-ST**, as informações financeiras e de avaliação de custo não são incluídas no escopo da localização.</span><span class="sxs-lookup"><span data-stu-id="5da34-136">During the receipt of a fiscal document, when the ICMS-ST is taxable by using taxation code 10, even though it is entered in the **Responsible for withholding ICMS-ST** field, the financial and costing information is not included in the scope of localization.</span></span>
