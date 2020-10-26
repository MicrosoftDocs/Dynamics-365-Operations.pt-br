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
ms.sourcegitcommit: 3c88c4adafb78b807842b0b41c69b19cf2b7aa23
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973083"
---
# <a name="nf-e-custom-certificate-validation"></a>Validação de certificado personalizado de NF-e

[!include [banner](../includes/banner.md)]

Quando você ativa o recurso de verificação de certificado personalizado da NF-e, a validação personalizada permite uma conexão com os serviços Web. Esta conexão é necessária para transmitir NF-e e receber autorização da SEFAZ.

A propriedade **Finalidade de Autenticação de Servidor** do certificado V5 é emitida pela autoridade de certificação raiz do Brasil. Essa propriedade é desativada por padrão e deve ser habilitada manualmente. Em algumas circunstâncias, a atualização automática de certificado pode alterar essa propriedade para que não seja mais habilitada. Se isso acontecer, a conexão TLS será afetada e não será mais confiável. A capacidade de emitir NF-e em ambientes de produção para os Estados de Minas Gerais (MG) e Paraná (PR) também será afetada.

Esta atualização permite uma solução alternativa para a validação de certificados, o que significa que é possível estabelecer uma comunicação segura.


