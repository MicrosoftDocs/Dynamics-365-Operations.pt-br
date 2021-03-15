---
title: Criar estruturas de conta
description: Este guia de tarefas aborda a criação de uma estrutura de conta.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a8df7d7d9c4555bf46ac1cc3f71695837b1369b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968570"
---
# <a name="create-account-structures"></a>Criar estruturas de conta

[!include [banner](../../includes/banner.md)]

Este guia de tarefas aborda a criação de uma estrutura de conta. As etapas usam a empresa USMF de dados de demonstração.

1. Vá para **Painel de Navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta**.
2. No **Painel de Ações**, clique em **Novo** para abrir a caixa de diálogo suspensa.
3. No campo **Estrutura de conta**, digite um nome para descrever a finalidade da estrutura de conta.
4. No campo **Descrição**, digite uma descrição para especificar a finalidade da estrutura de conta.
5. Clique em **Criar**.
6. Nos **Segmentos e valores permitidos**, clique em **Adicionar segmento**.
7. Na lista de dimensões, selecione a dimensão que será adicionada à estrutura de conta.
8. No final da lista, clique em **Adicionar segmento**.
9. Repita as etapas 6 a 9, conforme necessário.
10. Na seção **Detalhes do valor permitido**, selecione o segmento para editar os valores permitidos.
    Por exemplo, clique no campo **Conta Principal**.  
11. No campo **Operador**, selecione uma opção, como está entre e inclui.
12. No campo **Valor**, digite um valor. Por exemplo, 600000.  
13. No campo **por meio de**, digite um valor. Por exemplo, 699999.  
14. Na seção **Detalhes do valor permitido**, clique em **Aplicar**.
15. Repita as etapas 10 a 15, conforme necessário.  
16. Na seção **Detalhes do valor permitido**, clique em **Adicionar novos critérios**.
17. No campo Operador, selecione uma opção, como está entre e inclui.
18. No campo **Valor**, digite um valor. Por exemplo, 033.  
19. No campo **por meio de**, digite um valor. Por exemplo, 034.  
20. Clique em **Aplicar**.
21. Na grade, selecione o segmento para editar os valores permitidos. Por exemplo, Centro de custo.  
22. No campo **Centro de custo**, digite um valor. Por exemplo, 007..021.  
23. Nos **Segmentos e valores permitidos**, clique em **Adicionar**.
24. No campo **Conta principal**, digite um valor. Por exemplo, 600000..699999  
25. Na grade, selecione o segmento para editar os valores permitidos. Por exemplo, Departamento.  
26. No campo Departamento, digite um valor. Por exemplo, 032.  
27. No campo Centro de custo, digite um valor. Por exemplo, 086.  
28. No **Painel de Ações**, clique em **Validar**.
29. No **Painel de Ações**, clique em **Ativar**.
30. Clique em **Ativar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]