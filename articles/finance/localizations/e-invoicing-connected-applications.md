---
title: Aplicativos conectados
description: Este artigo explica como configurar aplicativos conectados no faturamento eletrônico.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: aa6c80914301cc0403974a6acc5e95ff61c9c1a7
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524680"
---
# <a name="connected-applications"></a>Aplicativos conectados

[!include [banner](../includes/banner.md)]

Os aplicativos conectados são as instâncias do Microsoft Microsoft Dynamics 365 Finance e do Dynamics 365 Supply Chain Management que você pode querer alcançar por meio do Regulatory Configuration Service (RCS). Por meio dos aplicativos conectados, você pode configurar parte do recurso de globalização no Finance ou no Supply Chain Management para que todo o cenário de faturamento eletrônico funcione.

Ao implantar seu recurso de globalização, as informações de configuração aplicáveis ao seu aplicativo Finance or Supply Chain Management podem ser publicadas diretamente do RCS para o aplicativo conectado apropriado.

A disponibilidade dos parâmetros do Finance or Supply Chain Management no RCS é útil quando há vários ambientes de aplicativos, como UAT (teste de aceitação de usuários) e ambientes de produção, e você deseja manter a configuração consistente implantando os mesmos parâmetros em diferentes ambientes.

## <a name="create-a-connected-application"></a>Crie um aplicativo conectado

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Links relacionados**, selecione o bloco **Configuração do ambiente**.
3. Na página **Configuração de ambiente**, no Painel de Ações, selecione **Aplicativos conectados**.
4. Selecione **Novo** para criar um aplicativo conectado.
5. No campo **Nome**, insira o nome do aplicativo a ser conectado.
6. No campo **Tipo**, selecione **Dynamics 365 Finance**.
7. No campo **Aplicação**, digite o URL do ambiente a ser conectado.
8. No campo **Locatário**, digite o locatário do ambiente.
9. Selecione **Salvar**.
10. No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente. Depois feche a página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicativos conectados a ambientes

1. Na página **Configuração de ambiente**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.
2. No campo **Aplicativo conectado**, selecione um aplicativo conectado.
3. No campo **Ambiente de serviço**, selecione um ambiente de serviço.
4. Selecione **Salvar** e feche a página.
