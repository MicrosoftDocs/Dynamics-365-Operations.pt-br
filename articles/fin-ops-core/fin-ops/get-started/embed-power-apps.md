---
title: Inserir aplicativos de tela a partir do Power Apps
description: Este artigo explica como inserir aplicativos de tela do Microsoft Power Apps no cliente para aumentar a funcionalidade do produto.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: fb81aa058e749df346ee87bbe83427b20b234b72
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898388"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Inserir aplicativos de tela do Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

O Microsoft Power Apps é um serviço que permite que desenvolvedores e usuários não técnicos criem aplicativos de negócios personalizados para dispositivos móveis, tablets e a Web sem precisar escrever código. Integração do suporte a aplicativos de Finanças e Operações com o Power Apps. Aplicativos de tela que você, sua organização ou o ecossistema mais amplo desenvolvem podem ser inseridos em aplicativos de Finanças e Operações para aumentar a funcionalidade do produto. Por exemplo, você pode criar um aplicativo de tela no Power Apps que complemente o aplicativo de Finanças e Operações com informações recuperadas de outro sistema.

Para saber mais sobre como incorporar aplicativos de tela, assista ao breve vídeo [Como inserir aplicativos de tela](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Adicionando um aplicativo de tela do Power Apps inserido em uma página

Antes de inserir um aplicativo de tela do Power Apps no cliente, você deve encontrar ou criar um aplicativo que tenha os recursos visuais ou funcionalidades desejados. Este artigo não inclui uma descrição detalhada do processo de criação de aplicativos. Se você está começando a usar o Power Apps, consulte a [documentação do Power Apps](/powerapps/).

Há três maneiras de incorporar um aplicativo de tela a um aplicativo de Finanças e Operações. Você pode usar a abordagem que melhor atende ao seu cenário. 

- Insira o aplicativo de tela no botão do **Power Apps** no Painel de Ação padrão de uma página. Os aplicativos que você adiciona dessa maneira aparecem como itens no botão de menu do **Power Apps** e os aplicativos abertos em painéis laterais. 
- Insira o aplicativo de tela diretamente em uma página existente como uma nova página de guia (guia dinâmica, Guia Rápida, folha ou seção de espaço de trabalho).
- Crie uma nova experiência de página inteira para o aplicativo de tela ou o painel.

Ao configurar seu aplicativo de tela inserido, você pode selecionar um único campo que deseja enviar como contexto para o aplicativo. Essa etapa permite que o aplicativo responda com base nos dados que você está exibindo atualmente.

> [!NOTE]
> Não é possível usar esse mecanismo para inserir aplicativos baseados em modelo.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Incorporando um aplicativo de tela em uma página existente

O procedimento a seguir mostra como inserir um aplicativo de tela em uma página existente do Power Apps.

1. Acesse a página onde deseja inserir o aplicativo de tela. Esta página conterá os dados que devem ser informados para o aplicativo como entrada.
2. Abra o painel **Adicionar aplicativo do Power Apps**:

    - Se o aplicativo for inserido diretamente na página, selecione **Opções** \> **Personalizar esta página** \> **Mais** e siga uma destas etapas:

        - Se o recurso **Aplicativos de página inteira** estiver ativado, selecione **Adicionar uma página** e selecione a região na qual você deseja adicionar o aplicativo. Para inserir o aplicativo no botão do menu do **Power Apps**, selecione o Painel de Ação. Para inserir o aplicativo diretamente na página, seleciona a guia apropriada, Guia Rápida, folha ou seção (se estiver em um espaço de trabalho). Em seguida, no painel **Adicionar um aplicativo**, selecione **Power Apps**.
        - Se o recurso **Aplicativos de página inteira** estiver desativado, selecione **Adicionar um aplicativo do Power Apps** e depois selecione a região na qual você deseja adicionar o aplicativo. Para inserir o aplicativo no botão do menu do **Power Apps**, selecione o Painel de Ação. Para inserir o aplicativo diretamente na página, seleciona a guia apropriada, Guia Rápida, folha ou seção (se estiver em um espaço de trabalho).

    - Se o aplicativo for acessado usando o botão do menu **Power Apps**, selecione o botão de menu do **Power Apps** no Painel de Ação padrão e, em seguida, selecione **Adicionar um aplicativo**.

3. Configurar o aplicativo inserido. Para obter mais informações, consulte a seção [Configurar um aplicativo de tela](#configuring-a-canvas-app) posteriormente neste artigo.
4. Depois de confirmar que a configuração está correta, selecione **Inserir**.

    - Se o recurso **Exibições salvas** estiver desativado, será solicitado que você atualize o navegador para ver o aplicativo inserido.
    - Se o recurso **Exibições salvas** estiver ativado, você deverá salvar a exibição para que a alteração seja persistida.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Inserindo um aplicativo de tela como uma experiência de página inteira do painel

Talvez você deseje inserir um aplicativo de tela do painel se o aplicativo não estiver relacionado a uma página existente, ou se você quiser destacar o aplicativo como uma experiência de página inteira no aplicativo de Finanças e Operações.

> [!NOTE]
> Para disponibilizar esse recurso, você deve ativar o recurso **Aplicativos de página inteira** no gerenciamento de Recursos. 

1. Abra o painel.
2. Selecione e segure (ou clique com o botão direito do mouse) na página, selecione **Personalizar** e, depois, **Adicionar uma página**.
3. No painel **Adicionar uma página**, selecione **Power Apps**.
4. Configurar o aplicativo inserido. Para obter mais informações, consulte a seção [Configurar um aplicativo de tela](#configuring-a-canvas-app) posteriormente neste artigo.
5. Selecione **Salvar** para adicionar o aplicativo ao painel como um novo bloco.
6. Selecione o novo bloco no painel e confirme que o aplicativo de tela aparece como esperado.

### <a name="configuring-a-canvas-app"></a>Configurando um aplicativo de tela

Ao incorporar um aplicativo de tela, você deve definir os seguintes parâmetros:

- **Nome** – insira o texto que deve ser mostrado para o botão ou guia que conterá o aplicativo inserido. Geralmente, convém repetir o nome do aplicativo neste campo.
- **ID do Aplicativo** - especifica o identificador global exclusivo (GUID) para o aplicativo de tela que você deseja inserir. Para recuperar este valor, localize o aplicativo no [make.powerapps.com](https://make.powerapps.com) e localize o campo **ID do Aplicativo** em **Detalhes**.
- **Contexto de entrada para o aplicativo** – você pode selecionar o campo contendo os dados que você quer informar para o aplicativo como entrada. Para obter informações sobre como o aplicativo pode acessar os dados enviados de aplicativos de finanças e operações, consulte a seção [Criar um aplicativo que aproveita dados enviados de aplicativos de finanças e operações](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) mais adiante neste artigo.

    A partir da versão 10.0.19, a entidade legal atual também será passada como contexto para o aplicativo de tela por meio do parâmetro da URL **cmp**. Esse comportamento não afetará no aplicativo de tela de destino até que o aplicativo use essas informações.

- **Tamanho do aplicativo** – Selecione o tipo de aplicativo que você está inserindo. Selecione **Pequeno** para aplicativos criados para dispositivos móveis e **Grande** para aplicativos criados para tablets. Esse parâmetro garantirá que uma quantidade suficiente de espaço seja alocada para o aplicativo inserido.
- **Entidades legais** – você pode selecionar as entidades legais para as quais o aplicativo deve estar disponível. Por padrão, o aplicativo está disponível para todas as entidades legais. Esta opção está disponível somente quando você insere diretamente em uma página existente e o recurso **[Exibições salvas](saved-views.md)** está desativado.

## <a name="sharing-an-embedded-app"></a>Compartilhando um aplicativo inserido

Depois de inserir um aplicativo de tela em uma página e confirmar que ele está funcionando corretamente com qualquer contexto de dados informado dessa página, talvez você queira compartilhar o aplicativo com outros usuários do sistema. Para compartilhar um aplicativo de tela inserido, siga as etapas a seguir.

1. [Compartilhar o aplicativo de tela no Power Apps](/powerapps/maker/canvas-apps/share-app) com os usuários apropriados para que eles possam acessar o aplicativo no Power Apps.
2. Compartilhe as personalizações associadas ao aplicativo inserido com os usuários desejados. É possível usar uma das seguintes abordagens:

    - **Publicar o modo de exibição (recomendado):** se o recurso **[Exibições salvas](saved-views.md)** estiver ativado, a abordagem recomendada e preferida é criar um modo de exibição que inclua o aplicativo de tela incorporado e, em seguida, publicar essa exibição para os usuários desejados. Essa abordagem garante que todos os usuários que possuem as funções de segurança que são direcionadas pela exibição publicada verão o aplicativo de tela na página.

        Você também pode publicar um aplicativo de tela que foi inserido como uma experiência de página inteira a partir do painel. No painel, selecione e segure (ou clique com o botão direito do mouse) no bloco associado ao aplicativo, selecione **Personalizar** e, depois, **Publicar página**. Uma experiência semelhante à experiência de *Publicação de exibições* é mostrada e você pode selecionar os direitos de acesso a serem publicados. Na atualização 10.0.21 ou posterior, se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, você também poderá publicar o aplicativo nas entidades legais desejadas.

    - Se o recurso **Exibições salvas** estiver desativado, o administrador do sistema poderá fornecer uma personalização que inclui o aplicativo de tela para o conjunto apropriado de usuários por meio da página **Personalização**. Como alternativa, você pode exportar as personalizações de sua página e enviá-las a um ou mais usuários. Cada um desses usuários pode então importar a personalização. A barra de ferramentas contém botões que permitem exportar e importar personalizações.

> [!NOTE]
> Se o aplicativo de tela foi compartilhado com usuários externos, esses usuários não podem usar o aplicativo inserido em aplicativos de Finanças e Operações. No entanto, eles podem acessar o aplicativo diretamente no Power Apps. Os usuários externos incluem convidados e usuários que não pertencem ao Microsoft 365 Azure Directory onde o aplicativo de Finanças e Operações é implantado.

Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes sobre os recursos de personalização do produto e como usá-los.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Criar um aplicativo de tela que usa dados enviados de aplicativos de Finanças e Operações

Ao criar um aplicativo de tela que será inserido em um aplicativo de Finanças e Operações, uma parte importante do processo é usar os dados de entrada desse aplicativo de Finanças e Operações. A partir da experiência de desenvolvimento do Power Apps, os dados de entrada transferidos de um aplicativo de Finanças e Operações podem ser acessados usando a variável **Param("EntityId")**. Somado a isso, a partir da versão 10.0.19, a entidade legal atual também será passada para o aplicativo de tela por meio da variável **Param("cmp")**. 

Por exemplo, na função OnStart do aplicativo, você pode definir os dados de entrada de aplicativos de Finanças e Operações para uma variável como esta:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Exibição de um aplicativo de tela

Para exibir um aplicativo de tela inserido em uma página em aplicativos de Finanças e Operações, basta ir para uma página que tenha um aplicativo inserido. Lembre-se de que os aplicativos podem ser acessados usando o botão **Power Apps** no Painel de Ações padrão. Se preferir, eles podem aparecer diretamente na página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho. Quando os usuários tentarem carregar um aplicativo pela primeira vez em uma página, eles serão solicitados a fazer logon. Essa etapa garante que os usuários tenham as permissões apropriadas para usar o aplicativo.

## <a name="editing-an-embedded-app"></a>Editando um aplicativo inserido

Depois que um aplicativo for inserido em uma página, será necessário fazer algumas alterações para a configuração desse aplicativo. Por exemplo, talvez você queira modificar a etiqueta associada ao aplicativo inserido ou uma nova versão de um aplicativo foi criada e você precisa atualizar o ID do Aplicativo para apontar para o mais recente.

Siga estas etapas para editar a configuração de um aplicativo inserido:

1. Acesse o painel **Editar um aplicativo**.

    - Se o aplicativo inserido for acessado usando o botão do menu do Power Apps, selecione e segure (ou clique com o botão direito do mouse) no botão do menu do Power Apps e selecione **Personalizar**. Selecione o aplicativo que você quer configurar no menu suspenso **Selecionar aplicativo**.
    - Se o aplicativo inserido aparecer diretamente na página, selecione **Opções** e, depois, **Personalizar esta página**. Usando a ferramenta **Selecionar**, clique no aplicativo inserido.
    - Se o aplicativo incorporado tiver sido adicionado usando o painel, abra o painel, selecione e segure (ou clique com o botão direito do mouse) no bloco associado ao aplicativo de tela, selecione **Personalizar** e, em seguida, selecione **Editar página**.

2. Faça as alterações necessárias na configuração do aplicativo e clique em **Salvar**.

## <a name="removing-an-app"></a>Removendo um aplicativo

Depois que um aplicativo for inserido em uma página, há algumas maneiras de removê-lo, se necessário:

- Acesse o painel **Editar um aplicativo** usando as instruções da seção [Editar um aplicativo inserido](#editing-an-embedded-app) anteriormente neste artigo. Confirme se o painel exibe informações para o aplicativo inserido que você deseja remover e clique no botão **Excluir**.
- Se o aplicativo incorporado tiver sido adicionado usando o painel, abra o painel, selecione e segure (ou clique com o botão direito do mouse) no bloco associado ao aplicativo de tela, selecione **Personalizar** e, em seguida, selecione **Remover página**. 
- Como um aplicativo inserido é salvo como dados de personalização, limpar a personalização da página também removerá todos os aplicativos inseridos nessa página. Observe que a remoção da personalização da página é permanente e não pode ser desfeita. Para remover as personalizações de uma página, selecione **Opções** e clique em **Personalizar esta página** e, por último, no botão **Limpar**. Após atualizar seu browser, todas as personalizações anteriores desta página serão removidas. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como otimizar as páginas usando a personalização.

## <a name="appendix"></a>Anexo

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Desenvolvedor] Modelar um aplicativo de tela em um formulário

Embora este artigo se concentre na incorporação de aplicativos de tela por meio de personalização, os desenvolvedores também têm a opção de adicionar um aplicativo de tela a um formulário usando a experiência de desenvolvimento do Visual Studio. Para isso, basta adicionar um PowerAppsHostControl ao formulário. As propriedades de metadados disponíveis no controle fornecem os mesmos recursos que a experiência de personalização.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Desenvolvedor] Especificando onde um aplicativo pode ser inserido

Por padrão, os usuários podem inserir aplicativos em qualquer página, sob o botão do menu do Power Apps ou diretamente na página como uma guia, Guia Rápida, folha ou como uma nova seção em um espaço de trabalho. Entretanto, se necessário, os desenvolvedores também podem configurar esse recurso para permitir a inserção de aplicativos somente em determinadas páginas, implementando os seguintes métodos:

- **isPowerAppPersonalizationEnabled** – Se este método retornar falso para uma página específica, então o botão do menu do Power Apps não aparecerá e os usuários não poderão inserir aplicativos em qualquer lugar desta página, incluindo como uma guia.
- **isPowerAppTabPersonalizationEnabled** – Se este método retornar falso para uma página específica, os usuários não poderão inserir aplicativos diretamente na página como uma guia, Guia Rápida, ou a seção do panorama. Os usuários ainda poderão inserir aplicativos usando o botão do menu do Power Apps, se a inserção for permitida na página.

O exemplo a seguir mostra uma nova classe com os dois métodos necessários para configurar onde os aplicativos podem ser inseridos.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
