---
title: Criar provedores de configuração e marcá-los como ativos
description: As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544900"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Criar provedores de configuração e marcá-los como ativos

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE). Cada configuração RE será referida ao fornecedor como o autor da configuração. Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.


## <a name="create-a-provider"></a>Criar um fornecedor
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Provedores de configuração.
3. Clique em Novo.
    * Um registro de fornecedor tem nome e URL exclusivos. Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (http://www.litware.com) já existir.  
4. No campo Nome, digite 'Litware, Inc.'.
    * Litware, Inc.  
5. No campo Endereço na Internet, digite 'http://www.litware.com'.
    * http://www.litware.com  
6. Clique em Salvar.
7. Feche a página.

## <a name="select-as-an-active-provider"></a>Selecione como um provedor ativo
1. Selecione o fornecedor "Litware, Inc.".
2. Clique em Definir como ativo.

