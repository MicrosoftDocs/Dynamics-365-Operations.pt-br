---
title: Solucionar problemas de atualização e migração para gerenciamento avançado de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao atualizar e migrar para o gerenciamento avançado de depósito.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 12dcadae2a65d71614a2eee9468ec93cac284a7b
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907878"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Solucionar problemas de atualização e migração para gerenciamento avançado de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao atualizar e migrar para o gerenciamento avançado de depósito.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Recebo a seguinte mensagem de erro: "java.security.cert.certPathValidatorException: A âncora de confiança para o caminho de certificação não foi encontrada."

### <a name="issue-description"></a>Descrição do problema

Você recebe esta mensagem de erro no aplicativo móvel Gerenciamento de Depósito, porque os certificados autoassinados não são confiáveis no Android 8 ou posterior em ambientes locais.

### <a name="issue-resolution"></a>Resolução do problema

Use uma autoridade de certificação (CA) externa (pública). Uma correção para esse problema está disponível na versão 1.9.0.0 do aplicativo de depósito. Para obter mais informações sobre esse problema e como corrigi-lo, consulte [Solucionar problemas de conexão do aplicativo móvel Gerenciamento de Depósito](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Qual é o processo aprovado para passar do depósito básico para o avançado?

### <a name="issue-description"></a>Descrição do problema

No momento, você está executando o gerenciamento de estoque e usando a funcionalidade de estoque básico e deseja passar para o depósito avançado para aproveitar as vantagens de dispositivos móveis, ciclos e trabalho. Contudo, você está tendo problemas ao tentar fazer essa mudança. Por exemplo, você não pode alterar seus produtos para que usem dimensões de armazenamento (site, depósito e local), porque os produtos têm transações em relação a eles. Portanto, você deve conhecer o processo aprovado para passar do depósito básico para o avançado.

### <a name="issue-resolution"></a>Resolução do problema

Para obter mais informações sobre o processo de mudança do depósito básico para o avançado, consulte as seguintes postagens e documentação no blog:

- [Habilitar processo de gerenciamento de depósito para itens e depósitos existentes](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migração do Microsoft Dynamics AX WMS para o novo depósito R3 e funcionalidade de transporte](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [Migração de item WMSI/WMS2](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Atualizar o gerenciamento de depósito do Microsoft Dynamics AX 2012 para o Supply Chain Management](./upgrade-migration-warehouse-management-processes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]