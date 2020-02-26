---
title: Inserir o Power Apps
description: Este tópico descreve como inserir Power Apps no cliente para melhorar a funcionalidade do produto.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 9585d5a399ebf45b0ad7640f3c4e48d8afc46cd8
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017719"
---
# <a name="embed-microsoft-power-apps"></a>Inserir o Microsoft Power Apps

[!include [banner](../includes/banner.md)]

O Finance and Operations oferece suporte à integração com o Microsoft Power Apps, um serviço para desenvolvedores e usuários não técnicos criarem aplicativos de negócios personalizados para dispositivos móveis, tablets e Web sem código de escrita. O Power Apps desenvolvido por você, pela sua organização ou pelo ecossistema mais amplo, poderá ser incorporado aos aplicativos do Finance and Operations para aprimorar a funcionalidade do produto. Por exemplo, você pode criar um aplicativo no Power Apps que complemente o Finance and Operations com informações recuperadas de outro sistema.

Para saber mais sobre como inserir Power Apps, assista ao breve vídeo [Como inserir Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Adicionando um aplicativo do Power Apps inserido em uma página

### <a name="overview"></a>Visão geral

Antes de inserir um aplicativo do Power Apps no cliente, você precisa localizar ou criar um aplicativo com os recursos visuais e/ou a funcionalidade desejados. Não descreveremos o processo detalhado para criar um aplicativo aqui. O tópico [Introdução do Power Apps](https://docs.microsoft.com/powerapps/getting-started) é um bom ponto de partida se você está começando a usar o Power Apps.

Quando estiver pronto para inserir um aplicativo específico, você pode escolher entre uma destas duas maneiras de acessar o aplicativo em uma página; aquela que se adaptar melhor ao seu cenário. A primeira maneira é usando o botão Power Apps que foi adicionado ao Painel de Ação padrão. Os aplicativos adicionados usando esse mecanismo aparecerão como itens de menu no botão do menu do Power Apps. Quando selecionado, cada um desses itens de menu aparecerá no painel lateral que contém o aplicativo inserido. Se preferir, você pode optar por inserir um aplicativo diretamente em uma página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho.

Ao configurar seu aplicativo inserido, você pode selecionar um único campo que deseja enviar como contexto para o aplicativo. Isso permite que o aplicativo responda com base nos dados que você está exibindo atualmente.

### <a name="details"></a>Detalhes

As instruções a seguir mostram como inserir um aplicativo do Power Apps no cliente web.

1. Vá para a página na qual você quer inserir o aplicativo. Esta será a mesma página que conterá os dados que precisam ser informados ao aplicativo como entrada.
2. Abra o painel **Adicionar aplicativo do Power Apps**:

    - Clique em **Opções** e selecione **Personalizar esta página**. No menu **Inserir**, selecione **Power Apps**. Por último, selecione a região na qual você quer adicionar o aplicativo. Se quiser inserir o aplicativo no botão do menu Power Apps, escolha o Painel de Ação. Se quiser inserir o aplicativo diretamente na página, escolha a guia apropriada, a guia rápida, folha ou seção (se estiver em um espaço de trabalho).
    - Se o aplicativo for acessado usando o botão do menu Power Apps, você poderá clicar no botão de menu **Power Apps** no Painel da Ação padrão e, depois, selecionar **Adicionar um aplicativo**.

3. Configurar o aplicativo inserido:

    - O campo **Nome** indica o texto mostrado para o botão ou a guia que conterá o aplicativo inserido. Muitas vezes, convém repetir o nome do aplicativo neste campo.
    - **ID do Aplicativo** é o GUID do aplicativo que você quer inserir. Para recuperar este valor, localize o aplicativo no [web.powerapps.com](https://web.powerapps.com) e localize o campo **ID do Aplicativo** em **Detalhes**.
    - Para **Dados de contexto para o aplicativo**, você pode selecionar o campo contendo os dados que você quer informar para o aplicativo como entrada. Consulte a seção posterior neste tópico chamada [Criação de aplicativos que aproveitam dados de aplicativos do Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) para obter detalhes sobre como o aplicativo pode acessar os dados enviados de aplicativos do Finance and Operations.
    - Selecione o **Tamanho do aplicativo** que corresponde ao tipo de aplicativo que você está inserindo. Selecione **Fino** para aplicativos criados para dispositivos móveis e **Largo** para aplicativos criados para tablets. Isso garantirá que uma quantidade suficiente de espaço seja alocada para o aplicativo inserido.
    - A guia rápida **Entidades legais** fornece a capacidade de escolher para quais entidades legais o aplicativo está disponível. O padrão é tornar o aplicativo acessível para todas as entidades legais. Esta opção está disponível somente quando o recurso [Exibições salvas](saved-views.md) estiver desabilitado. 

4. Depois de confirmar que a configuração está correta, clique em **Inserir** para inserir o Power App na página. Será solicitado que você atualize o navegador para ver o aplicativo inserido.

## <a name="sharing-an-embedded-app"></a>Compartilhando um aplicativo inserido

Depois de inserir um aplicativo em uma página e confirmar que ele está funcionando corretamente com qualquer contexto de dados informado da página, talvez você queira compartilhar isto com outros usuários do sistema. Isso pode ser realizado de duas formas usando os recursos de personalização do produto:

- O cenário recomendado é por meio do administrador do sistema, que pode enviar uma personalização a todos os usuários ou a um subconjunto de usuários.
- Como alternativa, você pode exportar suas personalizações da página, enviá-las para um ou mais usuários e fazer com que cada um desses usuários importe essas alterações. A barra de ferramentas contém ações que permitem exportar e importar personalizações.

Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes sobre os recursos de personalização do produto e como usá-los.

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Criando um aplicativo que utiliza os dados enviados de aplicativos do Finance and Operations

Uma parte importante da criação de um aplicativo do Power Apps que será inserido em um aplicativo do Finance and Operations é a utilização dos dados de entrada desse aplicativo. A partir da experiência de desenvolvimento do Power Apps, os dados de entrada transferidos de um aplicativo do Finance and Operations podem ser acessados usando a variável Param("EntityId").

Por exemplo, na função OnStart do aplicativo, você pode definir os dados de entrada de aplicativos do Finance and Operations para uma variável como esta:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Exibindo um aplicativo

Para exibir um aplicativo inserido em uma página em aplicativos do Finance and Operations, basta ir para uma página que tenha um aplicativo inserido. Lembre-se que os aplicativos podem ser acessados usando o botão Power Apps no Painel de Ação padrão ou podem aparecer diretamente na página como uma nova guia, Guia Rápida, folha ou uma nova seção em um espaço de trabalho. Quando um usuário tenta carregar um aplicativo pela primeira vez em uma página, ele deverá entrar para garantir que tem as permissões apropriadas para usar o aplicativo.

## <a name="editing-an-embedded-app"></a>Editando um aplicativo inserido

Depois que um aplicativo for inserido em uma página, será necessário fazer algumas alterações para a configuração desse aplicativo. Por exemplo, talvez você queira modificar a etiqueta associada ao aplicativo inserido ou uma nova versão de um aplicativo foi criada e você precisa atualizar o ID do Aplicativo para apontar para o mais recente.

Siga estas etapas para editar a configuração de um aplicativo inserido:

1. Vá para o painel **Editar um aplicativo**.

    - Se o aplicativo inserido for acessado usando o botão do menu Power Apps, clique com o botão direito do mouse no botão do menu Power Apps e selecione **Personalizar**. Selecione o aplicativo que você quer configurar no menu suspenso **Selecionar aplicativo**.
    - Se o aplicativo inserido aparecer diretamente na página, selecione **Opções** e, depois, **Personalizar esta página**. Usando a ferramenta **Selecionar**, clique no aplicativo inserido.

2. Faça as alterações necessárias na configuração do aplicativo e clique em **Salvar**.

## <a name="removing-an-app"></a>Removendo um aplicativo

Depois que um aplicativo for inserido em uma página, há duas maneiras de removê-lo, se necessário:

- Vá para o painel **Editar um aplicativo** usando as instruções da seção [Editando um aplicativo inserido](#editing-an-embedded-power-app) anteriormente neste tópico. Confirme se o painel exibe informações para o aplicativo inserido que você deseja remover e clique no botão **Excluir**.
- Como um aplicativo inserido é salvo como dados de personalização, limpar a personalização da página também removerá todos os aplicativos inseridos nessa página. Observe que a remoção da personalização da página é permanente e não pode ser desfeita. Para remover as personalizações de uma página, selecione **Opções** e clique em **Personalizar esta página** e, por último, no botão **Limpar**. Após atualizar seu browser, todas as personalizações anteriores desta página serão removidas. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como otimizar as páginas usando a personalização.

## <a name="appendix"></a>Anexo

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Controle do desenvolvedor onde um aplicativo pode ser inserido

Por padrão, os usuários podem inserir aplicativos em qualquer página, sob o botão do menu do Power Apps ou diretamente na página como uma guia, Guia Rápida, folha ou como uma nova seção em um espaço de trabalho. Entretanto, se necessário, os desenvolvedores também podem configurar esse recurso para permitir a inserção de aplicativos somente em determinadas páginas, implementando os seguintes métodos:

- **isPowerAppPersonalizationEnabled** – Se este método retornar falso para uma página específica, então o botão do menu do Power Apps não aparecerá e os usuários não poderão inserir aplicativos em qualquer lugar desta página, incluindo como uma guia.
- **isPowerAppTabPersonalizationEnabled** – Se este método retornar falso para uma página específica, os usuários não poderão inserir aplicativos diretamente na página como uma guia, Guia Rápida, ou a seção do panorama. Os usuários ainda poderão inserir aplicativos usando o botão do menu do Power Apps, se a inserção for permitida na página.

O exemplo a seguir mostra uma nova classe com os dois métodos necessários para configurar onde os aplicativos podem ser inseridos.

```
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
