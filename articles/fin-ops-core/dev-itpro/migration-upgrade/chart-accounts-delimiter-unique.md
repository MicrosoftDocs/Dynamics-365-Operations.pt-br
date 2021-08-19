---
title: O delimitador do plano de contas deve ser exclusivo
description: Este tópico explica que não é possível ter o mesmo delimitador para o plano de contas e valores de dimensão. Você deve alterar os valores do delimitador após a atualização.
author: panolte
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 5887eb2fb6a5849058981b93b3ae39be3f75a5e6ae0a8da15170ecb81792553a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719809"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>O delimitador do plano de contas deve ser exclusivo

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics AX 2012, era possível usar o mesmo delimitador para o plano de contas e os valores de dimensão. Nas versões atuais do Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão. Se houver um delimitador duplicado, você poderá alterá-lo após a atualização. 

Este recurso está disponível nas seguintes versões:
- Finance and Operations versão 8.0
- Finance and Operations versão 7.1, KB 4094701 – não é possível inserir as dimensões financeiras quando os valores de dimensão contêm o delimitador de plano de contas
- Finance and Operations versão 7.2, KB 4092967 – não é possível escolher subprojeto como dimensão quando o formato do subprojeto contém o delimitador de dimensão

## <a name="update-delimiter"></a>Atualizar delimitador
Se houver um conflito com o plano de contas, o delimitador do plano de contas e o formato da ID de projeto/subprojeto poderá ser alterado. Nenhum outro delimitador de dimensão pode ser alterado. 
- Você pode alterar o delimitador do plano de contas depois da atualização em **Parâmetros de contabilidade** > **Plano de contas e dimensões** > **Alterar delimitador**. 
- Se o único conflito for com o formato da ID do projeto/subprojeto, você poderá alterar esse valor em **Parâmetros de gerenciamento e contabilidade de projetos** > **Geral** > **Modificar o formato do subprojeto**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Como determinar se o ambiente requer delimitadores atualizados 
Se os delimitadores em seu ambiente atualizado estiverem em conflito, é possível que haja instabilidade ao inserir valores em um controle de entrada segmentada ou em um controle entrada de dimensão. Isso significa que você sempre precisará usar pesquisas ou um menu suspenso ao inserir combinações de conta e dimensão.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]