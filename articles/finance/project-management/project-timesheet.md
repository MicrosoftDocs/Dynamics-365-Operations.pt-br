---
title: Aplicativo móvel de folha de ponto de projeto
description: Este tópico fornece informações sobre o aplicativo móvel Microsoft Dynamics 365 Project Timesheet. O aplicativo móvel de folha de ponto de projeto permite que os usuários enviem e aprovem folhas de ponto de projetos em seus dispositivos móveis.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 753c2a2905835a03b6befe817d32f993d35a5d73
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552316"
---
# <a name="project-timesheet-mobile-application"></a>Aplicativo móvel de folha de ponto de projeto

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visão geral

O aplicativo móvel Microsoft Dynamics 365 Project Timesheet permite que os usuários enviem e aprovem folhas de ponto de projetos em seus dispositivos móveis (iPhone ou Android). Esse aplicativo móvel revela a funcionalidade de folha de ponto que reside na área Gerenciamento e contabilidade de projetos do Dynamics 365 Finance, melhorando a produtividade e a eficiência do usuário e permitindo a entrada e a aprovação oportunas de folhas de ponto de projetos.

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.

Baixe e instale o aplicativo móvel Microsoft Dynamics 365 Project Timesheet para Android ou iPhone da loja de aplicativos para seu dispositivo.

## <a name="enable-the-app"></a>Habilitar o aplicativo 

No Finance, o aplicativo móvel Project Timesheet deve ser habilitado. Para habilitar a funcionalidade, vá para **Parâmetros de gerenciamento e contabilidade do projeto \> Folha de ponto** e selecione o parâmetro **Habilitar Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Entrar no aplicativo

1.  Inicie o aplicativo móvel no seu dispositivo.

2.  Insira a URL do Finance.

3.  Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.

4.  Você será conectado à sua empresa padrão.

## <a name="submit-a-project-timesheet"></a>Enviar uma folha de ponto de projeto

Você pode criar e enviar uma folha de ponto de projeto no aplicativo. Você pode basear uma nova folha de ponto nas informações de uma folha de ponto anterior, em linhas salvas ou em atribuições do projeto. Se você for designado como um delegado, também poderá inserir uma folha de ponto para outro trabalhador. Para criar uma folha de ponto como delegado, selecione o botão **Menu** e, depois, um nome de recurso.

A página de folhas de ponto criará uma nova folha de ponto para o período com base na data atual. A semana de trabalho será exibida. Se o período da folha de ponto abranger várias semanas, será possível selecionar outra semana de trabalho nas guias correspondentes.
Se existir uma folha de ponto para a data atual, ela será exibida. Caso você precise criar uma nova folha de ponto em outro período de folha de ponto, selecione o botão **Menu** e, depois, **Nova folha de ponto**.

Você pode inserir informações sobre o projeto clicando nas ações **Adicionar hora** ou **Copiar horário de**. A ação **Copiar horário de** copiará as informações da linha do projeto, exceto as horas. O menu **Copiar horário de** inclui as seguintes opções:

- **Copiar da folha de ponto existente** – Copie as linhas de folha de ponto de uma folha de ponto existente.

- **Copiar de favoritos** – Crie novas linhas de folha de ponto usando as configurações de folha de ponto que você selecionou como favoritas.

- **Copiar atribuição de formulário** - Crie novas linhas de folha de ponto com base em projetos atribuídos.

As informações do projeto que são exibidas dependem dos parâmetros móveis definidos na página **Parâmetros de gerenciamento e contabilidade de projetos**.

No campo **Entidade legal**, selecione a entidade legal para a qual você executou o trabalho do projeto. O campo **Entidade legal** só estará disponível se o suporte para folhas de ponto intercompanhia foi habilitado para a entidade legal.

Selecione o cliente associado ao projeto da folha de ponto. Na versão inicial no Android, não há suporte para entrada pelo cliente, porque primeiro você precisa selecionar o projeto. Se você selecionou o projeto primeiro, o campo **Cliente** é preenchido automaticamente.

No campo **Projeto**, selecione o projeto para o qual você está inserindo as horas. O campo **Cliente** será preenchido automaticamente.

As pesquisas de cliente e de projeto permitem pesquisar por clientes e projetos.

Selecione informações nos campos **Categoria**, **Atividade**, **Propriedade da linha**, **Grupo de impostos** e **Grupo de impostos do item** conforme necessário. Esses campos podem ser substituídos.

O campo **Propriedade da linha** será definido com um valor padrão com base nos parâmetros de gerenciamento e contabilidade do projeto. Quando os parâmetros projeto/categoria e categoria/recurso forem habilitados, o valor **Propriedade da linha** será definido com o valor padrão que você definiu para essa validação. Quando os parâmetros projeto/categoria e categoria/recurso não forem habilitados, o valor **Propriedade da linha** terá como padrão o campo **Habilitar propriedade de linha padrão** na página **Parâmetros de gerenciamento e contabilidade de projetos**. O valor **Propriedade da linha** pode ser substituído.

Selecione um dia para adicionar horas. Insira o número de horas em que você trabalhou cada dia.

Para adicionar comentários sobre as horas inseridas, clique em **Adicionar comentários** e insira comentários para um público interno, público de clientes ou ambos.
Os comentários internos podem ser exibidos por gerentes de projeto. Os comentários para clientes são incluídos nas faturas.

Para salvar a linha como um favorito, marque a caixa de seleção e clique em **Salvar como favorito**.

Suporte para anexos e dimensão financeira não são fornecidos no aplicativo móvel.

Continue adicionando linhas de projeto conforme necessário para preencher a folha de ponto.

Clique em **Enviar** para enviar a folha de ponto para o fluxo de trabalho de aprovação.

## <a name="review-timesheets"></a>Revisar folhas de ponto

Uma lista de folhas de ponto que precisam ser revisadas está disponível no menu. Esta opção só estará disponível se você tiver sido designado como aprovador do fluxo de trabalho. O cabeçalho e a linha de aprovação são aceitos. A aprovação de linhas permite marcar uma ou mais linhas para aprovação. Depois de revisar as informações da folha de ponto, clique em **Aprovar**, **Delegar** ou **Devolução** para dar continuidade ao fluxo de trabalho.
