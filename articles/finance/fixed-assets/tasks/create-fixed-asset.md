---
title: Criar um ativo fixo
description: Este tópico explica como criar um novo registro de ativo fixo na página de listagem Ativo fixo.
author: saraschi2
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b7d65a047251fa036242fb456725bc8cba957b9
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000234"
---
# <a name="create-a-fixed-asset"></a>Criar um ativo fixo

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um novo registro de ativo fixo na página de listagem **Ativo fixo**.

O sistema atribui o número do ativo, com base na sequência numérica atribuída ao grupo de ativos fixos. Se você usar o modelo de ativo fixo para importar ativos por meio do suplemento do Microsoft Excel ou se usar outro trabalho de importação, o sistema criará automaticamente registros de ativo fixo e incrementará o número do ativo.

Para criar manualmente um registro de ativo, siga estas etapas.

1. Vá para **Painel de Navegação \> Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.
2. No **Painel de ação** , selecione **Novo**.
3. No campo **Grupo de ativo fixo** , insira ou selecione um valor. O campo **Número** será padrão se você tiver habilitado a **funcionalidade de ativos fixos Autonumber** nos **parâmetros de ativos fixos** e no **grupo de ativos fixos**. Se não, você deve inserir um número exclusivo para identificar o ativo fixo.
4. No campo **Nome** , insira um valor. Insira informações adicionais que sua empresa precisa para este ativo.
5. No **Painel de ação** , selecione **Registros**.
6. No campo **Data de aquisição** , insira uma data.
7. No campo **Preço de aquisição** , insira um número.

    - Insira informações adicionais que sua empresa precisa para este registro.
    - Insira informações adicionais que sua empresa precisa para os registros restantes.

8. Feche a página.

Também é possível importar ativos fixos usando o suplemento do Excel ou executando um trabalho de importação do espaço de trabalho **Gerenciamento de dados**. Antes de executar a importação, insira os valores dos campos obrigatórios no modelo.

Se você não tiver definido o número do ativo fixo no modelo do suplemento do Excel ou no Gerenciamento de dados, o sistema cria um número de ativo fixo para cada ativo importado e incrementa automaticamente a sequência numérica para cada um. No entanto, se você importar ativos e definir números de ativos no modelo, o sistema **não** incrementará automaticamente a sequência numérica. Nesse caso, um administrador pode ter que atualizar manualmente a sequência numérica. Se você tiver definido o número do ativo fixo no modelo do suplemento do Excel, o sistema usará o número do ativo fixo definido e incrementará a sequência numérica.
