---
title: Criar uma conta de armazenamento do Azure e um cofre de chaves
description: Este tópico explica como criar uma conta de armazenamento do Azure e um cofre de chaves.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 5c2ddad10f9cbedd77a04fe0f42bdc217fd43344
ms.sourcegitcommit: 54d3ec0c006bfa9d2b849590205be08551c4e0f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5963230"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Criar uma conta de armazenamento do Azure e um cofre de chaves

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas neste tópico, verifique se as seguintes tarefas foram concluídas:

- Criar um recurso de cofre de chaves no Azure. Para obter mais informações, consulte [Sobre o Azure Key Vault](/azure/key-vault/general/overview).
- Crie uma conta de armazenamento do Azure (armazenamento de Blob). Para obter mais informações, consulte [Manter a conta de armazenamento do Azure](/azure/storage/blobs/).

## <a name="overview"></a>Visão Geral

Neste tópico, você executará duas etapas principais:

- Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento.
- Configure o cofre de chaves para armazenar o URI da conta de armazenamento.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento

1. Abra a conta de armazenamento que você planeja usar com o Faturamento eletrônico.
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

1. Abra o cofre de chaves que você pretende usar com o Faturamento eletrônico.
2. Vá para **Configurações** \> **Segredos** e selecione **Gerar/Importar** para criar um novo segredo.
3. Na página **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
4. Insira o nome do segredo. Esse nome será usado durante a configuração do serviço no RCS (Regulatory Configuration Service) e será referenciado como *Nome secreto do cofre de chaves*.
5. No campo **Valor**, selecione **URI de Assinatura de Acesso Compartilhado** e, em seguida, selecione **Criar**.
6. Configure a política de acesso para conceder ao Faturamento eletrônico o nível correto de acesso seguro ao segredo criado. Vá para **Configurações \> Política de acesso** e selecione **Adicionar Política de Acesso**.
7. Defina as permissões secretas para as operações **Obter** e **Lista**.

    ![Conceder acesso ao serviço](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Defina as permissões de certificado para operações **Obter** e **Lista**.

    ![Conceder permissão de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. No campo **Selecionar principal**, selecione **Nenhum selecionado**.
10. Na caixa de diálogo **Entidade de segurança**, selecione a entidade de segurança, adicionando o **Serviço de faturamento eletrônico**.
11. Selecione **Adicionar** e, em seguida, **Salvar alterações do Key Vault**.
12. Na página **Visão geral**, copie o valor **Nome do DNS** para o cofre de chaves. Esse valor será usado durante a configuração do serviço no RCS e será referenciado como o *URI do cofre de chaves*.

> [!NOTE]
> Para obter segurança adicional na conta de armazenamento, configure o Azure Defender para armazenamento.
> 
> Para obter mais informações, consulte [Introdução ao Azure Defender para armazenamento](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
