---
title: Criar uma conta de armazenamento do Azure e um cofre de chaves
description: Este tópico explica como criar uma conta de armazenamento do Azure e um cofre de chaves.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 5a883011bbff6d82504497d739c07f1ada9e5f69
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4440528"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Criar uma conta de armazenamento do Azure e um cofre de chaves

[!include [banner](../includes/banner.md)]



O serviço complementar de faturamento eletrônica é responsável pelo armazenamento de todos os dados comerciais nos recursos do Microsoft Azure pertencentes à sua empresa. Para garantir que o serviço funcione corretamente e que todos os dados comerciais necessários e gerados pelo complemento de faturamento eletrônico sejam acessados somente pelo complemento, crie dois recursos principais do Azure:

- Uma conta de armazenamento do Azure (armazenamento de Blob) para armazenar faturas eletrônicas
- Um Azure Key Vault para armazenar certificados e o URI (Uniform Resource Identifier) da conta de armazenamento

> [!NOTE]
> Um recurso de compartimento de cofre de chaves e armazenamento de Blob de cliente deve ser alocado especificamente para ser usado com o complemento de faturamento eletrônico.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas neste tópico, verifique se as seguintes tarefas foram concluídas:

- Criar um recurso de cofre de chaves no Azure. Para obter mais informações, consulte [Sobre o Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Crie uma conta de armazenamento do Azure (armazenamento de Blob). Para obter mais informações, consulte [Manter a conta de armazenamento do Azure](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Visão Geral

Neste tópico, você executará duas etapas principais:

- Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento.
- Configure o cofre de chaves para armazenar o URI da conta de armazenamento.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento

1. Abra a conta de armazenamento que você pretende usar com o complemento de faturamento eletrônico.
2. Vá para **Serviço Blob** \> **Contêineres** e crie um novo contêiner.
3. Digite um nome para o contêiner e defina o campo **Nível de acesso público** como **Privado (sem acesso anônimo)**.
4. Abra o contêiner e vá para **Configurações \> Política de acesso**.
5. Selecione **Adicionar política** para adicionar uma política de acesso armazenada.
6. Defina os campos **Identificador** e **Permissões**, conforme apropriado. No campo **Permissões**, você deve selecionar todas as permissões.

    ![Conceder permissão de armazenamento de Blobs](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Insira as datas de início e de vencimento. A data de vencimento deve estar no futuro.
8. Selecione **OK** para salvar a política e salve as alterações no contêiner.
9. Retorne à conta de armazenamento e abra o **Gerenciador de Armazenamento (versão prévia)**.
10. Clique com o botão direito do mouse no contêiner e selecione **Obter assinatura de acesso compartilhado**.
11. Na caixa de diálogo **Assinatura de acesso compartilhado**, copie e armazene o valor no campo **URI**. Esse valor será usado no procedimento seguinte e será referenciado como *URI de assinatura de acesso compartilhado*.

    ![Selecionar e copiar o valor do URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configure o cofre de chaves para armazenar o URI da conta de armazenamento

1. Abra o cofre de chaves que você pretende usar com o complemento de faturamento eletrônico.
2. Vá para **Configurações** \> **Segredos** e selecione **Gerar/Importar** para criar um novo segredo.
3. Na página **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
4. Insira o nome do segredo. Esse nome será usado durante a configuração do serviço no RCS (Regulatory Configuration Service) e será referenciado como *Nome secreto do cofre de chaves*.
5. No campo **Valor**, selecione **URI de Assinatura de Acesso Compartilhado** e, em seguida, selecione **Criar**.
6. Configure a política de acesso para conceder ao complemento de faturamento eletrônico o nível correto de acesso seguro ao segredo criado. Vá para **Configurações \> Política de acesso** e selecione **Adicionar Política de Acesso**.
7. Defina as permissões secretas para as operações **Obter** e **Lista**.

    ![Conceder acesso ao serviço](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Defina as permissões de certificado para operações **Obter** e **Lista**.

    ![Conceder permissão de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. Na caixa de diálogo **Principal**, selecione o principal, adicionando o **Complemento de faturamento eletrônico**.
10. Selecione **Adicionar** e, em seguida, **Salvar alterações do Key Vault**.
11. Na página **Visão geral**, copie o valor **Nome do DNS** para o cofre de chaves. Esse valor será usado durante a configuração do serviço no RCS e será referenciado como o *URI do cofre de chaves*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]