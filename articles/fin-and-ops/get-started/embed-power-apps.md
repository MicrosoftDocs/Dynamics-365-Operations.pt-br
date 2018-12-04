---
title: Inserir aplicativos do PowerApps
description: "Este tópico descreve como inserir PowerApps no cliente Finance and Operations para acumular a funcionalidade do produto."
author: jasongre
manager: AnnBe
ms.date: 09/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 3b0bb61a52721f1e2eaf6df53e17b6cc162d8409
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="embed-powerapps-apps"></a>Inserir aplicativos do PowerApps

[!include [banner](../includes/banner.md)]

Na atualização 14 da Plataforma, o Microsoft Dynamics 365 for Finance and Operations suporta integração com o Microsoft PowerApps, um serviço para desenvolvedores e usuários não técnicos para criar aplicativos de negócios personalizados para dispositivos móveis, tablets e a Web sem código de gravação. O PowerApps desenvolvido por você, sua organização ou o amplo ecossistema pode ser inserido no cliente do Finance and Operations para acumular a funcionalidade do produto. Por exemplo, você pode criar um PowerApp para complementar o Finance and Operations com informações recuperadas de outro sistema. 

Para saber mais sobre a a inserção de PowerApps, assista ao breve vídeo [Como inserir PowerApps no Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Adicionando um PowerApp inserido em uma página
### <a name="overview"></a>Visão Geral
Antes de inserir um PowerApp no cliente do Finance and Operations, primeiro você precisa localizar ou criar um PowerApp com recursos visuais e/ou funcionalidade desejados. Não descreveremos o processo detalhado para criar um PowerApp aqui. O tópico [Introdução ao PowerApps](https://docs.microsoft.com/en-us/powerapps/getting-started) é um bom ponto de partida, se você for novo no PowerApps.

Quando estiver pronto para inserir um PowerApp específico, você pode escolher entre uma destas duas maneiras de acessar o PowerApp em uma página; aquela que se adaptar melhor ao seu cenário. A primeira maneira é através do botão PowerApps que foi adicionado ao Painel de Ação padrão. O PowerApps adicionado usando este mecanismo aparecerá como itens de menu no botão de menu do PowerApps. Quando selecionado, cada um desses itens de menu aparecerá no painel lateral que contém o PowerApp inserido. Se preferir, você pode optar por mostrar um PowerApp diretamente em uma página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho. 

Ao configurar seu PowerApp incorporado no Finance and Operations, você pode selecionar um campo único que você deseja enviar como entrada para o PowerApp. Isso permite que o PowerApp seja responsivo com base nos dados que você está exibindo atualmente no Finance and Operations.  

### <a name="details"></a>Detalhes
As instruções a seguir mostram como inserir um PowerApp no cliente web do Finance and Operations.  

1. Vá para a página na qual você deseja inserir o PowerApp. Esta será a mesma página que conterá os dados que precisam ser informados ao PowerApp como entrada.  
2. Abra o painel **Inserir um PowerApp**:
   - Clique em **Opções** e selecione **Personalizar este formulário**. No menu **Inserir**, selecione **PowerApp**. Finalmente, selecione a região na qual você deseja adicionar o PowerApp. Se quiser inserir o PowerApp no botão de menu do PowerApps, selecione o Painel da Ação. Se quiser inserir o PowerApp diretamente na página, escolha a guia apropriada, a guia rápida, folha ou seção (se estiver em um espaço de trabalho).   
   - Se o PowerApp for acessado usando o botão de menu do PowerApps, você poderá clicar no botão de menu **PowerApps** no Painel da Ação padrão e, em seguida, selecionar **Inserir um PowerApp**.  
3. Configurar o PowerApp inserido:
   - O campo **Nome** indica o texto mostrado para o botão ou a guia que conterá o PowerApp inserido. Muitas vezes, você pode querer repetir o nome do PowerApp neste campo.  
   - **ID do Aplicativo** é o GUID do PowerApp que você deseja inserir. Para recuperar este valor, localize o PowerApp no [web.powerapps.com](https://web.powerapps.com) e localize o campo **ID do Aplicativo** em **Detalhes**.  
   - Para **Dados de entrada para o PowerApp**, você pode selecionar o campo que contém os dados que você deseja informar para o PowerApp como entrada. Consulte a seção posteriormente neste tópico chamado [Criar um PowerApp que aproveita dados financeiros e de operações](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations) para obter detalhes sobre como o PowerApp pode acessar os dados enviados do Finance and Operations.  
   - Selecione o **Tamanho do aplicativo** que corresponde ao tipo de PowerApp que você está inserindo. Selecione **Fino** para PowerApps criados para dispositivos móveis e **Largo** para PowerApps criados para tablets. Isso garantirá que uma quantidade suficiente de espaço seja alocada para o PowerApp inserido.
   - A guia rápida **Entidades legais** fornece a capacidade de escolher para quais entidades legais o PowerApp está disponível. O padrão é mostrar o PowerApp em todas as entidades legais.  
4. Após confirmar se a configuração está correta, clique em **Inserir** para inserir o PowerApp na página. Será solicitado que você atualize o navegador para ver o PowerApp inserido. 

## <a name="sharing-an-embedded-powerapp"></a>Compartilhando um PowerApp inserido
Depois de inserir um PowerApp em uma página e confirmado que ele está funcionando corretamente com qualquer contexto de dados informado da página, talvez você queira compartilhar este PowerApp inserido com outros usuários do sistema. Isso pode ser realizado de duas formas usando os recursos de personalização do produto:

- O cenário recomendado é por meio do administrador do sistema, que pode enviar uma personalização a todos os usuários ou a um subconjunto de usuários. 

- Como alternativa, você pode exportar suas personalizações da página, enviá-las para um ou mais usuários e fazer com que cada um desses usuários importe essas alterações. A opção Gerenciar na barra de ferramentas de personalização permite exportar e importar personalizações.

Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes sobre os recursos de personalização do produto e como usá-los.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>Criando um PowerApp que aproveita os dados enviados do Finance and Operations
Uma parte importante de criar um PowerApp que será inserido no Finance and Operations é utilizar os dados de entrada do Finance and Operations. No PowerApp, esse dados de entrada podem ser acessados usando a variável Param("EntityId").  

Por exemplo, na função de OnStart do PowerApp, você pode definir os dados de entrada do Finance and Operations para uma variável como esta:

If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, "")); 

## <a name="viewing-an-embedded-powerapp"></a>Exibindo um PowerApp inserido
Para exibir um PowerApp inserido em uma página no Finance and Operations, simplesmente vá para uma página com um PowerApp incorporado. Lembre-se que o PowerApps pode ser acessado através do botão PowerApps no Painel da Ação padrão ou pode aparecer diretamente na página como uma nova guia, guia rápida, folha ou uma nova seção em um espaço de trabalho. Quando um usuário tentar carregar pela primeira vez um PowerApp em uma página, será solicitado que ele entre no PowerApps para garantir que o usuário tem as permissões apropriadas para usar o PowerApp.   

## <a name="editing-an-embedded-powerapp"></a>Editando um PowerApp inserido
Depois que um PowerApp for inserido em uma página, será necessário fazer algumas alterações para a configuração desse PowerApp. Por exemplo, talvez você queira modificar a etiqueta associada ao PowerApp inserido ou uma nova versão de um PowerApp foi criada e você precisa atualizar o ID do Aplicativo para apontar para o PowerApp mais recente. 

Siga estas etapas para editar a configuração de um PowerApp inserido:
1. Vá para o painel **Editar um PowerApp**. 
   - Se o PowerApp inserido for acessado através do botão de menu do PowerApps, clique com o botão direito do mouse no botão de menu do PowerApps e selecione **Personalizar**. Selecione o PowerApp que você deseja configurar no menu suspenso **Selecionar PowerApp**.  
   - Se o PowerApp inserido aparecer diretamente na página, selecione **Opções** e, em seguida, **Personalizar este formulário**. Usando a ferramenta **Selecionar** , clique no PowerApp inserido.  
2. Faça as alterações necessárias na configuração do PowerApps e clique em **Salvar**.  

## <a name="removing-an-embedded-powerapp"></a>Removendo um PowerApp inserido
Depois que um PowerApp for inserido em uma página, há duas maneiras de removê-lo, se necessário: 

- Vá para o painel **Editar um PowerApp** usando as instruções da seção [Editando um PowerApp inserido](#editing-an-embedded-powerapp) anteriormente neste tópico. Confirme se o painel exibe informações para o PowerApp inserido que você deseja remover e clique no botão **Excluir**. 

- Como um PowerApp inserido é salvo como dados de personalização, a limpeza de sua personalização de página também removerá quaisquer PowerApps inseridos nessa página. Observe que a remoção da personalização da página é permanente e não pode ser desfeita. Para remover as personalizações de uma página, selecione **Opções** e clique em **Personalizar este formulário**. No menu **Gerenciar**, selecione o botão **Limpar**. Após atualizar seu browser, todas as personalizações anteriores desta página serão removidas. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como otimizar as páginas usando a personalização.  

## <a name="appendix"></a>Anexo 
### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Controle do desenvolvedor onde um PowerApp pode ser inserido
Por padrão, os usuários podem inserir PowerApps em qualquer página, no botão de menu do PowerApps ou diretamente na página como uma guia, guia rápida, folha ou como uma nova seção em um espaço de trabalho. Entretanto, se necessário, os desenvolvedores também podem configurar esse recurso somente para permitir a inserção do PowerApps em determinadas páginas, implementando os seguintes métodos: 

- **isPowerAppPersonalizationEnabled** - Se este método retornar falso para uma página específica, então o botão de menu PowerApps será mostrado e os usuários não poderão inserir PowerApps em nenhum lugar desta página, incluindo uma guia. 

- **isPowerAppTabPersonalizationEnabled** - Se o método voltar falso para uma página específica, os usuários não poderão inserir PowerApps diretamente na página como uma guia, guia rápida ou seção do panorama. Os usuários ainda poderão inserir o PowerApps através do botão de menu do PowerApps, se a inserção for permitida na página.  

O exemplo a seguir mostra uma nova classe com os dois métodos necessários para configurar onde o PowerApps pode ser inserido.  

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{

    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return true;
    }

    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)   
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return true;
    }
    ```

}


