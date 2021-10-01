---
title: Inserir aplicativos de terceiros
description: Este tópico explica como inserir aplicativos de terceiros para aumentar a funcionalidade do produto.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 89f101bcf33080f6a73664fe7c3fe6719de04a4e
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488225"
---
# <a name="embed-third-party-apps"></a>Inserir aplicativos de terceiros

[!include [banner](../includes/banner.md)]

Muitos clientes usam vários aplicativos para executar negócios. Alguns desses aplicativos são aplicativos Web de terceiros que funcionam junto com aplicativos do Finance and Operations. Para fornecer uma experiência de usuário mais uniforme, você pode usar o recurso **Aplicativos de página completa** para inserir diretamente os aplicativos de terceiros em aplicativos do Finance and Operations (desde que os aplicativos de terceiros permitam serem inseridos). Dessa forma, os usuários podem acessar os sites e os aplicativos necessários sem precisar alternar guias ou janelas.

Antes de inserir aplicativos de terceiros no produto, você deve ativar o recurso **Aplicativos de página completa** no gerenciamento de Recursos. Você pode usar um dos métodos a seguir para inserir um aplicativo ou site de terceiros. Esses métodos são análogos aos métodos usados para inserir aplicativos de tela do Microsoft Power Apps em aplicativos do Finance and Operations.

- Insira o aplicativo ou o site em uma página existente como uma nova página de guia (guia dinâmica, Guia Rápida, folha ou seção de espaço de trabalho).
- Crie uma nova experiência de página inteira para o aplicativo ou o site no painel.

## <a name="embed-a-website-on-an-existing-page"></a>Inserir um site em uma página existente

Use este procedimento se desejar complementar uma página existente no sistema com um aplicativo incorporado.

1. Abra a página onde deseja inserir o aplicativo.
2. Abra o painel **Adicionar um aplicativo**:

    1. Selecione **Configurações** e, depois, **Personalizar** para abrir a barra de ferramentas **Personalização**.
    2. Selecione **Mais \> Adicionar um aplicativo**.

3. Selecione a região da página em que você deseja adicionar o aplicativo. Essa região deve ser um *contêiner de guias* para uma guia dinâmica, Guia Rápida, folha ou seção de espaço de trabalho.
4. Selecione **Site**.
5. Configurar o aplicativo inserido:

    - **Nome** – insira o texto que deve ser mostrado para a guia que contém o aplicativo inserido. Em geral, você deseja que esse texto seja o nome do aplicativo.
    - **URL** – especifique o local do aplicativo.

    > [!IMPORTANT]
    > - Por motivos de segurança, a URL deve usar o HTTPS (Hypertext Transfer Protocol Secure).
    > - O aplicativo ou o site deve estar configurado para permitir que ele próprio seja inserido.

