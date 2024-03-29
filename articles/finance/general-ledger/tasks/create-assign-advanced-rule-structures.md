---
title: Criar e atribuir estruturas de regras avançadas
description: Este artigo explica como criar e atribuir uma estrutura de regras avançada a uma estrutura de conta.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72688642936f9428c96aebb34bf9f240dd48b46b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896309"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Criar e atribuir estruturas de regras avançadas

[!include [banner](../../includes/banner.md)]

Este artigo explica como criar e atribuir uma estrutura de regras avançada a uma estrutura de conta. Este guia usa a empresa de demonstração USMF.

## <a name="create-an-advanced-rule-structure"></a>Criar estrutura de regras avançada
1. Acesse **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Estruturas de regras avançadas**.
2. Selecione **Novo** para abrir a caixa de diálogo suspensa.
3. No campo **Estrutura de regras avançada**, digite um nome para descrever a estrutura de regras.
4. Selecione **OK**.
5. Selecione **Adicionar segmento**.
6. Na lista de segmentos, selecione uma dimensão financeira. Por exemplo, **Loja**.  
7. Selecione **Adicionar segmento**.
8. Selecione **Ativar**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Aplicar estrutura de regra avançada a uma estrutura de conta
1. Acesse **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta**.
2. Na lista, localize e selecione a estrutura de conta à qual deseja aplicar a regra avançada.
3. Selecione **Editar**. Você também pode selecionar **Regras avançadas** e será solicitado a colocar a estrutura de conta no **Modo de rascunho**.  
4. Selecione **Regras avançadas**.
5. Selecione **Novo** para abrir a caixa de diálogo suspensa.
6. No campo **Regra avançada**, digite um valor.
7. No campo **Nome**, digite um valor.
8. Selecione **Criar**.
9. Selecione **Adicionar novos critérios**.
10. No campo **Onde**, selecione uma conta principal ou uma dimensão financeira.
11. No campo **Operador**, selecione uma opção, como **está entre** e **inclui**.
12. No campo **Valor**, digite um valor.
13. No campo **por meio de**, digite um valor.
14. Selecione **Adicionar** para abrir a caixa de diálogo suspensa.
15. Na lista, localize a estrutura de regra avançada que deseja usar quando os critérios inseridos forem atendidos.
16. Selecione **Adicionar**.
17. Feche a página.
18. Selecione **Ativar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
