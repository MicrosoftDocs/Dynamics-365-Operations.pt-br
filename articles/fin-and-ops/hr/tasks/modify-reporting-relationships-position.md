---
title: Modificar as relações de subordinação de uma posição
description: Este procedimento mostra como alterar a relação de subordinação de um funcionário.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e779a337ff8f8e0199a60e094f4bec9eba49e701
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "322688"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificar as relações de subordinação de uma posição

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como alterar a relação de subordinação de um funcionário. A relação de subordinação pode ser usada para documentos de roteiros com o fluxo de trabalho. O procedimento também mostra como atribuir um funcionário às hierarquias adicionais. Por exemplo, um funcionário pode fazer parte de uma equipe de projeto com uma relação de subordinação informal a um supervisor do projeto. As relações de subordinação adicionais podem ser definidas na posição para acomodar vários cenários de projeto ou de matriz. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para Recursos humanos > Posições > Posições.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Posição com um valor de '000091'.
3. Na lista, clique no link na linha selecionada.
4. Expanda a seção Relatórios para posição.
5. Clique em Novo para abrir a caixa de diálogo suspensa.
6. No campo Subordinado a, insira ou selecione um valor.
7. Clique em Criar.
8. Expanda a seção Relacionamentos.
9. Clique em Adicionar.
10. Marque a caixa de seleção à esquerda da grade.
11. No campo Nome da hierarquia, insira ou selecione um valor.
    * Exemplo: Projeto  
12. No campo Relatórios para posição, insira ou selecione um valor.  Exemplo: 000437
13. Clique em Salvar.

