---
title: Processar estrutura de guia
description: Este tópico fornece informações sobre a estrutura do guia de processos para os desenvolvedores que estão estendendo nossos processos móveis de depósito em X++.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902037"
---
# <a name="process-guide-framework"></a>Processar estrutura de guia

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a estrutura do guia de processos para os desenvolvedores que estão estendendo os processos móveis de depósito em X++. Os processos móveis de depósito são extensíveis como resultado de serem divididos em etapas pequenas. A criação da lógica de negócios e da interface de usuário de cada etapa foi extraída para classes individuais, o que permite a extensibilidade.

## <a name="overview-of-the-existing-design"></a>Visão geral do design existente

Os fluxos de execução móvel de depósito são expostos por meio de um único ponto de extremidade de serviço personalizado. A solicitação chega do aplicativo móvel na forma de uma cadeia de caracteres XML, que contém os metadados da interface de usuário apresentada no aplicativo móvel, bem como os valores inseridos pelo usuário.

Quando a solicitação é recebida, a primeira etapa é desserializar esse XML. A classe **WHSMobileAppServiceXMLTranslator** converte o XML em um contêiner, que contém as informações do controle, bem como informações da sessão.

Em seguida, as informações no contêiner são usadas para deduzir o processo de depósito no qual o usuário está trabalhando, ou prestes a iniciar (representado pela enumeração **WHSWorkExecuteMode**), e adequadamente criar uma instância de uma classe derivada de **WHSWorkExecuteDisplay**. O método **displayform()** é invocado e faz o seguinte:

-   Processa os dados do usuário (delegado para a classe **WHSRFControlData**, mas alguns processos implementam uma lógica específica substituindo o método **processControl()**).

-   Executa a lógica de negócios.

-   Incrementa a etapa.

-   Cria o contêiner que representa a nova interface de usuário (normalmente em um método **build…()**).

Em seguida, o contêiner é retornado ao tradutor, que serializa o XML e o envia de volta como uma resposta ao dispositivo móvel.

O diagrama da sequência a seguir mostra uma visão geral do fluxo de execução. Observe que o diagrama é mais uma visão geral esquemática e não uma representação 1:1 do código real.

