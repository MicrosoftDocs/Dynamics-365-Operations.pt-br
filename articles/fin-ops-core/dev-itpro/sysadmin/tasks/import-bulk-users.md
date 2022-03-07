---
title: Importar usuários do Azure Active Directory
description: Este procedimento pode ser usado por administradores de sistema para importar manualmente usuários selecionados ou um grande número de usuários do Azure Active Directory.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce8c98add0c6d5fb07b3ba5338037d9a12b1d8e50a2d2039b0231d3d305c9ebe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748279"
---
# <a name="import-users-from-azure-active-directory"></a>Importar usuários do Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importar usuários selecionados

Este procedimento pode ser usado por administradores de sistema para importar usuários selecionados do Azure Active Directory (Azure AD).

1. O usuário será importado com a empresa da sessão atual como a empresa padrão. Altere a empresa atual, se aplicável, antes de importar usuários.
2. Acesse **Administração do sistema > Usuários > Usuários**.
3. Clique em **Importar usuários**.
4. Selecione os usuários que devem ser importados e selecione **Importar usuários**.

Depois que a importação for concluída, será necessário atribuir funções aos usuários.

## <a name="import-users-in-bulk"></a>Importar usuários em massa

Este procedimento pode ser usado por administradores de sistema para importar um grande número de usuários do Azure Active Directory.
Observe que não será possível selecionar usuários ao usar a opção Importação em lote.

## <a name="run-the-import-as-a-batch-job"></a>Execute a importação como um trabalho em lotes
1. O usuário será importado com a empresa da sessão atual como a empresa padrão. Altere a empresa atual, se aplicável, antes de importar usuários.
2. Acesse **Administração do sistema > Usuários > Usuários**.
3. Clique em **Importação em lote**.
4. Expanda a seção **Executar em segundo plano**.
4. Selecione **Sim** no campo **Processamento em lotes**.
6. No campo **Grupo de lotes**, insira ou selecione um valor. Essa etapa é opcional.  
7. Selecione **Sim** no campo **Particular**. Essa etapa é opcional.  
8. Selecione **Sim** no campo **Trabalho crítico**. Essa etapa é opcional.  
9. No campo **Categoria de monitoramento**, selecione uma opção.
10. Clique em **OK**.

Depois que a importação for concluída, será necessário atribuir funções aos usuários.

## <a name="run-in-a-sandbox-environment"></a>Executar em um ambiente de área restrita
1. Selecione **Importação em lote**.
2. Selecione **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]