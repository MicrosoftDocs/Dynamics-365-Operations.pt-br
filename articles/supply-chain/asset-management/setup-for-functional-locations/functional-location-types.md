---
title: Tipos de locais funcionais
description: Este tópico descreve como criar tipos de locais funcionais em Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74ccda77a97d1e104940bb10a605d3ebbf45af75
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571245"
---
# <a name="functional-location-types"></a>Tipos de locais funcionais

[!include [banner](../../includes/banner.md)]

 

Este tópico descreve como criar tipos de locais funcionais em Gerenciamento de Ativos. Os tipos de locais funcionais são usados para gerenciar requisitos para locais funcionais, incluindo como ativos são instalados em um local funcional. Você pode configurar tipos de ativo, planos de manutenção, atributos de locais funcionais e requisitos de atributos de ativo para serem usados em um local funcional que utilize o tipo de local funcional específico. Quando você cria um local funcional, o tipo de local funcional é obrigatório.

>[!NOTE] 
>Para trabalhar com locais funcionais, você deve criar um local funcional padrão a ser usado apenas com a finalidade de criação de novos ativos. Para esse local funcional padrão, você deve criar um tipo de local funcional padrão que seja realmente simples e permita que vários ativos sejam instalados no local funcional padrão. Consulte [Criar locais funcionais](../functional-locations/create-functional-locations.md) para obter mais informações sobre como configurar locais funcionais.

## <a name="create-a-default-functional-location-type"></a>Criar um tipo de local funcional padrão.

Este procedimento mostra como criar um tipo de local funcional padrão a ser usado para um local funcional padrão.

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Locais funcionais** > **Tipos de locais funcionais**.
2. Selecione **Novo** para criar um tipo de local funcional.
3. Insira uma ID de tipo de local funcional no campo **Tipo de local funcional** como, por exemplo, "Padrão", e um nome no campo **Nome**.
4. Selecione um modelo do ciclo de vida no campo **Modelo do ciclo de vida de local funcional**.
5. Selecione "Sim" no botão de alternância **Vários ativos** para permitir que mais ativos sejam instalados em um local funcional (o local funcional padrão) usando esse tipo.

O tipo de local funcional padrão a ser usado somente em um local funcional padrão é criado. Você não deve adicionar outros requisitos ou restrições neste tipo de local funcional padrão.


## <a name="create-functional-location-types"></a>Criar tipos de locais funcionais

1. Selecione **Gerenciamento de Ativos** > **Configuração** > **Locais funcionais** > **Tipos de locais funcionais**.
2. Selecione **Novo** para criar um tipo de local funcional.
3. Insira uma ID de tipo de local funcional no campo **Tipo de local funcional** e um nome no campo **Nome**.
4. Selecione um modelo do ciclo de vida no campo **Modelo do ciclo de vida de local funcional**. Consulte [Estados do ciclo de vida de local funcional](../setup-for-functional-locations/functional-location-stages.md) para obter mais informações sobre como os estados do ciclo de vida de local funcional e modelos do ciclo de vida.
5. Selecione "Sim" no botão de alternância **Vários ativos** se for possível instalar vários ativos no local funcional usando este tipo de local funcional. Se você selecionar "Não", só poderá instalar *um* ativo em um local funcional usando esse tipo de local funcional.
6. Selecione "Sim" no botão de alternância **Atualizar dimensão de ativo** se desejar que os ativos instalados em um local funcional deste tipo para usem automaticamente as dimensões financeiras relacionadas ao local funcional. Isso significa que, se você alterar dimensões financeiras no formulário [Local funcional](../functional-locations/create-functional-locations.md) e o local funcional usar um tipo de local funcional com este botão de alternância definido como "Sim", as dimensões financeiras serão atualizadas automaticamente em todos os ativos instalados nesse local. funcional.
7. O campo **Tipo de ativo** é usado para criar automaticamente o ativo *um* para o local funcional com a mesma ID e nome que o local funcional que você está criando. Por exemplo, isso pode ser relevante se você cria um local funcional estático, como um prédio ou um pipeline. Nesse caso, selecione o tipo de ativo a ser usado para o ativo criado automaticamente. Lembre-se de que, se você fizer uma seleção neste campo, o botão de alternância **Vários ativos** deverá ser definido como "Não".
8. Na Guia Rápida **Tipos de ativo**, selecione os tipos de ativo a serem relacionados ao tipo de local funcional. Selecione **Adicionar linha** e os tipos de ativos. Se você adicionar tipos de ativos aqui, somente os ativos que usam esses tipos de ativo poderão ser instalados em um local funcional usando esse tipo de local funcional. Se nenhum tipo de ativo for selecionado na Guia Rápida **Tipos de ativo**, todos os tipos de ativo poderão ser instalados.
9. Na Guia Rápida **Planos de manutenção**, selecione planos de manutenção que devem ser automaticamente configurados em novos locais funcionais usando esse tipo de local funcional. Selecione **Adicionar linha** e os planos de manutenção. Se adicionar planos de manutenção aqui, somente esses planos poderão ser usados em um local funcional por meio desse tipo de local funcional.
10. Na Guia Rápida **Requisitos de atributos de ativos**, configure os atributos de ativos que devem ser automaticamente configurados em novos locais funcionais usando esse tipo de local funcional. Selecione **Adicionar linha** e o atributo. Esses requisitos de atributos funcionam como diretrizes. Eles não são validados em relação a atributos configurados em um ativo (**Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos** > selecione o ativo na página de lista > guia **Geral** > botão **Atributos**). Os requisitos de atributos são exibidos quando você instala ativos em locais funcionais.
11. Na Guia Rápida **Tipos permitidos**, selecione os tipos de locais funcionais que devem estar válidas para os tipos de sublocais funcionais relacionados a um tipo de local funcional pai, que utiliza o tipo de local funcional selecionado.
12. Na Guia Rápida **Atributos**, selecione atributos de local funcional que devem ser automaticamente configurados em locais funcionais usando esse tipo de local funcional. Selecione **Adicionar linha** e o atributo.


>[!NOTE] 
>Na Guia Rápida **Geral**, você pode obter uma visão geral do número de tipos de ativos, planos de manutenção, requisitos de atributos de ativo, tipos permitidos, atributos e locais funcionais configurados no tipo de local funcional. O campo **Locais funcionais** mostra o número de locais funcionais que usam o tipo de local funcional. Você pode usar o botão **Copiar** para copiar configurações de um tipo de local funcional para o tipo de local funcional selecionado.
