---
title: Ativos de vários níveis
description: Este artigo explica como criar e excluir ativos de vários níveis.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b13db8b8b12aaef2e067f9a55eb8754333eb16b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017135"
---
# <a name="multi-level-assets"></a>Ativos de vários níveis

[!include [banner](../../includes/banner.md)]

 

Este artigo explica como criar e excluir ativos de vários níveis. É possível criar ativos e subativos relacionados em uma estrutura de árvore hierárquica. Dessa forma, você pode mostrar as relações e dependências entre os ativos. Os trabalhos de manutenção podem ser relacionados a todos os níveis da estrutura de árvore. Também é possível criar estatísticas para um nível individual ou como uma soma de todos os níveis do ativo.

Na página de listagem **Todos os ativos** (**Gerenciamento de ativos** \> **Ativos** \> **Todos os ativos**), a coluna **Ativo** lista os ativos em ordem hierárquica. A coluna **Responsável** mostra o responsável relacionado. Além disso, se os ativos e subativos já tiverem sido criados, a seção **Árvore de ativos** no painel **Informações relacionadas** mostrará os ativos em uma estrutura de árvore.

Para obter informações sobre como criar um ativo, consulte [Criar um ativo](../objects/create-an-object.md). Para criar um subativo, selecione o ativo pai no campo **Ativo pai** da FastTab **Geral**.

## <a name="copy-an-asset-or-asset-structure"></a>Copiar um ativo ou uma estrutura de ativos

Se sua empresa tiver diversas estruturas semelhantes de ativos, você poderá usar a função Copiar em Gerenciamento de ativos para criá-las rapidamente.

1. Selecione **Gerenciamento de ativos** \> **Ativos** \> **Todos os ativos**.
2. Na página da lista **Todos os ativos**, selecione o ativo a ser copiado. Por exemplo, se você quiser copiar a estrutura de ativos inteira, incluindo os subativos, selecione um ativo pai.
3. Selecione **Copiar ativo**. Na seção **Copiar de**, o campo **Ativo** é definido como o ativo selecionado na página da lista.
4. Na seção **Copiar para**, no campo **Ativo**, insira o nome do novo ativo.
5. Caso o ativo que você está criando deva fazer parte de uma estrutura de ativos existente, na seção **Ativo pai**, no campo **Ativo**, selecione uma ID do ativo pai.
6. Selecione **OK**. A nova estrutura de ativos será exibida na página **Todos os ativos**. Todos os atributos de ativo, planos de serviço e rounds de manutenção relacionados ao ativo que você copiou serão transferidos para o novo ativo ou estrutura de ativos.

Ao copiar uma estrutura de ativos, os subativos da nova estrutura terão o mesmo nome dos subativos que você copiou. Após concluir o procedimento de cópia, você poderá alterar facilmente o nome e outras configurações de um ativo. Selecione o ativo na página **Todos os ativos**, e selecione o botão **Editar**.

> [!NOTE]
> Quando você copia um ativo ou uma estrutura de ativos, o estado do ciclo de vida dos novos ativos é redefinido para o estado que você definiu como o estado inicial do ciclo de vida dos ativos. O local funcional é redefinido para o local funcional padrão.

## <a name="delete-an-asset-or-asset-structure"></a>Excluir um ativo ou uma estrutura de ativos

Se um ativo tiver subativos relacionados, você só poderá excluí-lo se nenhuma solicitação de manutenção, ordem de trabalho, registro de falha ou avaliação de condição estiver registrado em qualquer um dos ativos.

1. Na página da lista **Todos os ativos**, selecione o ativo a ser excluído.
2. Selecione **Excluir**.

> [!NOTE]
> Se você não conseguir excluir um ativo usando este procedimento, outra maneira de excluir é configurar um estado do ciclo de vida do ativo pra essa finalidade. Por exemplo, é possível configurar um estado do ciclo de vida **Sucateado** ou **Excluído** na página **Estados do ciclo de vida do ativo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]