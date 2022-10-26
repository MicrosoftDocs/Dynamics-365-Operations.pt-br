---
title: Configurações avançadas da solução Invoice Capture
description: Este artigo fornece informações sobre configurações avançadas na solução Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691125"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Configurações avançadas da solução Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo fornece informações sobre configurações avançadas na solução Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Criar conexões adicionais para canais

Você deve criar conexões para o armazenamento de emails ou arquivos para permitir o monitoramento de faturas de entrada de diferentes canais. Você deve registrar as conexões no início para conceder acesso a fluxos automatizados usados na solução.

Os tipos de conexão a seguir são usados para importar faturas:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

O canal para a importação de faturas usará as conexões em etapas de configuração adicionais. Para que os usuários possam criar um canal de uma conexão específica, a função de segurança **Administrador** deve ser concedida a eles e os usuários devem criar conexões.

Para criar uma conexão ao Microsoft Dataverse, siga estas etapas.

1. Vá para **Sistema administrativo \> Solução padrão**.
2. Selecione **Novo** e, em seguida, selecione **Referência de Conexão**.
3. No campo **Nome de exibição**, insira um nome.
4. Selecione **Microsoft Dataverse** como o conector.
5. Se estiver configurando a conexão pela primeira vez, selecione **Nova conexão**.
6. Na caixa de diálogo mostrada, crie uma conexão do Dataverse e, em seguida, selecione **Criar**.
7. Insira a conta e a senha do Dataverse.
8. Depois que a validação for aprovada, vá para a página de conexão, selecione **Atualizar**, escolha a conta e, em seguida, selecione **Criar**.

Para criar conexão para o armazenamento de emails ou arquivos, siga estas etapas.

1. Na página **Criação de conexão**, no campo **Tipo de conexão**, selecione **Office 365 Outlook**.
2. Para uma conexão de email, você pode selecionar **Outlook.com** ou **Office 365 Outlook** como o conector. Para uma conexão de armazenamento de arquivos, você pode selecionar **OneDrive** ou **SharePoint**.

Para verificar as conexões existentes, vá para **Solução padrão \> Objetos \> Referências de Conexão**. O usuário que cria canais deve ter pelo menos uma conexão do Dataverse, além das conexões específicas de armazenamento de arquivos ou de email. O criador do novo canal deve ser o proprietário da conexão.
