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
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f13e8b8229bbd9e174e5bde7858a468048ba309b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990077"
---
# <a name="nf-e-custom-certificate-validation"></a>Validação de certificado personalizado de NF-e

[!include [banner](../includes/banner.md)]

Quando você ativa o recurso de verificação de certificado personalizado da NF-e, a validação personalizada permite uma conexão com os serviços Web. Esta conexão é necessária para transmitir NF-e e receber autorização da SEFAZ.

A propriedade **Finalidade de Autenticação de Servidor** do certificado V5 é emitida pela autoridade de certificação raiz do Brasil. Essa propriedade é desativada por padrão e deve ser habilitada manualmente. Em algumas circunstâncias, a atualização automática de certificado pode alterar essa propriedade para que não seja mais habilitada. Se isso acontecer, a conexão TLS será afetada e não será mais confiável. A capacidade de emitir NF-e em ambientes de produção para os Estados de Minas Gerais (MG) e Paraná (PR) também será afetada.

Esta atualização permite uma solução alternativa para a validação de certificados, o que significa que é possível estabelecer uma comunicação segura.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]