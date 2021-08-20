---
title: Criar um novo recurso de Faturamento eletrônico
description: Este tópico explica como criar um novo recurso de Faturamento eletrônico quando nenhum recurso configurável pronto para uso está disponível para seu país ou região.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744926"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Criar um novo recurso de Faturamento eletrônico

[!include [banner](../includes/banner.md)]

Este tópico explica como criar um novo recurso de Faturamento eletrônico quando nenhum recurso configurável pronto para uso está disponível para seu país ou região.

Para criar um novo recurso de Faturamento eletrônico, realize estas tarefas:

1. Crie uma nova configuração de formato de arquivo usando a configuração do modelo de fatura fornecida, e aproveite o mapeamento de fatura existente para o recurso que você deseja criar.
2. Adicione as configurações do formato de arquivo às configurações do recurso de Faturamento eletrônico.
3. Crie a configuração do recurso de Faturamento eletrônico.
4. Conclua o novo recurso de Faturamento eletrônico e publique-o no Repositório global da sua organização.
5. Implante o novo recurso de Faturamento eletrônico no ambiente de Serviço.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Criar novas configurações de formato de arquivo derivadas do modelo de fatura existente

Neste procedimento, você criará as configurações de formato de arquivo necessárias para o novo recurso de Faturamento eletrônico que deseja criar. É possível criar a configuração de formato de arquivo de fatura eletrônica e qualquer outra configuração de formato de arquivo que seu novo recurso de Faturamento eletrônico possa exigir.

Antes de iniciar este procedimento, faça login na sua conta de serviço do Regulatory Configuration Service (RCS).

1. No Microsoft Dynamics 365 Finance, no espaço de trabalho **Relatório eletrônico**, selecione **Repositórios** para o provedor de configuração **Microsoft**.
2. Selecione **Global**, **Abrir** e, no painel esquerdo, selecione a configuração **Modelo de fatura**.

    > [!IMPORTANT]
    > Para o Brasil, selecione a configuração de modelo **Documentos fiscais**.

3. Na guia **Configurações**, selecione **Importar**.
4. Feche a página.
5. Feche a página.
6. Selecione o bloco **Configurações de relatório** e, em seguida, o modelo de fatura importado.
7. Selecione **Criar configuração** e, em seguida, **Formato com base no modelo de contexto de fatura**.
8. Digite um nome e uma descrição para a configuração do formato.
9. No campo **Tipo de formato**, selecione o tipo de extensão de arquivo.
10. Selecione **Criar configuração** e, em seguida, a configuração de formato que você criou.
11. Selecione **Designer** e use a ferramenta Designer de formato para configurar o layout do arquivo para que ele atenda às especificações de formato de arquivo.
12. Feche a página.
13. Na guia **Versões**, selecione **Alterar status** \> **Concluir**.
14. Selecione **Alterar status** \> **Compartilhar** para publicar a configuração de formato no Repositório global.

A nova configuração de formato de arquivo precisa ser compartilhada com o domínio Microsoft para que possa ser consumida pelo serviço de Faturamento eletrônico.

1. Selecione a configuração de formato na qual você está trabalhando. O status da configuração precisa ser **Compartilhado**.
2. Na guia **Versões**, selecione **Compartilhamento avançado** \> **Repositório global**.
3. Na guia **Compartilhado com**, selecione **Organização**.
4. No campo **Parâmetros**, digite **Microsoft.com** para compartilhar a configuração de formato com o domínio Microsoft.
5. Selecione **OK**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Criar o novo recurso de Faturamento eletrônico

1. No RCS, no espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
2. Selecione **Adicionar** e, em seguida, **Novo recurso**.
3. Insira um nome e uma descrição para o recurso de Faturamento eletrônico.
4. Selecione **Criar recurso**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Adicionar configurações do recurso de Faturamento eletrônico

1. Selecione o recurso de Faturamento eletrônico no qual você está trabalhando.
2. Na guia **Configurações**, selecione **Adicionar**.
3. Na grade **Configurações**, procure e selecione as configurações de formato de arquivo que o recurso de Faturamento eletrônico exige para gerar o arquivo de fatura eletrônica.
4. Selecione **OK**.

## <a name="add-electronic-invoicing-feature-setups"></a>Adicionar configurações do recurso de Faturamento eletrônico

1. Na guia **Configurações**, selecione **Adicionar** e, em seguida, **Configuração personalizada**.
2. Insira um nome e uma descrição para a configuração do recurso.
3. No campo **Tipo de configuração**, selecione **Pipeline de processamento**.
4. Selecione **Criar**.
5. Selecione a configuração na qual você está trabalhando e, em seguida, **Editar**.
6. Na guia **Pipeline de processamento**, selecione **Novo** para adicionar uma ação de pipeline. Para obter mais informações sobre pipelines, consulte [Ações](e-invoicing-configuration-rcs.md#actions).
7. Na guia **Regras de aplicabilidade**, selecione **Nova** para adicionar cláusulas da regra de aplicabilidade. Para obter mais informações sobre regras de aplicabilidade, consulte [Regras de aplicabilidade](e-invoicing-configuration-rcs.md#applicability-rules).
8. Na guia **Variáveis**, selecione **Nova** para adicionar variáveis, conforme necessário.
9. Selecione **Salvar** e, em seguida, **Validar** para verificar a consistência da configuração.
10. Feche a página.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Implantar o recurso de Faturamento eletrônico no ambiente de Serviço

Para obter informações sobre como concluir essa tarefa, consulte [Implantar o recurso de Faturamento eletrônico ao Ambiente de serviço](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Implantar o recurso de Faturamento eletrônico ao aplicativo conectado

Para obter informações sobre como concluir essa tarefa, consulte [Configurar a configuração do aplicativo](e-invoicing-get-started.md#configure-the-application-setup) e [Implantar o recurso de Faturamento eletrônico ao Aplicativo conectado](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
