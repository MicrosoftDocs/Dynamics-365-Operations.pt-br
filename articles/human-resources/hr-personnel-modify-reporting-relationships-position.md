---
title: Modificar as relações de subordinação de uma posição
description: Este procedimento mostra como alterar a relação de subordinação de um funcionário.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7996733575c2d3a23971d08eb101962c1f6bbd9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066616"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificar as relações de subordinação de uma posição


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este procedimento mostra como alterar a relação de subordinação de um funcionário. A relação de subordinação pode ser usada para documentos de roteiros com o fluxo de trabalho. O procedimento também mostra como atribuir um funcionário às hierarquias adicionais. Por exemplo, um funcionário pode fazer parte de uma equipe de projeto com uma relação de subordinação informal a um supervisor do projeto. As relações de subordinação adicionais podem ser definidas na posição para acomodar vários cenários de projeto ou de matriz. A empresa de dados demo usada para criar este procedimento é USMF.

1. Acesse **Recursos humanos** \> **Posições** \> **Posições**.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtro em um valor **000091** para o campo **Posição**.
3. Na lista, selecione o link na linha selecionada.
4. Expanda a seção **Relatórios para posição**.
5. Selecione **Novo** para abrir a caixa de diálogo suspensa.
6. No campo **Subordinado a**, insira ou selecione um valor.
7. Selecione **Criar**.
8. Expanda a seção **Relacionamentos**.
9. Selecione **Adicionar**.
10. Marque a caixa de seleção à esquerda da grade.
11. No campo **Nome da hierarquia**, insira ou selecione um valor (por exemplo, **Projeto**).
12. No campo **Relatórios para posição**, insira ou selecione um valor (por exemplo, **000437**).
13. Selecione **Salvar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
