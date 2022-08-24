---
title: Certificados e segredos de cliente
description: Este artigo explica como configurar certificados e segredos do cliente no faturamento eletrônico.
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
ms.openlocfilehash: 3943e7cb43cc6bf93995f0b3957766227cc3ec99
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279830"
---
# <a name="customer-certificates-and-secrets"></a>Certificados e segredos de cliente

[!include [banner](../includes/banner.md)]

Se você já tiver uma referência do Microsoft Azure Key Vault no RCS (Regulatory Configuration Service), poderá criar referências aos certificados e segredos do Key Vault. Se você ainda não tiver uma referência do Key Vault, consulte [Ambientes de serviço](e-invoicing-service-environments.md) para obter informações sobre como criá-la.

## <a name="create-certificates-and-secrets"></a>Certificados e segredos de cliente

Siga estas etapas para criar e configurar certificados e segredos.

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Configuração de ambiente**, no Painel de Ações, selecione **Ambientes de serviço**.
4. Na página **Ambientes de serviço**, no Painel de Ações, selecione **Parâmetros do Key Vault**.
5. Na página **Parâmetros do Key Vault**, selecione uma referência ao Key Vault e então, na seção **Certificados**, selecione **Adicione**.
6. No campo **Nome**, digite o nome do segredo do Key Vault. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure no Portal do Azure](e-invoicing-create-azure-storage-account-azure-portal.md).
7. No campo **Descrição**, insira uma descrição.
8. No campo **Tipo**, selecione **Certificado** se estiver fazendo referência ao certificado armazenado no cofre de chaves. Selecione **Segredo** se estiver fazendo referência ao segredo armazenado no cofre de chaves.
9. Selecione **Salvar**.

> [!NOTE]
> Em alguns cenários, você deve usar certificados públicos que têm a extensão de nome de arquivo .cer. No entanto, o Key Vault não oferece suporte à importação e ao armazenamento de certificados deste tipo como certificados do Key Vault. Nesses cenários, você deve salvar o arquivo. cer como uma cadeia de caracteres Base-64-Encoded X.509 (.CER). Em seguida, em um segredo de Key Vault, armazene a cadeia de caracteres que aparece entre a linha **INICIAR CERTIFICADO** e **ENCERRAR CERTIFICADO** no arquivo. No ambiente de serviço, você ainda deve criar uma referência ao registro do Key Vault e definir o campo **Tipo** como **Certificado**.

## <a name="create-a-chain-of-certificates"></a>Criar uma cadeia de certificados

Se suas faturas específicas de país/região exigem uma cadeia de certificados para aplicar assinaturas digitais ou estabelecer uma conexão segura de (\[protocolo SSL\]) com serviços Web externos, crie uma cadeia de certificados em que os certificados estejam na seguinte ordem:

1. Certificados raiz
2. Certificados intermediários
3. Certificados de usuário final

As autoridades de certificação raiz (CAs) são uma fonte de certificados confiável. Os certificados de CA intermediários são pontes que vinculam os certificados de usuário final aos certificados da CA raiz.

Siga estas etapas para criar e configurar uma cadeia de certificados.

1. Na página **Parâmetros do Key Vault**, no Painel de Ações, selecione **Cadeia de certificados**.
2. Selecione **Novo** para criar uma cadeia de certificados.
3. No campo **Nome**, digite o nome da cadeia de certificados.
4. No campo **Descrição**, insira uma descrição.
5. Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.
6. Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia. Mantenha o certificado raiz da CA na parte superior da lista e o certificado de usuário final na parte inferior.
7. Selecione **Salvar**.

Você poderá criar quantas referências ao Key Vault no RCS quiser. Lembre-se de que o segredo para o token de assinatura de acesso compartilhado (SAS) de armazenamento é usado para vincular um determinado ambiente de serviço à referência ao Key Vault. Você pode fazer referência a certificados e segredos do Key Vault armazenados em um cofre de chaves que também contém o segredo para o token SAS de armazenamento que você usa ao configurar o ambiente de serviço.
