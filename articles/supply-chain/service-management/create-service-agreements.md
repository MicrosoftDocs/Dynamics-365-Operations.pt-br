---
title: Criar contratos de serviço
description: Este artigo descreve como usar os recursos em Gerenciamento de serviços e os módulos de Gerenciamento e contabilidade de projetos para criar contratos de serviço.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d18d279cd437e98cad6495def953978cb78e723e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901753"
---
# <a name="create-service-agreements"></a>Criar contratos de serviço

[!include [banner](../includes/banner.md)]

Este artigo descreve como usar os recursos em Gerenciamento de serviços e os módulos de Gerenciamento e contabilidade de projetos para criar contratos de serviço.

## <a name="create-a-service-agreement-from-service-management"></a>Criar um contrato de serviço em Gerenciamento de serviços

1. Navegue até **Gerenciamento de serviço**.
2. Selecione **Contratos de serviço** para criar uma nova linha de contrato de serviço no cabeçalho da página. 
3. Selecione **Novo**. Insira uma descrição, selecione uma referência a um projeto no campo **ID do projeto** e preencha os outros campos e as linhas do contrato de serviço. Selecione **Salvar**.
4. Na guia **Relações**, selecione **Objetos de serviço** ou **Tarefas de serviço** para criar relações de objeto de serviço ou relações de tarefa de serviço para o contrato de serviço. Os objetos e as tarefas de serviço para os quais você criou relações podem ser anexados às linhas do contrato de serviço.
5. Na metade inferior da página, crie linhas de contrato de serviço copiando linhas de um modelo de serviço, de outro contrato ou criando manualmente as linhas.

> [!NOTE]
> Se você copiar linhas de outro contrato de serviço no contrato, poderá indicar se também deseja copiar as relações de objeto e tarefa de serviço. Se copiar essas relações, elas serão adicionadas a todas as relações existentes no contrato de serviço. Se você copiar linhas de contrato de serviço de um modelo de serviço, as relações de objeto e tarefa de serviço são copiadas automaticamente como relações de objeto e de tarefa de serviço nas novas linhas do contrato.

## <a name="create-service-agreement-lines-manually"></a>Criar linhas de contrato de serviço manualmente

1. Na página **Contratos de serviço**, adicione uma linha de contrato de serviço nas grade de linhas. 
2. Insira as informações apropriadas para a linha do contrato de serviço. 
3. Selecione **Salvar** para salvar a linha e feche a página.

## <a name="create-a-service-agreement-from-project"></a>Criar um contrato de serviço em Projeto

1. Selecione **Gerenciamento e contabilidade do projeto**.
2. Selecione **Todos os projetos**.
3. Selecione o projeto na lista.
4. No **Painel de Ações**, selecione **Gerenciar**. No grupo de ação **Novo**, selecione **Serviço** e **Contrato de serviço**.
5. Siga as etapas na seção intitulada **Criar um contrato de serviço** como descrito anteriormente neste artigo para entrar nas referências de projeto.


## <a name="related-articles"></a>Artigos relacionados

[Visão geral de desenvolvimento e estabelecimento de contratos de serviço](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]