---
title: Estados do ciclo de vida de locais funcionais
description: Este tópico descreve como configurar estados de local funcional e modelos de ciclo de vida em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationLifecycleModel, EntAssetFunctionalLocationLifecycleState
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ded5fb032676a261566254427abcb642924451d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228722"
---
# <a name="functional-location-lifecycle-states"></a>Estados do ciclo de vida de locais funcionais

[!include [banner](../../includes/banner.md)]

 

Este tópico descreve como configurar estados de ciclo de vida de local funcional e modelos de ciclo de vida em Gerenciamento de Ativos. Os estados de ciclo de vida de local funcional definem os estados pelos quais um local funcional pode passar; por exemplo, criado, ativo e concluído. Você pode exibir todos os locais funcionais, independentemente do estado do ciclo de vida, na página de lista **Todos os locais funcionais**. Você pode alterar o estado de um local funcional selecionando-o na página **Todos os locais funcionais** e selecionando **Atualizar o estado do local funcional**.

## <a name="set-up-functional-location-lifecycle-states"></a>Configurar estados de ciclo de vida do local funcional

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Locais funcionais** > **Estados do ciclo de vida**.
2. Selecione **Novo** para criar um novo estado de local funcional.
3. Insira a ID de estado no campo **Estado do ciclo de vida** e um nome para o estado do local funcional no campo **Nome** . No campo **Modelos do ciclo de vida**, você pode ver o número de modelos de ciclo de vida do local funcional usando o estado do local funcional.
4. Na Guia Rápida **Geral**, selecione "Sim" no botão de alternância **Ativo** se o local funcional precisar estar ativo nesse estado.
5. Selecione "Sim" no botão de alternância **Criar ativos** se for possível criar automaticamente um ativo com o mesmo nome do local funcional e instalá-lo no local funcional nesse estado.  
>[!NOTE]
>Este botão de alternância está relacionado ao campo **Tipo de ativo** na Guia Rápida **Geral** no formulário **Tipos de locais funcionais** (**Gerenciamento de ativos** > **Configuração** > **Locais funcionais** > **Tipos de locais funcionais**).
6. Selecione "Sim" no botão de alternância **Renomear local** se for possível alterar o nome do local funcional nesse estado.
7. Selecione "Sim" no botão de alternância **Novos sublocais** se for possível adicionar novos sublocais ao local funcional nesse estado.
8. Selecione "Sim" no botão de alternância **Instalar ativos** se for possível instalar ativos no local funcional nesse estado.
9. Selecione "Sim" no botão de alternância **Excluir local funcional** se for possível excluir o local funcional nesse estado.
10. Selecione um estado de ativo fixo no campo **Estado do ciclo de vida** se desejar que o estado do ciclo de vida do ativo para todos os ativos instalados no local funcional seja atualizado automaticamente nesse estado. Exemplo: Se você encerrar um local funcional e definir o estado do ciclo de vida do local funcional como "Concluído", poderá alterar automaticamente o estado do ciclo de vida dos ativos instalados nesse local funcional para "Não em uso".


>[!NOTE]
>Os estados do ciclo de vida do local funcional, os modelos do ciclo de vida e os tipos estão relacionados e são usados da mesma forma que estados do ciclo de vida da ordem de serviço, modelos do ciclo de vida da ordem de serviço e tipos de ordem de serviço. 

## <a name="set-up-functional-location-lifecycle-models"></a>Configure modelos de ciclo de vida do local funcional

Após você criar os estados de ciclo de vida necessários para os seus locais funcionais, poderá dividi-los em grupos. Isso é feito para criar o fluxo do modelo de ciclo de vida que pode ser usado para diferentes tipos de locais funcionais. Como valor mínimo, um modelo padrão de ciclo de vida do local funcional deve ser criado.

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Locais funcionais** > **Modelos do ciclo de vida**.
2. Selecione **Novo** para criar um novo modelo de ciclo de vida.
3. Insira a ID do modelo de ciclo de vida no campo **Modelo do ciclo de vida** e um nome para o modelo de ciclo de vida no campo **Nome** . Nos campos **Tipos de locais funcionais** e **Estados do ciclo de vida**, você pode ver o número de tipos de locais funcionais que utilizam o modelo do ciclo de vida e o número de estados selecionados no modelo do ciclo de vida.
4. Na Guia Rápida **Estados de ciclo de vida**, selecione os estados que devem ser incluídos no modelo. Isso é feito clicando em um estado na seção **Estados de ciclo de vida restantes** e clicando no botão ![seta para frente](media/02-setup-for-functional-locations.png).
5. Caso queira selecionar todos os estados disponíveis para um modelo, clique no botão ![selecione todos os estágios disponíveis](media/03-setup-for-functional-locations.png). Todos os estados são transferidos para a seção **Estados de ciclo de vida selecionados**.
6. Se deseja remover um estado selecionado do modelo, selecione o estado na seção **Estados do ciclo de vida selecionados** e selecione o botão ![seta para voltar](media/04-setup-for-functional-locations.png).
7. Selecione **Atualizações do estado de ciclo de vida** para definir os estados de ciclo de vida que possam acompanhar um estado selecionado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]