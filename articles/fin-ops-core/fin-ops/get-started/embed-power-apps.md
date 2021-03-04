---
title: Inserir aplicativos de tela do Power Apps
description: Este tópico explica como inserir aplicativos de tela do Microsoft Power Apps no cliente para aumentar a funcionalidade do produto.
author: jasongre
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: ba3b736aeae8540349309ddd82bd431720b9701c
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693474"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Inserir aplicativos de tela do Power Apps

[!include [banner](../includes/banner.md)]

O Microsoft Power Apps é um serviço que permite que desenvolvedores e usuários não técnicos criem aplicativos de negócios personalizados para dispositivos móveis, tablets e a Web sem precisar escrever código. Os aplicativos do Finance and Operations oferecem suporte à integração com o Power Apps. Aplicativos de tela que você, sua organização ou o ecossistema mais amplo desenvolvem podem ser inseridos nos aplicativos do Finance and Operations para aumentar a funcionalidade do produto. Por exemplo, você pode criar um aplicativo de tela no Power Apps que complemente o Finance and Operations com informações recuperadas de outro sistema.

Para saber mais sobre como inserir Power Apps, assista ao breve vídeo [Como inserir Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Adicionando um aplicativo de tela do Power Apps inserido em uma página

### <a name="overview"></a>Visão Geral

Antes de inserir um aplicativo de tela do Power Apps no cliente, você deve encontrar ou criar um aplicativo que tenha os recursos visuais ou funcionalidades desejados. Este tópico não inclui uma descrição detalhada do processo de criação de aplicativos. Se você está começando a usar o Power Apps, consulte a [documentação do Power Apps](https://docs.microsoft.com/powerapps/).

Há duas formas de acessar um aplicativo de tela específico em uma página quando você estiver pronto para inserir o aplicativo. Você pode escolher qualquer abordagem que se ajuste melhor ao seu cenário. A primeira abordagem usa o botão **Power Apps** que foi adicionado ao Painel de Ações padrão. Os aplicativos que você adiciona usando essa abordagem aparecem como itens no botão de menu **Power Apps**. Quando você seleciona um desses itens, aparecerá um painel lateral que contém o aplicativo inserido. Se preferir, você pode inserir um aplicativo diretamente em uma página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho.

Ao configurar seu aplicativo de tela inserido, você pode selecionar um único campo que deseja enviar como contexto para o aplicativo. Essa etapa permite que o aplicativo responda com base nos dados que você está exibindo atualmente.

> [!NOTE]
> Atualmente, não é possível usar esse mecanismo para inserir aplicativos modelados.  

### <a name="details"></a>Detalhes

O procedimento a seguir mostra como inserir um aplicativo de tela do Power Apps no cliente Web.

1. Vá para a página onde deseja inserir o aplicativo de tela. Esta será a página que contém os dados que devem ser informados para o aplicativo como entrada.
2. Abra o painel **Adicionar aplicativo do Power Apps**:

    - Clique em **Opções** e selecione **Personalizar esta página**. No menu **Inserir**, selecione **Power Apps**. Por último, selecione a região na qual você quer adicionar o aplicativo. Se quiser inserir o aplicativo no botão do menu Power Apps, escolha o Painel de Ação. Se quiser inserir o aplicativo diretamente na página, escolha a guia apropriada, a guia rápida, folha ou seção (se estiver em um espaço de trabalho).
    - Se o aplicativo for acessado usando o botão do menu Power Apps, você poderá clicar no botão de menu **Power Apps** no Painel da Ação padrão e, depois, selecionar **Adicionar um aplicativo**.

3. Configurar o aplicativo inserido:

    - O campo **Nome** indica o texto mostrado para o botão ou a guia que conterá o aplicativo inserido. Muitas vezes, convém repetir o nome do aplicativo neste campo.
    - O campo **ID do Aplicativo** indica o identificador global exclusivo (GUID) para o aplicativo de tela que você deseja inserir. Para recuperar este valor, localize o aplicativo no [make.powerapps.com](https://make.powerapps.com) e localize o campo **ID do Aplicativo** em **Detalhes**.
    - Para **Dados de contexto para o aplicativo**, você pode selecionar o campo contendo os dados que você quer informar para o aplicativo como entrada. Consulte a seção posterior neste tópico chamada [Criando um aplicativo que utiliza os dados enviados de aplicativos do Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) para obter detalhes sobre como o aplicativo pode acessar os dados enviados de aplicativos do Finance and Operations.
    - Selecione o **Tamanho do aplicativo** que corresponde ao tipo de aplicativo que você está inserindo. Selecione **Fino** para aplicativos criados para dispositivos móveis e **Largo** para aplicativos criados para tablets. Isso garantirá que uma quantidade suficiente de espaço seja alocada para o aplicativo inserido.
    - A guia rápida **Entidades legais** fornece a capacidade de escolher para quais entidades legais o aplicativo está disponível. O padrão é tornar o aplicativo acessível para todas as entidades legais. Esta opção está disponível somente quando o recurso [Exibições salvas](saved-views.md) estiver desabilitado. 

4. Depois de confirmar que a configuração está correta, clique em **Inserir** para inserir o Power App na página. Será solicitado que você atualize o navegador para ver o aplicativo inserido.

## <a name="sharing-an-embedded-app"></a>Compartilhando um aplicativo inserido

Depois de inserir um aplicativo de tela em uma página e confirmar que ele está funcionando corretamente com qualquer contexto de dados informado dessa página, talvez você queira compartilhar o aplicativo com outros usuários do sistema. Para compartilhar um aplicativo de tela inserido, siga as etapas a seguir.

1. [Compartilhe o aplicativo de tela](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) com os usuários apropriados para que eles possam acessar o aplicativo no Power Apps. 

2. Verifique se os usuários específicos tenham as personalizações adequadas para que o aplicativo inserido apareça quando esses usuários exibirem a página. É possível usar uma das seguintes abordagens:

    - Recomendado: use o recurso [Exibições salvas](saved-views.md) para criar e publicar uma exibição que inclui o aplicativo inserido. Essa abordagem garante que todos os usuários que possuem as funções de segurança que são direcionadas pela exibição publicada verão o aplicativo nos aplicativos do Finance and Operations. 
    - Se o recurso Exibições salvas não estiver ativado, você pode fazer com que o administrador do sistema envie uma personalização que inclua o aplicativo inserido para todos os usuários ou um subconjunto de usuários. Como alternativa, você pode exportar as personalizações de sua página e enviá-las a um ou mais usuários. Cada um desses usuários pode então importar as personalizações. A barra de ferramentas contém ações que permitem exportar e importar personalizações. 
    
> [!NOTE]
> Se o aplicativo de tela foi compartilhado com usuários externos, esses usuários não podem usar o aplicativo inserido dentro dos aplicativos do Finance and Operations. No entanto, eles podem acessar o aplicativo diretamente no Power Apps. Os usuários externos incluem convidados e usuários que não pertencem ao Microsoft 365 Azure Directory onde o aplicativo do Finance and Operations é implantado.

Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes sobre os recursos de personalização do produto e como usá-los.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Criar um aplicativo de tela que usa dados enviados de aplicativos do Finance and Operations

Ao criar um aplicativo de tela que será inserido em um aplicativo do Finance and Operations, uma parte importante do processo é usar os dados de entrada desse aplicativo do Finance and Operations. A partir da experiência de desenvolvimento do Power Apps, os dados de entrada transferidos de um aplicativo do Finance and Operations podem ser acessados usando a variável **Param("EntityId")**.

Por exemplo, na função OnStart do aplicativo, você pode definir os dados de entrada de aplicativos do Finance and Operations para uma variável como esta:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-a-canvas-app"></a>Exibição de um aplicativo de tela

Para exibir um aplicativo de tela inserido em uma página em aplicativos do Finance and Operations, basta ir para uma página que tenha um aplicativo inserido. Lembre-se de que os aplicativos podem ser acessados usando o botão **Power Apps** no Painel de Ações padrão. Se preferir, eles podem aparecer diretamente na página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho. Quando os usuários tentarem carregar um aplicativo pela primeira vez em uma página, eles serão solicitados a fazer logon. Essa etapa garante que os usuários tenham as permissões apropriadas para usar o aplicativo.

## <a name="editing-an-embedded-app"></a>Editando um aplicativo inserido

Depois que um aplicativo for inserido em uma página, será necessário fazer algumas alterações para a configuração desse aplicativo. Por exemplo, talvez você queira modificar a etiqueta associada ao aplicativo inserido ou uma nova versão de um aplicativo foi criada e você precisa atualizar o ID do Aplicativo para apontar para o mais recente.

Siga estas etapas para editar a configuração de um aplicativo inserido:

1. Vá para o painel **Editar um aplicativo**.

    - Se o aplicativo inserido for acessado usando o botão do menu Power Apps, clique com o botão direito do mouse no botão do menu Power Apps e selecione **Personalizar**. Selecione o aplicativo que você quer configurar no menu suspenso **Selecionar aplicativo**.
    - Se o aplicativo inserido aparecer diretamente na página, selecione **Opções** e, depois, **Personalizar esta página**. Usando a ferramenta **Selecionar**, clique no aplicativo inserido.

2. Faça as alterações necessárias na configuração do aplicativo e clique em **Salvar**.

## <a name="removing-an-app"></a>Removendo um aplicativo

Depois que um aplicativo for inserido em uma página, há duas maneiras de removê-lo, se necessário:

- Vá para o painel **Editar um aplicativo** usando as instruções da seção [Editando um aplicativo inserido](#editing-an-embedded-app) anteriormente neste tópico. Confirme se o painel exibe informações para o aplicativo inserido que você deseja remover e clique no botão **Excluir**.
- Como um aplicativo inserido é salvo como dados de personalização, limpar a personalização da página também removerá todos os aplicativos inseridos nessa página. Observe que a remoção da personalização da página é permanente e não pode ser desfeita. Para remover as personalizações de uma página, selecione **Opções** e clique em **Personalizar esta página** e, por último, no botão **Limpar**. Após atualizar seu browser, todas as personalizações anteriores desta página serão removidas. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como otimizar as páginas usando a personalização.

## <a name="appendix"></a>Anexo

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