---
title: Validação de certificado personalizado de NF-e
description: Este tópico fornece informações sobre como habilitar e usar o certificado personalizado da NF-e.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440285"
---
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="05d60-103">Validação de certificado personalizado de NF-e</span><span class="sxs-lookup"><span data-stu-id="05d60-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05d60-104">Quando você ativa o recurso de verificação de certificado personalizado da NF-e, a validação personalizada permite uma conexão com os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="05d60-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="05d60-105">Esta conexão é necessária para transmitir NF-e e receber autorização da SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="05d60-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="05d60-106">A propriedade **Finalidade de Autenticação de Servidor** do certificado V5 é emitida pela autoridade de certificação raiz do Brasil.</span><span class="sxs-lookup"><span data-stu-id="05d60-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="05d60-107">Essa propriedade é desativada por padrão e deve ser habilitada manualmente.</span><span class="sxs-lookup"><span data-stu-id="05d60-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="05d60-108">Em algumas circunstâncias, a atualização automática de certificado pode alterar essa propriedade para que não seja mais habilitada.</span><span class="sxs-lookup"><span data-stu-id="05d60-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="05d60-109">Se isso acontecer, a conexão TLS será afetada e não será mais confiável.</span><span class="sxs-lookup"><span data-stu-id="05d60-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="05d60-110">A capacidade de emitir NF-e em ambientes de produção para os Estados de Minas Gerais (MG) e Paraná (PR) também será afetada.</span><span class="sxs-lookup"><span data-stu-id="05d60-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="05d60-111">Esta atualização permite uma solução alternativa para a validação de certificados, o que significa que é possível estabelecer uma comunicação segura.</span><span class="sxs-lookup"><span data-stu-id="05d60-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>


