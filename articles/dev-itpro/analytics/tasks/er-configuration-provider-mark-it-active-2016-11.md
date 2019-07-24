---
title: Criar provedores de configuração e marcá-los como ativos
description: Este tópico explica como um usuário atribuído à função Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um fornecedor de configuração para relatório eletrônico (RE) no Dynamics 365 for Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
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
ms.openlocfilehash: e02cd51478528db56a4f50b134fabf7f9e1dc8ea
ms.sourcegitcommit: a1354c6218b328d4d7dcc149d1339a7af10c48bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "1723111"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Criar provedores de configuração e marcá-los como ativos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como um usuário atribuído à função Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um fornecedor de configuração para relatório eletrônico (RE) no Dynamics 365 for Finance and Operations. Cada configuração RE será referida ao fornecedor como o autor da configuração. Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.

## <a name="create-a-provider"></a>Criar um fornecedor
1. Vá para o **painel de navegação** no canto superior esquerdo e selecione **Administração da organização**.
2. Vá para **Espaços de trabalho > Relatório eletrônico**.
3. Vá para **Links relacionados > Provedores de configuração**.
4. Selecione **Novo**.
    - Um registro de fornecedor tem nome e URL exclusivos. Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (https://www.litware.com) já existir.  
5. No campo Nome, digite `Litware, Inc.`.
6. No campo Endereço na Internet, digite `https://www.litware.com`.
7. Selecione **Salvar**.
8. Feche a página.

## <a name="select-as-an-active-provider"></a>Selecione como um provedor ativo
1. Selecione o fornecedor "Litware, Inc.".
2. Selecione **Definir como ativo**.

