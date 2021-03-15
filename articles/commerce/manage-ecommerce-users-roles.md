---
title: Gerenciar usuários e funções de comércio eletrônico
description: Este tópico explica como conceder aos usuários acesso ao ambiente de criação de seu site do Microsoft Dynamics 365 Commerce .
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d4987a824b786401c41c6ae63c8486ce7eb0c5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995682"
---
# <a name="manage-e-commerce-users-and-roles"></a>Gerenciar usuários e funções de comércio eletrônico


[!include [banner](includes/banner.md)]

Este tópico explica como conceder aos usuários acesso ao ambiente de criação de seu site do Microsoft Dynamics 365 Commerce .

Para ajudar a controlar o acesso do usuário e conceder permissão aos usuários para executar tarefas específicas, o ambiente de criação do site usa grupos de segurança que você cria no Microsoft Azure Active Directory (Azure AD). Você primeiro atribui um grupo de segurança novo ou existente do Azure AD a cada função no ambiente de criação. Você concede ou revoga permissões para usuários individuais, adicionando esses usuários a um grupo de segurança apropriado ou removendo-os de um grupo de segurança.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Visão geral das funções no ambiente de criação

O ambiente de criação do Dynamics 365 for Commerce suporta as seguintes funções.

| Função                 | Descrição |
|----------------------|-------------|
| Administrador do Sistema | Os usuários que possuem essa função têm todos os privilégios para todas as ferramentas e para todas as classificações e opiniões. Eles também podem criar sites. |
| Administrador   | Os usuários que possuem essa função têm todos os privilégios para todas as ferramentas e RnR em uma determinada estrutura de site. |
| Produtor da Web         | Os usuários que tiverem esta função podem criar páginas, fragmentos e modelos, carregar e gerenciar ativos e enriquecem produtos e categorias. |
| Leitor               | Os usuários que tiverem esta função poderão exibir páginas, modelos, ativos, fragmentos, layouts e configurações, mas não podem fazer alterações. |
| Moderador de RnR        | Os usuários que tiverem esta função pode moderar revisões do produto. |

## <a name="system-administrator-role"></a>Função de Administrador do sistema

Ao provisionar o Dynamics 365 Commerce no ambiente do Microsoft Dynamics Lifecycle Services, você precisa fornecer um grupo de segurança para a função de **Administrador do Sistema** . Esta função é aplicada automaticamente a todos os sites criados no ambiente que você está configurando. O grupo de segurança desta função pode ser atualizado apenas no LCS. Na **Administração do Site** para todos os sites, ele aparecerá como somente leitura e é meramente informativo.

## <a name="administrator-role"></a>Função de Administrador

Quando você cria um novo site no Comércio, você deve fornecer um grupo de segurança para a função de **Administrador** . Consulte a tabela anterior neste tópico para obter uma visão geral das permissões que essa função concede.

## <a name="add-or-update-security-groups"></a>Adicionar ou atualizar grupos de segurança

Depois que o site for criado, apenas os usuários que estão nos grupos de segurança associados às funções de **Administrador do Sistema** e de **Administrador** podem acessar o ambiente de criação desse site. Para atribuir aos usuários as funções de **Produtor da Web**, **Moderador de RnR** e **Leitor** é necessário atribuir grupos de segurança a essas funções. Para adicionar um grupo de segurança a uma função, ou atualizar um grupo de segurança que atualmente está atribuído a uma função, siga estas etapas.

1. Vá para o site que deseja atualizar.
1. No **Gerenciamento de site**, abra a página **Segurança**.
1. Selecione a função a ser modificada.
1. Adicione grupos de segurança a funções ou remova grupos de segurança de funções.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

[Considerações de otimização do mecanismo de pesquisa (SEO) para seu site](search-engine-optimization-considerations.md)

[Gerenciar a política de segurança de conteúdo (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]