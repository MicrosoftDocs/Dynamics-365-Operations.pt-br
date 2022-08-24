---
title: Criar uma conta de armazenamento do Azure no portal do Azure
description: Este artigo explica como criar uma conta de armazenamento do Azure para faturamento eletrônico.
author: gionoder
ms.date: 02/14/2022
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
ms.openlocfilehash: 5eca23985c48f4e577bd4567cc2e324df5aa9690
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291626"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Criar uma conta de armazenamento do Azure no portal do Azure

[!include [banner](../includes/banner.md)]

Todos os arquivos eletrônicos que são gerados pelo serviço de faturamento eletrônico ou acessam o serviço durante o processamento são armazenados em seus contêineres de conta de armazenamento do Microsoft Azure. Para garantir que o faturamento eletrônico possa acessar esses recipientes, você deve fornecer o token de assinatura de acesso compartilhado (SAS) da conta de armazenamento para o serviço de faturamento eletrônico. Além disso, para garantir que o token seja armazenado de forma segura, não forneça o token SAS diretamente. Em vez disso, armazene-o em um cofre de chaves do Azure e forneça um segredo do Azure Key Vault.

1. Abra a conta de armazenamento que você pretende usar com o serviço de faturamento eletrônico.
2. Vá para **Configurações** \> **Configuração** e verifique se o parâmetro **Permitir acesso público de blob** está definido como **Habilitado**.
3. Acesse **Armazenamento de dados** \> **Contêineres** e crie um novo contêiner.
4. Digite um nome para o contêiner e defina o campo **Nível de acesso público** como **Privado (sem acesso anônimo)**.
5. Abra o novo contêiner e acesse **Configurações** \> **Política de acesso**.
6. Selecione **Adicionar política** para adicionar uma política de acesso armazenada.
7. Defina o campo **Identificador**, conforme apropriado.
8. No campo **Permissões**, selecione todas as permissões.

    ![Todas as permissões selecionadas no campo permissões da caixa de diálogo Adicionar política.](media/e-invoicing-azure-1.png)

9. Insira as datas de início e de término. A data de término deve estar no futuro.
10. Selecione **OK** para salvar a política e salve as alterações no contêiner.
11. Vá para **Configurações** \> **Tokens de acesso compartilhado** e defina os valores do campo.
12. Insira as datas de início e de término. A data de término deve estar no futuro.
13. No campo **Permissões**, você deve selecionar as seguintes permissões:

    - Ler
    - Adicionar
    - Criar
    - Gravar
    - Excluir
    - Lista

14. Selecione **Gerar token SAS e URL**.
15. Copie e armazene o valor no campo **URL do SAS do blob**. Esse valor será usado depois neste procedimento e será referenciado como *URI de assinatura de acesso compartilhado*.
16. Abra o cofre de chaves que você pretende usar com o Faturamento eletrônico.
17. Acesse **Configurações** \> **Segredos** e selecione **Gerar/Importar** para criar um segredo.
18. Na página **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
19. Insira o nome do segredo. Esse nome será usado na configuração do serviço no RCS (Regulatory Configuration Service) e será referenciado como *Nome secreto do cofre de chaves*. Para obter mais informações sobre como configurar o RCS, consulte [Configurar o Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).
20. No campo **Valor**, digite o URL da assinatura de acesso compartilhado que você copiou antes.
21. Selecione **Criar**.
