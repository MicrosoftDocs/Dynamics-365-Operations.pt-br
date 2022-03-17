---
title: Criar um Recurso de globalização
description: Este tópico explica como criar um Recurso de globalização.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 197a5b983b307758425b1acc1f354d0a8bfbf8a1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371523"
---
# <a name="create-a-globalization-feature"></a>Criar um Recurso de globalização

[!include [banner](../includes/banner.md)]

Você pode criar um recurso de faturamento eletrônico do zero ou baseá-lo em um recurso existente. Ao criar um recurso do zero, você deve adicionar manualmente as configurações de ER e outros componentes, como a configuração da versão do recurso e detalhes da configuração do aplicativo. Quando você cria um recurso que se baseia em um recurso existente, o novo recurso herda todas as configurações e os parâmetros do recurso base. Você pode revisar o que é copiado do recurso base para o novo recurso.

## <a name="create-a-feature-from-scratch"></a>Criar um recurso do zero

Esta seção explica como criar um novo recurso de faturamento eletrônico quando nenhum Recurso de globalização estiver disponível imediatamente no Repositório global para seus cenários de negócio.

Para criar um recurso de faturamento eletrônico, siga estas etapas.

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Selecione **Adicionar**, na caixa de diálogo suspensa, selecione a opção **Novo recurso**.
4. Insira um nome e uma descrição para o recurso de faturamento eletrônico.
5. Selecione **Criar recurso**. A primeira versão do novo recurso aparece no lado direito da página e tem o status **Rascunho**.

    Em seguida, você deve adicionar configurações de ER e configurações de recurso. Antes de adicionar configurações de formato de ER novas ou existentes, verifique se elas existem no repositório agora do RCS.

6. Selecione o recurso de faturamento eletrônico no qual você está trabalhando.
7. Na guia **Configurações**, selecione **Adicionar**.
8. Na grade **Configurações**, procure e selecione as configurações de formato necessárias para o pipeline de processamento (por exemplo, para gerar arquivos de fatura eletrônica ou respostas de processo de serviços Web externos).
9. Selecione **OK**. Agora você pode usar as configurações em ações do pipeline de processamento. Para obter mais informações, consulte [Trabalhar com configurações](e-invoicing-work-configurations.md).
10. Para adicionar uma configuração de recurso de faturamento eletrônico, crie-a na guia **Configurações** da página **Novo recurso**. Para obter mais informações, consulte [Trabalhar com configurações de recurso](e-invoicing-feature-setup.md).
11. Conclua a configuração e implante o recurso de faturamento eletrônico no ambiente de serviço. Para obter mais informações, consulte [Concluir, publicar e implantar um Recurso de globalização](e-invoicing-complete-publish-deploy-globalization-feature).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Criar configurações de formato de arquivo derivadas do modelo de fatura existente

Você pode ignorar esta seção se não precisar criar configurações de ER, mas pode reutilizar versões existentes como base.

Este procedimento mostra como criar as configurações de formato de arquivo necessárias para o novo recurso de faturamento eletrônico que deseja criar. Crie a configuração de formato de arquivo de fatura eletrônica e qualquer outra configuração de formato de arquivo que seu novo recurso de faturamento eletrônico exija.

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.
3. Selecione o **Modelo de fatura** ou, para cenários brasileiros, selecione o **Modelo fiscal**.
4. Selecione **Criar configuração** e, na caixa de diálogo suspensa, selecione a opção **Formato baseado no modelo de dados Fatura**.
5. Digite um nome e uma descrição para a configuração do formato.
6. No campo **Tipo de formato**, selecione o tipo de extensão de arquivo.
7. No campo **Definição do modelo de dados**, selecione a estrutura raiz para a qual o formato será mapeado. Por exemplo, **InvoiceCustomer** é usado para os formatos de fatura de cliente.
8. Selecione **Criar configuração**.
9. Selecione a nova configuração de formato.
10. Selecione **Designer** e use a ferramenta Designer de formato para configurar o layout do arquivo para que ele atenda às especificações de formato de arquivo.
11. Feche a página.
12. Na guia **Versões**, selecione **Alterar status** \> **Concluir**.
13. Selecione **Alterar status** \> **Compartilhar** para publicar a configuração de formato no Repositório global.

As novas configurações de formato de arquivo precisa ser compartilhada com o domínio Microsoft para que possam ser consumidas pelo serviço de Faturamento eletrônico.

1. Selecione a configuração de formato na qual você está trabalhando. O status da configuração precisa ser **Compartilhado**.
2. Na guia **Versões**, selecione **Compartilhamento avançado** \> **Repositório global**.
3. Na guia **Compartilhado com**, selecione **Organização**.
4. No campo **Parâmetros**, digite **microsoft.com** para compartilhar a configuração de formato com o domínio Microsoft.
5. Selecione **OK**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Criar um recurso que se baseie em um recurso existente

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. No campo **Provedor de configuração**, certifique-se de selecionar seu provedor de configuração ativo. Dessa forma, o novo recurso de faturamento eletrônico aparecerá na lista após sua criação. Se o seu provedor de configuração ativo não estiver selecionado, o novo recurso será filtrado para fora da lista.
4. Selecione **Adicionar** e , na caixa de diálogo suspensa, selecione a opção **Com base na versão existente**.
5. Digite um nome e uma descrição para o recurso.
6. No campo **Recurso base**, selecione a versão base do recurso.
7. Selecione **Criar recurso**. O recurso é criado e tem o status **Rascunho**.
8. Revise os componentes do recurso para determinar se as atualizações são necessárias:

    - Revise as configurações, caso você precise personalizar os formatos de ER e sua associação com mapeamentos de formato para a versão do recurso.
    - Revise a configuração caso você precise personalizar a guia **Ações**, **Regras de aplicabilidade** ou a guia **Variáveis** para a versão do recurso.

9. Conclua a configuração e implante o recurso de faturamento eletrônico no ambiente de serviço. Para obter mais informações, consulte [Concluir, publicar e implantar um Recurso de globalização](e-invoicing-complete-publish-deploy-globalization-feature).
