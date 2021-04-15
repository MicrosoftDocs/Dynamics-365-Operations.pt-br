---
title: Adicionar um código QR ou código de barras a emails transacionais e de recebimento
description: Este tópico explica como inserir códigos QR e códigos de barras que representam IDs de ordens em emails transacionais e de recebimento no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797494"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="851a7-103">Adicionar um código QR ou código de barras a emails transacionais e de recebimento</span><span class="sxs-lookup"><span data-stu-id="851a7-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="851a7-104">Este tópico explica como inserir códigos QR e códigos de barras que representam IDs de ordens em emails transacionais e de recebimento no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="851a7-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="851a7-105">Você pode incluir facilmente os códigos QR e os códigos de barras em emails transacionais para ajudar a acelerar o processo de pesquisa de ordens em um ambiente de varejo.</span><span class="sxs-lookup"><span data-stu-id="851a7-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="851a7-106">Para inserir códigos QR e códigos de barras em emails, você usa uma marca HTML **\<img\>** que solicita um código QR ou uma imagem de código de barras de um serviço de geração e renderização.</span><span class="sxs-lookup"><span data-stu-id="851a7-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="851a7-107">A Microsoft não fornece esse serviço.</span><span class="sxs-lookup"><span data-stu-id="851a7-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="851a7-108">No entanto, há muitos serviços gratuitos ou baratos que podem servir códigos QR ou códigos de barras gerados dinamicamente com base em um valor que é passado em uma cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="851a7-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="851a7-109">Adicionar um código QR ou código de barras a um email transacional</span><span class="sxs-lookup"><span data-stu-id="851a7-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="851a7-110">Para inserir um código QR ou código de barras em um email transacional enviado como parte de uma compra de comércio eletrônico, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="851a7-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="851a7-111">Abra o código HTML de origem para o modelo de email transacional e adicione uma marca HTML **\<img\>** que aponte para o código QR ou o serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="851a7-112">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="851a7-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="851a7-113">Veja aqui uma explicação do exemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="851a7-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="851a7-114">**SEU\_SERVIÇO DE\_CÓDIGO\_QR DE\_CÓDIGO DE\_BARRAS** representa o domínio do seu código QR ou serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="851a7-115">**dados** representa o parâmetro que o código QR ou o serviço de código de barras usa para receber o conteúdo que deve ser processado como um código QR ou um código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="851a7-116">O valor **%salesid%** deve ser atribuído a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="851a7-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="851a7-117">Neste exemplo, observe que o valor também é usado como texto alternativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="851a7-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="851a7-118">**param1** e **param2** representam parâmetros opcionais adicionais.</span><span class="sxs-lookup"><span data-stu-id="851a7-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="851a7-119">Acesse **Varejo e Comércio \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização** e carregue o HTML atualizado no modelo de email transacional apropriado.</span><span class="sxs-lookup"><span data-stu-id="851a7-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="851a7-120">Os parâmetros podem ser diferentes entre o código QR e os provedores de serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="851a7-121">Portanto, lembre-se de contatar o provedor de serviços para confirmar os parâmetros aos quais você deve atribuir valores.</span><span class="sxs-lookup"><span data-stu-id="851a7-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="851a7-122">Adicionar um código QR ou código de barras a um email de recebimento</span><span class="sxs-lookup"><span data-stu-id="851a7-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="851a7-123">Para inserir um código QR ou código de barras em um email de recebimento que pode ser enviado depois que uma compra é feita no ponto de venda (PDV), siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="851a7-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="851a7-124">Abra o código HTML de origem para o modelo de email de recebimento e adicione uma marca HTML **\<img\>** que aponte para o código QR ou o serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="851a7-125">Veja um exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="851a7-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="851a7-126">Veja aqui uma explicação do exemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="851a7-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="851a7-127">**SEU\_SERVIÇO DE\_CÓDIGO\_QR DE\_CÓDIGO DE\_BARRAS** representa o domínio do seu código QR ou serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="851a7-128">**dados** representa o parâmetro que o código QR ou o serviço de código de barras usa para receber o conteúdo que deve ser processado como um código QR ou um código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="851a7-129">O valor **%receiptid%** deve ser atribuído a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="851a7-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="851a7-130">Neste exemplo, observe que o valor também é usado como texto alternativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="851a7-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="851a7-131">**param1** e **param2** representam parâmetros opcionais adicionais.</span><span class="sxs-lookup"><span data-stu-id="851a7-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="851a7-132">Acesse **Varejo e Comércio \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização** e carregue o HTML atualizado no modelo de email com o **emailrecpt** da ID do email.</span><span class="sxs-lookup"><span data-stu-id="851a7-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="851a7-133">Os parâmetros podem ser diferentes entre o código QR e os provedores de serviço de código de barras.</span><span class="sxs-lookup"><span data-stu-id="851a7-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="851a7-134">Portanto, lembre-se de contatar o provedor de serviços para confirmar os parâmetros aos quais você deve atribuir valores.</span><span class="sxs-lookup"><span data-stu-id="851a7-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="851a7-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="851a7-135">Additional resources</span></span>

[<span data-ttu-id="851a7-136">Enviar recibos por email do Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="851a7-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="851a7-137">Criar modelos de email para eventos transacionais</span><span class="sxs-lookup"><span data-stu-id="851a7-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