![Visão geral esquemática do processo.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Motivo do novo design

O design acima oferece uma estrutura muito simples para a criação de processos usados em fluxos móveis. No entanto, como está evidente acima, os métodos **displayform()** assumem várias responsabilidades. Ele os delega a outros métodos e classes, mas na ausência de responsabilidades concretas de classes, isso é feito de forma inconsistente entre as classes. Além disso, conforme o número de cenários com suporte cresce de forma orgânica, algumas dessas classes podem se tornar bastante complexas. Para tornar as coisas mais interessantes, algumas dessas classes/métodos são substituídas e usadas novamente em vários modos. Isso resulta em métodos extremamente longos com alta complexidade ciclomática. Eles criaram problemas de manutenção no passado. A correção de bugs nesses métodos tem sido arriscada e sujeita à regressão.
Por exemplo, o método **processWorkLine()** na classe **WhsWorkExecuteDisplay** é referenciado de vários processos (basicamente, de qualquer lugar onde a execução do trabalho é realizada).

Para torná-los extensíveis, uma das opções seria dividir os métodos **displayForm** em métodos menores e introduzir pontos de extensibilidade. No entanto, por causa da matriz de cenário, seria desafiador para os parceiros escrever extensões e validá-las em relação às regressões. Não só isso, devido à falta de distribuição estruturada de responsabilidades observada acima, o código continuaria crescendo de formas imprevisíveis ao longo do tempo, apresentando desafios na criação de extensões de qualidade.

Como resultado, o novo design é a opção sustentável, com o objetivo de ter classes claramente definidas com responsabilidades independentes. Uma classe deve ter uma responsabilidade, um motivo para ser alterada e um motivo para ser estendida.

## <a name="design-overview"></a>Visão geral do design

Na estrutura reformulada, a estratégia principal gira em torno de dois princípios: dividir o fluxo de execução em componentes individuais com responsabilidades bem definidas e ter pontos de extensão bem definidos em cada um dos componentes.

O nome da nova estrutura é "ProcessGuide". Isso porque o objetivo dessas classes é orientar um usuário por meio de um processo empresarial (em oposição ao cliente avançado, que é uma experiência baseada em formulário na qual o usuário tem mais flexibilidade na forma como interage com os dados ou na ordem em que executa tarefas).

> [!NOTE]
> Um detalhe notável é a omissão deliberada do prefixo "WHS". Embora os processos móveis tenham sido introduzidos para armazenamento no início, subsequentemente eles transcenderam limites para oferecer suporte a vários processos de gerenciamento de estoque e produção. Como resultado, a referência ao depósito foi excluída no nome da estrutura.

Para identificar os componentes, a primeira etapa é examinar o processo Início da Produção (classe **WhsWorkExecuteDisplayProdStart**). Veja um esquema do processo.

![Imagem do processo esquemático.](media/production-start-process-schematic.png)

Analisando o fluxo de controle, são necessários os seguintes componentes:

-   Um controlador para costurar todo o processo empresarial.
-   Uma etapa responsável pela execução de uma etapa no processo.
-   Um processador de dados para processar os dados em uma etapa.
-   Um construtor de páginas responsável pela criação da interface de usuário para uma etapa.
-   Um agente de navegação responsável pela transição de etapa.
-   Uma classe responsável pela execução do processo empresarial.

No diagrama de fluxo do processo acima, se você começar na etapa 1, iniciar o processamento dos dados da etapa anterior e terminar com a criação de uma interface de usuário, os dados continuarão sendo processados na próxima etapa. Isso introduz uma forte ligação entre etapas consecutivas, como resultado, nosso novo esquema de alto nível terá a aparência a seguir:

![Imagem do processo esquemático de alto nível.](media/high-level-schematic.png)

Estes são os componentes principais do processo reformulado:

-   **ProcessGuideController** - Esta classe orquestra a execução geral do processo empresarial. Ela define as fábricas que criam uma instância da etapa e do agente de navegação, que, posteriormente, constituem a execução do processo, bem como a lógica de limpeza para cancelamento ou saída do processo.

-   **ProcessGuideStep** - Esta classe representa uma única etapa no processo empresarial. Essa classe contém uma definição das fábricas que criam uma instância de um construtor de páginas, ações e processadores de dados e é responsável por invocá-las na sequência correta.

-   **ProcessGuideNavigationAgent** - Esta classe é responsável pela navegação entre as etapas. Quando uma etapa é concluída, o agente de navegação é responsável pela definição da próxima etapa e passa quaisquer parâmetros dos quais a etapa anterior pode precisar para se comunicar com a próxima.

-   **ProcessGuidePageBuilder** - Esta classe é responsável por criar uma instância da interface de usuário.

-   **ProcessGuideAction** - Esta classe representa uma ação, mostrada como um botão para o usuário.

-   **ProcessGuideDataProcessor** - Esta classe é responsável por processar os dados inseridos pelo usuário em um campo.

## <a name="execution-flow"></a>Fluxo de execução

O ponto de partida do fluxo de execução permanece inalterado. Portanto, a solicitação ainda chega pelos mesmos pontos de extremidade, seguida pela desserialização do XML no contêiner. Esse contêiner então é passado para **getNextFormState()**.

Há três classes importantes a serem observadas:

-  **ProcessGuideSessionState** – Ela contém informações do estado da sessão – modo, passagem, controlador, etapa em execução etc.

-  **ProcessGuidePage** – Ela contém uma representação fortemente tipada dos metadados da interface de usuário.

-  **ProcessGuideRequest** – Ela contém as duas acima como membros e é uma representação fortemente tipada da solicitação recebida do dispositivo móvel.

Essas classes são criadas usando as informações do contêiner (estado e dados de controle inseridos pelo usuário). Isso fornece uma maneira fortemente tipada de acessar e manipular os valores. Em comparação com o acesso repetido do contêiner durante o processo, isso oferece benefícios em termos de legibilidade e desempenho.

As informações do estado da sessão são usadas para criar uma instância da classe **ProcessGuideController** correta. Após a criação da instância, o método **createResponse()** na classe **ProcessGuideController** é invocado. Esse método é o ponto de entrada para a lógica do guia de processos e, depois da execução, volta com a resposta (representada na classe **ProcessGuideResponse**). A resposta então é convertida de volta para o contêiner e devolvida para a lógica herdada, que a serializa para o XML e a envia de volta para o dispositivo móvel.

Em seguida, o controlador precisa encontrar a próxima etapa a ser executada. Se esse for o início de um novo processo, o controlador chamará **initialStep()** para obter a primeira etapa do processo. Depois disso, ele chamará o método **execute()** no **ProcessGuideStep**. Esse método criará uma instância de uma classe **ProcessGuidePageBuilder** e chamará **buildPage()**, que retornará com um objeto **ProcessGuidePage**, uma representação virtual da interface de usuário a ser apresentada ao usuário. Em seguida, a etapa enviará o resultado de volta ao controlador, que salvará o estado da sessão atual e retornará o resultado para **getNextFormState()** no formulário da classe **ProcessGuideResponse**. Depois disso, a resposta será convertida de volta para o contêiner e, posteriormente, serializada para XML e enviada de volta para o dispositivo móvel.

O diagrama da sequência a seguir explica esse fluxo de controle. Observe que esse é o fluxo de controle mais comum, simplificado para explicar o design.

![Fluxo de controle simplificado.](media/control-flow.png)

Quando o usuário executa uma ação no dispositivo móvel clicando em um botão ou verificando um valor, o que geralmente dispara a ação padrão, a solicitação chega no método **createResponse()** na classe **ProcessGuideController** por meio do mesmo roteiro. Desta vez, no entanto, o controlador sabe, com base nas informações do estado da sessão, em que etapa o usuário está. Portanto, ele cria uma instância da classe **ProcessGuideStep** apropriada e invoca o método execute. O **ProcessGuideStep**, por sua vez, lê o nome da ação invocada pelo usuário, em seguida, cria uma instância da classe **ProcessGuideAction** apropriada e chama **execute()**.

A classe **ProcessGuideAction** é responsável por executar a ação específica, no entanto, há duas exceções notáveis.

A primeira é a classe **ProcessGuideOKAction**. Essa ação implica que o usuário deseja confirmar e avançar no processo. De acordo com isso, o método faz um retorno de chamada para a classe ProcessGuideStep, o que significa que a etapa invoca **processData()** no **ProcessGuideDataProcessor**. Isso processa os dados inseridos pelo usuário, em seguida, atualiza o estado da etapa e envia o resultado de volta ao controlador. Dependendo do resultado do processador, a etapa invoca o construtor de páginas para criar a interface de usuário apropriada ou define o status da etapa como concluído. Isso é refletido na metade superior do diagrama da sequência abaixo.

A outra exceção é a ação de cancelamento, implementada nas classes **ProcessGuideCancelResetProcessAction** e **ProcessGuideCancelExitProcessAction**. Essas ações representam uma intenção de cancelar o processo e voltar ao início do processo ou sair dele. Semelhante à ação **OK**, essas ações também executam um retorno de chamada para a etapa, o que sinaliza a intenção para o **ProcessGuideController**. O controlador então executa a limpeza necessária de variáveis de estado e move o controle para a etapa inicial no processo ou finaliza o processo totalmente.

Após a conclusão da etapa, se o status dela estiver definido como **Concluído**, o controlador criará uma instância do **ProcessGuideNavigationAgent**, o que retornará o nome da próxima etapa. Em seguida, ele criará uma instância dessa etapa e invocará o método **execute()**, e o ciclo continuará. Mais comumente, a nova etapa invoca o **ProcessGuidePageBuilder** correspondente para criar a interface de usuário para a próxima tela a ser apresentada ao usuário, que depois é enviada de volta. Esse fluxo é mostrado na metade inferior do diagrama da sequência abaixo.

![Diagrama da sequência.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Criar um novo processo usando a estrutura ProcessGuide

A melhor maneira de explicar o fluxo de controle é usando um exemplo que existe no aplicativo, o processo Início da Produção.

## <a name="overview-of-the-production-start-process"></a>Visão geral do processo de início da produção

Vamos começar compreendendo o fluxo de processo. Na primeira etapa, o usuário é solicitado a informar a ID da ordem de produção.

![Solicitação da ID de produção.](media/production-id-prompt.png)

Quando o usuário insere a ID da ordem de produção, o número da ordem é validado. Algumas das validações executadas se baseiam nas seguintes informações: se a ordem está no mesmo depósito ao qual o usuário está conectado e o status da ordem. Se a validação falhar, o usuário verá uma mensagem de erro. Se a validação for bem-sucedida, o usuário verá detalhes da ordem de produção e do item.

O usuário pode cancelar para voltar ao início do processo ou clicar em **OK** para confirmar. No último caso, o status da ordem de produção é definido como **Iniciado**, os diários correspondentes são lançados, o controle retorna para a primeira etapa e a mensagem "Trabalho Concluído" é exibida para o usuário.


## <a name="creating-the-controller"></a>Criar o controlador

A primeira etapa na criação do processo empresarial é criar a classe de controlador, estendendo da classe abstrata **ProcessGuideController**, que implementa os comportamentos padrão de um controlador. O nome da nova classe é **ProdProcessGuideProductionStartController** e ele é decorado com o valor **WHSWorkExecuteMode** de **StartProdOrder**. A mesma criação de instância baseada em **SysExtension** utilizada nas classes **WHSWorkExecuteDisplay** é usada, o que ajuda a criar uma instância do controlador quando o usuário executa um item de menu para esse modo.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> O padrão de nomenclatura da classe é **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**. Esse é o padrão usado para as classes de controlador e para estender para outras classes.


## <a name="building-the-first-step"></a>Criar a primeira etapa

Em seguida, para definir a primeira etapa, crie a classe **ProdProcessGuidePromptProductionIdStep**, estendendo de **ProcessGuideStep**.

A tarefa de criação de instância da classe é delegada a uma fábrica de etapas, que é invocada pela classe base **ProcessGuideController**. A implementação padrão da fábrica criar uma instância da etapa com base no nome. Portanto, para criar uma instância de **ProdProcessGuidePromptProductionIdStep** como a primeira etapa no controlador, você deve executar duas ações:

-   Decorar a classe **ProdProcessGuidePromptProductionIdStep** com um atributo **ProcessGuideStepName**.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   Na classe de controlador, implementar o método abstrato **initialStepName()** para retornar o nome da etapa.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> O valor no atributo **ProcessGuideStepName** não precisa corresponder exatamente ao nome da classe, conforme mostrado acima. No entanto, implementar isso permite a uniformidade e a segurança de tipos nas referências cruzadas ao usar a classe. É recomendável usar essa convenção de nomenclatura.
>
> A criação de instância da etapa baseada em **ProcessGuideStepName** é implementada na classe **ProcessGuideStepDefaultFactory**. No caso raro de você querer uma estratégia diferente para criar uma instância da etapa, é necessário fazer o seguinte:
> -   Criar uma nova classe de fábricas herdada de **ProcessGuidStepAbstractFactory**.
> -   Opcionalmente, criar uma nova classe de parâmetros implementando a interface **ProcessGuideIStepCreationParameters**, contendo os parâmetros de que a fábrica precisaria.
> -   Na classe de controlador, substituir os métodos **stepFactory()** e **stepCreationParameters()** para retornar a fábrica e os parâmetros acima.

A próxima etapa é implementar a funcionalidade da classe **ProdProcessGuidePromptProductionIdStep**. Você precisa implementar a lógica para criar a interface de usuário, processar os dados inseridos pelo usuário e determinar quando a etapa está concluída.

### <a name="building-the-user-interface-for-the-first-step"></a>Criar a interface de usuário para a primeira etapa

A interface de usuário é criada usando uma classe herdada da classe abstrata **ProcessGuidePageBuilder**. Nesta etapa, nomeie a classe para representar o que ela faz, **ProdProcessGuidePromptProductionIdPageBuilder**.

O mecanismo de criação de instância da classe é semelhante à forma como a etapa teve uma instância criada do controlador. 

-   Decore a classe **ProdProcessGuidePromptProductionIdPageBuilder** com um atributo **ProcessGuidePageBuilderName**.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   Na classe **ProdProcessGuidePromptProductionIdStep**, implemente o método abstrato **pageBuilderName()** para retornar esse nome.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Semelhante à fábrica de etapas, também há um padrão de fábrica abstrato implementado para a fábrica do construtor de páginas. Portanto, no caso raro de você querer uma estratégia diferente para criar uma instância do construtor de páginas, é possível fazer o seguinte:
> - Criar uma nova classe de fábricas herdada de **ProcessGuidePageBuilderAbstractFactory**.
> - Opcionalmente, criar uma nova classe de parâmetros implementando a interface **ProcessGuideIPageBuilderCreationParameters**, contendo os parâmetros de que a fábrica precisaria.
> - Na classe de etapa, substituir os métodos **pageBuilderFactory()** e **pageBuilderCreationParameters()** para retornar a fábrica e os parâmetros acima.

Para implementar a interface de usuário, você precisa de uma página com uma caixa de texto para inserir a ID da ordem de produção, além de um botão **OK** e um botão **Cancelar**. O botão **Cancelar** serve para sair do processo.

Para implementar isso, você precisa substituir dois métodos na classe **ProdProcessGuidePromptProductionIdPageBuilder**:

-   Use o método **addDataControls()** para adicionar a caixa de texto.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Use o método **addActionControls()** para adicionar os botões **OK** e **Cancelar**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Isso adiciona os controles de dados, seguidos pelos botões. No entanto, se você quiser criar uma tela com botões e controles de dados intercalados, é possível substituir o método **addControls()** para obter flexibilidade.

Um cenário adicional a ser considerado é como recriar a página em caso de falhas na validação, por exemplo, se o usuário inserir uma ID da ordem de produção incorreta. A classe base **ProcessGuidePageBuilder** implementa o comportamento padrão, que recria a interface de usuário, limpa o valor verificado e adiciona o controle de erro com a mensagem de erro. Como esse é o comportamento padrão que você deseja usar, não é necessário adicionar nenhum código para lidar com erros.

> [!TIP]
> Se você quiser implementar um comportamento personalizado da interface de usuário para situações de erro, é possível substituir um ou mais dos métodos **rebuildFromRequestPage()**, **isErrorState()** e **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Processar os dados inseridos pelo usuário na primeira etapa

O processamento dos dados é feito na classe **ProcessGuideDataProcessorDefault**, que, por sua vez, invoca a classe **WhsRfControlData** herdada. Nenhuma alteração é necessária nesse comportamento padrão e **WhsRfControlData** já tem uma lógica para validar o campo **ProdId**, portanto, você não precisará escrever nenhuma lógica para isso. No caso das extensões necessárias para a lógica de validação, considere o uso do mecanismo de extensão baseado em **WhsControl**.

### <a name="determine-if-the-first-step-is-complete"></a>Determinar se a primeira etapa foi concluída

Quando a validação é bem-sucedida, é hora de marcar a etapa como concluída. Isso é feito na classe base, no entanto, você precisa implementar a condição para determinar a conclusão da etapa. O método substituído a seguir faz isso.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Etapa 2: Exibir detalhes da ordem e confirmar

Na segunda etapa do processo, o usuário vê uma tela com detalhes sobre a ordem. Ele pode clicar no botão **OK** para confirmar o início da ordem de produção ou clicar em **Cancelar** para voltar ao início do processo. Para este exemplo, nomeie a etapa **ProdProcessGuideConfirmProductionOrderStep** e a classe do construtor de páginas **ProdProcessGuideConfirmProductionOrderPageBuilder**.

A classe ProdProcessGuideConfirmProductionOrderStep tem a seguinte aparência.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Como o usuário não insere nenhum valor aqui, não é necessário substituir o método **isComplete()**. A etapa é concluída quando o usuário clica em **OK**.

A classe do construtor de páginas substitui o método **addDataControls()** para adicionar três rótulos. O primeiro rótulo mostra a ID da ordem de produção, o segundo contém informações do item (como ID do item, dimensões ou descrição) e o terceiro contém a quantidade e a unidade de medida.

O **addActionControls()** então é substituído para adicionar dois botões: o botão **OK** e o botão **Cancelar** para cancelar o processo e voltar ao início dele.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Você pode encontrar o mesmo código-fonte para os métodos X++ neste tópico usando o Explorador de Aplicativos. Filtre o nome da classe, clique com o botão direito do mouse no nome da classe e selecione **Exibir código**.

### <a name="step-3-start-the-production-order"></a>Etapa 3: Iniciar a ordem de produção

Na terceira etapa, a lógica de negócios do início da ordem de produção é executada. Essa etapa é um pouco diferente das etapas anteriores, pois ela não tem uma interface de usuário. Ela é executada silenciosamente quando o usuário clica em **OK** na etapa anterior.

A classe abstrata **ProcessGuideStepWithoutPrompt** implementa o comportamento padrão para essas etapas. Portanto, a etapa atual deve estender a classe **ProcessGuideStepWithoutPrompt** e substituir o método **doExecute()**.

O exemplo de código a seguir mostra a implementação da classe e do método **doExecute()**. O método simplesmente recupera a ID da ordem e a ID do usuário do estado da sessão e invoca o método para iniciar essa ordem de produção.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

No caso de uma exceção, a lógica de tratamento de exceções da estrutura garante que o processo seja revertido para a etapa anterior.

> [!NOTE]
> A invocação para **addProcessCompletionMessage()** adiciona a mensagem "Trabalho concluído" aos parâmetros de navegação. A próxima etapa (pressupondo que tenha uma interface de usuário) exibirá essa mensagem. As classes base lidam com essa lógica e nenhum código específico precisa ser adicionado às classes de processo para obter esse comportamento.


### <a name="building-the-navigation-through-the-steps"></a>Criar a navegação pelas etapas

A classe base **ProcessGuideController** cria uma instância da classe **ProcessGuideNavigationAgentDefault**, que depende de um roteiro de navegação predefinido, um mapa simples das etapas de origem e de destino. Para o cenário de início da produção, como não há ramificação condicional, essa implementação seria suficiente. Portanto, você só precisa substituir o método **initializeNavigationRoute()** para definir o roteiro de navegação.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Há processos em que haverá ramificação condicional (com base nas ações do usuário ou qualquer outra condição). Esses processos precisam fazer o seguinte:

-   Implementar agentes de navegação específicos herdados da classe **ProcessGuideNavigationAgent**.

-   Implementar a fábrica do agente de navegação específico herdada da classe **ProcessGuideNavigationAgentAbstractFactory**, que contém a lógica para criar uma instância do agente de navegação correto com base na etapa, no estado da sessão, na ação do usuário ou em outra lógica atual.

-   Opcionalmente, substituir **navigationAgentCreationParameters()** na classe de controlador para passar parâmetros adequados.

-   Substituir **navigationAgentFactory()** no controlador para criar uma instância da fábrica do agente de navegação criada acima.

### <a name="action-classes"></a>Classes de ação

As classes de ação representam ações do usuário, portanto, este exemplo usa a ação **OK** para mostrar como as ações são criadas.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

A classe deve implementar dois métodos abstratos:

-   **label()**, que retorna o rótulo a ser exibido em um controle de botão vinculado a essa ação.

-   **doExecute()**, que executa a ação. Como mencionado anteriormente, o botão **OK** simplesmente executa um retorno de chamada para a etapa. No entanto, outras ações podem ter uma lógica mais complexa aqui.

A criação de instância das ações é feita usando a estrutura **SysExtension** com base no atributo **ProcessGuideActionName**. Semelhante à criação de instância dos construtores de páginas, a classe de etapa implementa a fábrica de ações padrão e é possível substituí-la. O construtor de páginas adiciona um controle de botão como esse.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

Ao fazer isso, ele solicita que a etapa crie uma classe de ação para o nome passado e vincula essa ação ao botão.

### <a name="summary"></a>Resumo

Para resumir tudo o que foi explicado neste tópico, aqui está um resumo abrangente do código necessário para o processo:

1.  **ProdProcessGuideProductionStartController**

    1.  Substitua **initialStepName()** para fornecer o nome da primeira etapa.
    2.  Substitua **initializeNavigationRoute()** para construir o mapa de navegação.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Substitua **isComplete()** para especificar quando a etapa é considerada concluída.
    2.  Substitua **pageBuilderName()** para especificar o construtor de páginas a ser usado.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Substitua **addDataControls()** para adicionar a caixa de texto **ID da Produção**.
    2.  Substitua **addActionControls()** para adicionar os botões **OK** e **Cancelar**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Substitua **pageBuilderName()** para especificar o construtor de páginas a ser usado.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Substitua **addDataControls()** para adicionar os rótulos de informações de ordem, item e quantidade.

    2.  Substitua **addActionControls()** para adicionar os botões **OK** e **Cancelar**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > O método **generateItemInfoForProdId()**, que é usado para gerar os rótulos de informações do item, foi excluído deste tópico. Esse método consulta algumas tabelas para obter ID do item, descrição e dimensões. Se você quiser uma compreensão melhor de **generateItemInfoForProdId()**, examine o código-fonte.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Substitua **doExecute()** para executar o processo de início da produção e adicionar a mensagem de conclusão do processo.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Observe que muitos dos padrões comuns (regeneração da interface de usuário em caso de erro, definição da mensagem de conclusão do processo, comportamento de **OK** e **Cancelar**) foram movidos para a estrutura, evitando que o desenvolvedor de aplicativos escrevesse um código padronizado que fosse sujeito a erros e tivesse um risco de comportamento inconsistente nos processos. No entanto, quando o cenário precisar desviar do caminho comum, o desenvolvedor de aplicativos receberá a opção de substituir métodos adequados, mas trata-se de um desvio intencional que é explícito e rastreável.


### <a name="extending-a-business-process"></a>Estender um processo empresarial

Até agora, este tópico destacou como criar um novo processo usando a estrutura **ProcessGuide**. Nesta seção final, você verá alguns exemplos de como esse processo empresarial pode ser estendido.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Adicionar uma etapa em um fluxo (usando ProcessGuideNavigationAgentDefault)

Onde estender:

-   Filho da classe **ProcessGuideController** para o processo.

Como estender:

-   Estenda o método **initializeNavigationRoute()** na classe de controlador e invoque **addFollowingStep()** na classe **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Adicionar uma etapa em um fluxo (usando agente de navegação personalizado)

Onde estender:

-   Filho de **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Como estender:

-   Crie uma nova classe filha de **ProcessGuideNavigationAgent** que retorne o nome da etapa desejada.

-   Crie uma nova classe derivada de **ProcessGuideNavigationAgentFactory** que condicionalmente retorne o agente de navegação criado acima.

-   Estenda o método **navigationAgentFactory()** na classe de controlador para retornar a fábrica criada acima.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Adicionar um novo controle na interface de usuário de uma etapa existente 

Onde estender:

-   Filho de **ProdProcessGuidePageBuilder** para a etapa.

Como estender:

-   Estenda o método **addDataControls()** e acrescente o controle adicional.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Concluir a revisão da interface de usuário em uma etapa existente

Onde estender:

-   Filho de **ProdProcessGuideStep**.

Como estender:

-   Crie uma nova classe filha da classe **ProdProcessGuidePageBuilder** e implemente a interface de usuário desejada.

-   Estenda o método **pageBuildeName()** na classe de etapa para retornar o **ProcessGuidePageBuilderNameAttribute** para a classe criada acima.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Alterar a lógica quando uma etapa for considerada concluída

Onde estender:

-   Filho de **ProdProcessGuideStep**.

Como estender:

-   Estenda o método **isComplete()** para criar a lógica adicional.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]