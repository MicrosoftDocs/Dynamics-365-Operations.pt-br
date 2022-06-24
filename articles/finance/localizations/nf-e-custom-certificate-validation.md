---
title: Validação de certificado personalizado de NF-e
description: Este artigo fornece informações sobre como habilitar e usar o certificado personalizado da NF-e.
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
ms.openlocfilehash: 3d69aa9d6d0ce33fbed9ba1c7a7af441e14d0d07
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875894"
---
# <a name="nf-e-custom-certificate-validation"></a>Validação de certificado personalizado de NF-e

[!include [banner](../includes/banner.md)]

A propriedade **Finalidade de autenticação do servidor** dos certificados emitidos pela Autoridade de Certificação Raiz do Brasil está desativada por padrão e deve ser habilitada manualmente. Em algumas circunstâncias, a atualização automática de certificado pode alterar essa propriedade para que não seja mais habilitada. Se isso acontecer, a conexão TLS será afetada e não será mais confiável. A capacidade de emitir NF-e (modelo 55 de documento fiscal eletrônico brasileiro) em ambientes de produção para os Estados de Minas Gerais (MG) e Paraná (PR) também será afetada.

Para habilitar a correção para a **Validação do certificado personalizado de NF-e**, acesse **Gerenciamento de recursos**. Esse recurso permite uma solução alternativa para as validações de certificados V5 e V10 e permite uma conexão confiável com os serviços Web, o que é necessário para a transmissão segura da NF-e e o recebimento da autorização da SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
