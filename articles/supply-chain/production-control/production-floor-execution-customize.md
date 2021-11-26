---
title: Personalizar a interface de execução de piso de produção
description: Este tópico explica como estender formulários atuais ou criar novos formulários e botões para a interface de execução de piso de produção.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 414fe5d6e16ad125bc2b9bb7ed427e5db5180ec9
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790956"
---
# <a name="customize-the-production-floor-execution-interface"></a>Personalizar a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

Os desenvolvedores podem estender formulários atuais ou criar seus próprios formulários e botões para a interface de execução de piso de produção. Depois de adicionar o código para esses novos elementos, os administradores ou os gerentes de chão de fábrica podem facilmente adicioná-los à interface usando os controles de configuração padrão.

Por exemplo, estas são algumas das soluções possíveis se forem necessárias novas colunas em um formulário principal:

- Estenda o formulário `JmgProductionFloorExecutionMainGrid` e adicione os campos desejados.
- Crie um novo formulário e adicione-o como uma nova exibição principal (guia).

## <a name="add-a-new-button-action"></a>Adicionar um novo botão (ação)

Para adicionar um novo botão (ação), siga estas etapas para criar uma classe que implemente a ação personalizada.

1. Crie uma nova classe denominada `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, em que:

    - `<ExtensionPrefix>` identifica exclusivamente sua solução, normalmente usando o nome da sua empresa.
    - `<ActionName>` é um nome exclusivo da classe. Ele costuma identificar o tipo de ação.

1. A nova classe deve estender a classe `JmgProductionFloorExecutionAction`.
1. Substitua todos os métodos necessários.

Para obter exemplos, examine o código das seguintes classes:

- `JmgProductionFloorExecutionBreakAction` – uma classe para uma ação simples que não precisa de registro.
- `JmgProductionFloorExecutionReportFeedbackAction` – uma classe que fornece funcionalidade mais complexa.

Quando você tiver concluído, o botão novo (ação) será listado automaticamente na página **Guias de design** do Microsoft Dynamics 365 Supply Chain Management. Nesse caso, você (ou um administrador ou gerente de chão de fábrica) pode adicioná-lo facilmente à barra de ferramentas principal ou secundária, da mesma forma que pode adicionar os botões padrão. Para obter instruções, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Adicionar uma nova exibição principal

1. Crie um novo formulário que tenha os elementos e a funcionalidade desejados. Observe que esse formulário é um formulário novo, não uma extensão. Nomeie o formulário como `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, onde:

    - `<ExtensionPrefix>` identifica exclusivamente sua solução, normalmente usando o nome da sua empresa.
    - `<FormName>` é um nome exclusivo do formulário.

1. Crie um item de menu chamado `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Crie uma extensão denominada `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, em que o método `getMainMenuItemsList` é estendido, adicionando o novo item de menu à lista. O código a seguir mostra um exemplo.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Quando terminar, a nova exibição principal será listada automaticamente na caixa de combinação **Exibição principal** na página **Guias de design** no Supply Chain Management. Nesse caso, você (ou um administrador ou gerente de chão de fábrica) pode adicioná-lo facilmente às guias novas ou existentes, da mesma forma que pode adicionar as exibições principais padrão. Para obter instruções, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Adicionar uma exibição de detalhes

1. Crie um novo formulário que tenha os elementos e a funcionalidade desejados. Observe que esse formulário é novo, não uma extensão. Nomeie o formulário como `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, onde: 

    - `<ExtensionPrefix>` identifica exclusivamente sua solução, normalmente usando o nome da sua empresa.
    - `<FormName>` é um nome exclusivo do formulário.

1. Crie um item de menu chamado `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Crie uma extensão denominada `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, em que o método `getDetailsMenuItemList` é estendido, adicionando o novo item de menu à lista.

Quando terminar, a nova exibição de detalhes será listada automaticamente na caixa de combinação **Exibição de detalhes** na página **Guias de design** no Supply Chain Management. Nesse caso, você (ou um administrador ou gerente de chão de fábrica) pode adicioná-lo facilmente às guias novas ou existentes, da mesma forma que pode adicionar as exibições de detalhes padrão. Para obter instruções, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Adicionar um teclado numérico a um formulário ou caixa de diálogo

O exemplo a seguir mostra como adicionar teclados numéricos a um formulário.

1. O número de controladores de teclado numérico que cada formulário contém deve ser igual ao número de teclados numéricos nesse formulário.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Configure o comportamento de cada controlador do teclado numérico e conecte cada controlador do teclado numérico a uma parte do formulário de teclado numérico.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Usar um teclado numérico como uma caixa de diálogo pop-up

O exemplo a seguir mostra uma maneira de configurar um controlador de teclado numérico para uma caixa de diálogo pop-up.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

O exemplo a seguir mostra uma maneira de chamar a caixa de diálogo pop-up de teclado numérico.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="additional-resources"></a>Recursos adicionais

- [Estilizar a interface de execução de piso de produção](production-floor-execution-styles.md)
- [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md)
