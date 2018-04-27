--- 
title: "Criar um provedor de configuração e marcá-lo como ativo para relatórios eletrônicos (ER)"
description: "As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 018aee917c13f576759ebd812d31cbc9d83e2d1a
ms.contentlocale: pt-br
ms.lasthandoff: 02/23/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a>Criar um provedor de configuração e marcá-lo como ativo para relatórios eletrônicos (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE). Cada configuração RE será referida ao fornecedor como o autor da configuração. Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.


## <a name="create-a-provider"></a>Criar um fornecedor
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Provedores de configuração.
3. Clique em Novo.
    * Um registro de fornecedor tem nome e URL exclusivos. Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (`http://www.litware.com`) já existir.  
4. No campo Nome, digite 'Litware, Inc.'.
    * Litware, Inc.  
5. No campo Endereço na Internet, digite `http://www.litware.com`.
6. Clique em Salvar.
7. Feche a página.

## <a name="select-as-an-active-provider"></a>Selecione como um provedor ativo
1. Selecione o fornecedor "Litware, Inc.".
2. Clique em Definir como ativo.


