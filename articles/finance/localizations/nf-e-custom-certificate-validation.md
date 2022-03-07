---
title: Validação de certificado personalizado de NF-e
description: Este tópico fornece informações sobre como habilitar e usar o certificado personalizado da NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755582"
---
# <a name="nf-e-custom-certificate-validation"></a>Validação de certificado personalizado de NF-e

[!include [banner](../includes/banner.md)]

A propriedade **Finalidade de autenticação do servidor** dos certificados emitidos pela Autoridade de Certificação Raiz do Brasil está desativada por padrão e deve ser habilitada manualmente. Em algumas circunstâncias, a atualização automática de certificado pode alterar essa propriedade para que não seja mais habilitada. Se isso acontecer, a conexão TLS será afetada e não será mais confiável. A capacidade de emitir NF-e (modelo 55 de documento fiscal eletrônico brasileiro) em ambientes de produção para os Estados de Minas Gerais (MG) e Paraná (PR) também será afetada.

Para habilitar a correção para a **Validação do certificado personalizado de NF-e**, acesse **Gerenciamento de recursos**. Esse recurso permite uma solução alternativa para as validações de certificados V5 e V10 e permite uma conexão confiável com os serviços Web, o que é necessário para a transmissão segura da NF-e e o recebimento da autorização da SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
