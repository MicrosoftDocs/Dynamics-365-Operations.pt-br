---
title: Criar um ativo fixo
description: Este artigo explica como criar um novo registro de ativo fixo na página de listagem Ativo fixo.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00c72081d20015737aa027cee9474a54e498cef4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868479"
---
# <a name="create-a-fixed-asset"></a>Criar um ativo fixo

[!include [banner](../../includes/banner.md)]

Este artigo explica como criar um novo registro de ativo fixo na página de listagem **Ativo fixo**.

O sistema atribui o número do ativo, com base na sequência numérica atribuída ao grupo de ativos fixos. Se você usar o modelo de ativo fixo para importar ativos por meio do suplemento do Microsoft Excel ou se usar outro trabalho de importação, o sistema criará automaticamente registros de ativo fixo e incrementará o número do ativo.

Para criar manualmente um registro de ativo, siga estas etapas.

1. Acesse **Painel de Navegação \> Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.
2. No **Painel de ação**, selecione **Novo**.
3. No campo **Grupo de ativo fixo**, insira ou selecione um valor. O campo **Número** será padrão se você tiver habilitado a **funcionalidade de ativos fixos Autonumber** nos **parâmetros de ativos fixos** e no **grupo de ativos fixos**. Se não, você deve inserir um número exclusivo para identificar o ativo fixo.
4. No campo **Nome**, insira um valor. Insira informações adicionais que sua empresa precisa para este ativo.
5. No **Painel de ação**, selecione **Registros**.
6. No campo **Data de aquisição**, insira uma data.
7. No campo **Preço de aquisição**, insira um número.

    - Insira informações adicionais que sua empresa precisa para este registro.
    - Insira informações adicionais que sua empresa precisa para os registros restantes.

8. Feche a página.

Também é possível importar ativos fixos usando o suplemento do Excel ou executando um trabalho de importação do espaço de trabalho **Gerenciamento de dados**. Antes de executar a importação, insira os valores dos campos obrigatórios no modelo.

Se você não tiver definido o número do ativo fixo no modelo do suplemento do Excel ou no Gerenciamento de dados, o sistema cria um número de ativo fixo para cada ativo importado e incrementa automaticamente a sequência numérica para cada um. No entanto, se você importar ativos e definir números de ativos no modelo, o sistema **não** incrementará automaticamente a sequência numérica. Nesse caso, um administrador pode ter que atualizar manualmente a sequência numérica. Se você tiver definido o número do ativo fixo no modelo do suplemento do Excel, o sistema usará o número do ativo fixo definido e incrementará a sequência numérica.

> [!NOTE]                                                                                                         
> Depois de lançar a depreciação, os campos **Colocado em serviço** e **Data de execução da depreciação** ficarão bloqueados na página **Registro**. Além disso, nenhum campo será atualizado a partir da entidade de dados.

> [!WARNING]
> O registro de ativo fixo não será excluído se as transações forem lançadas no registro associado ou se o ativo fixo recém-criado for inserido em uma linha do diário, mas não lançado. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
