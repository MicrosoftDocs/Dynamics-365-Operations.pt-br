---
title: Elementos da interface do usuário
description: Este tópico descreve os elementos da interface do usuário (IU) usados no aplicativo.
author: tlefor
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: feb6d5751bc22c05dbd2f01f47d5a0f99fca07a0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754719"
---
# <a name="user-interface-elements"></a>Elementos da interface do usuário

Este tópico descreve os elementos da interface do usuário (IU) usados no aplicativo. Para que os usuários possam navegar na interface, é importante saber os nomes e funções dos elementos que constituem a interface.

## <a name="overview"></a>Visão Geral

- **Painel de ações** - A barra abaixo da barra de navegação. Aqui, é possível selecionar guias para alterar os registros mostrados na página. Você pode editar e salvar os registros aqui.  
- **Quadro de Fatos** - Você pode ver informações e seguir as atividades de determinados registros neste painel.  
- **Painel de Quadro de Fatos** Aqui, você pode passar por diferentes aspectos de um registro para exibição no Quadro de Fatos.  
- **Painel de filtragem** - Em algumas páginas, você pode selecionar **Exibir filtros** para abrir esse painel. Permite refinar os resultados visíveis na página.  
- **Barra de navegação** - Na barra superior da interface. Ela contém o **portal do Dynamics 365**, **Pesquisar**, **seletor da empresa**, **Central de ações**, **Configurações**, **Ajuda e Suporte** e o perfil de usuário.  
- **Lista de navegação** - Em algumas páginas, você pode navegar neste painel para encontrar um registro específico. Quando selecionados, os detalhes do registro aparecerão na página.  
- **Painel de navegação** - O painel à esquerda. Aqui, é possível encontrar qualquer página no produto.  
- **Página** - O foco central da interface. As seleções feitas em outros componentes da interface de usuário afetarão quais registros são exibidos aqui.  
- **Painel** - O painel de tarefas à direita. Isso abrirá em alguns casos quando os aspectos de um registro precisarem ser alterados e salvos.  
- **Guia** - Ao consultar o Painel de Ações, é um menu de opções que aparece quando você seleciona uma determinada opção no Painel de Ações.  

![A imagem a seguir mostra a posição desses elementos na interface.](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a>Guias, campos e seções

Uma *guia* é uma seleção feita na página que abre um aspecto diferente de um registro na mesma página. Geralmente, permitirá que você altere determinados *campos* ou elementos da interface do usuário que permitem entrada por digitação. 

Uma *Guia Rápida* é uma guia com o benefício adicionado para permitir que várias guias fiquem visíveis no mesmo tempo. Você pode expandir uma Guia Rápida selecionando a seta apontando para baixo na ponta à esquerda dela.

![A imagem a seguir mostra um exemplo de guias e Guias Rápidas.](media/user-interface-02.png)

Uma *seção* é similar a uma guia. A palavra "seção" é frequentemente usada para descrever qualquer área de uma página que organiza uma categoria específica de informação. Na imagem a seguir, Resumo, Ordens e Favoritos, e Links são todos exemplos de seções.

![A imagem a seguir mostra um exemplo de guias e uma seção.](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a>Caixas de diálogo e menus suspensos

Uma *caixa de diálogo* é um painel que abre quando determinadas seleções são feitas para mudar ou criar um registro. As caixas de diálogo contêm campos que permitem a entrada de texto digitado. Ocasionalmente, um determinado campo permitirá que você selecione uma seta virada para baixo que abre uma lista de opções para escolha. Isso é chamado de um *menu suspenso*. Na imagem a seguir, os campos **Tipo** e **Grupo de clientes** contêm a opção para abrir um menu suspenso.

![A imagem a seguir mostra um exemplo da caixa de diálogo.](media/user-interface-04.png)

Em alguns casos, uma caixa de diálogo será aberta próxima a um botão quando você o seleciona. Isso é chamado de um *caixa de diálogo suspensa*. Na imagem a seguir, o botão **A partir da data** foi selecionado, que abriu uma caixa de diálogo suspensa.

![A imagem a seguir mostra um exemplo da caixa de diálogo suspensa.](media/user-interface-05.png)

## <a name="notifications"></a>Notificações

Determinadas alterações aos objetos que você analisa aparecerão como *notificações*. Notificações podem notificá-lo quando as informações de cliente específicas forem alterada, ou podem alertá-lo quando o sistema não pode aceitar entradas que você adicionou em determinados campos. Você pode aprender como personalizar as notificações que recebe em [Visão geral de alertas](../get-started/alerts-overview.md).

Notificações aparecem de diversas maneiras.
- **Recurso de texto explicativo** - Aparecerá próximo a um campo, guia ou outro botão para oferecer uma explicação de para quê o recurso foi usado. 
- **Central de ações** - Uma caixa que contém a notificação aparecerá próxima ao botão Central de ações na barra de navegação. Você pode ver detalhes sobre a notificação selecionando **Centro de ação**.  
- **Barra de mensagens** - Isso aparecerá abaixo do Painel de Ações.  

A seguinte imagem mostra exemplos desses tipos de notificações.

![A seguinte imagem mostra exemplos de notificações.](media/user-interface-06.png)

- **Caixa de mensagem** - É exibida na interface e você deve interagir com antes que você possa continuar a usar o produto.  

![A imagem a seguir mostra um exemplo da caixa de mensagens](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a>Barras de ferramentas, grades e listas

Uma *barra de ferramentas* contém ferramentas, como a habilidade de adicionar campos ou remover registros. Ocasionalmente, uma barra de ferramentas aparecerá na página acima de uma *grade*. Essa área, grade, é um nome fornecido para linhas de registros com várias colunas de dados. Nem todas as grades têm barras de ferramentas acima delas.

Uma *lista* é o nome dado a uma coleção de registros que você pode visualizar. Você pode trazer esses registros para a página selecionando-os. Geralmente, isso abrirá uma grade.

![Esta imagem mostra exemplos de barras de ferramentas, grades e listas.](media/user-interface-08.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]