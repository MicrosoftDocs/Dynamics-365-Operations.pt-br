---
title: Configurar uma conexão do SharePoint
description: Este artigo explica como configurar uma conexão para que o faturamento eletrônico possa acessar um site da Microsoft SharePoint.
author: gionoder
ms.date: 12/15/2021
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
ms.openlocfilehash: a2762178686d1f29c457b6de2a9b052fd048484b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283977"
---
# <a name="configure-a-sharepoint-connection"></a>Configurar uma conexão do SharePoint

[!include [banner](../includes/banner.md)]

O serviço de faturamento eletrônico pode ler arquivos de pastas do Microsoft SharePoint e carregar arquivos no SharePoint. Para garantir que o faturamento eletrônico possa acessar um site específico do SharePoint, você deve fornecer as credenciais do site ao serviço de faturamento eletrônico. Além disso, para garantir que as credenciais sejam armazenadas de forma segura, não as forneça diretamente. Em vez disso, armazene-as em um cofre de chaves do Azure e forneça um segredo do Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>Conceder acesso a uma do pasta SharePoint

1. Crie um registro de aplicativo no locatário em que o RCS (Regulatory Configuration Service) está instalado.

    1. Entre no [portal do Azure](https://portal.azure.com/).
    2. Vá para **Registros de aplicativos**.
    3. Selecione **Novo registro**.
    4. Insira um nome, tal como **Aplicativo SharePoint para faturamento eletrônico**, e conclua o registro
    5. Selecione o registro do novo aplicativo.
    6. Na guia **Autenticação**, habilite a opção **Permitir fluxos de cliente público**.
    4. Na guia **Certificados e segredos**, selecione **Novo segredo de cliente** para criar um segredo de cliente.
    5. Copie o valor do segredo que foi criado.

    Siga estas diretrizes:

    - Não use o mesmo registro de aplicativo para serviços diferentes.
    - Siga as [recomendações de diretiva de senha](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Configure a rotação de senhas. Durante a rotação, crie um novo segredo de cliente para o registro do aplicativo, atualize o cofre de chaves e exclua o segredo antigo.

2. Salve os valores de **Segredo do Registro de aplicativo** e **ID (cliente) do aplicativo** como dois segredos novos no cofre de chaves na configuração do seu ambiente de faturamento eletrônico.
3. Adicione os segredos que você criou aos parâmetros do cofre de chaves na configuração do seu ambiente de faturamento eletrônico no RCS.
4. No portal do Azure, conceda acesso ao SharePoint. Essa etapa deve ser concluída pelo administrador do locatário.

    1. Selecione o registro de aplicativo que você criou.
    2. Na guia **Permissões de API**, selecione **Adicionar uma permissão**.
    3. Selecione **Microsoft Graph (permissões de aplicativo)** \> **Sites.Selected**.
    4. Selecione **Conceder consentimento de administrador para \<user&nbsp;name\>**.
    5. Revise o campo **Status** para verificar se as permissões foram concedidas.

        ![Permissões concedidas na guia Permissões de API.](media/configured-permissions.jpg)

    6. Abra [Explorador do Graph - Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) e faça login.
    7. No painel esquerdo, na guia **Consultas de exemplo**, em **Sites do SharePoint**, selecione **obter site com base no caminho relativo do site do SharePoint**.
    8. Preencha os parâmetros **\{host-name\}** e **\{server-relative-path\}**. Por exemplo, preencha `<domain>.sharepoint.com` para **\{host-name\}** e `sites/<siteName>` para **\{server-relative-path\}**.

        > [!NOTE]
        > Para o site padrão, deixe o parâmetro **\{server-relative-path\}** em branco.

    9. Selecione **Executar consulta** e salve o resultado.
    10. Configure a consulta a seguir.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        Nessa consulta, **\{site-id\}** é o valor do nó **id** da resposta de consulta anterior.

        Este é o corpo da solicitação.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        Neste corpo da solicitação, **\{app-id\}** é o valor **ID (cliente) do aplicativo** e **\{app-name\}** do aplicativo é o valor do **Nome do aplicativo**.

        ![Consulta POST.](media/app-id-query.jpg)

    11. Na guia **Permissões de modificação**, selecione **Abrir o painel permissões** e, em seguida, selecione **Sites** \> **Sites.FullControl.All** \> **Consentimento**.
    12. Selecione **Executar consulta**.

Agora o serviço de faturamento eletrônico tem acesso ao seu site do SharePoint.
