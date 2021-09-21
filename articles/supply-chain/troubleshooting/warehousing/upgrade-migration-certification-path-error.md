---
title: Erro de caminho de certificação durante o upgrade ou a migração para o WMS
description: Se o aplicativo mostrar o erro "Âncora de confiança para caminho de certificação não encontrado" durante a atualização ou a migração para o WMS, esta página fornecerá informações sobre como corrigir o problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475554"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Âncora de confiança para caminho de certificação não encontrada ao atualizar e migrar para o WMS

## <a name="symptoms"></a>Sintomas

Quando você atualizar e migrar para o WMS (gerenciamento avançado de depósito), o aplicativo Warehouse Management poderá mostrar a seguinte mensagem de erro:

> java.security.cert.certPathValidatorException: Âncora de confiança para caminho de certificação não encontrada.

## <a name="cause"></a>Causa

Isso ocorre porque os certificados autoassinados não são confiáveis no Android 8+ em ambientes locais.

## <a name="resolution"></a>Resolução

Use uma autoridade de certificação (CA) externa (pública). Uma correção para esse problema está disponível na versão 1.9.0.0 do aplicativo Warehouse Management. Para obter mais informações sobre esse problema e como corrigi-lo, consulte [Âncora de confiança para caminho de certificação não encontrada ao configurar conexão de aplicativo](certification-path-app-connection-error.md).
