---
title: Configurar recursos do Azure para Faturamento Eletrônico
description: Este artigo fornece uma visão geral do processo para configurar recursos do Microsoft Azure para faturamento eletrônico.
author: gionoder
ms.date: 01/26/2022
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
ms.openlocfilehash: f11e4eac831d54a6cac765a5adc4e4ffddbe0a22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283075"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Configurar recursos do Azure para Faturamento Eletrônico

[!include [banner](../includes/banner.md)]

O processo de configuração de recursos do Microsoft Azure para faturamento eletrônico tem três etapas. As duas primeiras etapas, "Criar um cofre de chaves do Azure no portal do Azure" e "Criar uma conta de armazenamento do Azure no portal do Azure", são obrigatórias. A terceira etapa, "Configurar uma conexão do SharePoint", é opcional.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Criar um cofre de chaves do Azure no portal do Azure

Crie um recurso de cofre de chaves na sua assinatura Azure. Recomendamos que você crie um cofre de chave separado para o faturamento eletrônico e que não combine segredos com outros aplicativos. Crie quantos segredos e certificados forem necessários para as suas situações em documentos eletrônicos. Você deve criar pelo menos um segredo para armazenar o token de assinatura de acesso compartilhado (SAS) da conta de armazenamento do Azure que será criada na próxima etapa.

Para obter informações sobre como concluir esta etapa, consulte [Criar um cofre de chaves do Azure no portal do Azure](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Criar uma conta de armazenamento do Azure no portal do Azure

Você tem todos os documentos eletrônicos e arquivos gerados pelo serviço de faturamento eletrônico ou insere o serviço. Esses documentos e arquivos são armazenados em uma conta de armazenamento do Azure que você cria na sua assinatura do Azure. O serviço acessará sua conta de armazenamento usando o token SAS obtido do segredo do seu Key Vault.

Para obter informações sobre como concluir esta etapa, consulte [Criar uma conta de armazenamento do Azure no portal do Azure](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Configurar uma conexão do SharePoint

Em algumas situações, talvez seja necessário salvar os arquivos eletrônicos no SharePoint e recuperá-los do SharePoint. Para garantir que o serviço de faturamento eletrônico possa acessar suas pastas do SharePoint, configure o acesso ao SharePoint.

Para obter informações sobre como concluir esta etapa, consulte [Configurar uma conexão do SharePoint](e-invoicing-create-sharepoint-connection.md).
