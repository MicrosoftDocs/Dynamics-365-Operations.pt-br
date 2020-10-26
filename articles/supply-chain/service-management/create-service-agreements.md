---
title: Criar contratos de serviço
description: Este tópico descreve como usar os recursos em Gerenciamento de serviços e os módulos de Gerenciamento e contabilidade de projetos para criar contratos de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a1a47761869a4190eac6dc9e069a6b520bf7a1d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985133"
---
# <a name="create-service-agreements"></a>Criar contratos de serviço

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar os recursos em Gerenciamento de serviços e os módulos de Gerenciamento e contabilidade de projetos para criar contratos de serviço.

## <a name="create-a-service-agreement-from-service-management"></a>Criar um contrato de serviço em Gerenciamento de serviços

1. Navegue até **Gerenciamento de serviço**.
2. Clique em **Contratos de serviço** para criar uma nova linha de contrato de serviço no cabeçalho da página. 
3. Clique em **Novo**. Insira uma descrição, selecione uma referência a um projeto no campo **ID do projeto** e preencha os outros campos e as linhas do contrato de serviço. Clique em **Salvar**.
4. Na guia **Relações**, selecione **Objetos de serviço** ou **Tarefas de serviço** para criar relações de objeto de serviço ou relações de tarefa de serviço para o contrato de serviço. Os objetos e as tarefas de serviço para os quais você criou relações podem ser anexados às linhas do contrato de serviço.
5. Na metade inferior da página, crie linhas de contrato de serviço copiando linhas de um modelo de serviço, de outro contrato ou criando manualmente as linhas.

> [!NOTE]
> Se você copiar linhas de outro contrato de serviço no contrato, poderá indicar se também deseja copiar as relações de objeto e tarefa de serviço. Se copiar essas relações, elas serão adicionadas a todas as relações existentes no contrato de serviço. Se você copiar linhas de contrato de serviço de um modelo de serviço, as relações de objeto e tarefa de serviço são copiadas automaticamente como relações de objeto e de tarefa de serviço nas novas linhas do contrato.

## <a name="create-service-agreement-lines-manually"></a>Criar linhas de contrato de serviço manualmente

1. Na página **Contratos de serviço**, adicione uma linha de contrato de serviço nas grade de linhas. 
2. Insira as informações apropriadas para a linha do contrato de serviço. 
3. Pressione **CTRL+S** para salvar a linha e feche a página.

## <a name="create-a-service-agreement-from-project"></a>Criar um contrato de serviço em Projeto

1. Clique em **Gerenciamento e contabilidade de projetos**.
2. Clique em **Todos os projetos**.
3. Selecione o projeto na lista.
4. No **Painel de Ação**, clique em **Gerenciar**. No grupo de Ação **Novo**, clique em **Serviço** e selecione **Contratos de serviço**.
5. Siga as etapas na seção intitulada **Crie um contrato de serviço** como descrito anteriormente neste tópico para entrar nas referências de projeto.


## <a name="related-topics"></a>Tópicos relacionados

[Visão geral de desenvolvimento e estabelecimento de contratos de serviço](service-agreements.md)