6. Selecione **Salvar** para inserir o aplicativo na página. O aplicativo é adicionado como a última guia ou seção no grupo.
7. Confirme se o aplicativo aparece como esperado. Se o aplicativo não for renderizado, consulte a seção [Solução de problemas](#troubleshooting) mais adiante neste tópico.
8. Abra o seletor de exibição e selecione **Salvar** (se o aplicativo for associado à exibição atual) ou **Salvar como** (para salvar o aplicativo em uma exibição diferente).

    Se a página não tiver um seletor de exibição (por exemplo, se a página for uma caixa de diálogo ou um espaço de trabalho), você poderá ignorar esta etapa.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Insira um site como uma experiência de página inteira do painel

Use este procedimento se o aplicativo que você deseja inserir não estiver relacionado a uma página existente ou se você quiser apenas uma experiência de página inteira para o aplicativo dentro do aplicativo do Finance and Operations.

1. Abra o painel.
2. Selecione e segure (ou clique com o botão direito do mouse) no painel, selecione **Personalizar** e, depois, **Adicionar uma página**.
3. No painel **Adicionar uma página**, selecione **Site**.
4. Configurar o aplicativo inserido:

    - **Nome** – Insira o texto que deve ser mostrado no bloco que é adicionado ao aplicativo inserido no painel. Em geral, você deseja que esse texto seja o nome do aplicativo.
    - **URL** – especifique o local do aplicativo.

    > [!IMPORTANT]
    > - Por questões de segurança, a URL deve usar HTTPS.
    > - O aplicativo ou o site deve estar configurado para permitir que ele próprio seja inserido.

5. Selecione **Salvar** para adicionar o aplicativo ao painel como um novo bloco.
6. Selecione o novo bloco no painel e confirme que o aplicativo aparece como esperado. Se o aplicativo não estiver sendo renderizado, consulte a seção [Solução de problemas](#troubleshooting) mais adiante neste tópico.

## <a name="sharing-embedded-apps"></a>Compartilhar aplicativos inseridos

Depois de inserir um aplicativo usando um dos métodos descritos nas seções anteriores, talvez você deseje compartilhar a exibição com outros usuários no sistema. Para compartilhar um aplicativo inserido, use um dos seguintes métodos:

- **Publicar a exibição (Recomendado):** se o aplicativo inserido tiver sido salvo em uma exibição, a forma recomendada e preferível de compartilhá-lo é publicar a exibição para usuários com as funções de segurança apropriadas nas entidades legais direcionadas. Nesse caso, somente os usuários desejados verão o aplicativo incorporado nessa página. Para obter mais informações sobre como publicar uma exibição, consulte [Publicar exibições](saved-views.md#publishing-views).

    Você também pode publicar um aplicativo que foi inserido como uma experiência de página inteira a partir do painel. No painel, selecione e segure (ou clique com o botão direito do mouse) no bloco associado ao aplicativo, selecione **Personalizar** e, depois, **Publicar página**. Uma experiência semelhante à experiência de *Publicação de exibições* é mostrada e você pode selecionar os direitos de acesso a serem publicados. Na atualização 10.0.21 ou posterior, se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, você também poderá publicar o aplicativo nas entidades legais desejadas.

- **Copiar a personalização:** para páginas que não dão suporte a exibições (por exemplo, caixas de diálogo ou espaços de trabalho) ou para a experiência do aplicativo de página inteira, você pode copiar a personalização para os usuários apropriados. Para obter mais informações, consulte [Compartilhar personalizações](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Exibir aplicativos inseridos

Para exibir um aplicativo inserido em uma página em aplicativos do Finance and Operations, abra a página que tem o aplicativo inserido. Lembre-se de que, em algumas páginas, aplicativos inseridos podem ser acessados usando o botão **Power Apps** no Painel de Ações padrão. Eles podem aparecer diretamente na página como uma nova guia, Guia Rápida, folha ou uma nova seção em um espaço de trabalho.

## <a name="editing-or-removing-embedded-apps"></a>Editar ou remover aplicativos inseridos

Após um aplicativo ser inserido em uma página, talvez seja necessário editar a configuração (por exemplo, alterando o rótulo da seção ou a URL). Como alternativa, talvez seja necessário removê-lo da página. Use um dos procedimentos a seguir para editar a configuração de um aplicativo inserido ou removê-lo totalmente.

### <a name="apps-that-are-embedded-on-existing-pages"></a>Aplicativos inseridos em páginas existentes

1. Abra a página em que o aplicativo é inserido.
2. Selecione **Configurações** e, depois, **Personalizar** para abrir a barra de ferramentas **Personalização**.
3. Selecione a ferramenta **Selecionar** e, depois, selecione o aplicativo inserido.
4. Para editar o aplicativo, faça as alterações necessárias em sua configuração e selecione **Salvar**.

    Outra opção para remover o aplicativo é selecionar **Excluir**.

5. Salve novamente ou republique a exibição. Observe que, se você deixar a página sem salvar explicitamente a exibição, nenhuma das ações executadas no painel **Editar site** será mantida.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Aplicativos inseridos a partir do painel

1. Abra o painel.
2. Selecione e segure (ou clique com o botão direito do mouse) no bloco associado ao aplicativo inserido. Depois, selecione **Personalizar**.
3. Para editar o aplicativo, selecione **Editar página**. No painel **Editar site**, faça as alterações necessárias na configuração do aplicativo e selecione **Salvar**.

    Outra opção para remover o aplicativo é selecionar **Remover página**.

## <a name="appendix"></a>Anexo

### <a name="troubleshooting"></a>Solução de problemas

Se um site não for renderizado corretamente após ser inserido em um aplicativo do Finance and Operation, ou se você receber uma mensagem de erro indicando que uma conexão foi negada à URL, o site provavelmente será configurado para evitar que ele próprio seja inserido em um iFrame. Siga estas etapas para determinar se o site pode ser inserido.

1. Abra as ferramentas de desenvolvedor do navegador que você está usando.
2. Na guia **Rede**, localize e selecione a resposta no site inserido.
3. Na guia **Cabeçalhos**, em **Cabeçalhos de Resposta**, procure **x-frame-options**. Se **x-frame-options** existir nos cabeçalhos de resposta, e tiver o valor de **DENY** ou **SAMEORIGIN**, o site não poderá ser inserido no momento. Você precisará trabalhar com o proprietário do aplicativo para permitir que ele seja inserido com segurança.

### <a name="developer-modeling-a-website-on-a-form"></a>[Desenvolvedor] Modelar um site em um formulário

Embora este tópico foque a inserção de aplicativos ou sites de terceiros por meio de personalização, os desenvolvedores também podem inseri-los em um formulário usando a experiência de desenvolvimento do Visual Studio. Basta adicionar um controle **WebsiteHostControl** ao formulário. As propriedades de metadados disponíveis para o controle fornecem os mesmos recursos que a experiência de personalização.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
