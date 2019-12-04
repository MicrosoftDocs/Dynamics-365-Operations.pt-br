---
title: Inserir o Power Apps
description: Este tópico descreve como inserir Power Apps no cliente para melhorar a funcionalidade do produto.
author: jasongre
manager: AnnBe
ms.date: 09/20/2019
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
ms.openlocfilehash: 755a30f89725ca0a7e1c14252984c617d6ba280e
ms.sourcegitcommit: 4162d9ef4239c9d4e5297b8aaa903dd54f9cafc3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "2824484"
---
# <a name="embed-microsoft-power-apps"></a>Inserir o Microsoft Power Apps

[!include [banner](../includes/banner.md)]

A atualização de plataforma 14 dá suporte à integração com o Microsoft Power Apps, um serviço para desenvolvedores e usuários não técnicos que ajuda a criar aplicativos de negócios personalizados para dispositivos móveis, tablets e a Web sem escrever código. Os Power Apps desenvolvidos por você, sua organização ou o ecossistema mais amplo podem ser inseridos em aplicativos do Finance and Operations para ampliar a funcionalidade do produto. Por exemplo, você pode criar um Power App para complementar aplicativos do Finance and Operations com informações recuperadas de outro sistema.

Para saber mais sobre como inserir Power Apps, assista ao breve vídeo [Como inserir Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-power-app-to-a-page"></a>Adicionando um Power App inserido em uma página

### <a name="overview"></a>Visão Geral

Antes de inserir um Power App no cliente, primeiro você precisa localizar ou criar um Power App com os recursos visuais e/ou a funcionalidade desejada. Não descreveremos o processo detalhado para criar um Power App aqui. O tópico [Introdução do Power Apps](https://docs.microsoft.com/powerapps/getting-started) é um bom ponto de partida se você está começando a usar o Power Apps.

Quando estiver pronto para inserir um Power App específico, você poderá escolher uma entre as duas maneiras de acessar o Power App em uma página, seja qual for a que se adaptar melhor ao seu cenário. A primeira maneira é usando o botão Power Apps que foi adicionado ao Painel de Ação padrão. Os Power Apps adicionados usando esse mecanismo aparecerão como itens de menu no botão do menu Power Apps. Quando selecionado, cada um desses itens de menu aparecerá no painel lateral que contém o Power App inserido. Se preferir, você pode mostrar um Power App diretamente em uma página como uma nova guia, guia rápida, folha ou como uma nova seção em um espaço de trabalho.

Ao configurar seu Power App inserido, você pode selecionar um único campo que deseja enviar como entrada para o Power App. Isso permite que o Power App responda com base nos dados que você está exibindo atualmente.

### <a name="details"></a>Detalhes

As instruções a seguir mostram como inserir um Power App no cliente web.

1. Vá para a página na qual você quer inserir o Power App. Esta será a mesma página que contém os dados que precisam ser passados para o Power App como entrada.
2. Abra o painel **Inserir um Power App**:

    - Clique em **Opções** e selecione **Personalizar este formulário**. No menu **Inserir**, selecione **Power App**. Por último, selecione a região na qual você quer adicionar o Power App. Se quiser inserir o Power App no botão do menu Power Apps, escolha o Painel de Ação. Se quiser inserir o Power App diretamente na página, escolha a guia apropriada, guia rápida, folha ou seção (se estiver em um espaço de trabalho).
    - Se o Power App for acessado usando o botão do menu Power Apps, você poderá clicar no botão de menu **Power Apps** no Painel da Ação padrão e, depois, selecionar **Inserir um Power App**.

3. Configurar o Power App inserido:

    - O campo **Nome** indica o texto mostrado para o botão ou a guia que conterá o Power App inserido. Muitas vezes, convém repetir o nome do Power App neste campo.
    - **ID do Aplicativo** é o GUID do Power App que você quer inserir. Para recuperar este valor, localize o Power App no [web.powerapps.com](https://web.powerapps.com) e localize o campo **ID do Aplicativo** em **Detalhes**.
    - Para **Dados de entrada para o Power App**, você pode selecionar o campo contendo os dados que você quer informar para o Power App como entrada. Consulte a seção mais adiante neste tópico chamada [Criação de um Power App que aproveita dados de aplicativos do Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations-apps) para obter detalhes sobre como o Power App pode acessar os dados enviados de aplicativos do Finance and Operations.
    - Selecione o **Tamanho do aplicativo** que corresponde ao tipo de Power App que você está inserindo. Selecione **Fino** para Power Apps criados para dispositivos móveis e **Largo** para Power Apps criados para tablets. Isso garantirá que uma quantidade suficiente de espaço seja alocada para o Power App inserido.
    - A guia rápida **Entidades legais** permite escolher para quais entidades legais o Power App está disponível. O padrão é mostrar o Power App em todas as entidades legais.

4. Depois de confirmar que a configuração está correta, clique em **Inserir** para inserir o Power App na página. Você deverá atualizar o navegador para ver o Power App inserido.

## <a name="sharing-an-embedded-power-app"></a>Compartilhando um Power App inserido

Depois de inserir um Power App em uma página e confirmar que ele está funcionando corretamente com qualquer contexto de dados informado da página, talvez você queira compartilhar este Power App inserido com outros usuários do sistema. Isso pode ser realizado de duas formas usando os recursos de personalização do produto:

- O cenário recomendado é por meio do administrador do sistema, que pode enviar uma personalização a todos os usuários ou a um subconjunto de usuários.
- Como alternativa, você pode exportar suas personalizações da página, enviá-las para um ou mais usuários e fazer com que cada um desses usuários importe essas alterações. A opção Gerenciar na barra de ferramentas de personalização permite exportar e importar personalizações.

Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes sobre os recursos de personalização do produto e como usá-los.

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Criação de um Power App que aproveita dados enviados de aplicativos do Finance and Operations

Uma parte importante da criação de um Power App que será inserido em aplicativos do Finance and Operations é utilizar os dados de entrada desses aplicativos. No Power App, esse dados de entrada podem ser acessados usando a variável Param("EntityId").

Por exemplo, na função OnStart do Power App, você pode definir os dados de entrada de aplicativos do Finance and Operations para uma variável como esta:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Exibindo um Power App inserido

Para exibir um Power App inserido em uma página em aplicativos do Finance and Operations, basta ir para uma página que tem um Power App inserido. Lembre-se que os Power Apps podem ser acessados usando o botão Power Apps no Painel de Ação padrão ou podem aparecer diretamente na página como uma nova guia, Guia Rápida, folha ou uma nova seção em um espaço de trabalho. Quando um usuário tenta carregar um Power App pela primeira vez em uma página, ele deverá entrar no Power Apps para garantir que tem as permissões apropriadas para usar o Power App.

## <a name="editing-an-embedded-power-app"></a>Editando um Power App inserido

Depois que um Power App for inserido em uma página, será necessário fazer algumas alterações na configuração dele. Por exemplo, talvez você queira modificar a etiqueta associada ao Power App inserido ou uma nova versão de um Power App foi criada e você precisa atualizar o ID do Aplicativo para apontar para o Power App mais recente.

Siga estas etapas para editar a configuração de um Power App inserido:

1. Vá para o painel **Editar um Power App**.

    - Se o Power App inserido for acessado usando o botão do menu Power Apps, clique com o botão direito do mouse no botão do menu Power Apps e selecione **Personalizar**. Selecione o Power App que você quer configurar no menu suspenso **Selecionar Power App**.
    - Se o Power App inserido aparecer diretamente na página, selecione **Opções** e, depois, **Personalizar este formulário**. Usando a ferramenta **Selecionar**, clique no Power App inserido.

2. Faça as alterações necessárias na configuração do Power Apps e clique em **Salvar**.

## <a name="removing-an-embedded-power-app"></a>Removendo um Power App inserido

Depois que um Power App for inserido em uma página, há duas maneiras de removê-lo, se necessário:

- Vá para o painel **Editar um Power App** usando as instruções da seção [Editando um Power App inserido](#editing-an-embedded-powerapp) anteriormente neste tópico. Confirme se o painel exibe informações do Power App inserido que você quer remover e clique no botão **Excluir**.
- Como um Power App inserido é salvo como dados de personalização, limpar a personalização da página também removerá todos os Power Apps inseridos nessa página. Observe que a remoção da personalização da página é permanente e não pode ser desfeita. Para remover as personalizações de uma página, selecione **Opções** e clique em **Personalizar este formulário**. No menu **Gerenciar**, selecione o botão **Limpar**. Após atualizar seu browser, todas as personalizações anteriores desta página serão removidas. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como otimizar as páginas usando a personalização.

## <a name="appendix"></a>Anexo

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>Controle do desenvolvedor sobre onde um Power App pode ser inserido

Por padrão, os usuários podem inserir Power Apps em qualquer página, sob o botão do menu Power Apps ou diretamente na página como uma guia, Guia Rápida, folha ou como uma nova seção em um espaço de trabalho. Entretanto, se necessário, os desenvolvedores também podem configurar esse recurso para permitir a inserção de Power Apps somente em determinadas páginas, implementando os seguintes métodos:

- **isPowerAppPersonalizationEnabled** – Se este método retornar falso para uma página específica, então o botão do menu Power Apps não aparecerá e os usuários não poderão inserir Power Apps em qualquer lugar desta página, incluindo como uma guia.
- **isPowerAppTabPersonalizationEnabled** – Se este método retornar falso para uma página específica, os usuários não poderão inserir Power Apps diretamente na página como uma guia, Guia Rápida, ou a seção do panorama. Os usuários ainda poderão inserir Power Apps usando o botão do menu Power Apps, se a inserção for permitida na página.

O exemplo a seguir mostra uma nova classe com os dois métodos necessários para configurar onde é possível inserir Power Apps.

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
