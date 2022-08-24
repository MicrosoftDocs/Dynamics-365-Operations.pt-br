---
title: Tornar o delimitador do plano de contas exclusivo
description: Este artigo explica que não é possível ter o mesmo delimitador para o plano de contas e valores de dimensão. Você deve alterar os valores do delimitador após a atualização.
author: RyanCCarlson2
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: RCarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.openlocfilehash: 2184d26e104f803ae1bf59155cf18f560652f318
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292486"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>O delimitador do plano de contas deve ser exclusivo

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics AX 2012, era possível usar o mesmo delimitador para o plano de contas e os valores de dimensão. Nas versões atuais de finanças e operações, você não pode ter o mesmo delimitador para o plano de contas e para os nomes ou valores de dimensão. Se houver um delimitador duplicado, você poderá alterá-lo após a atualização. 

## <a name="update-delimiter"></a>Atualizar delimitador
Se houver um conflito com o plano de contas, o delimitador do plano de contas e o formato da ID de projeto/subprojeto poderá ser alterado. Nenhum outro delimitador de dimensão pode ser alterado. 
- Você pode alterar o delimitador do plano de contas depois da atualização em **Parâmetros de contabilidade** > **Plano de contas e dimensões** > **Alterar delimitador**. 
- Se o único conflito for com o formato da ID do projeto/subprojeto, você poderá alterar esse valor em **Parâmetros de gerenciamento e contabilidade de projetos** > **Geral** > **Modificar o formato do subprojeto**. 

### <a name="other-considerations"></a>Outras considerações
Semelhante à ID de projeto/subprojeto, todos os outros registros de dados mestres usados como dimensões financeiras, como fornecedores ou clientes, não devem ter valores de ID de conta que usam o mesmo caractere que o delimitador do plano de contas. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Como determinar se o ambiente requer delimitadores atualizados 
Se os delimitadores em seu ambiente atualizado estiverem em conflito, é possível que haja instabilidade ao inserir valores em um controle de entrada segmentada ou em um controle entrada de dimensão. Isso significa que você sempre precisará usar pesquisas ou um menu suspenso ao inserir combinações de conta e dimensão.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

